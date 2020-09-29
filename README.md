# SVG

SVG images are scalable, which in an age of increasingly varied viewport sizes is a huge boon to development. With SVG we have one graphic to rule them all that scales to all devices, and therefore can save us from subsequent HTTP requests. Even the newer CSS properties such as srcset and picture require different images to be cut for different viewports, but SVG avoids all of that extra work.‌

Vector \(rather than raster\) means that, because they are drawn with math, SVGs tend to have greater performance and smaller file sizes.‌

SVG is an XML file format, and we can use it to succinctly describe shapes, lines, and text while still offering a navigable DOM; this means it can be performant and accessible.‌

* In a **vector graphics system**, an image is described as a series of geometric shapes. Rather than receiving a finished set of pixels, a vector viewing program receives commands to draw shapes at specified sets of coordinates.
* Vector graphics can be scaled without loss of image quality.

## viewBox <a id="viewbox"></a>

The SVG **`viewBox`** is a very powerful attribute, as it allows the SVG canvas to truly be infinite, while controlling and refining the viewable space.‌

parameters: value are as follows: **`x`**, **`y`**, **`width`**, and **`height`**.​‌

![](https://gblobscdn.gitbook.com/assets%2F-MEU8LPP7CCL0cHMso72%2F-MHoH_RvR8zHRZZ94x0c%2F-MHoJTr575g_KFHOcIWi%2Fviewbox-1.jpg?alt=media&token=97bea519-1ab3-43b7-a0ad-57b4e586ba02)

* SVG also stores information outside the viewBox area. If we move a shape outside this space
* The **white area** is what the **viewer sees**, while the white and **gray area** together **hold the information** that the **SVG actually contains**.

​​

![](https://gblobscdn.gitbook.com/assets%2F-MEU8LPP7CCL0cHMso72%2F-MHoH_RvR8zHRZZ94x0c%2F-MHoJrStAzI-xdIBTsl0%2Fviewbox-2.jpg?alt=media&token=c261fb93-7ac5-4dfe-b6bb-91c705e3cbec)

​

