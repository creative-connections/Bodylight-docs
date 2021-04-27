## Bodylight.js-Components in Markdown

Bodylight web components contain special markdown components to read external MD file with components:
 - `bdl-markdown`
 - `bdl-markdown-book`
 - `bdl-markdown-book2`
All these have attribute `src` reffering to the MD file. MD file is read by fetch API from the same web directory as parent HTML file.
  
The file `home.html` may look like:

**home.html**
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Bodylight web component</title>
     <script type="module" src="bodylight.bundle.js"></script>
     <script type="module" src="modelfmi.js"></script>
  </head>
<body aurelia-app="webcomponents">

  <bdl-markdown src="home.md"></bdl-markdown>

</body>
```

After loading `home.html` the `bdl-markdown` component reads content of the file `home.md`:

**home.md**
```markdown
# Changing Heart Rate
heart rate can be set here:
<bdl-range id="id1" min="40" max="180" step="1" default="60"></bdl-range>
...
```
