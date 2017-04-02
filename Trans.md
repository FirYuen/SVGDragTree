<img src="mov.gif">

## About what is SDT.

SDT is an abbreviation for SVG Drag Tree,it's a front-end components that you could Simply drag and drop the SVG icon to generate a view with the tree structure and the corresponding data. The component doesn't depend on any other library or framework while leaving the user with  great freedom in the pattern. Therefore, the example does not represent its final style (for example, the connection can be set to a straight line). The file size of .min.js is about 13kb.

### Example [example](https://aute.github.io/SVGDragTree/)

## What SDT did?
* You don't need to worry about the elements will be stacked together because you get the size of the element automatically
* You can decide how they are placed and set the dependencies between elements 
* Straight line and curve can be chosed and you could set the line color
* The upper and lower margins between the elements are also settable, but the width between the elements will generate automatically
* The size of the target canvas is determined by the  DIVs, and you can customize the background
* Two methods are available: set up directly in HTML, or set in js
* If you do not make a setting, the component provides default settings
* Provides a global drag and zoom of the entire canvas, as well as a way back to the canvas center
* Undo or delete any element is also supproted, the rest of the elements will be re-arranged
* Two types of data can be returned : Lite and Full version. The lite only contains element type, ID, dependency to reduce the amount of data sent to the back-end, but the Lite version of the data can not be used for redraw. The Full version contains all the data contained in the Lite, and also contains drawing-related information, placing order-related information that can be used as redraw
* Yes, the method of receiving the "full version of the data" and then redrawing it is also provided(in the example, the canvas has been generated tree structure)
* When the users actions do not match your settings  a monitorable error massage will be returned

## What SDT can be used to
* For the moment, SDT has been applied to a cloud service providers in the virtual devices' arrangement.
* Perhaps to be a mind map is also good?

## Advantages of SDT
* Based on SVG, and relative to the Canvas class library inherited some of the advantages of SVG, for example, can work with CSS, DOM
* Native JS and has no any further dependency,Light-weight

## Introduction method
Introduction by &lt;script&gt;,If If the label is placed on the head, it must set to defer="defer".
If you need other JS to set up or call the component just like exampleScript.js down there, This Js file needs to be introduced after SDT.js* 
```html
<head>
	...
	<script src="SDT.js" defer="defer" type="text/javascript" charset="utf-8"></script>
	<script src="exampleScript.js" defer="defer" type="text/javascript" charset="utf-8"></script>
	...
</head>
```

In the html files, all SVG icons that can be dragged are surrounded by a <div> tag of a class = "sdt-drag-element-lis", each of which is given by a <div> label ' class = "sdt-drag-element" ' surrounded 
*Note:The label must be a data-sdt-type attribute, and the attribute value is a string that describes the type of the icon*
```html
<div class="sdt-drag-element-lis">
	<div class="sdt-drag-element" data-sdt-type="icon-1">
		<svg>...</svg>
	</div>
	<div class="sdt-drag-element" data-sdt-type="icon-2">
		<svg>...</svg>
	</div>
	<div class="sdt-drag-element" data-sdt-type="icon-3">
		<svg>...</svg>
	</div>
	...
</div>
```

In the html files, the  canvas is surrounded by a <div> tag of a class = "sdt-canvas", which determines the width and height of the target canvas. The canvas is a <svg> tag with id = "sdt-drop-canvas"
```html
<div class="sdt-canvas">
	<svg id="sdt-drop-canvas" width="100%" height="100%">...</svg>
</div>
```

## Configuration method
### Not Configured
If not configured, the component defaults elements can be placed above all elements, the default elements placed on the right side of the tree, the margins between the elements is the height of the elements themself.The elements linked by Bessel curve, color is # 999, and the center of the tree is located in the upper left corner of the canvas

<img src="noSet.jpg">

### Example for not configured ： [example](https://aute.github.io/SVGDragTree/noSet.html)

