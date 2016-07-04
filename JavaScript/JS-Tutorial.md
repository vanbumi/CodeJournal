# JavaScript Tutorial

* [JS - w3schools](http://www.w3schools.com/js/default.asp)

### Lesson 1

	<button type="button" onclick="document.getElementById('tanggal').innerHTML = Date()">
	  Click me to find out the date is
	</button>
	<p id="tanggal"></p>

[Test Code](https://jsfiddle.net/vanbumi/fhbof9ee/)	

### Lesson 2

#### JavaScript Can Change HTML Attributes 

This example changes an HTML image by changing the src (source) attribute of an <img> tag:

Prinsipnya adalah

	onclick="getElementById('myImage').src='myNewImage';"

Sample	

	<img id="myImage" src="http://res.cloudinary.com/medio/image/upload/v1467519618/pic_bulboff_diye3u.gif" alt=""><br>
	<button type="button" onclick="document.getElementById('myImage').src='http://res.cloudinary.com/medio/image/upload/v1467519606/pic_bulbon_hnaava.gif' ">
	  Click to ON Lamp
	</button>

	<button type="button" onclick="document.getElementById('myImage').src='http://res.cloudinary.com/medio/image/upload/v1467519618/pic_bulboff_diye3u.gif' ">Turn OFF again</button>

[Test Code](https://jsfiddle.net/vanbumi/eg5vfcye/1/)

### Lesson 3

#### JavaScript Can Change HTML Styles (CSS)

Changing the style of an HTML element, is a variant of changing an HTML attribute:

Prinsip:

	document.getElementById("demo").style.fontSize = "25px";

Sample:

	<h2>We going to change Font Size text & Color</h2>

	<p id="textme">This is the text we going to change the font style</p>

	<button type="button" onclick="document.getElementById('textme').style.fontSize='25px'">Change Size</button>
	<button type="button" onclick="document.getElementById('textme').style.color='red'">Change Color</button>	

[Test Code](https://jsfiddle.net/vanbumi/jc0reegf/10/)

### Lesson 4 

#### JavaScript Can Hide HTML Elements

Hiding HTML elements can be done by changing the display style:

Prinsip:

	document.getElementById("demo").style.display="none";

Sample:

	<h1 id="judul">Saya ingin menyembunyikan ini sesaat saya menekan tombol</h1>

	<button type="button" onclick="document.getElementById('judul').style.display='none'">
		Tombol
	</button>	

[Test Code](https://jsfiddle.net/vanbumi/3jouruqw/3/)

### Lesson 5

#### JavaScript Can Show HTML Elements

Showing hidden HTML elements can also be done by changing the display style:	

Prinsip:

	document.getElementById("demo").style.display="block";

Sample:

	<h3>Menampilkan text yang tersembunyi</h3>

	<p id="sembunyi" style="display:none;">Hello World Dyo!!!</p>

	Klik button untuk menampilkan sesuatu 
	<button type="button" onclick="document.getElementById('sembunyi').style.display='block'">
	  Click me
	</button>

[Test Code](https://jsfiddle.net/vanbumi/esadgyd9/7/)

### Lesson 6

#### JavaScript Functions and Events

A JavaScript function is a block of JavaScript code, that can be executed when "asked" for. For example, a function can be executed when an event occurs, like when the user clicks a button.

sample:

	<h3 id="rubah">Merubah text ini menjadi text lain</h3>
  
	<script>
	    function myFunction() {
	      document.getElementById('rubah').innerHTML="Text telah berubah menjadi yang ini."
	    }
	</script>
		 
	<p>
		<button type="button" onclick="myFunction()">Click deh</button>
	</p>

[Test Code](https://jsbin.com/mixeri/edit?html,output)

#### External JavaScript	

myScript.js

	function myFunction() {
	   document.getElementById("demo").innerHTML = "Paragraph changed.";
	}

put the extention link:

	<!DOCTYPE html>
	<html>
	<body>
		<script src="myScript.js"></script>
	</body>
	</html>	

Sample:

	<!DOCTYPE html>
	<html>
	<body>

	<h1>External JavaScript</h1>

	<p id="demo">A Paragraph.</p>

	<button type="button" onclick="myFunction()">Try it</button>

	<p><strong>Note:</strong> myFunction is stored in an external file called "myScript.js".</p>

	<script src="myScript.js"></script>

	</body>
	</html>	

### Lesson 7

#### JavaScript Display Possibilities

JavaScript can "display" data in different ways:

Writing into an alert box, using window.alert().
Writing into the HTML output using document.write().
Writing into an HTML element, using innerHTML.
Writing into the browser console, using console.log().

##### Using window.alert()

You can use an alert box to display data:

	<script>
		window.alert(5 + 6)
	</script>

[Test Code](https://jsfiddle.net/vanbumi/u2eLzg7o/)

##### Using document.write()

For testing purposes, it is convenient to use document.write():

	<script>
		document.write(8 + 6);
	</script>

[Test Code](https://jsfiddle.net/vanbumi/km6paLgc/1/)

Other sample:

	<button type="button" onclick="document.write(5 + 7)">
	  Try it!
	</button>

[Test Code](https://jsfiddle.net/vanbumi/Locaxm02/1/)	

##### Using innerHTML

To access an HTML element, JavaScript can use the document.getElementById(id) method.
*Untuk mengakses sebuah elemen HTML, JavaScript dapat menggunakan metode document.getElementById (id).*

The id attribute defines the HTML element. The innerHTML property defines the HTML content:
*Atribut id mendefinisikan elemen HTML. Properti innerHTML mendefinisikan konten HTML:*

	<p id="demo"></p>

	<script>
		document.getElementById("demo").innerHTML = 5 + 8;
	</script>

[Test Code](https://jsfiddle.net/vanbumi/zrpof0rw/1/)

##### Using console.log()

In your browser, you can use the console.log() method to display data.

Activate the browser console with F12, and select "Console" in the menu.

	<script>
	    console.log(5 +7)
	</script>

[Test Code](https://jsbin.com/fucerev/edit?html,js,console,output)

### Lesson 8

#### JavaScript Syntax

JavaScript syntax is the set of rules, how JavaScript programs are constructed.
*sintaks JavaScript adalah seperangkat aturan, bagaimana JavaScript program dibangun.*

##### JavaScript Programs

A computer program is a list of "instructions" to be "executed" by the computer.

In a programming language, these program instructions are called statements.

JavaScript is a programming language.

JavaScript statements are separated by semicolons.

	var x = 5;
	var y = 8;
	var z = x + y;
	document.getElementById("contoh1").innerHTML = z;

[Test Code](https://jsfiddle.net/vanbumi/41rqwnxz/)	

#### JavaScript Statements

JavaScript statements are composed of:

*Values, Operators, Expressions, Keywords, and Comments.*

##### JavaScript Values

The JavaScript syntax defines two types of values: Fixed values and variable values.

*Fixed values are called literals. Variable values are called variables.*

##### JavaScript Literals

The most important rules for writing fixed values are:

Numbers are written with or without decimals:

	10.5
	1001

Strings are text, written within double or single quotes:

	"John Doe"
	'John Doe'

##### JavaScript Variables

In a programming language, variables are used to store data values.

JavaScript uses the *var* keyword to declare variables.

*An equal* sign is used to assign values to variables.

In this example, x is defined as a variable. Then, x is assigned (given) the value 6:

	var x;
	x = 6;

	document.getElementById("demo").innerHTML = x;

##### JavaScript Operators

JavaScript uses an assignment operator ( = ) to assign values to variables:

	var x = 7;
	var y = 8;

	document.getElementById("demo").innerHTML = x + y;

Other sample:

	(5 + 6) * 10

[Test Code](https://jsfiddle.net/vanbumi/mLaLxamf/)

##### JavaScript Expressions

An expression is a combination of values, variables, and operators, which computes to a value.

The computation is called an evaluation.

For example, 5 * 10 evaluates to 50:		

	5 * 10

Expressions can also contain variable values:

	x * 10

The values can be of various types, such as numbers and strings.

For example, "John" + " " + "Doe", evaluates to "John Doe":

	"John" + " " + "Doe"

	document.getElementById("demo").innerHTML = "John" + " "  + "Doe";		

##### JavaScript Keywords

JavaScript keywords are used to identify actions to be performed.

The var keyword tells the browser to create a new variable:

	var x = 5 + 6;
	var y = x * 10;

##### JavaScript Comments

Not all JavaScript statements are "executed".

Code after double slashes // or between /* and */ is treated as a comment.

Comments are ignored, and will not be executed:

	var x = 5;   // I will be executed

	// var x = 6;   I will NOT be executed	

##### JavaScript Identifiers

Identifiers are names.

In JavaScript, identifiers are used to name variables (and keywords, and functions, and labels).

The rules for legal names are much the same in most programming languages.

In JavaScript, the first character must be a letter, an underscore (_), or a dollar sign ($).

Subsequent characters may be letters, digits, underscores, or dollar signs.

> Numbers are not allowed as the first character.
This way JavaScript can easily distinguish identifiers from numbers.

##### All JavaScript identifiers are case sensitive. 

The variables lastName and lastname, are two different variables.

	lastName = "Doe";
	lastname = "Peterson";

> JavaScript does not interpret VAR or Var as the keyword var.

##### JavaScript and Camel Case

Historically, programmers have used three ways of joining multiple words into one variable name:

Hyphens:

first-name, last-name, master-card, inter-city.

Underscore:

first_name, last_name, master_card, inter_city.

Camel Case:

FirstName, LastName, MasterCard, InterCity.

In programming languages, especially in JavaScript, camel case often starts with a lowercase letter:

firstName, lastName, masterCard, interCity.

> Hyphens are not allowed in JavaScript. It is reserved for subtractions.

##### JavaScript Character Set

JavaScript uses the Unicode character set.

Unicode covers (almost) all the characters, punctuations, and symbols in the world.

For a closer look, please study our [Complete Unicode Reference](http://www.w3schools.com/charsets/ref_html_utf8.asp).

### Lesson 9

#### JavaScript Statements

In HTML, JavaScript statements are "instructions" to be "executed" by the web browser.

This statement tells the browser to write "Hello Dolly." inside an HTML element with id="demo":

	document.getElementById("demo").innerHTML = "Hello Dolly.";

##### JavaScript Programs

Most JavaScript programs contain many JavaScript statements.

The statements are executed, one by one, in the same order as they are written.

In this example x, y, and z are given values, and finally z is displayed:

	Example
	var x = 5;
	var y = 6;
	var z = x + y;
	document.getElementById("demo").innerHTML = z;	

> JavaScript programs (and JavaScript statements) are often called JavaScript code.

##### Semicolons ;

Semicolons separate JavaScript statements.

Add a semicolon at the end of each executable statement:

	a = 5;
	b = 6;
	c = a + b;

	document.write(c);

[Test Code](https://jsfiddle.net/vanbumi/aobh5dgf/1/)	

When separated by semicolons, multiple statements on one line are allowed:

	x = 7; y = 6; z = x + y;

	document.write(z);	

[Test Code](https://jsfiddle.net/vanbumi/aobh5dgf/3/)		

> On the web, you might see examples without semicolons. 
Ending statements with semicolon is not required, but highly recommended.

##### JavaScript White Space

JavaScript ignores multiple spaces. You can add white space to your script to make it more readable.

The following lines are equivalent:

	var person = "Hege";
	var person="Hege";

A good practice is to put spaces around operators ( = + - * / ):

	var x = y + z;

##### JavaScript Line Length and Line Breaks

For best readability, programmers often like to avoid code lines longer than 80 characters.

If a JavaScript statement does not fit on one line, the best place to break it, *is after an operator:*

Example

	document.getElementById("demo").innerHTML =
	"Hello Dolly.";

##### JavaScript Code Blocks

JavaScript statements can be grouped together in code blocks, inside curly brackets {...}.

The purpose of code blocks is to define statements to be executed together.

One place you will find statements grouped together in blocks, are in JavaScript functions:

Example

	function myFunction() {
	    document.getElementById("demo").innerHTML = "Hello Dolly.";
	    document.getElementById("myDIV").innerHTML = "How are you?";
	}

[Test Code](https://jsfiddle.net/vanbumi/t8ezj2n1/5/)

##### JavaScript Keywords

JavaScript statements often start with a keyword to identify the JavaScript action to be performed.

Here is a list of some of the keywords you will learn about in this tutorial:

![keywordsJS](http://res.cloudinary.com/medio/image/upload/v1467558449/js-keyword_qxtjjr.png)

### Lesson 10

#### JavaScript Comments

Example

	// Change heading:
	document.getElementById("myH").innerHTML = "My First Page";
	// Change paragraph:
	document.getElementById("myP").innerHTML = "My first paragraph.";

Example

	var x = 5;      // Declare x, give it the value of 5
	var y = x + 2;  // Declare y, give it the value of x + 2

Example

	/*
	The code below will change
	the heading with id = "myH"
	and the paragraph with id = "myP"
	in my web page:
	*/
	document.getElementById("myH").innerHTML = "My First Page";
	document.getElementById("myP").innerHTML = "My first paragraph.";

### Lesson 11

#### JavaScript Variables

JavaScript variables are containers for storing data values.

In this example, x, y, and z, are variables:

Example

	var x = 5;
	var y = 6;
	var z = x + y;

From the example above, you can expect:

	x stores the value 5
	y stores the value 6
	z stores the value 11	

Example

	var price1 = 5;
	var price2 = 6;
	var total = price1 + price2;

sample:
	
	<p id="demo"></p>

	<script>
		var price1 = 5;
		var price2 = 6;
		var total = price1 + price2;

		document.getElementById("demo").innerHTML =
		"The total is: " + total;
	</script>

[Test Code](https://jsfiddle.net/vanbumi/360n0waf/)	

last http://www.w3schools.com/js/js_variables.asp		