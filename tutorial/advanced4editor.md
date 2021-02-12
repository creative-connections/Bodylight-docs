# Bodylight-Editor {num=4}

In this step we will create a new document in MARKDOWN syntax using Bodylight Editor which is part of the virtual-machine or is deployed as static web page. We will utilize previously generated ZIP file with WebAssembly version of model simulator.

Open Bodylight-Editor 
1. either from Bodylight-VirtualMachine using host browser at http://localhost:8080/editor/
2. or from public static web page at https://bodylight.physiome.cz/Bodylight-Editor/

![Editor](BodylightEditor1.png)

## Create new project

In the left menu click: 
`Project menu -> New project`

## Create new file

Under the left menu click button:
<button>`+ Create new file`</button>

## Add some text in Markdown

The [markdown-it](https://markdown-it.github.io/) is used to render markdown syntax and it is enhanced with `footnote`, `highlight.js` and [katex](https://katex.org/) plugins. Additionally [w3-css](https://www.w3schools.com/w3css/defaulT.asp) and [bodylight-components]() syntax in HTML/CSS is allowed. 

A demo markdown text is prefilled in the edit panel. Clear it and add some text in Markdown as follows:

```markdown
# Introduction

Hemodynamics model simulation

```

You may see live preview while editing in right panel. Usually live preview is generated when you create a new line or delete a line.

Use icon <button><i class='fa fa-refresh'></i></button> above to generate preview immediatelly.