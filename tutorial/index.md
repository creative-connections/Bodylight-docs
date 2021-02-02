# Tutorial to use Bodylight.js 2.0

This tutorial will guide you from model source code to functional interactive web simulator using ourp proprietary open-source toolchain called Bodylight.


1. Web simulator using Bodylight tools is a general web page in HTML
2. Web simulator can be written in Markdown - the 'markdown-it' renderer is used to render HTML output
3. the interactive components - called `Bodylight Components` are distributed as a reusable Javascript bundle folowing standard web components recommendation: custom elements. HTML or MARKDOWN powered by the 'bodylight.bundle.js' renderer is used to render interactive HTML/JS output in any modern browser.
4. The further tutorial will guide you to produce set of Markdown documents enriched with bodylight web components - however any other markup based language or raw HTML can be used.

# Basic tutorial

To produce basic interactive web simulator you need these Bodylight tools: Bodylight.js-FMU-Compiler, Bodylight.js-Components and Bodylight-Editor.

Basic guide will follow you to:

1. Compile Modelica model to FMU with source codes including solver.
2. Compile FMU to Javascript with embedded WebAssembly, this allows to run model using FMI api inside browser.
3. Create web simulator document.

<a href='#basic1exportdymola.md' class="w3-button w3-theme-l1">Basic Web Simulator Tutorial - start from Dymola</a>

<a href='#basic2exportom.md' class="w3-button w3-theme-l1">Basic Web Simulator Tutorial - start from OpenModelica</a>

# Advanced tutorial

To produce multipage interactive web simulators you need these Bodylight tools: Bodylight.js-FMU-Compiler, Bodylight.js-Components and Bodylight-Editor or Bodylight-Composer tool. 

Advanced guide will follow you to:
1. Compile Modelica model to FMU with source codes including solver.
2. Compile FMU to Javascript with embedded WebAssembly (this allows to run model FMU inside browser.
3. Create web simulator project in Bodylight Editor.

<a href='#advanced1exportdymola.md' class="w3-button w3-theme-l1">Advanced Web Simulator Tutorial - start from Dymola</a>

<a href='#advanced2exportom.md' class="w3-button w3-theme-l1">Advanced Web Simulator Tutorial - start from OpenModelica</a>

 