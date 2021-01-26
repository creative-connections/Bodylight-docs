# Tutorial to use Bodylight.js 2.0

This tutorial guides via usage of various tools to create interactive web based simulators. 
1. web simulator is a general web page in HTML
2. web simulator can be written in Markdown - the 'markdown-it' renderer is used to render HTML output
3. the Bodylight.js components are distributed as reusable web components - custom elements, which can be written next to HTML or Markdown - the 'bodylight.js' renderer is used to render HTML/JS output

## Basic web simulator

To produce single interactive web simulators you need only to use Bodylight.js-FMU-Compiler and Bodylight.js-Components.
Basic guide will follow you to:

1. Compile Modelica model to FMU with source codes including solver.
2. Compile FMU to Javascript with embedded WebAssembly (this allows to run model FMU inside browser.
3. Create web simulator document.

<a href='#basic1exportdymola' class="w3-button w3-theme-l1">Basic Web Simulator Tutorial - start from Dymola</a>

<a href='#basic2exportom' class="w3-button w3-theme-l1">Basic Web Simulator Tutorial - start from OpenModelica</a>



## Advanced web simulator

To produce multipage interactive web simulators you will need Bodylight.js-FMU-Compiler Bodylight.js-Components and Bodylight-Editor or Bodylight-Composer tool. 

Advanced guide will follow you to:
1. Compile Modelica model to FMU with source codes including solver.
2. Compile FMU to Javascript with embedded WebAssembly (this allows to run model FMU inside browser.
3. Create web simulator project in Bodylight Editor.

<a href='#advanced1exportdymola' class="w3-button w3-theme-l1">Advanced Web Simulator Tutorial - start from Dymola</a>

<a href='#advanced2exportom' class="w3-button w3-theme-l1">Basic Web Simulator Tutorial - start from OpenModelica</a>


