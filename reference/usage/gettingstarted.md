# Getting Started 
 
1) Use `bodylight.bundle.js` directly from CDN:
    ```html
      <script src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight.js-Components/dist/bodylight.bundle.js"></script>
    ``` 
     
2) Add attribute  `aurelia-app="webcomponents"` to the `body` e.g.:
```html
...
<body aurelia-app="webcomponents">
...
</body>
```

3) Use web components inside `<body>` to build interactive web simulator e.g.:
```
  <bdl-range id="id1" min="40" max="180" default="60" title="Heart rate"></bdl-range>
  <bdl-fmi ...></bdl-fmi>
  <bdl-chartjs ...></bdl-chartjs>
```

So the resulting HTML file may look like

**index.html**
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Sample simulator with bodylight web components</title>
      <script src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight.js-Components/dist/bodylight.bundle.js"></script>
  </head>
<body aurelia-app="webcomponents">
<!-- put HTML as well as web components inside -->
<bdl-range id="id1" min="40" max="180" step="1" default="60"></bdl-range>

<bdl-fmi id="id4" 
    fminame="MeursHemodynamics_Model_vanMeursHemodynamicsModel" 
    tolerance="0.001" 
    starttime="0" 
    guid="{1cd90fb1-006b-4957-b1f2-012702efe021}" 
    valuereferences="637534215,637534232" 
    inputs="id1,16777216" 
    otherinputs="id3"></bdl-fmi>

<bdl-dygraphchart 
    width="600" height="300" fromid="id4" refindex="0" refvalues="2" ></bdl-dygraphchart>

</body>
</html>
```

* All bodylight web-components are prefixed with `bdl-`
* `bdl-range` creates slider and if user change the value - this value is set to the model
* `bdl-fmi` controls Modelica model via FMI api. It creates button to start/stop simulation and binds 
model variables to other components - inputs and outputs
* `bdl-dygraphchart` shows a chart with values of variables retrieved from model

Other options of how to create HTML with custom elements are listed in <a class="w3-button w3-theme-d1" href="#usersguide/index.md">Reference guide</a>