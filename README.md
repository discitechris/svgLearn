# SVG



```markup
<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" 
x="0px" y="0px" width="450px" height="100px" viewBox="0 0 450 100">
 <rect x="10" y="5" fill="white" stroke="black" width="90" height="90"/>
 <circle fill="white" stroke="black" cx="170" cy="50" r="45"/>
 <polygon fill="white" stroke="black" points="279,5 294,35 328,40 303,62 309,94 
279,79 248,94 254,62 230,39 263,35 "/>
 <line fill="none" stroke="black" x1="410" y1="95" x2="440" y2="6"/>
 <line fill="none" stroke="black" x1="360" y1="6" x2="360" y2="95"/>
</svg>
```

SVG looks like a graph paper with infinite defining things with x and y co-ordinates

x = "0px" and y ="0px"\(redundant since they start 0 , we don't need them\) x/y defines the x/y coordinate of the upper left corner of its viewport.

width/height defines the horizontal/vertical length for the rendering area of the SVG viewport.

The viewBox attribute defines the position and dimension, in user space, of an SVG viewport.

The value of the viewBox attribute is a list of four numbers: min-x, min-y, width and height. The numbers separated by whitespace and/or a comma, which specify a rectangle in user space which is mapped to the bounds of the viewport established for the associated SVG element

rect places itself with x and y from upper-left corner circle x and y always reference the center point of the circle. polygon is clockwise direction with starting x/y point from upper left corner with unlimited x/y points in between and always tries to connect the endpoint to starting point. line is based on x1/x2 y1/y2 cordinates where x1/y1=starting point x2/y2=ending point

### Viewbox

if width/height of changed the graph becomes smaller/larger in respect to the viewbox

### check images

if the svg element

