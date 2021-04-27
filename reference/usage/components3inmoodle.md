# Bodylight.js-Components in Moodle

In order to add Bodylight.js Components into Moodle pages, you need to modify HTML source of Moodle page. You may also embed
web simulators in markdown syntax hosted on other public resource.   

## Bodylight components into page source

1. edit moodle page in HTML - use HTML source, click <i class="fa fa-level-down"></i> and then switch code - click <i class="fa fa-code"></i>
2. add the bodylight script
   ```html
   <script type="module" src="https://bodylight.physiome.cz/Bodylight.js-Components/bodylight.bundle.js"></script>
   <div aurelia-app="webcomponents"><br>
   ```
3. add bodylight component
   
## Embedding external web simulators

* Add `bdl-markdown` component referring external MD file.
* Markdown component needs `base` attribute to be specified.
* For resources in github repo use `cdn.jsdelivr.net/gh/` which is returning correct MIME Type.
E.g.:
   ```html
   <bdl-markdown 
      src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight-Scenarios@master/hemodynamics/index.cs.md" 
      base="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight-Scenarios@master/">
   bdl-markdown not supported
   </bdl-markdown>
   ```
`base` attribute ensures that FMI scripts and other content from markdown document is loaded from the correct resource base. 

