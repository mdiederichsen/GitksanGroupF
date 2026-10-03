# LING 431/531 Group F

LaTeX transcription files can be found in `transcriptions/`. 

[TODO: Organize the repo, add readings, other documents, etc.]

## Setup

To run LaTeX locally you have to install it on your system. (This site)[https://www.tug.org/texlive/] has links to LaTeX installation for different machines.

VS Code has am all-in-one extension LaTeX Workshop for running LaTeX. Search it up in the extensions tab and install it. 

Our files use the XeLaTeX compiler. To set this up, first open the command palette (cmd + shift + P on mac), and select `Preferences: Open User Settings (JSON)`. Then, add the following to the JSON file:
```
    "latex-workshop.latex.recipes": [
    {
        "name": "xelatex",
        "tools": ["xelatex"]
    }
    ],
    "latex-workshop.latex.tools": [
    {
        "name": "xelatex",
        "command": "xelatex",
        "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
        ]
    }
    ]
```

We use libertine font, make sure it's installed on your device. I used the [homebrew installation site](https://formulae.brew.sh/cask/font-linux-libertine).

Barring any dependencies that were already installed on my device, that's the entire setup!

