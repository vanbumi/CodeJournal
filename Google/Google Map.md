<h1 id="home">Google Map</h1>

## Content:

<ul>
	<li><a href="#home">Home</a></li>
	<li><a href="#tutgoomap">Tutorial Google Maps</a></li>
</ul>


Ref:

* [Tutorial](https://developers.google.com/maps/)
* [How to create a Basic Google Maps](http://findnerd.com/list/view/How-to-create-a-Basic-Google-Maps/17490/)
* [Google Maps API Tutorial - w3School](http://www.w3schools.com/googleapi/default.asp)
* [I follow this](http://www.tutorialspoint.com/google_maps/index.htm)
* [jQuery Google Map](http://tilotiti.github.io/jQuery-Google-Map/)
* [jQuer Google Map](https://hpneo.github.io/gmaps/)


	
<h3 id="tutgoomap">Tutorial Google Maps</h3>

Learn how to add a Google Map to a web page.

A Basic Web Page

### All web page are written in HTML.

To demonstrate how to add a Google Map to a web page, we will use a simple basic web page:

Example

	<!DOCTYPE html>
	<html>
	<body>

	<h1>My First Google Map</h1>

	<div id="map">My map will go here</div>

	</body>
	<html>

[Test Code](http://www.w3schools.com/howto/tryit.asp?filename=tryhow_google_map_1)		

### Set the Map Size

Set the size of the map:

Example

	<div id="map" style="width:400px;height:400px">

[Test Code](http://www.w3schools.com/howto/tryit.asp?filename=tryhow_google_map_2)	

### Add the Google API

The functionality of the map is provided by a JavaScript library located at Google.

The JavaScript library can be loaded in the <head> section of the HTML page.

> Note	Actually you can drop the <head> and </head> tags.

Example

	<head>
		<script src="https://maps.googleapis.com/maps/api/js"></script>
	</head>

[Test Code](http://www.w3schools.com/howto/tryit.asp?filename=tryhow_google_map_3)

### Create the Map Using JavaScript

Finally add the necessary JavaScript to the page:

Example

	var mapCanvas = document.getElementById("map");
	var mapOptions = {
	    center: new google.maps.LatLng(51.5, -0.2), zoom: 10
	}
	var map = new google.maps.Map(mapCanvas, mapOptions);

[Test Code](http://www.w3schools.com/howto/tryit.asp?filename=tryhow_google_map_4)	

### Example Explained

mapCanvas is the map's HTML element.

mapOptions is the map's options.

The center property gets the latitude and longitude (of London) by calling google.maps.LatLng().

The zoom property is set to 10. (try to experiment with the zoom)

The google.maps.Map object is created with mapCanvas and mapOptions as parameters.

Go to our [Google Maps API Tutorial](http://www.w3schools.com/howto/tryit) to learn more about Google Maps.