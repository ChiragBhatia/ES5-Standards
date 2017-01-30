+++
date = "2017-01-20T00:45:05+05:30"
title = "Date.now()"

+++

The *Date.now()* method returns the number of milliseconds elapsed since 1 January 1970 00:00:00 UTC.

<h3>Need for this</h3>
Returns the number of milliseconds between midnight, January 1, 1970, and the current date and time.


    var timeInMs = Date.now();

<h3>Advantages</h3>
<ol>
  <li>Date.getTime() and Date.now() are effectively equivalent but Date.now() is twice faster than the former. 
  </li>
</ol>


<h3>Working Example</h3>
The following example illustrates the use of the *Date.now()* function.

	var start = Date.now();
	var response = prompt("What is your name?", "");
	var end = Date.now();
	var elapsed = (end - start) / 1000;
	document.write("You took " + elapsed + " seconds" + " to type: " + response);
	
	// Output:
	// You took <seconds> seconds to type: <name>

<h3>References</h3>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now)<br/>
[http://stackoverflow.com/questions/12517359/performance-date-now-vs-date-gettime](http://stackoverflow.com/questions/12517359/performance-date-now-vs-date-gettime)

