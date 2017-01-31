+++
date = "2017-01-30T00:45:05+05:30"
title = "String.prototype.trim()"
next = "/objects/String.prototype.trim"
prev = "/objects/StrictMode"
toc = true
weight = 31

+++

The *trim()* method removes whitespace from both ends of a string. Whitespace in this context is all the whitespace characters (space, tab, no-break space, etc.) and all the line terminator characters (LF, CR, etc.).

<h3>Need for this</h3>
The trim() method returns the string stripped of whitespace from both ends. trim() does not affect the value of the string itself.


    str.trim()

<h3>Advantages</h3>
<ol>
  <li>Most JavaScript trim() implementations you see around are based on regular expressions and work fairly well for infrequent use on short strings. But using this method it is better and faster. 
  </li>
</ol>

<h3>Disadvantages</h3>
<ol>
  <li>For browsers that do not support string.trim(), e.g. Internet Explorer 8 or earlier, you can add your own trim() method to string object's prototype by including the following script in the <HEAD> section of your page, prior to any script that uses string.trim():</li>
</ol>

	if (!String.prototype.trim) {
	  String.prototype.trim = function () {
	    return this.replace(/^[\s\uFEFF\xA0]+|[\s\uFEFF\xA0]+$/g, '');
	  };
	}

<h3>Working Example</h3>
The following example illustrates the use of the *String.prototype.trim()* function.

	var orig = '   foo  ';
	console.log(orig.trim()); // 'foo'
	
	// Another example of .trim() removing whitespace from just one side.
	
	var orig = 'foo    ';
	console.log(orig.trim()); // 'foo'


<h3>References</h3>
[https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/String/trim](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/String/trim)<br/>
[http://stackoverflow.com/questions/498970/trim-string-in-javascript](http://stackoverflow.com/questions/498970/trim-string-in-javascript)

