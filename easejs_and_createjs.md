#EaseJS and CreateJS

##SETTING UP

###Getting to know EaselJS and CreateJS

What is EaselJS ?

* Group of JavaScript libraries
* Interactive HTML5 experiences
* Use individually or mix them up

What does EaselJS do ?

* Object handling and management
* Ease to access and nest object
* Access to input
* Familiar approach

Canvas vs EaselJS

* Canvas creates a drawing are
  + Pixels completely redrawn
  + Programmers manage objects
* EaselJS retained drawing
  + Easel creates an object list
  + Easel handles drawing to canvas
  
Lib: [https://code.createjs.com/easeljs-0.6.0.min.js](https://code.createjs.com/easeljs-0.6.0.min.js)

##DRAWING GRAPHICS

###Reviewing how Canvas draws and animates

Demo : [http://codepen.io/nguyentb1412/pen/grxGdG](http://codepen.io/nguyentb1412/pen/grxGdG)

###Comparing Canvas vs EaselJS

Demo : [http://codepen.io/nguyentb1412/pen/oxeGaL?editors=1010](http://codepen.io/nguyentb1412/pen/oxeGaL?editors=1010)
	
###Understanding basic fills and colors

EaselJS display object (shape) properties

| Properties | Details |
| :------| :-----------|
|alpha|A transparency. 0 is transparent, 1 is opaque|
|x,y|Position of the shape on the stage|
|regX, regY|Registration point around which transformation are performed|
|scaleX, scaleY|Stretch factor… 2 is twice as big, .5 is half|
|skewX, skewY|Skew the object in either x or y direction|

EaselJS graphic primitives

| Properties | Details |
| :------| :-----------|
|rectangles|rect(x, y, w, h) or fillRect(x, y, w, h)|
|Rounded rectangles|drawRoundRect( x, y, w, h, radius )|
|circle|drawCircle (x, y, radius)|
|ellipse|drawEllipse( x, y, w, h)|
|Stars & starbursts|drawPolyStar( x, y, radius, sides, pointSize, angle )|

Fills

| type | method |
| :------| :-----------|
|Solid fill|beginFill(color)|
|Linear gradient|beginLinearGradientFill( colors, ratios, x0, y0, x1, y1) <br> Colors =[color1, color2],ratios = [0-1, 0-1] <br> Origin x/y, destination x/y|
|Radial gradient|beginRadialGradientFill ( colors, ratios, x0, y0,  r0, x1, y1, r1) <br> Colors = [color1, color2], ratios = [0-1, 0-1] <br> Origin x/y, destination x/y|

Demo : [http://codepen.io/nguyentb1412/pen/dMzwVw](http://codepen.io/nguyentb1412/pen/dMzwVw)

###Defining lines and strokes
Stoke styles

| type | method |
| :------| :-----------|
|solid fill|beginFill(color)|
|linear gradient|beginLinearGradientFill( colors, ratios, x0, y0, x1, y1) <br> Colors = [color1, color2], ratios = [0-1, 0-1] <br> Origin x/y, destination x/y|
|radial gradient|beginRadialGradientFill ( colors, ratios, x0, y0,  r0, x1, y1, r1)<br>Colors = [color1, color2], ratios = [0-1, 0-1]<br>Origin x/y, destination x/y|

| primitive | method |
| :------| :-----------|
|thickness|Width of the stroke in pixels|
|caps (optional)|Caps at the end of open line segments:<br>“butt”-0 (default), “round”-1, or “square”-2|
|joints (optional)|Shape where two lines meet: <br>“miter”-0 (default), “round”-1, or “bevel”-2|
|miter (optional)|If joint is set up to miter, then this is a value that specifies when miter will be clipped|

Additional LineTo methods

| Properties | details |
| :------| :-----------|
|Quadratic curves|quadraticCurveTo(cpx, cpy, x, y)|
|arcs|arcTo(x1, y1, x2, y2, radius)|
|Bezier curves|bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)|

Demo : [http://codepen.io/nguyentb1412/pen/yOoGPb](http://codepen.io/nguyentb1412/pen/yOoGPb)

###Drawing with other graphic primitives

Rectangles

| type | method |
| :------| :-----------|
|rectangles|rect(x, y, w, h);<br> X and y coordinates, plus width and height can also be called as drawRect() to match canvas. You can also use drawRect();|
|Round rectangles|drawRoundRect(x, y, w, h, radius)<br>Rectangles with equal corner radius<br>x/y coordinates, width, height and corner radius|
|Complex round rectangles|drawRoundRectComplex(x, y, w, h, radiusTL, radiusTR, radiusBR, radiusBL)<br>Like round rect, but lets you specify top left, top right, bottom right and bottom left radius separately|

Ellipses and arcs

| type | method |
| :------| :-----------|
|circle|drawCircle(x, y, radius)<br>X and y coordinates, plus distance from center|
|ellipses|drawEllipse(x, y, w, h)<br>X and y coordinates, plus width and height|
|arcs|arc(x, y, radius, startAngle, endAngle, anticlockwise) <br>Draws part of a complete circle, x/y origin, distance from center, start and end angles in radians, and an optional direction of the arc|


Polygons and stars
	
drawPolyStar(x, y, radius, sides, pointSize, angle)

| type | method |
| :------| :-----------|
|origin(x,y)|Vertical and horizontal position on the stage|
|radius|Distance from origin|
|sides|Number of points of stars or sides of polygon|
|pointSize|Describes a star’s pointiness as a number from 0-1 <br>0 draws polygons, 1 draws spikes|
|angle|Angle of the first point or corner of the shape <br>-90 will draw it pointing up|

Demo: [http://codepen.io/nguyentb1412/pen/xVLmBm](http://codepen.io/nguyentb1412/pen/xVLmBm)

###Chaining and compacting drawing commands

Common graphic shortcuts

| method | shortcut |
| :------| :-----------|
|origin(x,y)|bf|
|radius|bs|
|sides|f|
|pointSize|lf|
|angle|ls|
|beginStroke|s|
|drawPolyStar|dp|
|drawRect|r or dr|
|lineTo|lt|
|moveTo|mt|

Parameters: 0 - default or first, 1  - Second,2 -Third

Demo : [http://codepen.io/nguyentb1412/pen/qZXgEG](http://codepen.io/nguyentb1412/pen/qZXgEG)

##USING DISPLAY OBJECTS

###Transforming and animating shapes

Demo : [http://codepen.io/nguyentb1412/pen/ONxMry](http://codepen.io/nguyentb1412/pen/ONxMry)

###Working with text

Demo : [http://codepen.io/nguyentb1412/pen/RaLrvb](http://codepen.io/nguyentb1412/pen/RaLrvb)

###Importing bitmaps and vector graphics

Demo : [http://codepen.io/nguyentb1412/pen/oxGbRO](http://codepen.io/nguyentb1412/pen/oxGbRO)

###Animating bitmaps with math

Demo : [http://codepen.io/nguyentb1412/pen/oxGbRO](http://codepen.io/nguyentb1412/pen/oxGbRO)

###Using sprite sheets for animation

Demo : [http://codepen.io/nguyentb1412/pen/oxGbRO](http://codepen.io/nguyentb1412/pen/oxGbRO)

##HANDLING INPUT

###Tracking mouse movement

Demo : [http://codepen.io/nguyentb1412/pen/BKwLBe](http://codepen.io/nguyentb1412/pen/BKwLBe)

###Handling mouse events

Demo : [http://codepen.io/nguyentb1412/pen/dMVpye](http://codepen.io/nguyentb1412/pen/dMVpye)

##EXAMPLE


1) TweenJS : [http://codepen.io/nguyentb1412/pen/ZWprdo](http://codepen.io/nguyentb1412/pen/ZWprdo)

2) TweenJS demo 2: [http://codepen.io/nguyentb1412/pen/MyYOQE](http://codepen.io/nguyentb1412/pen/MyYOQE)

3) Ball : [http://codepen.io/nguyentb1412/pen/XdJevg](http://codepen.io/nguyentb1412/pen/XdJevg)

4) Man blink : [http://codepen.io/nguyentb1412/pen/PNqYBy](http://codepen.io/nguyentb1412/pen/PNqYBy)

5) Man dying : [http://codepen.io/nguyentb1412/pen/GZJKOd](http://codepen.io/nguyentb1412/pen/GZJKOd)

6) Man moving: [http://codepen.io/nguyentb1412/pen/WwveKB](http://codepen.io/nguyentb1412/pen/WwveKB)

6) Robot 1: [http://codepen.io/nguyentb1412/pen/qZEVzw](http://codepen.io/nguyentb1412/pen/qZEVzw)

7) Robot 2: [http://codepen.io/nguyentb1412/pen/MyYrbq](http://codepen.io/nguyentb1412/pen/MyYrbq)

8) Robot 3: [http://codepen.io/nguyentb1412/pen/vGEpWX](http://codepen.io/nguyentb1412/pen/vGEpWX)







