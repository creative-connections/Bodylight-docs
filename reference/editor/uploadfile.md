Click <button>+ Upload file</button> and an area appear, you may drag and drop file here, or you may click <button>Browse</button> to select exact file.

These file types are recognized based on extension:
  * .md - document file in Markdown format, all document files should be listed in summary.md, you may create link to the document file either manually or using link icon (<i class="fa fa-link"></i>). `[index2](#index2.md`. Note that the link starts with `#` which is detected by the `bdl-markdown-book` component in URL as a request to show new document in page.
  * .zip - zip archive created by Bodylight.js-FMU-Compiler - it's FMU compiled into webassembly - contains JS file and `modelDescription.xml`. It is used by the `<bdl-fmu>` component.
  * .jpg .png .gif - static image or animated gif - it can be used in markdown e.g.`![image1](image1.jpg)` or directly by html tags `<img src="image1.jpg"></img>`. Animated GIF can be also used by `bdl-animate-gif` component to synchronize animation framews with model simulation.
  * .js - animation from Adobe Animate published as CreateJS component. It's more flexible animation than animated GIFs allowing to animated independently several elements. To prepare animation, please use this convention:
    * all animatable objects must be named with `_anim` suffix, the animation object may lineary interpolate shape between values 0-99 or 0-159. The value comming from model simulation is mapped to animation value by the component `<bdl-bind2a>`.
    * all text objects - e.g. numbers must be named with `_text` suffix, model variable value can be shown as text using  

If the file is not recognized then it's moved to 'OTHER' type.


   