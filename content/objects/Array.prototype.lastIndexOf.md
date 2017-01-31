+++
date = "2016-11-16T00:45:05+05:30"
title = "Array.prototype.lastIndexOf"
next = "/objects/Array.prototype.map"
prev = "/objects/Array.prototype.indexOf"
toc = true
weight = 6

+++

The index of the last occurrence of searchElement in the array, or -1 if searchElement is not found.

<h3>Need for this</h3>
The lastIndexOf method searches an array for a specified value. The method returns the index of the first occurrence, or -1 if the specified value is not found.

<h3>Disadvantage</h3>
<ol>
  <li>The search occurs in descending index order (last member first). To search in ascending order, use the indexOf Method (Array) (JavaScript).</li>
</ol>

<h3>Advantages</h3>
<ol>
	<li>The array elements are compared to the searchElement value by strict equality, similar to the comparison made by the === operator. For more information, see Comparison Operators (JavaScript).</li>
	<li>The optional fromIndex argument specifies the array index at which to begin the search. If fromIndex is greater than or equal to the array length, the whole array is searched. If fromIndex is negative, the search starts at the array length plus fromIndex. If the computed index is less than 0, -1 is returned.</li>
</ol>

<h3>Working Example</h3>

// Create an array.
var ar = ["ab", "cd", "ef", "ab", "cd"];

// Determine the first location, in descending order, of "cd".
document.write(ar.lastIndexOf("cd") + "<br/>");

// Output: 4

// Find "cd" in descending order, starting at index 2.
document.write(ar.lastIndexOf("cd", 2) + "<br/>");

// Output: 1

// Search for "gh" (which is not found).
document.write(ar.lastIndexOf("gh")+ "<br/>");

// Output: -1

// Find "ab" with a fromIndex argument of -3.
// The search in descending order starts at index 3,
// which is the array length minus 2.
document.write(ar.lastIndexOf("ab", -3) + "<br/>");
// Output: 0

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf
<br>
https://msdn.microsoft.com/en-us/library/ff679972(v=VS.94).aspx
<br>
https://github.com/FreeCodeCamp/FreeCodeCamp/wiki/JS-Array-Prototype-LastIndexOf
