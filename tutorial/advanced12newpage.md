# Advanced {num=12}

click on `animation.md`file in project panel to see it's content.

## Page layout

Divide the page into 2 thirds and 1 third using w3.css:

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

<div class="w3-panel w3-pale-green">

  The first `<div class="w3-row">` defines that everything till the closing `</div>` is treated as a row in layout. The inner `<div class='w3-third'>...</div>` selects first 33% of horizontal screen and all content is pushed there. The other `<div class="w3-twothird">...</div>` sets the rest 66% to be filled with other content.
  
</div>

## Simulation and Charts

Copy & paste simulation, range slider and chart into simulation section.
```markdown
<bdl-fmi id="idfmi" src="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation.js" fminame="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation" tolerance="0.000001" starttime="0" fstepsize="0.01" guid="{a786b906-f58b-4014-8c9b-5df08bd77f4b}" valuereferences="637534370" valuelabels="aorta.pressure" inputs="id1,16777329,1,60" inputlabels="heartRate.k"></bdl-fmi>

<bdl-range id="id1" title="heart rate" min="40" max="180" default="60" step="1" maxlength="2"></bdl-range>

<bdl-chartjs-time id="id10" width="300" height="200" fromid="idfmi" labels="Pressure in Aorta" initialdata="" refindex="0" refvalues="1"></bdl-chartjs-time>
```

