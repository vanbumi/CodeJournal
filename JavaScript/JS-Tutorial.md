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