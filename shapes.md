# Shapes

## rect

rect refers to a rectangle or square.

```markup
<svg>
<rect x="10" y="5" fill="white" stroke="black" width="90" height="90" />
</svg>
```

* The **`x`** and **`y`**values, just as with the SVG itself, are where the shape begins: 
  * in this case, its upper-left corner. 
* The shape’s **`width`** and **`height`** use the **same coordinate system**
* The **`fill`** and the **`stroke`** are designated here as white and black;
* if **`fill`** and **`stroke`** **is not specified** here, the **`fill` would default to black** and the **`stroke` would be none \(i.e., invisible\).**

## circle

```markup
<svg>
<circle fill="white" stroke="black" cx="170" cy="50" r="45"/>
<ellipse fill="white" stroke="black" cx="170" cy="50" rx="45" ry="30"/>
</svg>
```

* **`cx`** is the point where the **center** of the circle **lies on the x-axis**,
* **`cy`** is the point where the **center** of the circle **lies on the y-axis**,
* **`r`** is the **radius**.
* **`ellipse`** require **two radius values** **`rx`** and **`ry`** for oval shapes

## polygon

polygon passes an array of values in a space-separated list, defined by points

```markup
<svg>
<polygon fill="white" stroke="black" points="279,5 294,35 328,40 303,62 
309,94 279,79 248,94 254,62 230,39 263,35"/>
</svg>
```

* **first value** represents the **x coordinate position**, followed by a comma,
* **second value** represents the **matching y coordinate position** to **plot the point**.

## line

```markup
<svg>
<!-- diagonal line -->
<line fill="none" stroke="black" x1="410" y1="95" x2="440" y2="6" />
<!-- straight line -->
<line fill="none" stroke="black" x1="360" y1="6" x2="360" y2="95" />
</svg>
```

* The **first point** of line is **plotted at the `x1` and `y1` values**.
* The **end point** of the line **plotted** **at the `x2` and `y2` values.**

