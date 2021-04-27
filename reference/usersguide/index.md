# Reference guide to Bodylight.js Components

Bodylight.js Components is collection of custom elements enhancing HTML following Web Components standard. These web components are available 
* FMI component - to control simulation of Modelica model exported as FMI unit. `Modelica` model can be exported by any Modelica tool into `FMU`. [Bodylight FMU Compiler](https://github.com/creative-connections/Bodylight.js-FMU-Compiler) can be used to export FMU into WebAssembly.
* Adobe-Animate and Gif-Animate components (supported by CreateJS and giffy libraries) - to control animation exported from Adobe-Animate or animated GIF and bind them to variables of model simulation.
* charting components (supported by ChartJS, DygraphJS and Plotly libraries) - to visualise model variables in different chart types.
* other components to support markdown and enhanced web widgets

Bodylight components are distributed in 2 different way: 
1. Standard web components ^[Web Components: https://developer.mozilla.org/en-US/docs/Web/Web_Components]. This is recommended option to create framework agnostic web simulator using HTML or Markdown. Source codes at [Bodylight.js-Components](https://github.com/creative-connections/Bodylight.js-Components) are just wrapper which makes standard web-components from all aurelia-plugin elements.   
2. Plugin for Aurelia framework ^[Aurelia framework: https://aurelia.io/] - source codes at [aurelia-bodylight-plugin](https://github.com/creative-connections/aurelia-bodylight-plugin). This is optional way to create interactive application using `Aurelia` framework.


## Standard web components

1) Use `bodylight.bundle.js`:
    * EITHER refer bundle directly from CDN:
    ```html
      <script type="module" src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight.js-Components/dist/bodylight.bundle.js"></script>
    ``` 
    * OR download `bodylight.bundle.js` locally and refer it from your HTML `<script>`:
    ```html
        <script type="module" src="bodylight.bundle.js"></script>
    ```  
    * OR install it via npm: `npm i bodylight-components`
    
   
2) Add attribute  `aurelia-app="webcomponents"` to the `div` or `body` with web components e.g.:
```html
index.html
...
<body aurelia-app="webcomponents">
...
</body>
```

3) Use web components to build interactive web simulator e.g.:
```
  <bdl-range id="id1" min="40" max="180" default="60" title="Heart rate"></bdl-range>
  <bdl-fmi ...></bdl-fmi>
  <bdl-chartjs ...></bdl-chartjs>
```

4) (optional) use markdown components `bdl-markdown-*` and refer MD document, Markdown syntax with HTML and web-components is interpretted.
E.g. `doc/index.md` with main content and `summary.md` with sidebar list of links.

**index.html**
```html
...
<body aurelia-app="webcomponents">
    <bdl-markdown-book2 index="index.md" summary="summary.md">
      <img src="docs/loading.gif"/>
    </bdl-markdown-book>
</body>
```

**index.md**
```markdown
# Introduction
Markdown syntax is interpretted. Syntax highlighting is enabled for source code. KATEX plugin is enabled to allow
basic equation e.g. $$e = m c^2$$

## bodylight web components
Use bodylight web components directly:
  <bdl-range id="id1" min="40" max="180" default="60" title="Heart rate"></bdl-range>
  <bdl-fmi ...></bdl-fmi>
  <bdl-chartjs ...></bdl-chartjs>
```

**summary.md**
```markdown

| EN | [CZ](#doc/index.cs.md&summary=doc/summary.cs.md) |   
  * [First Page](#doc/index.md)
  * [Second Page](#doc/index2.md)
    * [Sub page of second page](#doc/index22.md)
```

## Web components as plugin for Aurelia

We recommend to use [aurelia](https://aurelia.io) framework to build web application with Bodylight Web components.
Follow Aurelia doc's how to prepare your project and  install `aurelia-bodylight-plugin` by `npm` command-line:
```bash
npm i aurelia-bodylight-plugin
```

In your `main.js` file enable the plugin by `aurelia.use.plugin(PLATFORM.moduleName('aurelia-bodylight-plugin'))`, so it may look like:
```javascript
//main.js
import {PLATFORM} from 'aurelia-pal';

export function configure(aurelia) {
  aurelia.use
    .standardConfiguration()
    .plugin(PLATFORM.moduleName('aurelia-bodylight-plugin'))

  aurelia.start().then(() => {
    aurelia.setRoot(PLATFORM.moduleName('app'));
  });
}
```
Bodylight web components are available in any template, use them without `bdl-` prefix:
```html
<template>
  <range id="id1" min="40" max="180" default="60" title="Heart rate"></range>
  <fmi ...></fmi>
  <chartjs ...></chartjs>
...
</template>
```
