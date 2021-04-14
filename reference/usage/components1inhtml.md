# Bodylight.js-Components in HTML
 
Example usage of Bodylight components in HTML:
  * add script module `bodylight.bundle.js` into head or other location:
  ```html
  <script type="module" src="bodylight.bundle.js"></script>`
  ```
  * add atrribute `aurelia-app="webcomponents"` into div or body containing web components:
  ```html
  <body aurelia=app="webcomponents"> ... </body>
  ```
     
Use custom elements with prefix `bdl-`:

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Bodylight web component</title>
     <script type="module" src="bodylight.bundle.js"></script>
     <script type="module" src="modelfmi.js"></script>
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
    width="600" height="300" fromid="id4" inputs="time,aorta pressure,ventricle pressure"></bdl-dygraphchart>

</body>
</html>
```
Where
  * `bdl-range` render a range input
  * `bdl-fmi` render simulation buttons and controls model simulation using `FMI` interface
  * `bdl-dygraphchart` renders 2d chart of selected variables 

