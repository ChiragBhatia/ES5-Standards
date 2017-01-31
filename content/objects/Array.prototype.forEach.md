+++
date = "2016-11-16T00:45:05+05:30"
title = "Array.prototype.forEach()"
next = "/objects/Array.prototype.indexOf"
prev = "/objects/Array.prototype.filter"
toc = true
weight = 4

+++

The forEach() method executes a provided function once for each array element

<h3>Need for this</h3>
forEach() executes the provided callback once for each element present in the array in ascending order. It is not invoked for index properties that have been deleted or are uninitialized (i.e. on sparse arrays).

callback is invoked with three arguments:

the element value
the element index
the array being traversed

If a thisArg parameter is provided to forEach(), it will be passed to callback when invoked, for use as its this value.  Otherwise, the value undefined will be passed for use as its this value. The this value ultimately observable by callback is determined according to the usual rules for determining the this seen by a function.

The range of elements processed by forEach() is set before the first invocation of callback. Elements that are appended to the array after the call to forEach() begins will not be visited by callback. If the values of existing elements of the array are changed, the value passed to callback will be the value at the time forEach() visits them; elements that are deleted before being visited are not visited. If elements that are already visited are removed (e.g. using shift()) during the iteration, later elements will be skipped - see example below.

forEach() executes the callback function once for each array element; unlike map() or reduce() it always returns the value undefined and is not chainable. The typical use case is to execute side effects at the end of a chain.

<h3>Disadvantage</h3>
<ol>
  <li>The forEach method calls the callbackfn function one time for each element present in the array, in ascending index order. The callback function is not called for missing elements of the array.</li>
  <li>The forEach method does not directly modify the original array, but the callback function might modify it.</li>

</ol>

<h3>Advantages</h3>
<ol>
	<li>In addition to array objects, the forEach method can be used by any object that has a length property and that has numerically indexed property names.</li>
</ol>

<h3>Working Example</h3>

	function logArrayElements(element, index, array) {
  	console.log('a[' + index + '] = ' + element);
	}

	// Notice that index 2 is skipped since there is no item at
	// that position in the array.
	[2, 5, , 9].forEach(logArrayElements);
	// logs:
	// a[0] = 2
	// a[1] = 5
	// a[3] = 9

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach
<br>
https://msdn.microsoft.com/en-us/library/ff679980(v=vs.94).aspx
<br>
https://www.tutorialspoint.com/javascript/array_filter.htm
