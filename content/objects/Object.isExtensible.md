+++
date = "2016-11-02T00:45:05+05:30"
title = "Object.isExtensible()"
next = "/objects/Object.isFrozen"
prev = "/objects/Object.getPrototypeOf"
toc = true
weight = 25

+++

The Object.isExtensible() method determines if an object is extensible (whether it can have new properties added to it).

<h3>Need for this</h3>
Objects are extensible by default: they can have new properties added to them, and (in engines that support __proto__) their __proto__ property can be modified. An object can be marked as non-extensible using `Object.preventExtensions()`, `Object.seal()`, or `Object.freeze()`. `Object.isExtensible()` helps find out if an object is extensible.

<h3>Advantage</h3>
<ol>
  <li>Object.isExtensible is a single function that can check whether an object is sealed, frozen or is marked with Object.preventExtension.</li>
</ol>

<h3>Working Example</h3>

		// New objects are extensible.
		var empty = {};
		Object.isExtensible(empty); // === true

		// ...but that can be changed.
		Object.preventExtensions(empty);
		Object.isExtensible(empty); // === false

		// Sealed objects are by definition non-extensible.
		var sealed = Object.seal({});
		Object.isExtensible(sealed); // === false

		// Frozen objects are also by definition non-extensible.
		var frozen = Object.freeze({});
		Object.isExtensible(frozen); // === false

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isExtensible
<br>
https://msdn.microsoft.com/vi-vn/library/ff806188(v=vs.94).aspx
