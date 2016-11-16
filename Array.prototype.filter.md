+++
date = "2016-11-16T00:45:05+05:30"
title = "Array.prototype.filter()"

+++

The `Array.prototype.filter()` method creates a new array with all elements that pass the filter test implemented by the provided function.

<h3>Need for this</h3>
Array.prototype.filter() provides a clean method for developers to iterate through an array and filter out array items based on a certain criteria without having to loop through the Array manually using a for loop.

<h3>Disadvantage</h3>
<ol>
  <li>The method does not directly modify the original array, but creates a new array instead. This results in usage of extra memory in cases where the original array needs to be replaced.</li>
</ol>

<h3>Advantages</h3>
<ol>
	<li>Array.prototype.filter() provides a clean way for filtering out unwanted array items based on a filter criteria without having to iterate through the array using for loops.</li>
	<li>A polyfill is available for `Array.prototype.filter()` for older browsers where the method is not supported by the browser.</li>
</ol>

<h3>Working Example</h3>

	// Define a callback function to filter prime numbers.
	function CheckIfPrime(value, index, ar) {
	    var high = Math.floor(Math.sqrt(value)) + 1;

	    for (var i = 2; i <= high; i++) {
	        if (value % i == 0) {
	            return false;
	        }
	    } 
	    return true;
	}

	// Create the original array.
	var numbers = [51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73];

	// Get the prime numbers that are in the original array. 
	var primes = numbers.filter(CheckIfPrime);

	console.log(primes);
	// Output: 53, 59, 61, 67, 71, 73

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter
<br>
https://msdn.microsoft.com/en-us/library/ff679973(v=vs.94).aspx
<br>
https://www.tutorialspoint.com/javascript/array_filter.htm
