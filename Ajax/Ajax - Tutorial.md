# AJAX Tutorial

## With Ajax you can:

* Update a web page without reloading the page
* Request data from a server - after the page has loaded 
* Receive data from a server - after the page has loaded
* Send data to a server - in the background

## AJAX Introduction

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

## AJAX - Create an XMLHttpRequest Object

The keystone of AJAX is the XMLHttpRequest object.

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

## AJAX - Send a Request To a Server

The XMLHttpRequest object is used to exchange data with a server.

### Send a Request To a Server

To send a request to a server, we use the open() and send() methods of the XMLHttpRequest object:

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

next GET or POST? http://www.w3schools.com/ajax/ajax_xmlhttprequest_send.asp

	