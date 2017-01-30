+++
date = "2017-01-20T00:45:05+05:30"
title = "Date.prototype.toISOString()"

+++

The toISOString() method returns a string in simplified extended ISO format (ISO 8601), which is always 24 or 27 characters long (YYYY-MM-DDTHH:mm:ss.sssZ or ±YYYYYY-MM-DDTHH:mm:ss.sssZ, respectively). The timezone is always zero UTC offset, as denoted by the suffix "Z".

<h3>Need for this</h3>
Returns a date as a string value in simplified ISO 8601 Extended format.


    dateObj.toISOString()

<h3>Advantages</h3>
<ol>
  <li>The ISO 8601 Extended format is supported by Date.parse(), it is therefore a good choice when dates need to be exchanged between APIs. 
  </li>
</ol>


<h3>Working Example</h3>
The following example illustrates the use of the *Date.prototype.toISOString()* function.

	var today = new Date('05 October 2011 14:48 UTC');
	
	console.log(today.toISOString()); // Returns 2011-10-05T14:48:00.000Z


<h3>References</h3>
[https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Date/toISOString](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Date/toISOString)<br/>
[https://docs.webplatform.org/wiki/javascript/Date/toISOString](https://docs.webplatform.org/wiki/javascript/Date/toISOString)

