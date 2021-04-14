## Customize application prepared in Bodylight Composer v1.0

In order to do just minor updates in application prepared already in Bodylight.js v1.0 do:
  1. Export BJP into Application HTML (do not set 'minimize')
  2. Edit Application HTML
  3. find 'createModelRuntime' and set global variable instance, e.g.: 
  ```javascript
function createModelRuntime(Model, config, functions) {
...
            //add this row to set explicitly global variable 
            // BodylightModel to be accessed from outside
            window.BodylightModel = model;
...
  ```
  Now the `BodylightModel` is exposed. You can call API `model.setValue()` in Application HTML:
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
