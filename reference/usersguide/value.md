### BdlValue, bdl-value
`<bdl-value>` renders numerical value 
  * `fromid` ID of component which will be listened for events `fmidata`
  * `refindex` reference index of value sent by `fmidata` event
  * `convertors` - conversion of the raw value from fmi to thhe value shown in form  either `convertors=numerator,denominator,addend` or `convertor=(exprsssion with x)` e.g. `convvertors=1/x` 
  * `precision=4` - precision to be shown - default 4 literals
  * `throttle=500` - throttle update of data, if data are update multiple times per second show it every 500 ms.

Example: 
`<bdl-value fromid="id4" refindex="8"></bdl-value>`
<bdl-value fromid="id4" refindex="8"></bdl-value>
