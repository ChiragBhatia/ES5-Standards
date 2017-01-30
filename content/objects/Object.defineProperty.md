+++
date = "2016-11-02T00:45:05+05:30"
title = "Object.defineProperty()"
next = "/objects/Object.freeze"
prev = "/objects/Object.defineProperties"
toc = true
weight = 11

+++

The Object.defineProperty() method defines a new property directly on an object, or modifies an existing property on an object, and returns the object.

<h3>Need for this</h3>
This method allows precise addition to or modification of a property on an object. Normal property addition through assignment creates properties which show up during property enumeration (for...in loop or Object.keys method), whose values may be changed, and which may be deleted. This method allows these extra details to be changed from their defaults. By default, values added using Object.defineProperty() are immutable.

<h3>Advantages</h3>
<ol>
  <li>Object.defineProperty allows the developer to modify data properties of an object. e.g. to make an Object property read-only.</li>
  <li>Object.defineProperty allows the developer to override the default browser properties which are otherwise not overridable. This can be useful during unit testing.</li>
</ol>

<h3>Working Example</h3>

		// Create a user-defined object.
		var obj = {};

		// Add a read-only data property to the object.
		Object.defineProperty(obj, "newDataProperty", {
		    value: 101,
		    writable: false,
		    enumerable: true,
		    configurable: true
		});

		console.log(obj.newDataProperty);	// 101
		obj.newDataProperty = 202;
		console.log(obj.newDataProperty);	// 101

		// Change read-only property to writable
		Object.defineProperty(obj, "newDataProperty", {
			writable: true
		});

		console.log(obj.newDataProperty);	// 101
		obj.newDataProperty = 202;
		console.log(obj.newDataProperty);	// 202

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty
<br>
https://msdn.microsoft.com/en-us/library/dd548687(v=vs.94).aspx
<br>
https://davidwalsh.name/defineproperty
