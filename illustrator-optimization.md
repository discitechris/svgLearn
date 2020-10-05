# Illustrator Optimization

Layers in the graphic will be exported as groups, complete with id values derived from the layer names. You may find, though, that upon export, your SVG has a lot of information that the code in the preceding examples does not:

```markup
<?xml version="1.0" encoding="utf-8"?>
<!-- Generator: Adobe Illustrator 18.1.1, SVG Export Plug-In . SVG Version: 
   6.00 Build 0)  -->
<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" 
   xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
     width="218.8px" height="87.1px" viewBox="0 0 218.8 87.1" 
  enable-background=
    "new 0 0 218.8 87.1" xml:space="preserve">
  <g>
    <path fill="#FFFFFF" stroke="#000000" stroke-miterlimit="10" 
      d="M133.1,58.2c0,0,12.7-69.2,24.4-47.5c0,0,4.1,8.6,9.5,0.9
              c0,0,5-10,10.4,0.9c0,0,12.2,32.6,13.6,43c0,0,39.8,5.4,15.8,
      15.4c-13.2,5.5-53.8,13.1-77.4,5.9C129.5,76.8,77.5,61.4,133.1
      ,58.2z"/>
    <path fill="#FFFFFF" stroke="#000000" stroke-miterlimit="10" 
    d="M6.7,61.4c0,0-3.3-55.2,20.8-54.8s-7.2,18.1,4.1,29.9
            s8.6-31.2,32.1-15.8S86.7,41,77.2,61.8C70.4,76.8,76.8,79,37.9,
    79c-0.4,0-0.9,0.1-1.3,0.1C9,81,40.1,58.7,40.1,58.7" />
  </g>
</svg>
```

code again for comparison:

```markup
<svg viewBox="0 0 218.8 87.1">
 <g fill="none" stroke="#000">
   <path d="M7.3 75L25.9 6.8s58.4-6.4 33.5 13-41.1 32.8-11.2 30.8h15.9v5.5s42.6 
     18.8 0 20.6" />
   <path d="M133.1 58.2s12.7-69.2 24.4-47.5c0 0 4.1 8.6 9.5.9 0 0 5-10 10.4.9 0 
     0 12.2 32.6 13.6 43 0 0 39.8 5.4 15.8 15.4-13.2 5.5-53.8 13.1-77
       .4 5.9.1 0-51.9-15.4 3.7-18.6z" />
 </g>
</svg>
```

You can see it’s much smaller: **without proper optimization, you can easily bloat SVG code.**

{% hint style="info" %}
**TIP:**    When using Illustrator, be sure to use File → Export → SVG to save an SVG rather than using Save As. \(This is only available in Illustrator CC 2015.2 or later.\) This will bring up the SVG Options dialog

Export will give you a much smaller and more precise output than Save As, which is not optimized for SVG. I personally always retain a copy or several copies of the .ai source, because sometimes heavily modified SVGs don’t backport well into Illustrator.
{% endhint %}

Some of this information is useful, and some we can do away with.

* The comment about Illustrator generating the code can certainly be removed.
* We also do not need the version or layer information, as the web will not use it
* If x and y are defined as 0 \(usually the case\), we can strip those out, too.
  * The only case where we’d want to leave them in is if we’re working with a child SVG nested inside another SVG.
* We can also strip away the XML definitions if we are using an SVG inline.
  * If you decide to use the SVG in an object or image, you should keep this XML markup because leaving it out can cause issues in older browsers: **`xmlns="`**[**`http://www.w3.org/2000/svg`**](http://www.w3.org/2000/svg)**`"`**
* You can also optimize paths. Illustrator will export path data with unnecessary decimal places that can be removed, and may also export group markup that will clutter your code.

## Reduce Path Points

* If you’re going to create a hand drawing, you can trace it, but past that point you should use Object → Path → Simplify.
  * The image quality will tend to degrade quickly as the curve precision is lowered, 91% is usually the lowest you can get away with. The number of points removed at this level still reduces the file size dramatically.
* A more labor-intensive way that I use for smaller, unnecessarily complex pieces is to redraw them with the **Pen tool**.

## Optimization Tools

There are many great tools for optimizing SVGs and they offer more ways to help trim your code, such as rounding and rewriting numbers, merging path data, removing unneeded groups, and more.

The following list includes some of the available open source tools. The ones that visually show the output tend to be the most useful, as you can see how optimization may change the result:

### [SVGOMG](https://jakearchibald.github.io/svgomg/)

Jake Archibald has created a really nice web-based GUI for the terminal-based SVGO \(see below\). This tool is the most robust and easy to work with, and includes many toggle optimization options. SVGOMG shows the relative visual output and the byte-saving comparison after optimization.

## [SVG Editor](http://petercollingridge.appspot.com/svg-editor)

Peter Collingridge’s SVG Editor is very similar to SVGOMG, with slightly fewer options. A nice feature is that you can edit the SVG right in another panel in case you need to adjust the output just slightly. It’s web-based, with a nice visual interface.

## DEFAULT EXPORT SETTINGS TO BE AWARE OF 

Be mindful of some of the defaults when you’re exporting. The ones that I find myself **checking and unchecking the most are:**

* **Clean IDs**—This will remove any carefully named layers you may have. 
* **Collapse useless groups**—You might have grouped them to animate them all together, or just to keep things organized. 
* **Merge paths**—Nine times out of 10 this one is OK, but sometimes merging a lot of paths keeps you from being able to move elements in the DOM around independently. 
* **Prettify**—This is only necessary when you need to continue working with the SVG code in an editor.



