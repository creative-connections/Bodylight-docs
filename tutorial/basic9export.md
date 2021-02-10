# Simulator Export

This section guide you to export simulation as a single HTML page or as a set of HTML pages.

## Export to HTML

Click <button>Project menu</button> and select <button>Export project as HTML</button>.
A dialog will appear

## Exported file

Fill the dialog name and submit.
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


