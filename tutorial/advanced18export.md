# 18. Simulator Export

This section guide you to export simulation as a set of pages.

## Review the source code

Add some text before components, e.g.:
```markdown
# Heart during cardiac cycle
<div class="w3-row">
<div class="w3-twothird">

### simulation and chart
<bdl-fmi id="idfmi" src="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation.js" fminame="Physiolibrary_Fluid_Examples_Fernandez2013_PulsatileCirculation" tolerance="0.000001" starttime="0" fstepsize="0.01" guid="{a786b906-f58b-4014-8c9b-5df08bd77f4b}" valuereferences="637534370,637534288,637534348,637534458,637534516,637534313,637534482" valuelabels="aortaPressure.pressure,mitralValve.open,aorticValve.open,tricuspidValve.open,pulmonaryValve.open,leftVentricle.volume,rightVentricle.volume,aorta.pressure" inputs="id1,16777329,1,60" inputlabels="heartRate.k"></bdl-fmi>

<bdl-range id="id1" title="heart rate" min="40" max="180" default="60" step="1" maxlength="2"></bdl-range>

<bdl-chartjs-time id="id10" width="300" height="200" fromid="idfmi" labels="Pressure in Aorta [mmHg]" initialdata="" refindex="0" refvalues="1"
convertors="x/133.322-760"></bdl-chartjs-time>
</div>
<div class="w3-third">

### animation
<bdl-animate-adobe src="CardiaccycleStage.js" width="200" height="200" name="Faze_srdce" fromid="idfmi"></bdl-animate-adobe>

<bdl-bind2a findex="1" aname="ValveMV_anim" amin="99" amax="0" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="2" aname="ValveAOV_anim" amin="0" amax="99" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="3" aname="ValveTV_anim" amin="99" amax="0" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="4" aname="ValvePV_anim" amin="0" amax="99" fmin="0" fmax="1"></bdl-bind2a>
<bdl-bind2a findex="5" aname="ventricles.ventriclesTotal.VentricleLeft_anim" amin="100" amax="0" fmin="0.00015" fmax="0.00021"></bdl-bind2a>
<bdl-bind2a findex="6" aname="ventricles.ventriclesTotal.children.0.VentricleRight_anim" amin="100" amax="0" fmin="0.00012" fmax="0.00018"></bdl-bind2a>

</div>
</div>
```
## (optionally) Save project as ZIP
Save the project as a ZIP file for further usage. 

Click <button>Project Menu</button> and click <button> Save project as ZIP</button>. 

The ZIP file contains all MD and other files, additionally it contains project specific json file to facilitate loading project in another computer.

Bodylight-Editor is static web page - meaning it does not store and transfer your data to a server, thus it's necessary to save your project locally. The current project is stored in browser local cache and will disapear when browser cache is cleaned.

## Export to HTML

Click <button>Project menu</button> and select <button>Export project as HTML</button>.
A dialog asking for file name will appear. Fill the name and submit.
A ZIP file will be created and `Save As` feature of web browser is used to save the ZIP locally to your computer.

## HTML Export Zip file structure

A ZIP file contains these files:
 - index.md (document with web simulator)
 - animation.md (second document with advanced web simulator)
 - summary.md (list of all web simulators) 
 - bodylight.bundle.js (bodylight web components bundle implementation)
 - index.html (HTML index file containing markdown-book component refering to index.md and summary.md)
 - JS and modelDescription.xml (WebAssembly compilation of FMU with model simulator)

## Static web site
You may deploy all the files in ZIP archive into any web server - the index.html serves as a static page loading the other MD, JS files rendered on demand.

## Local web site
You may unzip all files and test it locally by loading index.html by browser.

### Firefox 
Firefox version >68.0 requires `privacy.file_unique_origin` to be `false`. Set it in `about:config` and open `index.html` from the exported project.

### Chrome
Chrome can be used with [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb) extension, which can serve selected directory as a root of local web server. 


