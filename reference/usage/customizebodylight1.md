# Notes on usage of application of Bodylight.js v1.0

## Embeding existing v1.0 apps

Bodylight.js v1.0 apps are exported as single HTML files. This HTML can be embedded as iframe into web page.
   
## Manual interaction and customization with v1.0 app
Interaction between v1.0 app and other components or v2.0 app can be done using following example:

  1. Export BJP into Application HTML (do not set 'minimize')
  2. Edit the resulting HTML file
  3. find `createModelRuntime` and add a row to export the `model` object as a global variable `window.BodylightModel`, e.g.: 
  ```javascript
function createModelRuntime(Model, config, functions) {
...
            //add this row to set explicitly global variable 
            // BodylightModel to be accessed from outside
            window.BodylightModel = model;
...
  ```
  Now the `BodylightModel` is exposed. You can call API `model.setValue()` as `window.BodylightModel.setValue()`:
```html
<p>Added component, manipulating Bodylight web app from outside:</p>
<p>set heart rate:
<input id="myheartrateinput" 
       type="number" 
       min="40" 
       max="180" 
       onchange="setMyHeartRate(this.value)"></input> 
</p>
<script>
function setMyHeartRate(value){
  //global variable BodylightModel set explicitly in the code above
  //need to know value reference of heart rate in model 
  // - it is 16777216 in this case
  window.BodylightModel.setValue(16777216,value); 
}
</script>
```
...
