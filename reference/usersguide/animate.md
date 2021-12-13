Components to place animated gif into page. GIF animation can be controlled by simulator variable 
## `bdl-animate-gif`
Place animated gif into page. GIF animation is started/stopped per events `fmistart` and `fmistop` from DOM id defined in attribute`fromid`. Animation speed is uncontrolled.
```xml
<bdl-animate-gif src="heart.gif" fromid="id4" ></bdl-animatedheart> 
```
* `src` - link to GIF file, should be deployed locally next to web simulator document
* `fromid` - ID of element to listen events to start/stop/control animation FMU or other which sends DOM events `fmistart` and `fmistop`.
 
## `bdl-animate-sync-gif`
Animates gif like previous component, but synchronizes the animation loop with simulation loop by defining simulation step size in s -
```xml
<bdl-animate-sync-gif src="heart.gif" fromid="id4"
                      simulationstepsize="0.01" ></bdl-animatedheart> 
```
* `src` - link to GIF file, relative or absolute URL location of the GIF file. It should be accessible from the same context as the web simulator page.
* `fromid` - ID of element FMU or other which sends DOM events `fmistart` and `fmistop`.
* `simulationstepsize` - set real simulation step size in seconds. GIF animation speed is counted.

## `bdl-animate-control`
Renders control buttons to start/stop and step animation. Optionally segments can be defined to sync with simulation variables. Controls animation, defines segments - frames where animation changes state
labels which are presented and condition when met, simulation or animation is stopped.

```xml
<bdl-animate-control 
id="id4" speedfactor="20"></bdl-animate-control>
```
* `id` - unique ID. `bdl-animate-gif` should refer this id if controlled by this component.
* `speedfactor` - optional, values 0-100 in percent, 0 - no speed, 50 - half speed, 100 - full speed of animation
* `segments` - semicolon separated number of frame determining final frame of each segment, e.g. `3;5` determines 1st segment from frames `0..2`, second segment `3..4`
* `segmentlabels` - optional semicolon separated labels, the label is shown next to buttons to show which segment is currently animated
* `fromid` - optional, if specified it should refer to FMU component
* `segmentcond` - optional, if specified, semicolon separated condition of variable to be met when segment ends, i.e. `6,eq,0;7,eq,1` - 1st segment ends when 6th variable from FMU is equal to 0. 2nd segment ends when 7th variable is equal to 1 
* `simsegments` - optional, semicolon separated numbers - estimated simulation step index per segment `10;25` - 1st segment usually takes 10 simulation steps, 2nd segment usually takes 15 steps, this is used to spread animation frames into a segment  
* `allowcontinuous=false` - if segments defined - `false` = animation is stopped after each segment, `true` = animation is continuous - no stop after each segment

Note that segmentlabels can be detected and show on chartjs-time graph using attribute `sectionid`. 

## Examples

### animation controlled by segments
```xml
Press button to control animation of systole and diastole:

<bdl-animate-control 
id="id4" 
speedfactor="20" 
segments="3;5;14;17;29" 
segmentlabels="
4b filling, atrial systole;
1 ventricular systole - isovolumic contraction;
2 ventricular systole - ejection;
3 isovolumic relaxation;
4a filling
"></bdl-animate-control>

animation:

<bdl-animate-gif fromid="id4" src="heart.gif"></bdl-animate-gif>
```
Press button to control animation of systole and diastole:
<bdl-animate-control
id="id4"
speedfactor="20"
segments="3;5;14;17;29"
segmentlabels="4b filling, atrial systole;1 ventricular systole - isovolumic contraction;2 ventricular systole - ejection;3 isovolumic relaxation;4a filling"></bdl-animate-control>

animation:
<bdl-animate-gif fromid="id4" src="heart.gif"></bdl-animate-gif>

### continuous animation controlled by segments and sync with fmi
```xml
<div class="w3-row">
    <div class="w3-half">
        <bdl-fmi id="id14" src="BurkhoffFMI.js"
         fminame="Cardiovascular_Model_Burkhoff_HemodynamicsBurkhoff_0shallow"
         tolerance="0.000001" starttime="0" guid="{b5629132-3ba6-4153-87c2-f3ff108e1920}"
         valuereferences="33554435,637534265,637534241,637534290,16777312,637534466,637534294,637534268"
         valuelabels="Left Ventricle Volume,Pressure in Left Ventricle,Pressure in Aorta, Pressure in Left Atria, Heart Rate, LA elastance,MV open, AOV open"
         inputs="id1,16777312,1,60"
         controlid="id15"
         showcontrols="false"></bdl-fmi>
    <bdl-animate-control
            id="id15"
            fromid="id14"
            speedfactor="20"
            segments="3;5;14;17;29"
            allowcontinuous="true"
            segmentlabels="
4b filling, atrial systole;
1 ventricular systole - isovolumic contraction;
2 ventricular systole - ejection;
3 isovolumic relaxation;
4a filling
"
            segmentcond="6,eq,0;7,eq,1;7,eq,0;6,eq,1;5,gt,100000"
            simsegments="14;24;35;52;76"></bdl-animate-control>
        
        <bdl-range id="id1" min="40" max="180" step="1" default="60" title="Heart rate"></bdl-range>
        
        <bdl-animate-gif fromid="id15" src="heart.gif"></bdl-animate-gif>
    </div>        
    <div class="w3-half">
        <bdl-chartjs-time  
                width="600"
                height="400"
                id="id11" 
                fromid="id14"  
                labels="Pressure in Aorta,Pressure in Left Ventricle, Left Ventricle Volume" 
                refindex="1"  
                refvalues="3" 
                verticalline="true" 
                sectionid="id15" 
                maxdata="160"
                throttle="0"></bdl-chartjs-time>
    </div>
</div>
```

<div class="w3-row">
    <div class="w3-half">

<bdl-fmi id="id14" src="BurkhoffFMI.js"
         fminame="Cardiovascular_Model_Burkhoff_HemodynamicsBurkhoff_0shallow"
         tolerance="0.000001" starttime="0" guid="{b5629132-3ba6-4153-87c2-f3ff108e1920}"
         valuereferences="33554435,637534265,637534241,637534290,16777312,637534466,637534294,637534268"
         valuelabels="Left Ventricle Volume,Pressure in Left Ventricle,Pressure in Aorta, Pressure in Left Atria, Heart Rate, LA elastance,MV open, AOV open"
         inputs="id1,16777312,1,60"
         controlid="id15"
         showcontrols="false"></bdl-fmi>

<bdl-animate-control
            id="id15"
            fromid="id14"
            speedfactor="20"
            segments="3;5;14;17;29"
            allowcontinuous="true"
            segmentlabels="
4b filling, atrial systole;
1 ventricular systole - isovolumic contraction;
2 ventricular systole - ejection;
3 isovolumic relaxation;
4a filling
"
            segmentcond="6,eq,0;7,eq,1;7,eq,0;6,eq,1;5,gt,100000"
            simsegments="14;24;35;52;76"></bdl-animate-control>

<bdl-range id="id1" min="40" max="180" step="1" default="60" title="Heart rate"></bdl-range>

<bdl-animate-gif fromid="id15" src="heart.gif"></bdl-animate-gif>
</div>        
<div class="w3-half">
<bdl-chartjs-time  
                width="600"
                height="400"
                id="id11" 
                fromid="id14"  
                labels="Pressure in Aorta,Pressure in Left Ventricle, Left Ventricle Volume" 
                refindex="1"  
                refvalues="3" 
                verticalline="true" 
                sectionid="id15" 
                maxdata="160"
                throttle="0"></bdl-chartjs-time>
</div>
</div>


