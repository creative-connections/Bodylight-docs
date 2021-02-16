# Advanced {num=12}

click on `animation.md` file in project panel to go back from summary. 

## Page layout

Delete the sample page content and add following:


```markdown
# Heart during cardiac cycle

<div class="w3-row">
<div class="w3-twothird">

## simulation and chart

</div>
<div class="w3-third">

## animation

</div>
</div>
```

This divides the page horizontally into 2 parts:
* The first `<div class="w3-row">` defines that everything till the closing `</div>` is treated as a row in layout. 
* The inner `<div class='w3-third'>...</div>` sets this part tob be one third of screen width ( 33% ), all content will be filled into this space.
* The other `<div class="w3-twothird">...</div>` sets the other part to be two-thirds of screen width ( 66% ) to be filled with other content.
  
## Simulation and Charts

Now copy & paste simulation, range slider and chart after the line `## simulation and chart`
as it was created in Basic Tutorial:
```markdown
<bdl-fmi id="idfmi" src="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation.js" fminame="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation" tolerance="0.000001" starttime="0" fstepsize="0.01" guid="{a786b906-f58b-4014-8c9b-5df08bd77f4b}" valuereferences="637534370" valuelabels="aorta.pressure" inputs="id1,16777329,1,60" inputlabels="heartRate.k"></bdl-fmi>

<bdl-range id="id1" title="heart rate" min="40" max="180" default="60" step="1" maxlength="2"></bdl-range>

<bdl-chartjs-time id="id10" width="300" height="200" fromid="idfmi" labels="Pressure in Aorta" initialdata="" refindex="0" refvalues="1"></bdl-chartjs-time>
```
## Check simulation

Check whether simulation controls starts/stops simulation and chart is showing some data by pressing the button <button><i class="fa fa-play"></i></button>.


