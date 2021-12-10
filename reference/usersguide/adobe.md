These components can be used to place graphics exported from Adobe Animate using CreateJS library and control it's animatable objects by model variables and 
start/stop animation on model start or user request by pressing buttons.

## `bdl-animate-adobe`
Basic component, renders the exported animation into the HTML canvas. 

There should be only one such animation component in a page.

Sample:
```xml
<bdl-animate-adobe 
    src="ZelezoCelek.js" 
    width="800"
    height="600"
    name="ZelezoCelek"
    fromid="id4" ></bdl-animate-adobe> 
``` 
* `src` - link to exported JS file from Adobe Animate, should be deployed locally next to web simulator document
* `width` - width of the canvas (default 800px)
* `height` - height of the canvas (default 600px)
* `name` - name of the object exported in JS, should be taken from JS file, usually same as filename. 
* `fromid` - ID of FMU component or animate-adobe-control 
  * EITHER FMU component giving the data to animate. It listens events 'fmustart', 'fmudata', 'fmustop', 
  * OR animate-adobe-control component. It listens events 'animatestart', 'animatestop' and plays/stops animation

## `bdl-animate-adobe-control` 
Optional component. Use this if the animation start and stop should be controlled by buttons.
It displays play/stop and step button and sends custom events `animatestart` and `animatestop`. 
The target `bdl-animate-adobe` component listen these events by specifying `fromid` which is equal to this `id`.
```xml
<bdl-animate-adobe-control
   id="id4"></bdl-animate-adobe-control>
   
```
* `id` - unique id referred by animate-adobe component to be listened

## `bdl-bind2a` 
Component defines binding between FMU simulation variable and animation object value. This should be used if fromid refers to FMU component.
All animation objects reflects it's animation state by model variable value. All other objects (not bind by this component) are played - animated continuously.

* `findex` index of variable in fmu array
* `aname` name of animation component in AA (can go deep using dot `.` notation, see example bellow)
* `amin` (default = 0) minimal value in animate component
* `amax` (default = 100) maximal value in animate component
* `fmin` (default = 0) minimal value of variable from fmu model to be animated
* `fmax` (default = 100) maximal value of variable from fmu model to be animated
The conversion is made as linear approximation between amin and amax as following:
* $x<f_{min} \Rightarrow a_{min}$ 
* $f_{min} < x < f_{max} \Rightarrow a_{min} + \frac{(x-f_{min})(a_{max}-a_{min}}{f_{max}-f_{min}}$
* $f_{max} < x \Rightarrow a_{max}$

Example binding model variables to animation objects:
```xml
<bdl-bind2a findex="0" aname="ventricles.ventriclesTotal.VentricleLeft_anim" amin="100" amax="0" fmin="0.00007" fmax="0.00015"></bdl-bind2a>
<bdl-bind2a findex="6" aname="ValveMV_anim" amin="99" amax="0" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="7" aname="ValveAOV_anim" amin="0" amax="99" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="14" aname="ValveTV_anim" amin="99" amax="0" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="15" aname="ValvePV_anim" amin="0" amax="99" fmin="0" fmax="1"></bdl-bind2a>
```

## Example

```xml
<div class="w3-row">
  <div class="w3-third">
    <bdl-animate-adobe-control id="id4"></bdl-animate-adobe-control>
  </div>
  <div class="w3-twothird">
    <bdl-animate-adobe 
    src="ZelezoCelek.js" 
    width="1080"
    height="1080"
    name="ZelezoCelek"
    fromid="id4" ></bdl-animate-adobe>
  </div>
</div>
```
<div class="w3-row">
  <div class="w3-third">
<bdl-animate-adobe-control id="id4"></bdl-animate-adobe-control>
  </div>
  <div class="w3-twothird">
<bdl-animate-adobe 
    src="ZelezoCelek.js" 
    width="1080"
    height="1080"
    name="ZelezoCelek"
    fromid="id4" ></bdl-animate-adobe>
  </div>
</div>
    

