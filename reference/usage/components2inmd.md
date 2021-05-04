## Bodylight.js-Components in Markdown

Bodylight web components contain special markdown components to read external MD file with components:
 - `bdl-markdown`
 - `bdl-markdown-book`
 - `bdl-markdown-book2`
All these have attribute `src` reffering to the MD file. MD file is read by fetch API from the same web directory as parent HTML file.
  
The file `home.html` may look like:

**home.html**
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Bodylight web component</title>
        <script src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight.js-Components/dist/bodylight.bundle.js"></script>
  </head>
<body aurelia-app="webcomponents">
  <bdl-markdown src="home.md"></bdl-markdown>
</body>
```

After loading `home.html` the `bdl-markdown` component reads content of the file `home.md`:

**home.md**
```markdown
# Simulator of Pulsatile Cardiovascular system

## Press start button to start the simulation:

<bdl-fmi id="idfmi" 
         src="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation.js" 
         fminame="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation" 
         tolerance="0.000001" starttime="0" fstepsize="0.01" guid="{a786b906-f58b-4014-8c9b-5df08bd77f4b}" 
         valuereferences="637534370,637534288,637534348,637534458,637534516,637534313,637534482" 
         valuelabels="aortaPressure.pressure,mitralValve.open,aorticValve.open,tricuspidValve.open,pulmonaryValve.open,leftVentricle.volume,rightVentricle.volume,aorta.pressure" 
         inputs="id1,16777329,1,60" 
         inputlabels="heartRate.k"></bdl-fmi>

## change heart rate parameter during simulation:

<bdl-range id="id1" title="heart rate" min="40" max="180" default="60" step="1" maxlength="2"></bdl-range>

## see pressure in aorta (should be between 120/80 mmHg).

<bdl-chartjs-time id="id10" width="300" height="200" fromid="idfmi" labels="Pressure in Aorta [mmHg]" 
refindex="0" refvalues="1" convertors="x/133.322-760"></bdl-chartjs-time>

<bdl-range id="id1" min="40" max="180" step="1" default="60"></bdl-range>

```
