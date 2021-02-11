# Simulator Export {num=9}

This section guide you to export simulation as a single HTML page or as a set of HTML pages.

## Review the source code

Add some text before components, e.g.:
```markdown
# Introduction

Hemodynamics model simulator:

Press buttons to start/stop/step/reset simulation:
<bdl-fmi id="idfmi" src="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation.js" fminame="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation" tolerance="0.000001" starttime="0" fstepsize="0.01" guid="{a786b906-f58b-4014-8c9b-5df08bd77f4b}" valuereferences="637534370" valuelabels="aorta.pressure" inputs="id1,16777329,1,60" inputlabels="heartRate.k"></bdl-fmi>

Change the slider value. When released - it is sent to model and simulation is recalculated accordingly:
<bdl-range id="id1" title="heart rate" min="40" max="180" default="60" step="1" maxlength="2"></bdl-range>

Show some variables in chart:
<bdl-chartjs-time id="id10" width="300" height="200" fromid="idfmi" labels="Pressure in Aorta" initialdata="" refindex="0" refvalues="1"></bdl-chartjs-time>
```

## Export to HTML

Click <button>Project menu</button> and select <button>Export project as HTML</button>.
A dialog asking for file name will appear.

## Exported file

Fill the name and submit.
A ZIP file will be created and`Save As` feature of web browser is used to save the ZIP locally to your computer.

## Zip file structure

A ZIP file contains these files:
 - index.md (document with web simulator)
 - summary.md (generated list of all web simulators, in case of multiple page) 
 - bodylight.bundle.js (bodylight web components bundle implementation)
 - index.html (HTML index file containing markdown-book component refering to index.md and summary.md)
 - JS and modelDescription.xml (WebAssembly compilation of FMU with model simulator)

## Static web site
You may deploy all the files in ZIP archive into any web server - the index.html serves as a static page loading the other MD, JS files rendered on demand.

## Local web site
You may unzip all files and test it locally by loading index.html by browser.

### Firefox 
Firefox version >68.0 requires `privacy.file_unique_origin` to be `false`. Set it in `about:config` and index.html from the exported project.

### Chrome
Chrome can be used with [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb) extension, which can serve selected directory as a root of local web server and open index.html from the exported project.


