+++
date = "2016-11-11T00:45:05+05:30"
title = "Array.prototype.reduce()"
next = "/js/Array.prototype.reduceRight"
prev = "/js/Array.prototype.filter"
toc = true
weight = 4

+++

The *reduce()* method applies a function against an accumulator and each value of the array (from left-to-right) to reduce it to a single value.

<h3>Need for this</h3>
Calls the specified callback function for all the elements in an array. The return value of the callback function is the accumulated result, and is provided as an argument in the next call to the callback function.

    arr.reduce(callback[, initialValue])

reduce executes the callback function once for each element present in the array, excluding holes in the array, receiving four arguments:

<ul>
  <li>previousValue</li>
  <li>currentValue</li>
  <li>currentIndex</li>
  <li>array</li>
</ul>

<h3>Advantages</h3>
<ol>
  <li>Searching for a particular element in a JavaScript array is often carried out using a typical iteration. In some cases, forEach and some can be used as well. What is often overlooked is the potential use of Array.prototype.reduce to perform such an operation.</li>
  <li>Every time you find yourself going from a list of values to one value ( reducing ) ask yourself if you could leverage the built-in *Array.prototype.reduce()* function. You can reduce with any sort of operation that combines two values. Not just addition. And not just arithmetic operations.</li>
</ol>

Let’s take a look at the following problem (part of JavaScript Under Pressure): **find the longest string** in an array of strings. An imperative solution looks something like the following code (using forEach may simplify the loop but the idea remains the same):

	function findLongest(entries) {
	  for (var i = , longest = ''; i < entries.length; ++i)
	    if (entries[i].length > longest.length) longest = entries[i];
	  return longest;
	}
A version which relies on **reduce** is a single statement:

	function findLongest(entries) {
	  return entries.reduce(function (longest, entry) {
	    return entry.length > longest.length ? entry : longest;
	  }, '');
	}

<h3>Disadvantages</h3>
<ol>
  <li>If an initialValue is provided, the reduce method calls the callbackfn function one time for each element present in the array, in ascending index order. If an initialValue is not provided, the reduce method calls the callbackfn function on each element, starting with the second element.</li>
  <li>The return value of the callback function is provided as the previousValue argument on the next call to the callback function. The return value of the last call to the callback function is the return value of the reduce method.</li>
  <li>The callback function is not called for missing elements of the array.</li>
</ol>


<h3>Working Example</h3>
The following example illustrates the use of the *Array.prototype.reduce()* method.

    var total = [0, 1, 2, 3].reduce(function(a, b) {
      return a + b;
    });
    // total == 6

    var flattened = [[0, 1], [2, 3], [4, 5]].reduce(function(a, b) {
      return a.concat(b);
    }, []);
    // flattened is [0, 1, 2, 3, 4, 5]

<br/>

    // Define the callback function.
    function appendCurrent (previousValue, currentValue) {
    return previousValue + "::" + currentValue;
    }

    // Create an array.
    var elements = ["abc", "def", 123, 456];

    // Call the reduce method, which calls the callback function
    // for each array element.
    var result = elements.reduce(appendCurrent);

    document.write(result);

    // Output:
    //  abc::def::123::456

<h3>References</h3>
[https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)<br/>
[https://github.com/FreeCodeCamp/FreeCodeCamp/wiki/JS-Array-Prototype-Reduce](https://github.com/FreeCodeCamp/FreeCodeCamp/wiki/JS-Array-Prototype-Reduce)<br/>
[https://msdn.microsoft.com/en-us/library/ff679975(v=VS.94).aspx](https://msdn.microsoft.com/en-us/library/ff679975(v=VS.94).aspx)
<br/>
[https://ariya.io/2013/10/searching-using-array-prototype-reduce](https://ariya.io/2013/10/searching-using-array-prototype-reduce)