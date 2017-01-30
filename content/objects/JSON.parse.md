+++
date = "2016-11-11T00:45:05+05:30"
title = "JSON.parse()"
next = "/objects/JSON.stringify"
prev = "/objects/Array.prototype.some"
toc = true
weight = 7

+++

The JSON.parse() method parses a JSON string, constructing the JavaScript value or object described by the string. An optional reviver function can be provided to perform a transformation on the resulting object before it is returned.

<h3>Need for this</h3>
JSON.parse allows developers to fetch JSON strings through ajax requests or other similar methods and convert them into a JSON object. Prior to the introduction of `JSON.parse()`, a common approach used by developers to convert a string to a JSON object was to use `eval()`. Using `eval()` for conversion of data can be dangerous since the JSON data may be suffixed with malicious code which can get evaluated unintentionally. `JSON.parse` ensures that no code is run within the string as it is only responsible for conversion.

<h3>Advantages</h3>
<ol>
  <li>JSON.parse() ensures that the JSON string is not malformed.</li>
  <li>JSON.parse() allows a second (reviver) parameter to transform the JSON values before they are returned as a JSON object.</li>
</ol>

<h3>Working Example</h3>

    JSON.parse('{"p": 5}', (key, value) =>
    typeof value === 'number'
    ? value * 2 // return value * 2 for numbers
    : value     // return everything else unchanged
    );

    // { p: 10 }

<h3>References</h3>
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse
<br>
https://msdn.microsoft.com/library/cc836466(v=vs.94).aspx