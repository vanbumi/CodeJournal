# JavaScript Tutorial

* [JS - w3schools](http://www.w3schools.com/js/default.asp)

## Contents

<ul>
	<li><a href="#lesson1">Lesson 1 - ..</a></li>
</ul>

### Lesson 1
<h3 id="lesson1">Lesson 1</h3>

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

<!-- Example

	var price1 = 5;
	var price2 = 6;
	var total = price1 + price2;

	<p id="demo"></p>

	<script>
	  var price1 = 5;
	  var price2 = 6;
	  var total = price1 + price2;
	  
	  document.getElementById("demo").innerHTML = "The total are: " + total;
	</script>

[Test Code](https://jsfiddle.net/vanbumi/emeym69s/) -->

#### JavaScript Identifiers

All JavaScript variables must be identified with unique names.

These unique names are called identifiers.

Identifiers can be short names (like x and y), or more descriptive names (age, sum, totalVolume).

The general rules for constructing names for variables (unique identifiers) are:

* Names can contain letters, digits, underscores, and dollar signs.
* Names must begin with a letter
* Names can also begin with $ and _ (but we will not use it in this tutorial)
* Names are case sensitive (y and Y are different variables)
* Reserved words (like JavaScript keywords) cannot be used as names

#### The Assignment Operator

In JavaScript, the equal sign (=) is an "assignment" operator, not an "equal to" operator.

This is different from algebra. The following does not make sense in algebra:

	x = x + 5

#### JavaScript Data Types

JavaScript variables can hold numbers like 100, and text values like "John Doe".

In programming, text values are called text strings.

JavaScript can handle many types of data, but for now, just think of numbers and strings.

*Strings are written inside double or single quotes. Numbers are written without quotes.*

If you put quotes around a number, it will be treated as a text string.

Example

	var pi = 3.14;
	var person = "John Doe";
	var answer = 'Yes I am!';

#### Declaring (Creating) JavaScript Variables

Creating a variable in JavaScript is called "declaring" a variable.

You declare a JavaScript variable with the var keyword:

	var carName;

After the declaration, the variable has no value. (Technically it has the value of undefined)

To assign a value to the variable, use the equal sign:

	carName = "Volvo";

You can also assign a value to the variable when you declare it:

	var carName = "Volvo";

> It's a good programming practice to declare all variables at the beginning of a script.	

Example:

	<p id="sample"></p>

	<script>
		var schoolName = "Universitas Indonesia";
	  
	  document.getElementById("sample").innerHTML = schoolName;
	</script>

[Test Code](https://jsfiddle.net/vanbumi/ttmsre2k/)		

#### One Statement, Many Variables

You can declare many variables in one statement.

Start the statement with var and separate the variables by comma:

	var person = "John Doe", carName = "Volvo", price = 200;

A declaration can span multiple lines:

	var person = "John Doe",
	carName = "Volvo",
	price = 200;

#### Value = undefined

In computer programs, variables are often declared without a value. The value can be something that has to be calculated, or something that will be provided later, like user input.

A variable declared without a value will have the value undefined.

The variable carName will have the value undefined after the execution of this statement:

Example
	
	var carName;

#### Re-Declaring JavaScript Variables

If you re-declare a JavaScript variable, it will not lose its value.

The variable carName will still have the value "Volvo" after the execution of these statements:

Example

	var carName = "Volvo";
	var carName;

#### JavaScript Arithmetic

As with algebra, you can do arithmetic with JavaScript variables, using operators like = and +:

Example

	var x = 5 + 2 + 3;

	document.write(x);
	document.write(x)

or 

	var y = "John" + " " + "Doe";
	document.write(y)

or

	var z = "5" + 2 + 3;
  	document.write(z)

If you add a number to a string, the number will be treated as string, and concatenated.			

[Test Code](https://jsfiddle.net/vanbumi/vq12rgrf/3/)

### Lesson 12 - JavaScript Operators

Example

Assign values to variables and add them together:

	var x = 5;         // assign the value 5 to x
	var y = 2;         // assign the value 2 to y
	var z = x + y;     // assign the value 7 to z (x + y)

#### JavaScript Arithmetic Operators

Arithmetic operators are used to perform arithmetic on numbers (literals or variables).

![Arithmetic operators](http://res.cloudinary.com/medio/image/upload/v1467600840/jsAritmeticOperators_wprgfb.png)	

The addition operator (+) adds numbers:

Adding

	var x = 5;
	var y = 2;
	var z = x + y;

The multiplication operator (*) multiplies numbers.

Multiplying

	var x = 5;
	var y = 2;
	var z = x * y;

#### JavaScript Assignment Operators

Assignment operators assign values to JavaScript variables.

![Assignment op](http://res.cloudinary.com/medio/image/upload/v1467601188/jsAsingOp_w8vdtq.png)	

The assignment operator (=) assigns a value to a variable.

Assignment

	var x = 10;	

The addition assignment operator (+=) adds a value to a variable.

Assignment

	var x = 10;
	x += 5;

#### JavaScript String Operators

The + operator can also be used to add (concatenate) strings.

> When used on strings, the + operator is called the concatenation operator.

Example

	txt1 = "John";
	txt2 = "Doe";
	txt3 = txt1 + " " + txt2;

The result of txt3 will be:

	John Doe

The += assignment operator can also be used to add (concatenate) strings:

Example

	txt1 = "What a very ";
	txt1 += "nice day";

The result of txt1 will be:

	What a very nice day	

#### Adding Strings and Numbers

Adding two numbers, will return the sum, but adding a number and a string will return a string:

Example

	x = 5 + 5;
	y = "5" + 5;
	z = "Hello" + 5;
	The result of x, y, and z will be:

	10
	55
	Hello5

The rule is: If you add a number and a string, the result will be a string!

#### JavaScript Comparison and Logical Operators

![Comparison and Logical Op](http://res.cloudinary.com/medio/image/upload/v1467601559/jscomparisonLogicalOperator_lmqxgp.png)

### Lesson 13 - JavaScript Data Types

	String, Number, Boolean, Array, Object.

#### Data Types 

JavaScript variables can hold many data types: numbers, strings, arrays, objects and more:

	var length = 16;                               // Number
	var lastName = "Johnson";                      // String
	var cars = ["Saab", "Volvo", "BMW"];           // Array
	var x = {firstName:"John", lastName:"Doe"};    // Object	

#### The Concept of Data Types

In programming, data types is an important concept.

To be able to operate on variables, it is important to know something about the type.

Without data types, a computer cannot safely solve this:

	var x = 16 + "Volvo";

Does it make any sense to add "Volvo" to sixteen? Will it produce an error or will it produce a result?

JavaScript will treat the example above as:

	var x = "16" + "Volvo";

> When adding a number and a string, JavaScript will treat the number as a string. 

	var x = 16 + "Volvo";

	var x = "Volvo" + 16;

JavaScript evaluates expressions from left to right. Different sequences can produce different results:

Example:

	var x = 16 + 4 + "Volvo";

Result:

	20Volvo

Example:	

	var x = "Volvo" + 16 + 4;

Result:

	Volvo164

In the first example, JavaScript treats 16 and 4 as numbers, until it reaches "Volvo".

In the second example, since the first operand is a string, all operands are treated as strings.

#### JavaScript Booleans

Booleans can only have two values: true or false.

Example

	var x = true;
	var y = false;

Booleans are often used in conditional testing.

#### JavaScript Arrays

JavaScript arrays are written with square brackets.

Array items are separated by commas.

The following code declares (creates) an array called cars, containing three items (car names):

Example

	var cars = ["Saab", "Volvo", "BMW"];	

Array indexes are zero-based, which means the first item is [0], second is [1], and so on.

You will learn more about arrays later in this tutorial.

#### JavaScript Objects

JavaScript objects are written with curly braces.

Object properties are written as name:value pairs, separated by commas.

Example

	var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

The object (person) in the example above has 4 properties: firstName, lastName, age, and eyeColor.

You will learn more about objects later in this tutorial.

#### The typeof Operator

You can use the JavaScript typeof operator to find the type of a JavaScript variable:

Example

	typeof "John"                // Returns string 
	typeof 3.14                  // Returns number
	typeof false                 // Returns boolean
	typeof [1,2,3,4]             // Returns object
	typeof {name:'John', age:34} // Returns object

> In JavaScript, an array is a special type of object. Therefore typeof [1,2,3,4] returns object. 

#### Undefined

In JavaScript, a variable without a value, has the value undefined. The typeof is also undefined.

Example

	var person;                  // Value is undefined, type is undefined

Any variable can be emptied, by setting the value to undefined. The type will also be undefined.

Example

	person = undefined;          // Value is undefined, type is undefined

#### Empty Values

An empty value has nothing to do with undefined.

An empty string variable has both a value and a type.

Example

	var car = "";                // The value is "", the typeof is string

#### Null

In JavaScript null is "nothing". It is supposed to be something that doesn't exist.

Unfortunately, in JavaScript, the data type of null is an object.

Note	You can consider it a bug in JavaScript that typeof null is an object. It should be null.
You can empty an object by setting it to null:

Example

	var person = null;           // Value is null, but type is still an object	

You can also empty an object by setting it to undefined:

Example

	var person = undefined;     // Value is undefined, type is undefined

Difference Between Undefined and Null

	typeof undefined             // undefined
	typeof null                  // object
	null === undefined           // false
	null == undefined            // true

### Lesson 14 - JavaScript Functions

A JavaScript function is a block of code designed to perform a particular task.

A JavaScript function is executed when "something" invokes it (calls it).

	function myFunction(p1, p2) {
	    return p1 * p2;         // The function returns the product of p1 and p2
	}

Example

	<p id="demo"></p>

	<script>
		function myFunction(a, b) {
	  	return a * b;
	  }

	  // memanggil function dengan getElement dari luar block function iu sendiri.
	   document.getElementById("demo").innerHTML = myFunction(5, 3);
	</script>

[Test Code](https://jsfiddle.net/vanbumi/xL7c4dv0/)	

#### JavaScript Function Syntax

A JavaScript function is defined with the function keyword, followed by a name, followed by parentheses ().

Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).

The parentheses may include parameter names separated by commas:
(parameter1, parameter2, ...)

The code to be executed, by the function, is placed inside curly brackets: {}

	function name(parameter1, parameter2, parameter3) {
	    code to be executed
	}

* Function parameters are the names listed in the function definition.

* Function arguments are the real values received by the function when it is invoked.

* Inside the function, the arguments behave as local variables.

#### Function Invocation

The code inside the function will execute when "something" invokes (calls) the function:

* When an event occurs (when a user clicks a button)
* When it is invoked (called) from JavaScript code
* Automatically (self invoked)
* You will learn a lot more about function invocation later in this tutorial.

#### Function Return

When JavaScript reaches a return statement, the function will stop executing.
*Saat JS mendapat return statement, function akan berhenti eksekusi*

If the function was invoked from a statement, JavaScript will "return" to execute the code after the invoking statement.
*Jika function sudah dipanggil dari statement, JS akan 'mengembalikan' nya untuk mengeksekusi kode tersebut setelah di statement panggil.*

Functions often compute a return value. The return value is "returned" back to the "caller":
*Function sering menjalankan nilai pengembalian. Nilai pengembalian di kembalikan kepada sipemanggil*

Example

Calculate the product of two numbers, and return the result:

	var x = myFunction(4, 3);        // Function is called, return value will end up in x

	function myFunction(a, b) {
	    return a * b;                // Function returns the product of a and b
	}

The result in x will be:

	12

#### Why Functions?

You can reuse code: Define the code once, and use it many times.

You can use the same code many times with different arguments, to produce different results.

Example

	Convert Fahrenheit to Celsius:

	function toCelsius(fahrenheit) {
	    return (5/9) * (fahrenheit-32);
	}
	document.getElementById("demo").innerHTML = toCelsius(77);

[Test Code](https://jsfiddle.net/vanbumi/pbacu59m/)	

#### The () Operator Invokes the Function

Using the example above, toCelsius refers to the function object, and toCelsius() refers to the function result.

Example

Accessing a function without () will return the function definition:

	function toCelsius(fahrenheit) {
	    return (5/9) * (fahrenheit-32);
	}
	document.getElementById("demo").innerHTML = toCelsius;

[Test Code](https://jsfiddle.net/vanbumi/qvwLm546/)

#### Functions Used as Variables

Functions can be used as variable values in formulas, assignments, and calculations.

Example

You can use:

	var text = "The temperature is " + toCelsius(77) + " Celsius";
	
toCelsius(77) is a function with the value already.

Instead of:

	var x = toCelsius(32);

	var text = "The temperature is " + x + " Celsius";

Example

	<p id="demo">Display the result here.</p>

	<script>
	function myFunction(name) {
	    return "Hello " + name;
	}
	document.getElementById("demo").innerHTML = myFunction("John")
	</script>	

[Test Code](https://jsfiddle.net/vanbumi/vjvsw7hf/)

Example

	<h4>Define a function named "myFunction", and make it display "Hello World!" in the element.</h4>

	<p id="demo"></p>

	<script>
	  function myFunction() {
	  document.getElementById("demo").innerHTML = "Hello World!"; 
	  }
	  myFunction()
	</script>

[Test Code](https://jsfiddle.net/vanbumi/bnfhy4mx/)	

### Lesson 15 - JavaScript Objects

#### Real Life Objects, Properties, and Methods

In real life, a car is an object.

A car has properties like weight and color, and methods like start and stop:

![js object](http://res.cloudinary.com/medio/image/upload/v1467642574/object_bgyv81.png)

All cars have the same properties, but the property values differ from car to car.

All cars have the same methods, but the methods are performed at different times.

#### JavaScript Objects

You have already learned that JavaScript variables are containers for data values.

This code assigns a simple value (Fiat) to a variable named car:

	var car = "Fiat";

Objects are variables too. But objects can contain many values.

This code assigns many values (Fiat, 500, white) to a variable named car:

	var car = {type:"Fiat", model:"500", color:"white"};

	<p id="demo"></p>

	<script>
	  var car = {type:"Fiat", model:"500", color:"white"};
	  document.getElementById("demo").innerHTML = "Type of Car: " + car.type;
	</script>	

[Test Code](https://jsfiddle.net/vanbumi/ku4xrh6g/)

The values are written as name:value pairs (name and value separated by a colon).

> JavaScript objects are containers for named values.

#### Object Properties

The name:values pairs (in JavaScript objects) are called properties.

	var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

![object property](http://res.cloudinary.com/medio/image/upload/v1467643418/objectProperty_za2hlx.png)

#### Object Methods

Methods are actions that can be performed on objects.

Methods are stored in properties as function definitions.

Property	Property Value

firstName	John
lastName	Doe
age			50
eyeColor	blue
fullName	function() {return this.firstName + " " + this.lastName;}

> JavaScript objects are containers for named values (called properties) and methods.

#### Object Definition

You define (and create) a JavaScript object with an object literal:

Example

	var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

Example

	<p id="demo"></p>

	<script>
	  var person = {firstName:"John", lastName: "Doe", age:	50, 
	  eyeColor: "blue"};

		document.getElementById("demo").innerHTML = person.firstName + " is " + person.age + " years old";

	</script>

[Test Code](https://jsfiddle.net/vanbumi/tton98mq/)

Spaces and line breaks are not important. An object definition can span multiple lines:

Example

	var person = {
	    firstName:"John",
	    lastName:"Doe",
	    age:50,
	    eyeColor:"blue"
	};

[Test Code](https://jsfiddle.net/vanbumi/1uoc9q95/)	

#### Accessing Object Properties

You can access object properties in two ways:

	objectName.propertyName

or

	objectName["propertyName"]

Example1

	person.lastName;

[Test Code](https://jsfiddle.net/vanbumi/3n3v4jtu/)	

Example2

	person["lastName"];

[Test Code](https://jsfiddle.net/vanbumi/koxv66tz/)		

#### Accessing Object Methods

You access an object method with the following syntax:

	objectName.methodName()

Example

	name = person.fullName();

With the following code

	var karyawan = {
	  namaDepan: "Dyo",
	  namaBelakang: "Bumi",
	  umur: 37,
	  id: 222,
	  // create method
	  namaLengkap: function() {
	  	return this.namaDepan + " " + this.namaBelakang;
	  }
	};
	document.getElementById("coba").innerHTML = karyawan.namaLengkap();	

[Test Code](https://jsfiddle.net/vanbumi/m5eLryde/)

If you access the fullName property, without (), it will return the function definition:

	name = person.fullName;

[See Code](https://jsfiddle.net/vanbumi/gr5ff8s7/)

Exercise:

Create an object called person with name = John, age = 50.
Then, access the object to display "John is 50 years old".

Answwer

	var person = {
	  name: "John",
	  age: 50
	}
	document.getElementById("demo").innerHTML = person.name + " is " + person.age + " years old";	

[Test Code](https://jsfiddle.net/vanbumi/oyqv1vsu/)

#### Do Not Declare Strings, Numbers, and Booleans as Objects!

When a JavaScript variable is declared with the keyword "new", the variable is created as an object:

	var x = new String();        // Declares x as a String object
	var y = new Number();        // Declares y as a Number object
	var z = new Boolean();       //	Declares z as a Boolean object

Avoid String, Number, and Boolean objects. They complicate your code and slow down execution speed.

> Note	You will learn more about objects later in this tutorial.

next http://www.w3schools.com/js/js_scope.asp

## Skip for while

http://www.w3schools.com/js/js_loop_while.asp

Loops can execute a block of code as long as a specified condition is true.

#### The While Loop

The while loop loops through a block of code as long as a specified condition is true.

##### Syntax

	while (condition) {
	    code block to be executed
	}

Example

In the following example, the code in the loop will run, over and over again, as long as a variable (i) is less than 10:

Example

	while (i < 10) {
	    text += "The number is " + i;
	    i++;
	}

Example

	<button type="button" onclick="myFunction()">Try this</button>

	function myFunction() {
	    var text = "";
	    var i = 0;
	    while (i < 10) {
	        text += "<br>The number is " + i;
	        i++;
	    }
	    document.getElementById("demo").innerHTML = text;
	}	

[Test Code](https://jsfiddle.net/vanbumi/xc9p3fet/)

Other Example

	<p id="demo"></p>

	<script>
		var x = 0;
	  text = "";
	  while( x < 10) {
	    text += "<br> number is " + x ; 
	 		x++;
	    document.getElementById("demo").innerHTML = text;
	  }
	</script>













