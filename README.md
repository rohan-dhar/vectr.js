<h1>vectr.js</h1>
A simple, yet powerful JavaScript library to work with 2D vectors. It provides a simple API to perform complicated tasks. Vectr.js has no dependancies can be used everywhere: in the browser as well as in Node.js.

<h2>Usage</h2> 
To use Vectr.js, you need to include the source file "vectr.js" or the minified source file "vectr.min.js".

<h2>API</h2>


<h3>The constructor</h3>

<ul>
<li>
<h4><code>new Vectr()</code></h4>
Creates a new Vectr object based on the parameters provided.

<h5>Paramerers</h5>
<ol>
<li>
<b><code>new Vectr(x, y)</code></b>
<ul>
<li><b>x</b>: Optional - The x component of the vector. Should be a number.<br>Default: 0</li>
<li><b>y</b>: Optional - The y component of the vector. <br>Default: 0</li>
</ul>
</li>

<li>
<code>new Vectr(object)</code>
<b>object</b>: Optional - Contains the x and y components of the vector.
<ul>
<li><code>object.x</code>: Optional - The x component of the vector. Should be a number. <br>Default: 0</li>
<li><code>object.y</code>: Optional - The y component of the vector. Should be a number. <br>Default: 0</li>
</ul>
</li>

<li>
<code>new Vectr(object)</code>
<b>object</b>: Optional - Contains the angle (from the x-axis) and the magnitude of the vector.
<ul>
<li><code>object.magnitude</code>: Optional - The magnitude of the vector. Should be a number. <br>Default: 0</li>
<li><code>object.angle</code>: Optional - The angle of the vector <b>in radian</b>. Should be a number. <br>Default: 0</li>
<li><code>object.angleDeg</code>: Optional - The angle of the vector <b>in degree</b>. Should be a number. <br>Default: 0</li>		
</ul>
<b>NOTE: If both angle and angleDeg are provided, the value of angleDeg will be used.</b>
</li>
</ol>
<h5>Return Value</h5>
Returns a new Vectr object.

<h5>Example</h5>
<pre>
<code>
var vec1 = new Vectr(10, 10); // Creates a new Vector with x = 10 and y = 10 
var vec2 = new Vectr({x: 10, y: 10}); // Creates a new Vector with x = 10 and y = 10 
var vec3 = new Vectr({magnitude: 10, angleDeg: 45}); // Creates a new Vector with a magnitude of 10 and an angle of 45 degree from the X axis
</code>
</pre>
</li>
</ul>

<h3>Helper functions</h3>
<ul>
<li>
<h4><code>Vectr.toRadian()</code></h4>
Converts and angle in degree to radian

<h5>Parameters</h5>
<code>Vectr.toRadian(deg)</code>
<code>deg</code>: Optional - The angle in degree to convert to radian. Should be a number. <br> Default: 1

<h5>Examples</h5>
<pre>
<code>
var rad = Vectr.toRadian(45); // deg contains the value 0.785398 (pi/4)
</code>
</pre>
</li>


<li>
<h4><code>Vectr.toDegree()</code></h4>
Converts and angle in degree to radian

<h5>Parameters</h5>
<code>Vectr.toDegree(radian)</code>
<code>radian</code>: Optional - The angle in radian to convert to degree. Should be a number. <br> Default: 1

<h5>Examples</h5>
<pre>
<code>
var deg = Vectr.toDegree(Math.PI/4); // deg contains the value 45
</code>

</li>

</ul>

<h3>Methods to represent a Vectr in different forms.</h3>

<ul>
<li>
<h4>.getAs()</h4>
<h5>Parameters</h5>
<code>Vectr.getAs(type, angleAndMag, deg)</code>
<ul> 
<li>
<code>type</code>: Optional - A string specify the type in which the vectr is to be returned in. Possible values are : 
<ul>
<li><code>"string"</code>: To get the vector as a string.</li>
<li><code>"array"</code>: To get the vector as an array. The first element is the x component and the second element is the y component.</li>
<li><code>"object"</code>: To get the vector as an object. It contains <code>x</code> and <code>y</code> properties which are the x and y components respectively.</li>
</ul>
Default: "string"
</li>
<li>
<code>angleAndMag</code>: Optional - A boolean specify if the Vectr should be returned as angle and magnitude instead of x and y components. If type is "array", the first (0th) element of the array is the angle and the second (1st) element is the magnitude. If the type is "object", the returned object has the properties <code>angle</code> and <code>magnitude</code> containing the angle and the magnitude respecticely.<br>
Default: false
</li>
<li>
<code>deg</code>: Optional - A boolean specify if the angle should be returned in degrees instead of radians. Only needed if angleAndMag is true.<br>
Default: true
</li>
</ul>
<h5>Return value</h5>
Returns either a string or an array or an object depending on the supplied parameters.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(10, 20);
var str = v.getAs("string"); // str contains the value "x: 10, y = 20"
var arr = v.getAs("array");  // arr contains an array [10, 20]
var obj = v.getAs("object"); // obj contains an array {x: 10, y: 20}			
</code>
</pre>
</li>

<li>
<h4><code>.magnitude()</code></h4>
Returns the magnitude of the Vectr.

<h5>Parameters</h5>
<code>.magnitude()</code> does not accept any parameters.

<h5>Return values</h5>
A number which is the magnitude of the Vectr.

<h5>Examples</h5>
<pre>
<code>		
var v = new Vectr(3, 4);
var mag = v.magnitude(); //mag contains the value 5
</code>
</pre>
</li>

<li>
<h4><code></code></h4>

<h5>Parameters</h5>
<code></code>
<ul>
<li>

</li>
</ul>

<h5>Return values</h5>

<h5>Examples</h5>
<pre>
<code>

</code>

</li>

<li>
<h4><code>.angle()</code></h4>
Returns the angle of the Vectr from the X axis.

<h5>Parameters</h5>
<code>.angle(deg)</code>
<ul>
<li>
<code>deg</code>: Optional - A Boolean specifying if the angle returned is in degree instead of radian. <br> Default: false
</li>
</ul>

<h5>Return values</h5>
Returns a number specifying the angle of the Vectr from the X axis.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(10, 10);
var angle = v.angle();        //angle contains the value 0.785398 (pi/4)
var angleDeg = v.angle(true); // angle contains the value 45
</code>
</pre>
</li>

<li>
<h4><code>.direction()</code></h4>
An alias for <code>.angle()</code>
</li></li>



<li>
<h4><code>.verticalAngle()</code></h4>
Returns the angle of the Vectr from the Y axis.

<h5>Parameters</h5>
<code>.verticalAngle(deg)</code>
<ul>
<li>
<code>deg</code>: Optional - A Boolean specifying if the angle returned is in degree instead of radian. <br> Default: false
</li>
</ul>

<h5>Return values</h5>
Returns a number specifying the angle of the Vectr from the Y axis.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(10, 10);
var angle = v.verticalAngle();        //angle contains the value 0.785398 (pi/4)
var angleDeg = v.verticalAngle(true); // angle contains the value 45
</code>
</pre>
</li>

</ul>

<h3>Methods to perform arithmetic operations on one or more Vectrs</h3>

<ul>
<li>
<h4><code>.add()</code></h4>
Adds a number or another Vectr to the Vectr and returns the Vectr. Is chainable.

<h5>Parameters</h5>
<code>.add(n, new)</code>
<ul>
<li>
<code>n</code>: Required - A number or a Vectr. If the <code>n</code> is a Vectr, x component of <code>n</code> is added to the x of the Vectr and the y component of <code>n</code> is added to the y of the Vectr. If <code>n</code> is a number, it is added to both the x and y components of the Vectr.
</li>
<li>
<code>new</code>: Optional - A boolean specify if the add operation should be performed on a new Vectr without affecting the value of the current Vectr. If <code>new</code> is true, a brand new Vectr is returned, else the same Vectr is returned.
</li>
</ul>

<h5>Return values</h5>
Returns a Vectr if <code>n</code> is a number or a Vectr. If <code>n</code> is not a valid number or Vectr, <code>.add()</code> returns <code>false</code>.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(10, 20);
v.add(10); //v is now (x: 20, y: 30)
var v2 = v.add(10, true); //v is still (x: 20, y: 30) but v2 is (x: 30, y: 40), because the new parameter was true
v2.add(v); // v2 is now (x: 50, y: 70);
</code>
</pre>
</li>

<li>
<h4><code>.addX()</code></h4>
Adds a number or another Vectr's x component to the x component of the Vectr and returns the Vectr. Is chainable.

<h5>Parameters</h5>
<code>.add(n, new)</code>
<ul>
<li>
<code>n</code>: Required - A number or a Vectr. If the <code>n</code> is a Vectr, x component of <code>n</code> is added to the x of the Vectr but the y of the Vectr is unchanged. If <code>n</code> is a number, it is added only to the x component of the Vectr.
</li>
<li>
<code>new</code>: Optional - A boolean specify if the add operation should be performed on a new Vectr without affecting the value of the current Vectr. If <code>new</code> is true, a brand new Vectr is returned, else the same Vectr is returned.
</li>
</ul>

<h5>Return values</h5>
Returns a Vectr if <code>n</code> is a number or a Vectr. If <code>n</code> is not a valid number or Vectr, <code>.add()</code> returns <code>false</code>.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(10, 20);
v.addX(10); //v is now (x: 20, y: 20)
v.addX(v); //v is now (x: 40, y: 20)
</code>
</pre>
</li>

<li>
<h4><code>.addY()</code></h4>
Adds a number or another Vectr's y component to the y component of the Vectr and returns the Vectr. Is chainable.

<h5>Parameters</h5>
<code>.add(n, new)</code>
<ul>
<li>
<code>n</code>: Required - A number or a Vectr. If the <code>n</code> is a Vectr, y component of <code>n</code> is added to the x of the Vectr but the y of the Vectr is unchanged. If <code>n</code> is a number, it is added only to the y component of the Vectr.
</li>
<li>
<code>new</code>: Optional - A boolean specify if the add operation should be performed on a new Vectr without affecting the value of the current Vectr. If <code>new</code> is true, a brand new Vectr is returned, else the same Vectr is returned.
</li>
</ul>

<h5>Return values</h5>
Returns a Vectr if <code>n</code> is a number or a Vectr. If <code>n</code> is not a valid number or Vectr, <code>.add()</code> returns <code>false</code>.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(10, 20);
v.addY(10); //v is now (x: 10, y: 30)
v.addY(v); //v is now (x: 10, y: 60)
</code>
</pre>
</li>

<li>
<h4><code>.subtract()</code></h4>
subtracts a number or another Vectr to the Vectr and returns the Vectr. Is chainable.

<h5>Parameters</h5>
<code>.subtract(n, new)</code>
<ul>
<li>
<code>n</code>: Required - A number or a Vectr. If the <code>n</code> is a Vectr, x component of <code>n</code> is subtracted to the x of the Vectr and the y component of <code>n</code> is subtracted to the y of the Vectr. If <code>n</code> is a number, it is subtracted to both the x and y components of the Vectr.
</li>
<li>
<code>new</code>: Optional - A boolean specify if the subtract operation should be performed on a new Vectr without affecting the value of the current Vectr. If <code>new</code> is true, a brand new Vectr is returned, else the same Vectr is returned.
</li>
</ul>

<h5>Return values</h5>
Returns a Vectr if <code>n</code> is a number or a Vectr. If <code>n</code> is not a valid number or Vectr, <code>.subtract()</code> returns <code>false</code>.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(10, 20);
v.subtract(10); //v is now (x: 0, y: 10)
var v2 = v.subtract(10, true); //v is still (x: 0, y: 10) but v2 is (x: -10, y: 0), because the new parameter was true
v2.subtract(v); // v2 is now (x: -10, y: -10);
</code>
</pre>
</li>

<li>
<h4><code>.subtractX()</code></h4>
subtracts a number or another Vectr's x component to the x component of the Vectr and returns the Vectr. Is chainable.

<h5>Parameters</h5>
<code>.subtract(n, new)</code>
<ul>
<li>
<code>n</code>: Required - A number or a Vectr. If the <code>n</code> is a Vectr, x component of <code>n</code> is subtracted to the x of the Vectr but the y of the Vectr is unchanged. If <code>n</code> is a number, it is subtracted only to the x component of the Vectr.
</li>
<li>
<code>new</code>: Optional - A boolean specify if the subtract operation should be performed on a new Vectr without affecting the value of the current Vectr. If <code>new</code> is true, a brand new Vectr is returned, else the same Vectr is returned.
</li>
</ul>

<h5>Return values</h5>
Returns a Vectr if <code>n</code> is a number or a Vectr. If <code>n</code> is not a valid number or Vectr, <code>.subtract()</code> returns <code>false</code>.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(20, 20);
v.subtractX(10); //v is now (x: 10, y: 20)
v.subtractX(v); //v is now (x: 0, y: 20)
</code>
</pre>
</li>

<li>
<h4><code>.subtractY()</code></h4>
subtracts a number or another Vectr's y component to the y component of the Vectr and returns the Vectr. Is chainable.

<h5>Parameters</h5>
<code>.subtract(n, new)</code>
<ul>
<li>
<code>n</code>: Required - A number or a Vectr. If the <code>n</code> is a Vectr, y component of <code>n</code> is subtracted to the x of the Vectr but the y of the Vectr is unchanged. If <code>n</code> is a number, it is subtracted only to the y component of the Vectr.
</li>
<li>
<code>new</code>: Optional - A boolean specify if the subtract operation should be performed on a new Vectr without affecting the value of the current Vectr. If <code>new</code> is true, a brand new Vectr is returned, else the same Vectr is returned.
</li>
</ul>

<h5>Return values</h5>
Returns a Vectr if <code>n</code> is a number or a Vectr. If <code>n</code> is not a valid number or Vectr, <code>.subtract()</code> returns <code>false</code>.

<h5>Examples</h5>
<pre>
<code>
var v = new Vectr(10, 20);
v.subtractY(10); //v is now (x: 10, y: 10)
v.subtractY(v); //v is now (x: 10, y: 0)
</code>
</pre>
</li>


</ul>