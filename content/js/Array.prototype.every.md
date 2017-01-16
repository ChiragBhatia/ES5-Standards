+++
date = "2016-11-16T00:45:05+05:30"
title = "Array.prototype.every()"
next = "/js/Array.prototype.filter"
prev = "/js/Array.isArray"
toc = true
weight = 2

+++

The `every()` method tests whether all the elements in an array passes the test implemented by the provided function.

<h3>Need for this</h3>
Array.prototype.every() provides a clean method for developers to iterate through an array and check if all items in the array pass a certain test criteria without having to loop through the Array manually using a for loop.

<h3>Advantages</h3>
<ol>
	<li>Array.prototype.every() provides a clean way for checking if all array items pass the test criteria without having to iterate through the array using for loops.</li>
	<li>A polyfill is available for Array.prototype.every() for older browsers where the method is not supported by the browser.</li>
</ol>

<h3>Working Example</h3>

	function isEven(element, index, array) {
	  return (element % 2 === 0);
	}

	[50, 37, 49, 94, 4].every(isEven);   // false
	[40, 32, 16, 128, 78].every(isEven); // true

<h3>References</h3>
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/every
<br>
https://docs.webplatform.org/wiki/javascript/Array/every
<br>
https://www.tutorialspoint.com/javascript/array_every.htm
