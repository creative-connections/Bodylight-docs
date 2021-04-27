# Tabs

```html
<bdl-tabs idlist="uvod,modelplic,modeltkani,krivkao2,krivkaco2,porovnani" 
  titlelist="Úvod,Model plic,Model tkání,Křivka O2,KřivkaCO2,Porovnání O2 a CO2"></bdl-tabs>
```
* `idlist` - list of associated id's separated by comma `,`
* `titlelist` - optional titles on button, if not specified, then ids are used, separated by comma `,`
Creates tabs (buttons) - associated with divs with id. Active tab shows associated div, other divs are hidden.  
When tab is clicked -associated div is made visible while the previous is hidden.

Example:

```html
<bdl-tabs idlist="uvod,modelplic,modeltkani,krivkao2,krivkaco2,porovnani" 
  titlelist="Úvod,Model plic,Model tkání,Křivka O2,KřivkaCO2,Porovnání O2 a CO2"></bdl-tabs>
<div id="uvod">uvod</div>
<div id="modelplic">modelplic</div>
<div id="modeltkani">modeltkani</div>
<div id="krivkao2">krivkao2</div>
<div id="krivkaco2">krivkaco2</div>
<div id="porovnani">porovnani</div>

```
Is rendered as:
   
<bdl-tabs idlist="uvod,modelplic,modeltkani,krivkao2,krivkaco2,porovnani" 
  titlelist="Úvod,Model plic,Model tkání,Křivka O2,KřivkaCO2,Porovnání O2 a CO2"></bdl-tabs>
<div id="uvod">uvod</div>
<div id="modelplic">modelplic</div>
<div id="modeltkani">modeltkani</div>
<div id="krivkao2">krivkao2</div>
<div id="krivkaco2">krivkaco2</div>
<div id="porovnani">porovnani</div>
