+++
date = "2017-01-30T00:45:05+05:30"
title = "Function.prototype.bind()"
next = "/objects/index"
prev = "/objects/Date.prototype.toJSON"
toc = true
weight = 14

+++


The *bind()* method creates a new function that, when called, has its this keyword set to the provided value, with a given sequence of arguments preceding any provided when the new function is called.

<h3>Need for this</h3>
The bind() function creates a new bound function (BF). A BF is an exotic function object (term from ECMAScript 2015)  that wraps the original function object. Calling a BF generally results in the execution of its wrapped function.
A BF has the following internal properties:


   <ul><li>[[BoundTargetFunction]] - the wrapped function object;</li>
   <li>[[BoundThis]] - the value that is always passed as the this value when calling the wrapped function.</li><li>[[BoundArguments]]  - a list of values whose elements are used as the first arguments to any call to the wrapped function.</li><li>[[Call]] - executes code associated with this object. Invoked via a function call expression. The arguments to the internal method are a this value and a list containing the arguments passed to the function by a call expression.</li>

   </ul>


    fun.bind(thisArg[, arg1[, arg2[, ...]]])

<h3>Advantages</h3>
<ol>
  <li>Function binding is most probably your least concern when beginning with JavaScript, but when you realize that you need a solution to the problem of how to keep the context of this within another function, then you might not realize that what you actually need is Function.prototype.bind().
  </li>
  <li>The first time you hit upon the problem, you might be inclined to set this to a variable that you can reference when you change context. Many people opt for self, _this or sometimes context as a variable name. They’re all usable and nothing is wrong with doing that, but this is a better way.</li>
</ol>

<h3>Disadvantages</h3>
<ol>
  <li>As you can see, unfortunately, Function.prototype.bind isn’t supported in Internet Explorer 8 and below, so you’ll run into problems if you try to use it without a fallback.</li>
</ol>

<h3>Working Example</h3>
The following example illustrates the use of the *Function.prototype.bind()* function.

	var Button = function(content) { 
	  this.content = content;
	};
	Button.prototype.click = function() {
	  console.log(this.content + ' clicked');
	}
	
	var myButton = new Button('OK');
	myButton.click();
	
	var looseClick = myButton.click;
	looseClick(); // not bound, 'this' is not myButton - it is the global object
	
	var boundClick = myButton.click.bind(myButton);
	boundClick(); // bound, 'this' is myButton

Which prints out:

	OK clicked
	undefined clicked
	OK clicked

You can also add extra parameters after the 1st (this) parameter and bind will pass in those values to the original function. Any additional parameters you later pass to the bound function will be passed in after the bound parameters:

<h3>References</h3>
[https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_objects/Function/bind](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_objects/Function/bind)
[https://www.smashingmagazine.com/2014/01/understanding-javascript-function-prototype-bind/](https://www.smashingmagazine.com/2014/01/understanding-javascript-function-prototype-bind/)
[http://stackoverflow.com/questions/2236747/use-of-the-javascript-bind-method](http://stackoverflow.com/questions/2236747/use-of-the-javascript-bind-method)

