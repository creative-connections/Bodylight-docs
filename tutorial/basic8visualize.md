# 8. Output and visualise variable

In this section we will create a component which will visualize a variable comming as output from fmu component.

## Chartjs-time component

click bdl-chartjs-time.

This will open an chartjs-time component dialog.

## Chartjs-time options

set the following options

* id: `id10`
  * component id referred by fmu component.
* width: `300`
  * in pixels
* height: `200`
  * in pixels
* fromid: `idfmi`
  * referring the id of fmu component
* labels: `Pressure in Aorta`
  * label in chart, if more, separate by comma
* initialdata: \`\`
  * some initial values to be displayed
* refindex: `0`
  * index of variable referenced from fmu component array (starting from 0)
* refvalues: `1`
  * number of variables to be displayed from the reference index

![EditorChart1](../img/EditorChart1.png)

## Submit the component

Click submit.

![EditorChartPreview](../img/EditorChartPreview.png)

This creates a `bdl-chartjs-time` component xml tag in the editor panel and renders a chart in the preview panel.

## Check simulation

Click the play  to check whether simulation starts.

![EditorChartPlay](../img/EditorChartPlay.png)
