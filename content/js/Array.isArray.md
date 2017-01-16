+++
date = "2016-11-11T00:45:05+05:30"
title = "Array.isArray()"
next = "/js/Array.prototype.every"
prev = "/js/Array.isArray"
toc = true
weight = 1

+++

The *Array.isArray()* determines whether the passed value is an Array.

<h3>Need for this</h3>
If the passed object is an Array, true is returned, otherwise false is returned.

    Array.isArray(obj)

<h3>Advantages</h3>
<ol>
  <li>In most cases instanceof Array should be enough. However, since instanceof Array doesn't work correctly across iframes/window, Array.isArray() would be more robust solution.</li>
</ol>

<h3>Disadvantages</h3>
<ol>
  <li><i>Array.isArray()</i> is slow comparative to <i>instanceof Array</i> as it performs more robust check and takes a slight performance hit. </li>
</ol>


<h3>Working Example</h3>
The following example illustrates the use of the *Array.isArray()* function.

    // Using Array string litteral
    var ar = [];
     var result = Array.isArray(ar);
     // Output: true

    // Using new Array with an empty set
     var ar = new Array();
     var result = Array.isArray(ar);
     // Output: true

     var ar = [1, 2, 3];
     var result = Array.isArray(ar);
     // Output: true

    // Testing with a string litteral "an array"
     var injectingString = Array.isArray("an array");
     document.write(injectingString);
     // Output: false

    // Testing with an object litteral
     var injectingObject = Array.isArray({});
     document.write(injectingObject);
     // Output: false


<h3>References</h3>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/isArray)<br/>
[https://docs.webplatform.org/wiki/javascript/Array/isArray](https://docs.webplatform.org/wiki/javascript/Array/isArray)