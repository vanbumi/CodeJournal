<h1 id="home">AJAX Tutorial</h1>

## Contents

<ul>
	<li><a href="#home">Home</a></li>
	<li><a href="#intro">Introduction</a></li>
	<li><a href="#lesson1">Ajax XMLHttp</a></li>
	<li><a href="#lesson2">Ajax Request</a></li>
	<li><a href="#lesson3">Ajax Response</a></li>
	<li><a href="#home">Home</a></li>
</ul>

## With Ajax you can:

* Update a web page without reloading the page
* Request data from a server - after the page has loaded 
* Receive data from a server - after the page has loaded
* Send data to a server - in the background

<h2 id="intro">AJAX Introduction</h2>

AJAX is about updating parts of a web page, without reloading the whole page.

### What You Should Already Know

Before you continue you should have a basic understanding of the following:

* HTML
* JavaScript

### What is AJAX?

AJAX = Asynchronous JavaScript and XML.

> AJAX is a misleading name. You don't have to understand XML to use AJAX.

AJAX is a technique for creating fast and dynamic web pages.

AJAX allows web pages to be updated asynchronously by exchanging small amounts of data with the server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

Classic web pages, (which do not use AJAX) must reload the entire page if the content should change.

Examples of applications using AJAX: Google Maps, Gmail, YouTube, and Facebook.

How AJAX Works

![ajax](http://res.cloudinary.com/medio/image/upload/v1468251169/ajax_bcle6y.gif)

### AJAX is Based on Internet Standards

AJAX is based on internet standards, and uses a combination of:

* XMLHttpRequest object (to retrieve data from a web server)
* JavaScript/DOM (to display/use the data)

> Note	XMLHttpRequest is a misleading name. You don't have to understand XML to use AJAX.

### Google Suggest

AJAX was made popular in 2005 by Google, with Google Suggest.

Google Suggest is using AJAX to create a very dynamic web interface: When you start typing in Google's search box, a JavaScript sends the letters off to a server and the server returns a list of suggestions.

### Start Using AJAX Today

AJAX is based on existing standards. These standards have been used by developers for several years. Read our next chapters to see how it works!

---

<h2 id="lesson1">Lesson 1 - Create an XMLHttpRequest Object</h2>

The keystone of AJAX is the **XMLHttpRequest object**.

### The XMLHttpRequest Object

All modern browsers support the XMLHttpRequest object.

The XMLHttpRequest object is used to exchange data with a server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.

### Create an XMLHttpRequest Object

All modern browsers (Chrome, IE7+, Firefox, Safari, and Opera) have a built-in XMLHttpRequest object.

#### Syntax for creating an XMLHttpRequest object:

	variable = new XMLHttpRequest();

Old versions of Internet Explorer (IE5 and IE6) use an ActiveX Object:

	variable = new ActiveXObject("Microsoft.XMLHTTP");

To handle all browsers, including IE5 and IE6, check if the browser supports the XMLHttpRequest object. If it does, create an XMLHttpRequest object, if not, create an ActiveXObject:

	var xhttp;
	if (window.XMLHttpRequest) {
	    xhttp = new XMLHttpRequest();
	    } else {
	    // code for IE6, IE5
	    xhttp = new ActiveXObject("Microsoft.XMLHTTP");
	}

[Test Code](http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_ie)

In the next chapter you will learn about sending server requests.

---

<h2 id="lesson2">Lesson 2 - Send a Request To a Server</h2>

The **XMLHttpRequest object** is used to exchange data with a server.

### Send a Request To a Server

To send a request to a server, we use the open() and send() methods of the **XMLHttpRequest object**:

	xhttp.open("GET", "ajax_info.txt", true);
	xhttp.send();

Table	

	Method						Description

	open(method, url, async)	Specifies the type of request

								method: the type of request: GET or POST
								url: the server (file) location
								async: true (asynchronous) or false (synchronous)

	send()						Sends the request to the server (used for GET)

	send(string)				Sends the request to the server (used for POST)	

### GET or POST?

GET is simpler and faster than POST, and can be used in most cases.

However, always use POST requests when:

* A cached file is not an option (update a file or database on the server).
* Sending a large amount of data to the server (POST has no size limitations).
* Sending user input (which can contain unknown characters), **POST is more robust and secure than GET**.

### GET Requests

A simple GET request:

Example

	xhttp.open("GET", "demo_get.asp", true);
	xhttp.send();

Detail Code

	<h2>AJAX</h2>

	<button type="button" onclick="loadDoc()">Request data</button>

	<p id="demo"></p>

	<script>
	function loadDoc() {
	  var xhttp = new XMLHttpRequest();
	  xhttp.onreadystatechange = function() {
	    if (xhttp.readyState == 4 && xhttp.status == 200) {
	      document.getElementById("demo").innerHTML = xhttp.responseText;
	    }
	  };
	  xhttp.open("GET", "demo_get.asp", true);
	  xhttp.send();
	}
	</script>	

[Test Code](http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_get)

In the example above, you may get a cached result. To avoid this, add a unique ID to the URL:

Example

	xhttp.open("GET", "demo_get.asp?t=" + Math.random(), true);
	xhttp.send();
		
Detail Code

	<h2>AJAX</h2>

	<button type="button" onclick="loadDoc()">Request data</button>

	<p>Click the button several times to see if the time changes, or if the file is cached.</p>

	<p id="demo"></p>

	<script>
	function loadDoc() {
	  var xhttp = new XMLHttpRequest();
	  xhttp.onreadystatechange=function() {
	    if (xhttp.readyState == 4 && xhttp.status == 200) {
	      document.getElementById("demo").innerHTML = xhttp.responseText;
	    }
	  };
	  xhttp.open("GET", "demo_get.asp?t=" + Math.random(), true);
	  xhttp.send();
	}
	</script>

[Test Code](http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_get_unique)

If you want to send information with the GET method, add the information to the URL:

Example

	xhttp.open("GET", "demo_get2.asp?fname=Henry&lname=Ford", true);
	xhttp.send();

Detail Code

	<h2>AJAX</h2>

	<button type="button" onclick="loadDoc()">Request data</button>

	<p id="demo"></p>

	<script>
	function loadDoc() {
	  var xhttp = new XMLHttpRequest();
	  xhttp.onreadystatechange = function() {
	    if (xhttp.readyState == 4 && xhttp.status == 200) {
	      document.getElementById("demo").innerHTML = xhttp.responseText;
	    }
	  };
	  xhttp.open("GET", "demo_get2.asp?fname=Henry&lname=Ford", true);
	  xhttp.send();
	}
	</script>

[Test Code](http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_get2)

## POST Requests

A simple POST request:

Example

	xhttp.open("POST", "demo_post.asp", true);
	xhttp.send();

Detail Code

	<h2>AJAX</h2>

	<button type="button" onclick="loadDoc()">Request data</button>

	<p id="demo"></p>
	 
	<script>
	function loadDoc() {
	  var xhttp = new XMLHttpRequest();
	  xhttp.onreadystatechange = function() {
	    if (xhttp.readyState == 4 && xhttp.status == 200) {
	      document.getElementById("demo").innerHTML = xhttp.responseText;
	    }
	  };
	  xhttp.open("POST", "demo_post.asp", true);
	  xhttp.send();
	}
	</script>

[Test Code](http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_post)

To POST data like an HTML form, add an **HTTP header** with **setRequestHeader()**. Specify the data you want to send in the send() method:

Example

	xhttp.open("POST", "ajax_test.asp", true);
	xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
	xhttp.send("fname=Henry&lname=Ford");

Detail Code

	<h2>AJAX</h2>

	<button type="button" onclick="loadDoc()">Request data</button>

	<p id="demo"></p>
	 
	<script>
	function loadDoc() {
	  var xhttp = new XMLHttpRequest();

	  xhttp.onreadystatechange = function() {
	    if (xhttp.readyState == 4 && xhttp.status == 200) {
	      document.getElementById("demo").innerHTML = xhttp.responseText;
	    }
	  };

	  xhttp.open("POST", "demo_post2.asp", true);
	  xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
	  xhttp.send("fname=Henry&lname=Ford");
	}
	</script>

[Test Code](http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_post2)

	Method								Description

	setRequestHeader(header, value)		Adds HTTP headers to the request

										header: specifies the header name
										value: specifies the header value

### The url - A File On a Server

The url parameter of the open() method, is an address to a file on a server:

	xhttp.open("GET", "ajax_test.asp", true);

The file can be any kind of file, like .txt and .xml, or server scripting files like .asp and .php (which can perform actions on the server before sending the response back).

### Asynchronous - True or False?

AJAX stands for Asynchronous JavaScript and XML, and for the **XMLHttpRequest object** to behave as AJAX, the async parameter of the open() method has to be set to true:

	xhttp.open("GET", "ajax_test.asp", true);

Sending asynchronous requests is a huge improvement for web developers. Many of the tasks performed on the server are very time consuming. Before AJAX, this operation could cause the application to hang or stop.

With AJAX, the JavaScript does not have to wait for the server response, but can instead:

* execute other scripts while waiting for server response
* deal with the response when the response ready

### Async=true

When using async=true, specify a function to execute when the response is ready in the onreadystatechange event:

Example

	xhttp.onreadystatechange = function() {
	  if (xhttp.readyState == 4 && xhttp.status == 200) {
	    document.getElementById("demo").innerHTML = xhttp.responseText;
	  }
	};
	xhttp.open("GET", "ajax_info.txt", true);
	xhttp.send();

[Test Code](http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_first)

You will learn more about onreadystatechange in a later chapter.

### Async=false

To use async=false, change the third parameter in the open() method to false:

	xhttp.open("GET", "ajax_info.txt", false);

Using async=false is not recommended, but for a few small requests this can be ok.

Remember that the JavaScript will NOT continue to execute, until the server response is ready. If the server is busy or slow, the application will hang or stop.

Note: When you use async=false, do NOT write an onreadystatechange function - just put the code after the send() statement:

Example

	xhttp.open("GET", "ajax_info.txt", false);
	xhttp.send();
	document.getElementById("demo").innerHTML = xhttp.responseText;

Detail Code

	<p id="demo">Let AJAX change this text.</p>

	<button type="button" onclick="loadDoc()">Change Content</button>

	<script>
	function loadDoc() {
	  var xhttp = new XMLHttpRequest();
	  xhttp.open("GET", "ajax_info.txt", false);
	  xhttp.send();
	  document.getElementById("demo").innerHTML = xhttp.responseText;
	}
	</script>

[Test Code](http://www.w3schools.com/ajax/tryit.asp?filename=tryajax_asyncfalse)

<h2 id="lesson3">Lesson 3 - Ajax Server Response</h2>





