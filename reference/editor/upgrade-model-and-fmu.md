# Upgrade model and FMU

After model change in Modelica and export to FMU, the value references may change.&#x20;

To upgrade the compiled FMU (zip file with embedded WebAssembly in Javascript produced by Bodylight.js-Compiler):

1. delete` modelDescription.xml` and `[model_name].js` from model section
2. upload the compiled FMU with upgraded model
3. move cursor to <`bdl-fmi>` component&#x20;
4. if some variable name was changed in model, do the same change manually in attribute `valuelabels` and `inputlabels`
5. click <mark style="background-color:blue;">identify/edit</mark>
6. under <mark style="background-color:blue;">Variables</mark> section click update FMU vars&#x20;

Based on stored labels, it will check and update reference values.

![](../.gitbook/assets/2e7gQAc60D.gif)



