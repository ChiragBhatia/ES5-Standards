+++
date = "2016-11-03T00:45:05+05:30"
title = "Object.create()"

+++

The Object.create() method creates a new object with the specified prototype object and properties.

<h3>Need for this</h3>
Object.create() is very similar to the `new` keyword. Both create a new instance of the Object type specified. The only difference is that Object.create() does not execute the constructor unless specified to do so.

<h3>Disadvantages of this tag</h3>
<ol>
  <li>Object.create does not call the constructor function unless specifically asked to do so.</li>
  <li>A limited variant of Object.create is available as a polyfill for older browsers which do not have support for the same.</li>
</ol>

<h3>Advantages of this tag</h3>
<ol>
  <li>Object.create allows you to initialize properties of the created object using the second argument of its function, with an object literal using a syntax similar to the one used by the Object.defineProperties and Object.defineProperty methods.</li>
  <li>It lets you set the property attributes during initialization (enumerable, writable, or configurable), which can be really useful.</li>
</ol>

<h3>Working Example</h3>

		// Shape - superclass
		function Shape() {
		  this.x = 0;
		  this.y = 0;
		}

		// superclass method
		Shape.prototype.move = function(x, y) {
		  this.x += x;
		  this.y += y;
		  console.info('Shape moved.');
		};

		// Rectangle - subclass
		function Rectangle() {
		  Shape.call(this); // call super constructor.
		}

		// subclass extends superclass
		Rectangle.prototype = Object.create(Shape.prototype);
		Rectangle.prototype.constructor = Rectangle;

		var rect = new Rectangle();

		console.log('Is rect an instance of Rectangle?', rect instanceof Rectangle);// true
		console.log('Is rect an instance of Shape?', rect instanceof Shape);// true
		rect.move(1, 1); // Outputs, 'Shape moved.'

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/create
<br>
http://stackoverflow.com/a/2709811/976897
<br>
http://speakingjs.com/es5/ch17.html