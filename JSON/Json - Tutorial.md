# JSON Tutorial

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

## JSON - Introduction	

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

## JSON Syntax

The JSON syntax is a subset of the JavaScript syntax.

last http://www.w3schools.com/json/json_syntax.asp



