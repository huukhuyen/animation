#THE CANVAS
##INTRODUCING THE CANVAS ELEMENT

###Introducing	

* The Canvas element provides web pages with a drawing surface for drawing all kinds of graphics - shapes, images, text, etc.
* Supported in the latest browsers: IE 9+, Chrome 3+, Safari 3+, Opera 10+, Firefox 3+
http://caniuse.com/#feat=canvas
* Browsers that don’t support Canvas can display fallback content(text, image, Flash, etc.)
* Pages can have more than one Canvas - they can even overlap
* Canvas contents are created on-the-fly using script
* Canvas is good for dynamic visual media, but the contents are not part of the page

###The canvas tag

* The canvas coordinate system starts at the upper left, with increasing values of x going left to right an increasing values of y from top to bottom

![image](https://s31.postimg.org/ifkxnlxbv/image04.png)

* Canvas element start out invisible (transparent black background) * 
* The &lt;canvas&gt; tag has the following syntax:* 

~~~
<canvas id=”canvas1” width=”400” height=”300”>

Fallback content
			
</canvas>
~~~

| Attribute/Function | Description |
| :------| :-----------|
| width   | The width of the canvas in pixels |
| height | The height of the canvas in pixels |
| toDataURL(type)    | Convert the contents of the canvas to static image. The type parameter indicates the image type (image/png) |
| getContext(ctxID)    | Get the drawing context for the canvas |		

###The canvas properties and methods

* The width and height properties represent the canvas width and height
* These properties can be set as well as retrieved
* The toDataURL() method converts the contents of the image to a data://URL of the given image type. image/png support is mandatory, but others can be supported
* The getContext() method retrieves the drawing context for the canvas. This content contains information about the canvas and provides all of the drawing methods for that particular context

##HOW CANVAS COMPARES TO SVG: KEY DIFFERENT

| Canvas | SVG |
| :------| :-----------|
| Element are drawn programmatically   | Element are part of the page’s DOM |
| Drawing is done with pixels | Drawing is done with vectors |
| Animation are not built    | Effects such as animation are built |
| High performance for pixels-based drawing operations  | Based on standard XML syntax, which provides better accessibility |


##UNDERSTANDING THE CANVAS ELEMENT AND 2D DRAWING API

* Drawing on a canvas requires a series of steps:
   + Retrieve a reference to the canvas element
   + Get the drawing context from the element using getContext()
   + If the result of the getContext() is not null, you can start using the drawing API
* Drawing on the canvas must be scripted. Consider the following example:

~~~
<canvas id=”canvas1” width=”400” height=”300”>

Fallback content
			
</canvas>
function drawOnCanvas() {
	var cElem = document.getElementById(“canvas1”);
	var ctx = cElem.getContext(“2d”);
	if(ctx != null) {
		   // go ahead and draw away !	
	}
}
~~~

Demo : [http://codepen.io/nguyentb1412/pen/NNjBrK](http://codepen.io/nguyentb1412/pen/NNjBrK)

##BASIC CANVAS DRAWING TECHNIQUES

###Setting and using colors and styles

| Context Property | Description |
| :------| :-----------|
| fillStyle | Style to use when filling. CSS Color, Gradient, Pattern (black) |
| strokeStyle | Style to use on strokes, CSS Color, Gradient, Pattern (black) |
| lineWidth | Width of the imaginary pen to use when drawing lines |

Two step process to draw with colors and styles:
	
1. Set the fill and stroke styles and line width

2. Call a drawing operation that creates a shape

Demo : [http://codepen.io/nguyentb1412/pen/wGdxyB](http://codepen.io/nguyentb1412/pen/wGdxyB)

###Rectangles and lines 

* Rectangles are the only primitive shape supported by canvas

| Rectangle Function | Description |
| :------| :-----------|
| clearRect (x,y,w,h) | Erases the given rectangle, makes the area fully transparent |
| strokeRect (x,y,w,h) | Outlines a rectangle with the current strokeStyle |
| fillRect (x,y,w,h) | Fills a given rectangle with the current fillStyle |

Demo : [http://codepen.io/nguyentb1412/pen/EKXdVB](http://codepen.io/nguyentb1412/pen/EKXdVB)
	
* All three rectangle-drawing operations take a starting point of the upper-left corner of the rectangle (x,y) and a width and height value (w,h)
* Lines can be created using a variety of settings for how lines join together and how they end.

| Rectangle Function | Description |
| :------| :-----------|
| move(x, y) | Moves the pen to the given coordinates, does not draw |
| lineTo(x, y) | Draws a line from the current pen position to the new point |
| lineWidth | Determines the pixels with that lines will be draw in |
| lineCap | How line endings are drawn: butt (default), round, square |
| lineJoin | How lines join together: round, bevel, miter (default) |
| miterLimit | The limit at which line joins are cut off drawn as bevels (10) |
| beginPath() | Begins a new set of path-drawing operations|
| stroke() | Collects all of the current path commands and draws them |

Demo:  [http://codepen.io/nguyentb1412/pen/GZEYZW](http://codepen.io/nguyentb1412/pen/GZEYZW)

###Canvas state
* Each context maintains a drawing state, which your code can manage
* You can save the current state and restore a previous one
* The state can be pushed onto a stack of saved states
* The canvas state keeps track of several properties of the canvas:
   1. Current values of lineWidth, strokeStyle, fillStyle, lineCap, etc.
   2. Current transformation matrix
   3. Current clipping region
* Why would you want to save and restore states ?
  + Your code may have set up a whole bunch of complex drawing settings that you don’t want to have to manually keep track of
* To save and restore the state, use the save() and restore() functions:
  1. Call context.save()
  2. Perform a set a drawing operations, which may changes the state
  3. Call context.restore()
  
Demo : [http://codepen.io/nguyentb1412/pen/vGmorL](http://codepen.io/nguyentb1412/pen/vGmorL)

###Arcs and paths

* A path is simply a set of points, connected by lines or curves, and is either open or closed. The context always has one (and only me) current path
* A closed path has an endpoint that is the same as its starting point
* To begin creating a path, call the beginPath() method
* To add paths, use one or more path drawing routines
* To stroke the current path, call stroke(). To fill it, call fill()
* To close the current path, call ClosePath()


   Demo: [http://codepen.io/nguyentb1412/pen/jqwNOp](http://codepen.io/nguyentb1412/pen/jqwNOp)

* Arcs are curves that positions of a circle (which is a full 360 degree arc )

| Path Operation | Description |
| :------| :-----------|
| arc(x, y, r, sA, eA, ac) | Adds an arcs to the current path that starts at x,y and has a radius of r, with a starting angle of sA, and ending angle of eA. The aC argument is true if the arc is anti-clock |
| arcTo(x1,y1,x2,y2,r) | Adds an arc to the current path that starts at the current pen position, has the given control points, and a radius of r |
| closePath() | Closes the current drawing path |

* Note: Angles are in radians, not degrees. To convert degrees to radians:

	var radians = (Math.Pi / 180) * degrees;
* Arcs examples (remember, 360 degrees = 2Pi radians)

	Stroke a 90 degrees arc, clockwise
	
	ctx.beginPath();
	
	ctx.arc(50, 150, 100, 1.5 * Math.Pi, 2*Math.Pi);
	
	ctx.stroke();
	
![image](https://s31.postimg.org/uk074la7v/image09.png)

     
Demo: [http://codepen.io/nguyentb1412/pen/EKXYVY](http://codepen.io/nguyentb1412/pen/EKXYVY)
	       		
###Bezier and quadratic curves 

* The canvas API allows for creating Bezier and quadratic curves
* Bezier curves are drawn starting from a context point to an end point using two control points to determine the curve
* Quadratic curves use a start point, one control point, and and end point

[http://www.webvietfree.com/threads/html5-ve-hinh-cung-va-duong-cong-bezier-trong-canvas.336/](http://www.webvietfree.com/threads/html5-ve-hinh-cung-va-duong-cong-bezier-trong-canvas.336/)

Quadratic curve

![image](https://s31.postimg.org/8i4uxfjej/image03.png)
	

Bezier curve

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://s31.postimg.org/sur3wiuij/image11.png)


| Path Operation | Description |
| :------| :-----------|
| bezierCurveTo(cx1, cy1, cx2, cy2, end1, end2) | Draw a Bezier curve starting at the current pen position using the two control points define by cx1, cy1 and ending at the point end1, end2 |
| quadraticCurveTo(cx, cy, x, y) | Draw a quadratic curve starting at the current pen position using the given control point cx, cy and ending at the end point defined by x,y |

Demo : [http://codepen.io/nguyentb1412/pen/yOXLYY](http://codepen.io/nguyentb1412/pen/yOXLYY)

###Rendering text 

* Drawing text is very similar to drawing any other path
* Text can be stroked or filled using the same fillStyle and strokeStyle as paths
* Text drawn on the canvas is not affected by any box model. It’s just a path
* Don’t use text on the canvas as a replacement for regular document text - that violates basic accessibility rules

| Text Operation | Description |
| :------| :-----------|
| font | Font setting to use. Anything you would normally put into a font CSS rule: family, size, weight, variant, etc. (default to 10px san-serif) |
| textAlign | “start” (default), “end”, “left”, “right”, “center” |
| textBaseline | “top”, “hanging”, “middle”, “alphabetic” (default), “ideographic”, “bottom” |
| fillText( text, x, y, [maxW])| Render the text string at x,y no wider than maxW |
| strokeText( text, x, y, [maxW])| Render the text (with no fill)  at x,y no wider than maxW |
| measureText(text) | Returns the dimension metrics of the string the current font settings |

Demo : [http://codepen.io/nguyentb1412/pen/qZjBRp](http://codepen.io/nguyentb1412/pen/qZjBRp)

##COMPLEX CANVAS DRAWING TECHNIQUES

###Creating shadows

* There are four shadow attributes for the drawing context
* All drawing operations on the canvas are affected by the shadow attributes. This includes paths, images, text, etc
* Shadows can be colored, offset in both the X and Y axes, and have a blur value

| Attributes | Description |
| :------| :-----------|
|shadowColor|The color to use for the shadow. Use any CSS color string. Defaults to transparent black|
|shadowOffsetX|Horizontal offset of the shadow (defaults to 0)|
|shadowBlur|Blur value of the shadow. Defaults to 0. Must be set to greater than 0 to have an effect|

Demo : [http://codepen.io/nguyentb1412/pen/EKXdVB](http://codepen.io/nguyentb1412/pen/EKXdVB)

###Drawing with patterns

* You can use not only colors, but also patterns and gradients as values in any drawing operation that has a fill or stroke property
* A pattern is created from an image, video, or another canvas element.
  + If the image is an animated image, the pattern uses the poster frame
  + For video, the current playback frame is used as the pattern
* Patterns can be set to repeat in both directions, repeat in only the X or Y dimensions, or not repeat at all

| Function | Description |
| :------| :-----------|
|createPattern(elem, repeat)|Creates a pattern from given element. The first argument must be an image, video, or canvas element. The repeat argument can be no-repeat, repeat, repeat-x, repeat-y |

Demo : [http://codepen.io/nguyentb1412/pen/ZWYyBy](http://codepen.io/nguyentb1412/pen/ZWYyBy)

###Drawing with gradients
* There are two kinds of gradients: linear and radial
* Gradients are created in two steps
  1. Use the appropriate function to create a gradient of the right type
  2. Add color stops to the gradient to create color transitions
After the gradient has been created, it can be used anywhere a stroke of fill style is used
![image](https://s31.postimg.org/lnpf0njln/image07.png =473x220)

| Function | Description |
| :------| :-----------|
|createLinearGradient(x0,y0,x1,y1)|Defines a linear gradient that start at point (x0,y0) and travels to (x1,y1)|
|createRadialGradient(x0,y0,r0,y1,r1)|Defines a radial gradient that begins with the circle whose center is at (x0,y0) and has radius r0, and travels to the circle whose center is at (x1,y1) and has radius r1|
|addColorStop(position, color)|Adds a color stop at the given position and has the given color, position is a floating point number from 0.0 to 1.0|

Demo: [http://codepen.io/nguyentb1412/pen/zqzmWY?editors=0010](http://codepen.io/nguyentb1412/pen/zqzmWY?editors=0010)

###Using clipping paths

* Think of clipping paths as masks-they define a region inside of which drawing takes place, and outside of which drawing has no effect
* Be default, the entire canvas is the current clipping path
* Any path can be defined as a clipping path
* The clip() function defines the current path as clipping path

| Path Function | Description |
| :------| :-----------|
|clip()|Creates a new clipping region by calculating the intersection of the current and the area described by the current path. The new clipping region replaces the current clipping region|

Demo : [http://codepen.io/nguyentb1412/pen/JXyPVR?editors=1010](http://codepen.io/nguyentb1412/pen/JXyPVR?editors=1010)

Examples
Shape : [http://codepen.io/nguyentb1412/pen/QNwgxp](http://codepen.io/nguyentb1412/pen/QNwgxp)

Clock:   [http://codepen.io/nguyentb1412/pen/KVEpEj](http://codepen.io/nguyentb1412/pen/KVEpEj)

Solar System : [http://codepen.io/nguyentb1412/pen/xVbKPr](http://codepen.io/nguyentb1412/pen/xVbKPr)

