<h1 id="home">jQuery - AJAX</h1>

## Content

<ul>
	<li><a href="#home">Home</a></li>
	<li><a href="^lesson1">jQuery - AJAX Introduction</a></li>
</ul>

<h2 id="lesson1">jQuery - AJAX Introduction</h2>

AJAX is the art of exchanging data with a server, and updating parts of a web page - without reloading the whole page.

jQuery AJAX Example

	jQuery and AJAX is FUN!
	This is some text in a paragraph.

[Test Code](http://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_ajax_load)

### What is AJAX?

AJAX = Asynchronous JavaScript and XML.

In short; AJAX is about loading data in the background and display it on the webpage, without reloading the whole page.

Examples of applications using AJAX: Gmail, Google Maps, Youtube, and Facebook tabs.

You can learn more about AJAX in our AJAX tutorial.

### What About jQuery and AJAX?

jQuery provides several methods for AJAX functionality.

With the jQuery AJAX methods, you can request text, HTML, XML, or JSON from a remote server using both HTTP Get and HTTP Post - And you can load the external data directly into the selected HTML elements of your web page!

> **Without jQuery, AJAX coding can be a bit tricky!** 
Writing regular AJAX code can be a bit tricky, because different browsers have different syntax for AJAX implementation. This means that you will have to write extra code to test for different browsers. However, the jQuery team has taken care of this for us, so that we can write AJAX functionality with only one single line of code.

### jQuery AJAX Methods

In the next chapters we will look at the most important jQuery AJAX methods.

<h2 id="lesson2">jQuery - AJAX load() Method</h2>

The jQuery load() method is a simple, but powerful AJAX method.

The load() method loads data from a server and puts the returned data into the selected element.

Syntax:

	$(selector).load(URL,data,callback);

The required URL parameter specifies the URL you wish to load.

The optional data parameter specifies a set of querystring key/value pairs to send along with the request.

The optional callback parameter is the name of a function to be executed after the load() method is completed.

Here is the content of our example file: "demo_test.txt":

	<h2>jQuery and AJAX is FUN!!!</h2>
	<p id="p1">This is some text in a paragraph.</p>

The following example loads the content of the file "demo_test.txt" into a specific <div> element:

Example

	$("#div1").load("demo_test.txt");

[Test Code](http://www.w3schools.com/jquery/tryit.asp?filename=tryjquery_ajax_load)














