+++
date = "2017-01-30T00:45:05+05:30"
title = "Date.prototype.toJSON()"
next = "/objects/Function.prototype.bind"
prev = "/objects/Date.prototype.toISOString"
toc = true
weight = 13

+++

The toJSON() method returns a string representation of the Date object.

<h3>Need for this</h3>
Date instances refer to a specific point in time. Calling toJSON() returns a string (using toISOString()) representing the Date object's value. This method is generally intended to, by default, usefully serialize Date objects during JSON serialization.


    dateObj.toJSON()


<h3>Working Example</h3>
The following example illustrates the use of the *Date.prototype.toJSON()* function.

	var jsonDate = (new Date()).toJSON();
	var backToDate = new Date(jsonDate);
	
	console.log(jsonDate); //2015-10-26T07:46:36.611Z

<h3>References</h3>
[https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Date/toJSON](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Date/toJSON)<br/>
[http://stackoverflow.com/questions/11382606/javascript-date-tojson-dont-get-the-timezone-offset](http://stackoverflow.com/questions/11382606/javascript-date-tojson-dont-get-the-timezone-offset)

