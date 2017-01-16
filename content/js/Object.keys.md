+++
date = "2016-11-02T00:45:05+05:30"
title = "Object.keys()"
next = "/js/Object.preventExtensions"
prev = "/js/Object.isSealed"
toc = true
weight = 17

+++

Object.keys() returns an array whose elements are strings corresponding to the enumerable properties found directly upon object. The ordering of the properties is the same as that given by looping over the properties of the object manually.

<h3>Need for this</h3>
The Object.keys() method returns an array of a given object's own enumerable properties, in the same order as that provided by a for...in loop (the difference being that a for-in loop enumerates properties in the prototype chain as well). This can be useful when iterating through the keys and values of a JavaScript object.

<h3>Disadvantage</h3>
<ol>
  <li>Object.keys might behave slightly differently in different browser versions due to minor changes in ES6. In ES5, if the argument to this method is not an object (a primitive, like string), then it will cause a TypeError. In ES6, a non-object argument will be coerced to an object.</li>
</ol>

<h3>Advantages</h3>
<ol>
  <li>for-in loops over the object's own enumerable properties and the enumerable properties of its prototype (and its prototype, etc.). Object.keys only lists the object's own enumerable properties.</li>
	<li>Working polyfills are available for older environments if the developer is required to support older browser versions which do not have support for Object.keys.</li>
</ol>

<h3>Working Example</h3>

		var arr = ['a', 'b', 'c'];
		console.log(Object.keys(arr)); // console: ['0', '1', '2']

		// array like object
		var an_obj = { 100: 'a', 2: 'b', 7: 'c' };
		console.log(Object.keys(an_obj)); // console: ['2', '7', '100']

<h3>References</h3>
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/keys
<br>
http://stackoverflow.com/questions/29004314/why-are-object-keys-and-for-in-different
