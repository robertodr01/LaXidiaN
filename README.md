<p align="center">
  <img width="250" src="https://github.com/angelonazzaro/LaXidiaN/assets/58223071/c343757d-d762-433c-801d-fe2b379647d5" />
</p>
<h3 align="center">
 LaXidiaN
</h3>
<p align="center">
 A LaTeX template inspired by Obisdian. 
<br>
<p align="center">
<a href="#"><img src="https://img.shields.io/github/contributors/robertodr01/LaXidiaN?style=for-the-badge" alt="Contributors"/></a>
<img src="https://img.shields.io/github/last-commit/robertodr01/LaXidiaN?style=for-the-badge" alt="last commit">
</p>
<p align="center">
<a href="#"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=for-the-badge" alt="PRs Welcome"/></a>
<a href="#"><img src="https://img.shields.io/github/stars/robertodr01/LaXidiaN?style=for-the-badge&color=yellow" alt="stars" /></a>
<a href="#"><img src="https://img.shields.io/github/forks/robertodr01/LaXidiaN?style=for-the-badge" alt="stars" /></a>
</p>

# LaXidiaN
LaXidiaN is a LaTeX template inspired by [Obsidian](https://obsidian.md/) for taking notes. 

## Features 
This template features: 
- Unbreakable callout boxes. There are four types of callout boxes: success, danger, info and warning.
- Custom callout boxes. You can create your own callout box if you have specifc needs.
- Referencable callout boxes. You can create a reference to one or more of your callout boxes and re-use them later in the document. 
- Pre-defined mathematical operators and expression.
- Custom images and tables fitting and formatting. 
- Custom theorems, proofs and quotes.

## Template structure
The template is structured as follows: 
- `packages.sty`, it contains all the packages used for styling and defining new commands;
- `definitions.sty`, it contains all the definitions of the mathematical operators and expressions; 
- `styles.sty`, here are defined the styles for the various callout boxes, along with the theorems, proofs and quotes.
 
## Set up your VsCode Environment

In order to write and compile LaTeX on VsCode, install the [LaTeX Workshop extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) on the marketplace. <br>
Once you have enabled it, open the extension's settings and set the `Out Dir` option to `%TMPDIR%`, like illustrated below. This will ensure that all compiled files will be placed in a temporary directory and not in your current working directory.

![immagine](https://github.com/angelonazzaro/LaXidiaN/assets/58223071/5032ead6-8115-4dcb-b5de-c58bde4cbf35)

Finally, edit your `settings.json` file and paste the following code: 
```json 
"latex-workshop.latex.tools": [
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-shell-escape",
                "-synctex=1",
                "-interaction=nonstopmode",
                // "-file-line-error",
                "-pdf",
                "-outdir=%TMPDIR%",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "lualatexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-lualatex",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "xelatexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-xelatex",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "latexmk_rconly",
            "command": "latexmk",
            "args": [
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ],
            "env": {}
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
            "name": "rnw2tex",
            "command": "Rscript",
            "args": [
                "-e",
                "knitr::opts_knit$set(concordance = TRUE); knitr::knit('%DOCFILE_EXT%')"
            ],
            "env": {}
        },
        {
            "name": "jnw2tex",
            "command": "julia",
            "args": [
                "-e",
                "using Weave; weave(\"%DOC_EXT%\", doctype=\"tex\")"
            ],
            "env": {}
        },
        {
            "name": "jnw2texminted",
            "command": "julia",
            "args": [
                "-e",
                "using Weave; weave(\"%DOC_EXT%\", doctype=\"texminted\")"
            ],
            "env": {}
        },
        {
            "name": "pnw2tex",
            "command": "pweave",
            "args": [
                "-f",
                "tex",
                "%DOC_EXT%"
            ],
            "env": {}
        },
        {
            "name": "pnw2texminted",
            "command": "pweave",
            "args": [
                "-f",
                "texminted",
                "%DOC_EXT%"
            ],
            "env": {}
        },
        {
            "name": "tectonic",
            "command": "tectonic",
            "args": [
                "--synctex",
                "--keep-logs",
                "%DOC%.tex"
            ],
            "env": {}
        }
    ],
    "latex-workshop.latex.autoClean.run": "onBuilt",
    "latex-workshop.latex.clean.subfolder.enabled": true,
    "latex-workshop.latex.outDir": "%TMPDIR%",
    "latex-workshop.message.warning.show": false,
```

## Contributing
If you'd like to contribute to the project, please: 
1. Create a fork of this repository; 
2. Clone the newly created fork; 
3. Create a branch named with the feature/fix you would like to implement, for example: `git branch -m fix-boxes`
4. Create a pull request and wait for approval;

Cmon, join our contributors: 

<a href="https://github.com/robertodr01/LaXidiaN/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=robertodr01/LaXidiaN" />
</a>

## License 
This template is distributed under the [GNU General Public License v3.0](LICENSE.md).  
