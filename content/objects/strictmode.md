+++
date = "2017-01-30T00:45:05+05:30"
title = "Strict Mode"
next = "/objects/strictmode"
prev = "/objects/Date.prototype.toJSON"
toc = true
weight = 30

+++

*Strict Mode* is a new feature in ECMAScript 5 that allows you to place a program, or a function, in a "strict" operating context. This strict context prevents certain actions from being taken and throws more exceptions.

You can enable the strict mode by declaring this in the top of your script/function.

	'use strict';

<h3>Why Strict Mode?</h3>
<ul>
  <li>Strict mode makes it easier to write "secure" JavaScript. 
  </li>
  <li>Strict mode changes previously accepted "bad syntax" into real errors. As an example, in normal JavaScript, mistyping a variable name creates a new global variable. In strict mode, this will throw an error, making it impossible to accidentally create a global variable.
  </li>
  <li>In normal JavaScript, a developer will not receive any error feedback assigning values to non-writable properties. 
  </li>
  <li>In strict mode, any assignment to a non-writable property, a getter-only property, a non-existing property, a non-existing variable, or a non-existing object, will throw an error. 
  </li></ul>

<h3>Where should I use 'use strict';?</h3>
<ul>
  <li>In my existing JavaScript code: <b>Probably not!</b> If your existing JavaScript code has statements that are prohibited in strict-mode, the application will simply break. If you want strict mode, you should be prepared to debug and correct your existing code. This is why using 'use strict'; does not suddenly make your code better. 
  </li>
  <li>In my new JavaScript application: <b>Absolutely!</b> Strict mode can be used as a whistleblower when you are doing something stupid with your code. 
  </li>
</ul>

<h3>How do I use strict mode?</h3>
1.Insert a 'use strict'; statement on top of your script:
	
	// File: myscript.js

	'use strict';
	var a = 2;
	....

Note that everything in the file myscript.js will be interpreted in strict mode.

2.Insert a 'use strict'; statement on top of your function body:

	function doSomething() {
	    'use strict';
	    ...
	}

Everything in the lexical scope of function doSomething will be interpreted in strict mode.

<h3>List of features</h3>
<ul>
<li>In strict mode all variables have to be declared: if you assign a value to an identifier that has not been declared as variable, function, function parameter, catch-clause parameter or property of the global Object, then you will get a ReferenceError. In normal mode the identifier is implicitly declared as a global variable (as a property of the global Object)</li>
<li>In strict mode the keyword this has the value undefined in functions that were invoked as functions (not as methods). (In normal mode this always points to the global Object). This difference can be used to test if an implementation supports the strict mode: <br/><br/>

//var hasStrictMode = (function() { "use strict"; return this===undefined }());<br/><br/>

</li>
<li>Also when a function is invoked with call() or apply in strict mode, then this is exactly the value of the first argument of the call()or apply() invocation. (In normal mode null and undefined are replaced by the global Object and values, which are not objects, are cast into objects.)</li>
<li>You cannot use the with-statement in strict mode.
</li>
<li>In strict mode you will get a TypeError, when you try to assign to readonly properties or to define new properties for a non extensible object. (In normal mode both simply fail without error message.)
</li>
<li>In strict mode, when passing code to eval(), you cannot declare or define variables or functions in the scope of the caller (as you can do it in normal mode). Instead, a new scope is created for eval() and the variables and functions are within that scope. That scope is destroyed after eval() finishes execution.
</li>
<li>In strict mode the arguments-object of a function contains a static copy of the values, which are passed to that function. In normal mode the arguments-object has a somewhat "magical" behaviour: The elements of the array and the named function parameters reference both the same value.
</li>
<li>In strict mode you will get a SyntaxError when the delete operator is followed by a non qualified identifier (a variable, function or function parameter). In normal mode the delete expression would do nothing and is evaluated to false.
</li>
<li>In strict mode you will get a TypeError when you try to delete a non configurable property. (In normal mode the attempt simply fails and the delete expression is evaluated to false).
</li>
<li>In strict mode it is considered a syntactical error when you try to define several properties with the same name for an object literal. (In normal mode there is no error.)
</li>
<li>In strict mode it is considered a syntactical error when a function declaration has multiple parameters with the same name. (In normal mode there is no error.)
</li>
<li>In strict mode octal literals are not allowed (these are literals that start with 0x. (In normal mode some implementations do allow octal literals.)
</li>
<li>In strict mode are more restrictions on the possibilities to examine the call stack. arguments.caller and arguments.callee cause a TypeError in a function in strict mode. Furthermore, some caller- and arguments properties of functions in strict mode cause a TypeError when you try to read them.
</li>
</ul>

<h3>Advantages</h3>
<ul>
<li>Eliminate JavaScript silent errors by throwing error.</li>
<li>Fixes mistake that make it difficult for JavaScript engine to perform optimisation.</li>
<li>Make code run faster sometime than identical code that’s not in strict mode
</li>
<li>Make code run faster sometime than identical code that’s not in strict mode
Prohibits some syntax likely to be defined in future version of ECMAScript.</li>
</ul>


<h3>References</h3>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode)<br/>
[https://javascriptweblog.wordpress.com/2011/05/03/javascript-strict-mode/](https://javascriptweblog.wordpress.com/2011/05/03/javascript-strict-mode/)<br/>
[http://cjihrig.com/blog/javascripts-strict-mode-and-why-you-should-use-it/](http://cjihrig.com/blog/javascripts-strict-mode-and-why-you-should-use-it/)<br/>
[http://stackoverflow.com/questions/8651415/what-is-strict-mode-and-how-is-it-used](http://stackoverflow.com/questions/8651415/what-is-strict-mode-and-how-is-it-used)
