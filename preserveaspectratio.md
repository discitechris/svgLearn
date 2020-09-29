# preserveAspectRatio

* The preserveAspectRatio attribute lets you specify the alignment of the scaled image with respect to the viewport, and whether you want it to meet the edges or be sliced off.
*  The model for this attribute is

```markup
<svg height="100" width="100" viewBox="0 0 10 50"
preserveAspectRatio="alignment [meet | slice | none ]" /> 
```

* where alignment specifies the axis and location and is one of the combinations
* This alignment specifier is formed by concatenating an x-alignment and a y-alignment min, mid \(middle\), or max value. 
* The **default** value for **`preserveAspectRatio`** is **`xMidYMid meet`**.

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>Y Alignment</b>
      </th>
      <th style="text-align:left"><b>X Alignment</b>
      </th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p><b><code>xMin </code></b>
        </p>
        <p><b>Align minimum <code>x </code><br />value of <code>viewBox</code> with</b>
        </p>
        <p><b>left edge of viewport</b>
        </p>
      </td>
      <td style="text-align:left">
        <p><b><code>xMid</code></b>
        </p>
        <p><b>Align midpoint <code>x</code> value of </b>
        </p>
        <p><b><code>viewBox</code> with <br />horizontal center of viewport</b>
        </p>
      </td>
      <td style="text-align:left">
        <p><b><code>xMax</code></b>
        </p>
        <p><b>Align maximum <code>x</code> value</b>
        </p>
        <p><b>of <code>viewBox</code> with <br />right edge of viewport</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b><code>yMin</code></b>
        </p>
        <p><b>Align minimum <code>y</code> value of <code>viewBox</code> with <br />top edge of viewport</b>
        </p>
      </td>
      <td style="text-align:left"><b><code>xMinYMin</code></b>
      </td>
      <td style="text-align:left"><b><code>xMidYMin</code></b>
      </td>
      <td style="text-align:left"><b><code>xMaxYMin</code></b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b><code>yMid</code></b>
        </p>
        <p><b>Align midpoint <code>y</code> value of</b>
        </p>
        <p><b><code>viewBox</code> with <br />vertical center of viewport</b>
        </p>
      </td>
      <td style="text-align:left"><b><code>xMinYMid</code></b>
      </td>
      <td style="text-align:left"><b><code>xMidYMid</code></b>
      </td>
      <td style="text-align:left"><b><code>xMaxYMid</code></b>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><b><code>yMax</code></b>
        </p>
        <p><b>Align maximum <code>y</code> value</b>
        </p>
        <p><b>of <code>viewBox</code> with</b>
        </p>
        <p><b>bottom edge of viewport</b>
        </p>
      </td>
      <td style="text-align:left"><b><code>xMinYMax</code></b>
      </td>
      <td style="text-align:left"><b><code>xMidYMax</code></b>
      </td>
      <td style="text-align:left"><b><code>xMaxYMax</code></b>
      </td>
    </tr>
  </tbody>
</table>

{% hint style="warning" %}
**NOTE:**    The **y-alignment begins with a capital letter,** because the x- and y-alignments are concatenated into a single word.
{% endhint %}

* **If you don’t specify** a preserveAspectRatio, the **default value is xMidYMid meet**, 
* which will scale down the graphic to fit the available space, and center it both horizontally and vertically.

### **meet**

* **`meet`**will attempt to scale the graphic as much as possible to fit inside the containing viewBox, while keeping the aspect ratio consistent. 
* This functionality is **similar to `background-size: contain`** in that the image will stay contained in the boundaries of the containing unit.

### slice

* **`slice`**will allow the graphic within the viewBox to expand beyond what the user sees in the direction specified, while filling up the available area. 
* You can think about it like **`background-size: cover`** in that the image will push beyond the boundaries of the containing unit to fill up the available user space.

