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

<bdl-fmi id="idfmi" 
         src="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation.js" 
         fminame="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation" 
         tolerance="0.000001" starttime="0" fstepsize="0.01" guid="{a786b906-f58b-4014-8c9b-5df08bd77f4b}" 
         valuereferences="637534370,637534288,637534348,637534458,637534516,637534313,637534482" 
         valuelabels="aortaPressure.pressure,mitralValve.open,aorticValve.open,tricuspidValve.open,pulmonaryValve.open,leftVentricle.volume,rightVentricle.volume,aorta.pressure" 
         inputs="id1,16777329,1,60" 
         inputlabels="heartRate.k"></bdl-fmi>

<bdl-range id="id1" title="heart rate" min="40" max="180" default="60" step="1" maxlength="2"></bdl-range>

<bdl-chartjs-time id="id10" width="300" height="200" fromid="idfmi" labels="Pressure in Aorta [mmHg]" 
refindex="0" refvalues="1" convertors="x/133.322-760"></bdl-chartjs-time>

</body>
</html>
```

* All bodylight web-components are prefixed with `bdl-`
* `bdl-range` creates slider and if user change the value - this value is set to the model
* `bdl-fmi` controls Modelica model via FMI Api. It creates button to start/stop simulation and binds 
model variables to other components - inputs and outputs
* `bdl-chartjs-time` shows a chart with values of variables retrieved from model during simulation.

Other options of how to create HTML with custom elements are listed in <a class="w3-button w3-theme-d1" href="#usersguide/index.md">Reference guide</a>