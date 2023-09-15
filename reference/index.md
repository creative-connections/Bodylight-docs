# Introduction

Bodylight is suite of tools to integrate 
1. mathematical models in Modelica
2. interactive animation in Adobe Animate, SVG, animated GIF
3. basic and advanced charts for web (chartjs, plotly, dygraph)

to create interactive web simulators with proper visualisation.

<a class="w3-button w3-theme-d1" href="https://orgpad.com/s/0VGy27nGaid">High Level presentation</a> - High level presentation about Bodylight.js 2.0 given in CompBioMed 2023 conference in Munich.

Briefly:

1. Web simulators are in-browser therefore no server, no cloud or enhanced resources are required. 

2. Web simulators can be distributed as static web pages. As proper example - the following documentation includes live web simulators utilizing great service of `GITHUB-PAGES` to deliver static web content. Means server serves the files only - no server computing or calculation is needed.

3. As a consequence - web simulators can be integrated into standalone apps - native mobile apps or virtual reality apps - thanks to WebView implementation for various platforms.

The documentation is divided to: 

<a class="w3-button w3-theme-d1" href="#usage/gettingstarted.md">Getting Started</a> - Quick samples on the usage of components in HTML, Markdown, Moodle, Adobe Captivate and notes on usage with apps created in Bodylight v1.0.

<a class="w3-button w3-theme-d1" href="#usersguide/index.md">Reference guide</a> - reference guide to collection of custom elements enhancing HTML following Web Components standard implemented in HTML and Javascript (ES6). 

<a class="w3-button w3-theme-d1" href="#example/index.md">Examples</a> - selected more complex examples using Bodylight.js Components.

<a class="w3-button w3-theme-d1" href="#editor/tools.md">Tools</a> - tools and instruction how to transform Modelica model into JS with WebAssembly, Bodylight-Editor helper tool to facilitate setting of web components,

<a class="w3-button w3-theme-d1" href="#developersguide/index.md">Developer's Guide</a> - source codes and links to other tools.

Step by step guide to create an in-browser simulator from Modelica model to interactive web simulator:

The recommended workflow is in tutorials: <a class="w3-button w3-theme-d1" href="#../tutorial/basic.md">Basic Tutorial</a> and
<a class="w3-button w3-theme-d1" href="#../tutorial/advanced.md">Advanced Tutorial</a>.

## Release notes 

Bodylight.js 2.1
  * tested with first prototypes and many improvements
  * updated dependent chart.js to 2.9.6
  * plotly and it's dependency removed - if using plotly charts, need to additionally include plotly.js into web page
  * added `oneshot` and `contiunous` mode into `bdl-fmi` component to allow simulation step to be done at start and at each parameter change
  * improved tools (Bodylight-Editor, Bodylight-Compiler compiles models from OpenModelica with Euler solver)

Bodylight.js 2.0 compared to Bodylight.js v1.0
  * v2.0 do not need of special tool to create web simulator - HTML or Markdown syntax with custom-elements can be edited in any text editor.
  * features of Bodylight.js Composer v1.0 was split into several independent subsystems - Bodylight.js-Components, Bodylight-Editor, Bodylight-VirtualBody (3D visualization)   
  * optional [Bodylight-Editor](https://bodylight.physiome.cz/Bodylight-Editor/) can be used to edit the web simulator in Markdown syntax. It supports live preview for Markdown, Bodylight.js-Components, animation from Adobe Animate
  * BJP files from version 1.0 are not usable in v 2.0. 
  * v1.0 HTML export can be used as iframes within v2.0 application
  * v2.0 supports charts and graphs using following third party libraries dygraph.js, chart.js and plotly.js
  * v2.0 supports 3D graphics of virtualbody in WEBGL. See sample app: [Bodylight-Virtualbody](https://github.com/creative-connections/Bodylight-VirtualBody)  

