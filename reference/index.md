# Introduction

Bodylight is suite of tools to integrate technology of mathematical modeling in Modelica, 
interactive animation in Adobe Animate or SVG, 
visualisation in WebGL or HTML Canvas and
standard web publishing in HTML (or Markdown) as interactive web documents with live in-browser simulators. 

The documentation is divided to: 

<a class="w3-button w3-theme-d1" href="#usage/gettingstarted.md">Getting Started</a> - reference guide to collection of custom elements enhancing HTML following Web Components standard implemented in HTML and Javascript (ES6).

<a class="w3-button w3-theme-d1" href="#usersguide/index.md">Reference guide</a> - reference guide to collection of custom elements enhancing HTML following Web Components standard implemented in HTML and Javascript (ES6). 

<a class="w3-button w3-theme-d1" href="#example/index.md">Examples</a> - selected more complex examples using Bodylight.js Components

How to create an in-browser simulator from Modelica model? 
The recommended workflow is in tutorials: <a class="w3-button w3-theme-d1" href="../tutorial/#basic.md">Basic Tutorial</a> and
<a class="w3-button w3-theme-d1" href="../tutorial/#advanced.md">Advanced Tutorial</a>.

## Release notes 

Bodylight.js 2.0 compared to Bodylight.js v1.0
  * v2.0 do not need of special tool to create web simulator - HTML or Markdown syntax with custom-elements can be edited in any text editor.
  * features of Bodylight.js Composer v1.0 was split into several independent subsystems - Bodylight.js-Components, Bodylight-Editor, Bodylight-VirtualBody (3D visualization)   
  * optional [Bodylight-Editor](https://bodylight.physiome.cz/Bodylight-Editor/) can be used to edit the web simulator in Markdown syntax. It supports live preview for Markdown, Bodylight.js-Components, animation from Adobe Animate
  * BJP files from version 1.0 are not usable in v 2.0. 
  * v1.0 HTML export can be used as iframes within v2.0 application
  * v2.0 supports charts and graphs using following third party libraries dygraph.js, chart.js and plotly.js
  * v2.0 supports 3D graphics of virtualbody in WEBGL. See sample app: [Bodylight-Virtualbody](https://github.com/creative-connections/Bodylight-VirtualBody)  

