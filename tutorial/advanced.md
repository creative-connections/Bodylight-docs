# 10. Advanced tutorial

To produce multipage interactive web simulators you need these Bodylight tools: Bodylight.js-FMU-Compiler, Bodylight.js-Components and Bodylight-Editor. 

Advanced guide will follow you to:
1. Create multipage web simulator project in Bodylight Editor.
2. Integrate Adobe Animate object for visualisation

And will enhance the basic simulator to the following 

<div class="w3-card">

# Heart during cardiac cycle
<div class="w3-row">
<div class="w3-twothird">

## simulation and chart
<bdl-fmi id="idfmi" src="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation.js" fminame="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation" tolerance="0.000001" starttime="0" fstepsize="0.01" guid="{a786b906-f58b-4014-8c9b-5df08bd77f4b}" valuereferences="637534370,637534288,637534348,637534458,637534516,637534313,637534482" valuelabels="aortaPressure.pressure,mitralValve.open,aorticValve.open,tricuspidValve.open,pulmonaryValve.open,leftVentricle.volume,rightVentricle.volume,aorta.pressure" inputs="id1,16777329,1,60" inputlabels="heartRate.k"></bdl-fmi>

<bdl-range id="id1" title="heart rate" min="40" max="180" default="60" step="1" maxlength="2"></bdl-range>

<bdl-chartjs-time id="id10" width="300" height="200" fromid="idfmi" labels="Pressure in Aorta [mmHg]" initialdata="" refindex="0" refvalues="1"
convertors="x/133.322-760"></bdl-chartjs-time>
</div>
<div class="w3-third">

## animation
<bdl-animate-adobe src="CardiaccycleStage.js" width="200" height="200" name="Faze_srdce" fromid="idfmi"></bdl-animate-adobe>

<bdl-bind2a findex="1" aname="ValveMV_anim" amin="99" amax="0" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="2" aname="ValveAOV_anim" amin="0" amax="99" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="3" aname="ValveTV_anim" amin="99" amax="0" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="4" aname="ValvePV_anim" amin="0" amax="99" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="5" aname="ventricles.ventriclesTotal.VentricleLeft_anim" amin="100" amax="0" fmin="0.00015" fmax="0.00021"></bdl-bind2a>
<bdl-bind2a findex="6" aname="ventricles.ventriclesTotal.children.0.VentricleRight_anim" amin="100" amax="0" fmin="0.00012" fmax="0.00018"></bdl-bind2a>

</div>
</div>


</div>


