# Bodylight.js-Components in Moodle

Moodle^[E-learning system Moodle https://moodle.org/] can embed web-components directly or embed published web pages indirectly.

## Bodylight components in page source

1. edit moodle page in HTML - use HTML source, click <i class="fa fa-level-down"></i> and then switch code - click <i class="fa fa-code"></i>
2. add the bodylight script
   ```html
   <script src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight.js-Components/dist/bodylight.bundle.js"></script>
   <div aurelia-app="webcomponents"><br>
   ```
3. add any Bodylight.js components:
   
## Embedding external web simulators

1. Add `bdl-markdown` component referring external MD file.
2. Markdown component needs `base` attribute to be specified.
3. For resources in github repo use `cdn.jsdelivr.net/gh/` (it returns correct MIME Type)
E.g.:
   ```html
   <script src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight.js-Components/dist/bodylight.bundle.js"></script>
   <div aurelia-app="webcomponents"><br>   
   <bdl-markdown 
      src="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight-Scenarios@master/hemodynamics/index.cs.md" 
      base="https://cdn.jsdelivr.net/gh/creative-connections/Bodylight-Scenarios@master/">
   bdl-markdown not supported
   </bdl-markdown>
   </div>
   ```
`base` attribute ensures that FMI scripts and other content from markdown document is loaded from the correct resource base. 

