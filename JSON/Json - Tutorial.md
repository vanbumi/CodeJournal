<h1 id="home">JSON Tutorial</h1>

## Contents

<ul>
	<li><a href="#home">Home</a></li>
	<li><a href="#lesson1">JSON Introduction</a></li>
	<li><a href="#lesson2">JSON Syntax</a></li>
	<li><a href="#lesson3">JSON How To</a></li>
</ul>

JSON: JavaScript Object Notation.

JSON is a syntax for storing and exchanging data.

JSON is an easier-to-use alternative to XML.

The following JSON example defines an employees object, with an array of 3 employee records:

JSON Example

	{"employees":[
	    {"firstName":"John", "lastName":"Doe"},
	    {"firstName":"Anna", "lastName":"Smith"},
	    {"firstName":"Peter", "lastName":"Jones"}
	]}

Example

	{
		"pegawai": 
		[
			{"namaDepan":"Ersya", "namaBelakang":"Prahesti"},
			{"namaDepan":"Brandon", "namaBelakang":"Bumi"},
			{"namaDepan":"SDyo", "namaBelakang":"Bumi"}

		]

	}

The following XML example also defines an employees object with 3 employee records:

XML Example

	<employees>
	    <employee>
	        <firstName>John</firstName> <lastName>Doe</lastName>
	    </employee>
	    <employee>
	        <firstName>Anna</firstName> <lastName>Smith</lastName>
	    </employee>
	    <employee>
	        <firstName>Peter</firstName> <lastName>Jones</lastName>
	    </employee>
	</employees>	

## What is JSON?

* JSON stands for JavaScript Object Notation
* JSON is a lightweight data-interchange format
* JSON is language independent *
* JSON is "self-describing" and easy to understand

> Note	* JSON uses JavaScript syntax, but the JSON format is text only, just like XML.
Text can be read and used as a data format by any programming language.

<h2 id="lesson1">JSON - Introduction</h2>	

### JSON - Evaluates to JavaScript Objects

The JSON format is syntactically identical to the code for creating JavaScript objects.

Because of this similarity, instead of using a parser (like XML does), a JavaScript program can use standard JavaScript functions **to convert JSON data into native JavaScript objects.**

### Try it Yourself

With our editor, you can edit JavaScript code online and click on a button to view the result:

#### JSON Example

	<!DOCTYPE html>
	<html>
	<body>

	<h2>JSON Object Creation in JavaScript</h2>

	<p id="demo"></p>

	<script>
	var text = '{"name":"John Johnson","street":"Oslo West 16","phone":"555 1234567"}';

	var obj = JSON.parse(text);

	document.getElementById("demo").innerHTML =
	obj.name + "<br>" +
	obj.street + "<br>" +
	obj.phone;
	</script>

	</body>
	</html>

[Test Code](http://www.w3schools.com/json/tryit.asp?filename=tryjson_create)

#### Much Like XML Because

* Both JSON and XML are "self describing" (human readable)
* Both JSON and XML are hierarchical (values within values)
* Both JSON and XML can be parsed and used by lots of programming languages
* Both JSON and XML can be fetched with an XMLHttpRequest

#### Much Unlike XML Because

* JSON doesn't use end tag
* JSON is shorter
* JSON is quicker to read and write
* JSON can use arrays

The biggest difference is:

XML has to be parsed with an XML parser. JSON can be parsed by a standard JavaScript function.

#### Why JSON?

For AJAX applications, JSON is faster and easier than XML:

Using XML

* Fetch an XML document
* Use the XML DOM to loop through the document
* Extract values and store in variables

Using JSON

* Fetch a JSON string
* JSON.Parse the JSON string

<h2 id="lesson2">JSON Syntax</h2>

The JSON syntax is a subset of the JavaScript syntax.

### JSON Syntax Rules

JSON syntax is derived (berasal) from JavaScript object notation syntax:

* Data is in name/value pairs
* Data is separated by commas
* Curly braces hold objects
* Square brackets hold arrays

### JSON Data - A Name and a Value

JSON data is written as name/value pairs.

A name/value pair consists (terdiri) of **a field name (in double quotes)**, followed by **a colon**, followed by **a value**:

Example

	"firstName":"John"

> Note!! JSON names require double quotes. JavaScript names don't.

### JSON Values

JSON values can be:

* A number (integer or floating point)
* A string (in double quotes)
* A Boolean (true or false)
* An array (in square brackets)
* An object (in curly braces)
* null

### JSON Objects

JSON objects are written inside curly braces.

Just like JavaScript, JSON objects can contain multiple name/values pairs:

Example

	{"firstName":"John", "lastName":"Doe"}

### JSON Arrays

JSON arrays are written inside square brackets.

Just like JavaScript, a JSON array can contain multiple objects:

Example

	"employees":[
	    {"firstName":"John", "lastName":"Doe"}, 
	    {"firstName":"Anna", "lastName":"Smith"}, 
	    {"firstName":"Peter","lastName":"Jones"}
	]

In the example above, the object "employees" is an array containing three objects. Each object is a record of a person (with a first name and a last name).

### JSON Uses JavaScript Syntax

Because JSON syntax is derived from JavaScript object notation, very little extra software is needed to work with JSON within JavaScript.

With JavaScript you can create an array of objects and assign data to it, like this:

Example

	var employees = [
	    {"firstName":"John", "lastName":"Doe"},
	    {"firstName":"Anna", "lastName":"Smith"},
	    {"firstName":"Peter","lastName": "Jones"}
	];

The first entry in the JavaScript object array can be accessed like this:

Example

	// returns John Doe
	employees[0].firstName + " " + employees[0].lastName;

[Test Code](https://jsfiddle.net/vanbumi/fncgbfms/)

It can also be accessed like this:

Example

	// returns John Doe
	employees[0]["firstName"] + " " + employees[0]["lastName"];

[Test Code](https://jsfiddle.net/vanbumi/5L7jum7p/)

Data can be modified like this:

Example

	employees[0].firstName = "Gilbert";

[Test Code](https://jsfiddle.net/vanbumi/r34ccgj6/)	

It can also be modified like this:

Example

	employees[0]["firstName"] = "Gilbert";

[Test Code](http://www.w3schools.com/json/tryit.asp?filename=tryjson_objectarray_4)

In the next chapter you will learn how to convert a JSON text to a JavaScript object.

### JSON Files

* The file type for JSON files is ".json"
* The MIME type for JSON text is "application/json"

<h2 id="lesson3">JSON How To</h2>

A common use of JSON is **to read data from a web server, and display the data in a web page**.

For simplicity, this can be demonstrated by using a string as input (instead of a file).

### JSON Example - Object From String

Create a JavaScript string containing JSON syntax:

	var text = '{ "employees" : [' +
	'{ "firstName":"John" , "lastName":"Doe" },' +
	'{ "firstName":"Anna" , "lastName":"Smith" },' +
	'{ "firstName":"Peter" , "lastName":"Jones" } ]}';

JSON syntax is a subset of JavaScript syntax.

The JavaScript function JSON.parse(text) can be used to convert a JSON text into a JavaScript object:

	var obj = JSON.parse(text);	

Use the new JavaScript object in your page:	

#### Example

	<p id="demo"></p> 

	<script>
	document.getElementById("demo").innerHTML =
	obj.employees[1].firstName + " " + obj.employees[1].lastName; 
	</script>

#### Using eval()

Older browsers without the support for the JavaScript function JSON.parse() can use the eval() function to convert a JSON text into a JavaScript object:

Example

	var obj = eval ("(" + text + ")");


http://www.w3schools.com/json/json_eval.asp