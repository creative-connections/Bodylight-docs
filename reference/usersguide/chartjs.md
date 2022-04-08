Chartjs components utilizes the library **chartjs** from https://chartjs.org 
The library version 2.9.4 is embedded in `bodylight.bundle.js`.

## `bdl-chartjs`  

Creates basic chartjs graph from current data. 

```xml
<bdl-chartjs 
  id="id9" 
  width="300" 
  height="500"
  responsive="false"  
  fromid="id4" 
  type="doughnut" 
  labels="Intrathoracic Arteries,ExtraThoracic Arteries, Pulmonary Arteries, Intrathoracic Veins, Extrathoracic veins, Pulmonary Veins"
  initialdata="0,4,2,3" 
  refindex="2" 
  refvalues="6"
  animation="true"
  convertors="numerator1,denominator1;numerator2,denominator2"></bdl-chartjs>
``` 
* `fromid` - reference to component sending fmu data, usually id of `bdl-fmi` component
* `labels` - comma separated labels of dataset
* `refindex` - index in reference value array within fmu data sent by `bdl-fmi` component, if more  indexes, use refvalues or separate indices by comma
* `refvalues` - number of values to be red from the refindex, if they are after each other, if not then use comma separated values in refindex
  * `refindex="2" refvalues="3"` will take 3 values from an array sent by fmu component with indices 2,3,4
  * `refindex="2,5,8"` will take 3 values from an array sent by fmu component with indices 2,5,8
* `type` - type of chart; available from chartjs library, default `doughnut`, possible values `line`, `bar`, `radar`,`doughnut`, `pie`, `polarArea`
* `initialdata=''` - comma separated values of initial data (for more datasets use semicolon `;` - not used in basic charts)
* `width=300`  - width of chart canvas in px
* `height=200` - height of chart canvas in px
* `animate=false` - if `true`, smooth animation (by 500 ms) when data is updated. Default `false`.
* `id` - (optional) unique id of component;
* `ylabel` - label on y axis
* `xlabel` - label on x axis
* `convertors` - convertors separated by semicolon per variable ';' to convert raw data taken from fmu into visualisation in 
  * EITHER `numerator,denominator,addend` $x_{converted} = \frac{x \times \text{numerator}}{\text{denominator}} + \text{addend}$
  * e.g.: `convertors="1,60,0"` will convert value as $x_c = \frac{x \times 1}{60} + 0$
  * OR `expression with x`, $x_{converted} = \overbrace{f(x)}^{\text{expression with x}}$
  * e.g.:`convertors="x/60"` will convert value as $x_c = \frac{x}{60}$
* `generatelabels=false` - if true, labels for dataset are generated as 'variable 1' .. ' variable n'
* `responsive = false` - if `true`, canvas is rescaled per available space, `false` - to keep width and height
* `canvasobj` - if defined then use this object name to get canvas object. E.g. to draw chart to another environment (e.g. surface in VR or AR)
* `throttle=200` - time to throttle chart update, `0` - no throttle - update on every data change, `200` - wait 200 ms to update, chart data may change more frequently  
* `precision=4` - precision to be displayed in tooltips when hovering mouse over


Examples - 6 types of charts `doughnut, line, bar, radar, pie, polarArea`

```xml
<bdl-chartjs 
  id="id9" 
  width="300" 
  height="500"
  responsive="false"  
  fromid="id4" 
  type="doughnut" 
  labels="Intrathoracic Arteries,ExtraThoracic Arteries, Pulmonary Arteries, Intrathoracic Veins, Extrathoracic veins, Pulmonary Veins"
  initialdata="0,4,2,3" 
  refindex="2" 
  refvalues="6"
  animation="true"
  convertors="numerator1,denominator1;numerator2,denominator2"></bdl-chartjs>
```
<div class="w3-row">
<div class="w3-quarter">
<bdl-chartjs
id="id9"
width="300"
height="500"
responsive="false"  
fromid="id4"
type="doughnut"
labels="Intrathoracic Arteries,ExtraThoracic Arteries, Pulmonary Arteries, Intrathoracic Veins, Extrathoracic veins, Pulmonary Veins"
initialdata="0,4,2,3"
refindex="2"
refvalues="6"
animation="true"
convertors="numerator1,denominator1;numerator2,denominator2"></bdl-chartjs>
</div><div class="w3-quarter">

<bdl-chartjs
id="id9"
width="300"
height="500"
responsive="false"  
fromid="id4"
type="line"
labels="Intrathoracic Arteries,ExtraThoracic Arteries, Pulmonary Arteries, Intrathoracic Veins, Extrathoracic veins, Pulmonary Veins"
initialdata="0,4,2,3"
refindex="2"
refvalues="6"
animation="true"
convertors="numerator1,denominator1;numerator2,denominator2"></bdl-chartjs>
</div><div class="w3-quarter">
<bdl-chartjs
id="id9"
width="300"
height="500"
responsive="false"  
fromid="id4"
type="bar"
labels="Intrathoracic Arteries,ExtraThoracic Arteries, Pulmonary Arteries, Intrathoracic Veins, Extrathoracic veins, Pulmonary Veins"
initialdata="0,4,2,3"
refindex="2"
refvalues="6"
animation="true"
convertors="numerator1,denominator1;numerator2,denominator2"></bdl-chartjs>  
</div><div class="w3-quarter">
<bdl-chartjs
id="id9"
width="300"
height="500"
responsive="false"  
fromid="id4"
type="radar"
labels="Intrathoracic Arteries,ExtraThoracic Arteries, Pulmonary Arteries, Intrathoracic Veins, Extrathoracic veins, Pulmonary Veins"
initialdata="0,4,2,3"
refindex="2"
refvalues="6"
animation="true"
convertors="numerator1,denominator1;numerator2,denominator2"></bdl-chartjs>
</div><div class="w3-quarter">
<bdl-chartjs
id="id9"
width="300"
height="500"
responsive="false"  
fromid="id4"
type="pie"
labels="Intrathoracic Arteries,ExtraThoracic Arteries, Pulmonary Arteries, Intrathoracic Veins, Extrathoracic veins, Pulmonary Veins"
initialdata="0,4,2,3"
refindex="2"
refvalues="6"
animation="true"
convertors="numerator1,denominator1;numerator2,denominator2"></bdl-chartjs>
</div><div class="w3-quarter">
<bdl-chartjs
id="id9"
width="300"
height="500"
responsive="false"  
fromid="id4"
type="polarArea"
labels="Intrathoracic Arteries,ExtraThoracic Arteries, Pulmonary Arteries, Intrathoracic Veins, Extrathoracic veins, Pulmonary Veins"
initialdata="0,4,2,3"
refindex="2"
refvalues="6"
animation="true"
convertors="numerator1,denominator1;numerator2,denominator2"></bdl-chartjs>
</div>
</div>

## `bdl-chartjs-time`
Special case of `bdl-chartjs` for line type charts in time series. FMU data contains time point data was taken, the X axis contains this time, Y axis contains data remembered in each fmu data point. Additional attributes
* `min` - (optional) set min for y scale - sets chart.js `options.scales.y.min`
* `max` - (optional) set max for y scale - sets chart.js `options.scales.x.min`
* `maxdata=256` - max data to remember, after the buffer is full, the first data are taken away from the buffer 
* `verticalline=false` - verticalline plugin - will show vertical line in each segment - use with `sectionid`
* `sectionid` - if set, then listens the component with this id for 'addsection' event, bind it to `bdl-animate-control` component, use it with `verticalline=true`
 
### Example
```xml
<bdl-chartjs-time  
  id="id10" 
  width="300" 
  height="500" 
  fromid="id4" 
  labels="Pressure in Aorta,Pressure in Left Ventricle, Pressure in Left Atria"
  initialdata="0,1,2,3,4,5,6,7,8,9,10;80,100,120,115,110,105,100,95,90,85;20,25,30,28,26,24,22,20,18,16;20,100,120,115,110,27,25,23,21,19,17" 
  refindex="2,3,4"></bdl-chartjs-time>
```

<bdl-chartjs-time  
  id="id10" 
  width="300" 
  height="500" 
  fromid="id4" 
  labels="Pressure in Aorta,Pressure in Left Ventricle, Pressure in Left Atria"
  initialdata="0,1,2,3,4,5,6,7,8,9,10;80,100,120,115,110,105,100,95,90,85;20,25,30,28,26,24,22,20,18,16;20,100,120,115,110,27,25,23,21,19,17" 
  refindex="2,3,4"></bdl-chartjs-time>


## `bdl-chartjs-xy`

XY chart from data. The first variable is X axis, Second variable is Y axis - `maxdata` are taken same as in `chartjs-time`.


```xml
<bdl-chartjs-xy id="id10" width="400" height="400" fromid="id4" 
labels="Pressure in Left Ventricle, Left Ventricle Volume" 
initialdata=";;0,0.00015;0,28000;0,0.00015;0,1400" 
refindex="0" refvalues="2"></bdl-chartjs-xy>
``` 

where `initialdata` may contain additional static curves after first values 
delimite by `;` there might be x values delimited by `,` followed by y values delimited by `,`
and so on. 

## `bdl-chartjs-barplot`

barplot chart with extreme limits and normal limits to be shown
```xml
<bdl-chartjs-barplot
  id="id11"
  fromid="id4"
  refindex="2"
  extremelimits="0,1"
  normallimits="6.9,7.1">
</bdl-chartjs-barplot>
```
<bdl-chartjs-barplot
  id="id11"
  fromid="id4"
  refindex="2"
  extremelimits="4,8"
  normallimits="6.9,7.1"
  initialdata="7">
</bdl-chartjs-barplot>

