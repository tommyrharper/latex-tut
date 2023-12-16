# Latex Tutorial

This is my reference notes for learning latex.

See: https://www.youtube.com/watch?v=ydOTMQC7np0

To write lates online: https://www.overleaf.com/

## Latex How To in VSCode

### Quick start if already setup

To use latex in vscode:
1. create a file with extension `.tex`
2. press `option-command-b` to build the file
3. open the file and press `option-command-v` to open the preview


Here is a basic outline to try:

```latex
\documentclass[]{article}

\begin{document}

Here is some stuff it compiiles as i go along

\end{document}
```

### Setting up from scratch

See: https://mathjiajia.github.io/vscode-and-latex/

1. Download & Install TeX Live
2. 
3. install the extension `LaTeX Workshop` for VSCode
4. Shift + Cmd + P (macOS) to show all commands. Then type Open User Settings JSON and open the first item.
5. Add the following to the settings.json file:
```json
"latex-workshop.latex.tools": [
 {
  "name": "latexmk",
  "command": "latexmk",
  "args": [
   "-synctex=1",
   "-interaction=nonstopmode",
   "-file-line-error",
   "-pdf",
   "-outdir=%OUTDIR%",
   "%DOC%"
  ],
  "env": {}
 },
 {
  "name": "xelatex",
  "command": "xelatex",
  "args": [
   "-synctex=1",
   "-interaction=nonstopmode",
   "-file-line-error",
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
 }
],
```

```json
"latex-workshop.latex.recipes": [
 {
  "name": "pdfLaTeX",
  "tools": [
   "pdflatex"
  ]
 },
 {
  "name": "latexmk 🔃",
  "tools": [
   "latexmk"
  ]
 },
 {
  "name": "xelatex",
  "tools": [
   "xelatex"
  ]
 },
 {
  "name": "pdflatex ➞ bibtex ➞ pdflatex`×2",
  "tools": [
   "pdflatex",
   "bibtex",
   "pdflatex",
   "pdflatex"
  ]
 },
 {
 "name": "xelatex ➞ bibtex ➞ xelatex`×2",
 "tools": [
   "xelatex",
   "bibtex",
   "xelatex",
   "xelatex"
  ]
 }
]

```
6. Follow the `Quick start if already setup` instructions at the top of this doc
