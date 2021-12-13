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
* `src` - relative or absolute URL location of the JS file from Adobe Animate. It should be accessible from the same context as the web simulator page.
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
## `bdl-bind2a-text`
defines binding between FMU simulation variable and animation object text value
* `findex` index of variable in fmu array
* `aname` name of animation component in AA (can go deep using dot `.` notation, see example bellow)
* `convertor` optional convertor - in form of 'numerator,denominator' or '1/x' or 'some algebraic expression with x' (e.g.'x^2' or '365-1/x'), displayed is converted value
* `precision` - if defined the value is converted to string using method toPrecision(precision). E.g. `precision=3` converts `152.635` to `152`
* `fixed` - if defined the value is converted to string using method toFixed(fixed), E.g. `fixed=2` shows PI to `152.635` to `152.64` 

```
<bdl-bind2a-text findex="8" aname="Hodnota5_text" convertor="1,0.237"></bdl-bind2a-text>
<bdl-bind2a-text findex="7" aname="Hodnota2Cerveny_text" convertor="1,3.612"></bdl-bind2a-text>
<bdl-bind2a-text findex="4" aname="Hodnota4_text" convertor="1,0.7428"></bdl-bind2a-text>
<bdl-bind2a-text findex="5" aname="Hodnota3_text" convertor="1,2.228"></bdl-bind2a-text>
<bdl-bind2a-text findex="18" aname="Hodnota9_text" convertor="1,1.51"></bdl-bind2a-text>   
```

## `bdl-bind2a-play`

defines binding between FMU simulation variable and playable animation object value
* `findex` index of variable in fmu array
* `aname` name of animation component in AA (can go deep using dot `.` notation, see example bellow)
* `limit` default `1e-12` - if the value of FMU variable goes over this limit, then animation is started - otherwise animation is stopped.

```
<bdl-bind2a-play findex="8" aname="circle1"></bdl-bind2a-play>
<bdl-bind2a-play findex="7" aname="circle2" limit="1.5"></bdl-bind2a-play>
```

## Example

```xml
<div class="w3-row">
  <div class="w3-third">
    Press buttons to start stop animation or to do a animation step:
    
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

  Press buttons to start stop animation or to do a animation step:

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
    

