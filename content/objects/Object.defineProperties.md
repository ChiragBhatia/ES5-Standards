+++
date = "2016-11-02T00:45:05+05:30"
title = "Object.defineProperties()"
next = "/objects/Object.defineProperty"
prev = "/objects/Object.create"
toc = true
weight = 19

+++

The Object.defineProperties() method defines new or modifies existing properties directly on an object, returning the object.

<h3>Need for this</h3>
Object.defineProperties works similar to `Object.defineProperty` in the sense that both are used to create or modify properties of an object. The only difference is that Object.defineProperties allows the developer to work on multiple properties in a single line of code as opposed to Object.defineProperty which can only handle one property at a time.

<h3>Advantage</h3>
<ol>
  <li>Object.defineProperties allows the developer to work on multiple properties of an object in a single line of code.</li>
</ol>

<h3>Working Example</h3>

		var obj = {};
		Object.defineProperties(obj, {
		  "property1": {
		    value: true,
		    writable: true
		  },
		  "property2": {
		    value: "Hello",
		    writable: false
		  }
		  // etc. etc.
		});

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperties
<br>
https://msdn.microsoft.com/en-us/library/ff800817(v=vs.94).aspx
