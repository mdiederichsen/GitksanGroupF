# LING 431/531 Group F

LaTeX transcription files can be found in `transcriptions/`. 

[TODO: Organize the repo, add readings, other documents, etc.]

## Setup

To run LaTeX locally you have to install it on your system. (This site)[https://www.tug.org/texlive/] has links to LaTeX installation for different machines.

VS Code has am all-in-one extension LaTeX Workshop for running LaTeX. Search it up in the extensions tab and install it. 

Our files use the XeLaTeX compiler. To set this up, first open the command palette (cmd + shift + P on mac), and select `Preferences: Open User Settings (JSON)`. Then, add the following to the JSON file:
```
    "latex-workshop.intellisense.biblatexJSON.replace": {},
    "latex-workshop.latex.tools": [
        {
            "name": "latexmk-xelatex",
            "command": "latexmk",
            "args": [
                "-xelatex",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ],
            "env": {}
        },
        {
            "name": "biber",
            "command": "biber",
            "args": [
                "%DOCFILE%"
            ]
        },
        {
            "name": "makeglossaries",
            "command": "makeglossaries",
            "args": [
              "%DOCFILE%"
            ]
          },
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk (xelatex)",
            "tools": ["latexmk-xelatex"]
        },
        {
            "name": "biber",
            "tools": [
                "biber"
            ]
        },
        {
            "name": "makeglossaries",
            "tools": [
                "makeglossaries",
            ]
        },
    ],
    "latex-workshop.intellisense.citation.backend": "biblatex",
```

We use libertine font, make sure it's installed on your device. I used the [homebrew installation site](https://formulae.brew.sh/cask/font-linux-libertine).

Barring any dependencies that were already installed on my device, that's the entire setup!

## Workflow

The `transcriptions/` folder has three main components: 
1. `sessions/`: A folder containing the LaTeX transcriptions organized by elicitation date.
2. `main.tex`: The main document that is compiled and outputs the PDF.
3. `preamble.tex`: Document defining packages and other stuff.

When you update any individual tex file in `sessions/`, it compiles to `main.pdf`. Will have to see if this setup is reasonable once we get more files. For now, compilation time is fast.
