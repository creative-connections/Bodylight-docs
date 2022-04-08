### Range, bdl-range
`<bdl-range>` Renders a range input which may trigger a value. With following attributes:
  * `id` unique id
  * `min`, `max` minimum and maximum range value (default 0,100)
  * `step`, step between the range values (default 1)
  * `default`, default value of the range component (default 50)

Example:
  * `<bdl-range id="id1" min="10" max="20" step="2" default="12"></bdl-range>` will render range from 10 to 20 with default value 12 and step 2.
  *  <bdl-range id="id1" min="10" max="20" step="2" default="12"></bdl-range>  


### range-smooth
`<bdl-range-smooth>` Extends range by smoothing inputs to be sent. It will generate 'number' of input events which gradually converges to the user selected values.
* `number` number of steps - default 5
* `time`, time between events in ms - default 200 ms

Example:
* `<bdl-range-smooth id="id1" min="10" max="20" step="2" default="12" number="10" time="300"></bdl-range-smooth>` will render range from 10 to 20 with default value 12 and step 2.On each user change it will generate '10' events which gradually converges to the user selected values
*  <bdl-range-smooth id="id1" min="10" max="20" step="2" default="12" number="10" time="300"></bdl-range-smooth>
