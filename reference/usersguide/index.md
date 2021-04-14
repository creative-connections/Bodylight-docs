# Bodylight.js Components

Bodylight.js Components is collection of custom elements enhancing HTML following Web Components standard. These web components are available 
* FMI component - to control simulation of Modelica model exported as FMI unit. `Modelica` model can be exported by any Modelica tool into `FMU`. [Bodylight FMU Compiler](https://github.com/creative-connections/Bodylight.js-FMU-Compiler) can be used to export FMU into WebAssembly.
* Adobe-Animate and Gif-Animate component - to control animation exported from Adobe-Animate or animated GIF and bind them to variables of model simulation.
* ChartJS, DygraphJS, Plotly components - to visualise model variables in different chart types.

## Overview

To build web simulator:

1) You need to export Modelica model into FMU with source codes including source codes for solver (Dymola exports CVODE, OpenModelica 1.14.x exports Euler and 1.16.x is declared to support CVODE export too).
2) Then you need to convert the FMU into WebAssembly - using [Bodylight FMU Compiler](https://github.com/creative-connections/Bodylight.js-FMU-Compiler) 
3) the exported ZIP contains JS file - to be reffered from `bdl-fmi` component, and `modelDescription.xml` - standard FMU description with variable references.
4) optional - export Adobe Animate animation into CreateJS library usable by `bdl-adobe` component.
5) use the Bodylight components, This plugin is distributed in 2 different way: 
   * **1. Standard web components**[1] - source codes at [Bodylight.js-Components](https://github.com/creative-connections/Bodylight.js-Components) to create web simulator using HTML or Markdown - web framework agnostic way.  
   * **2. Aurelia web components**[2] - source codes at [aurelia-bodylight-plugin](https://github.com/creative-connections/aurelia-bodylight-plugin) to create more interactive application using `Aurelia` framework.

