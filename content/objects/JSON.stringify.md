+++
date = "2016-11-16T00:45:05+05:30"
title = "JSON.parse()"
next = "/objects/Object.create"
prev = "/objects/JSON.parse"
toc = true
weight = 16

+++

The JSON.stringify() method converts a JavaScript value to a JSON string, optionally replacing values if a replacer function is specified, or optionally including only the specified properties if a replacer array is specified.

<h3>Need for this</h3>
JSON.stringify allows developers to convert JavaScript objects into strings for processing. Optionally, it also allows the developer to pass a `replacer` function that allows manipulation / filter of key / values of the input Object before it is returned as a string.

<h3>Advantages</h3>
<ol>
  <li>JSON.stringify() ensures that the JSON object passed is not malformed and in some cases fixes the syntax of malformed JSON objects.</li>
  <li>JSON.stringify() allows a second (replacer) parameter to transform / filter out the JSON values before they are returned as a string.</li>
</ol>

<h3>Working Example</h3>

	JSON.stringify({ x: 15, y: 26 });
	// '{"x":5,"y":6}'

	function replacer(key, value) {
		// Filtering out properties
		if (typeof value === "number" || typeof value === "object") {
			return value;
		}
		return undefined;
	}
	var foo = {name: "Deloitte", city: "Mumbai", offices: 1, location: "Powai", employees: 15000};
	JSON.stringify(foo, replacer);
	// '{"offices":1,"employees":15000}'


<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify
<br>
https://msdn.microsoft.com/library/cc836459(v=vs.94).aspx