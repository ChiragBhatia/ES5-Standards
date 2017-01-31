+++
date = "2016-11-16T00:45:05+05:30"
title = "Array.prototype.map()"
next = "/objects/Array.prototype.reduce"
prev = "/objects/Array.prototype.lastIndexOf"
toc = true
weight = 7

+++

The Array.prototype.map() method creates a new array with the results of calling a provided function on every element in this array.

<h3>Need for this</h3>
map calls a provided callback function once for each element in an array, in order, and constructs a new array from the results. callback is invoked only for indexes of the array which have assigned values, including undefined. It is not called for missing elements of the array (that is, indexes that have never been set, which have been deleted or which have never been assigned a value).

callback is invoked with three arguments: the value of the element, the index of the element, and the Array object being traversed.

If a thisArg parameter is provided to map, it will be passed to callback when invoked, for use as its this value. Otherwise, the value undefined will be passed for use as its this value. The this value ultimately observable by callback is determined according to the usual rules for determining the this seen by a function.

<h3>Disadvantage</h3>
<ol>
  <li>Array.prototype.map() method does not mutate the array on which it is called (although callback, if invoked, may do so).</li>
  <li>The range of elements processed by map is set before the first invocation of callback. Elements which are appended to the array after the call to map begins will not be visited by callback. If existing elements of the array are changed, their value as passed to callback will be the value at the time map visits them. Elements that are deleted after the call to map begins and before being visited are not visited.</li>
</ol>

<h3>Advantages</h3>
<ol>
	<li>Due to the algorithm defined in the specification if the array which map was called upon is sparse, resulting array will also be sparse keeping same indices blank.</li>
	<li>Using map to reformat objects in an array</li>
</ol>

<h3>Working Example</h3>

var numbers = [1, 5, 10, 15];
var roots = numbers.map(function(x) {
   return x * 2;
});
// roots is now [2, 10, 20, 30]
// numbers is still [1, 5, 10, 15]

var numbers = [1, 4, 9];
var roots = numbers.map(Math.sqrt);
// roots is now [1, 2, 3]
// numbers is still [1, 4, 9]

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map
<br>
https://msdn.microsoft.com/en-us/library/ff679973(v=vs.94).aspx
<br>
https://www.tutorialspoint.com/javascript/array_map.htm
