# Google Maps API Tutorial

What is Google Maps?

Google Maps allows you to display maps on your web site:

![gooMap](http://res.cloudinary.com/medio/image/upload/v1468717498/goomap_ue8gqd.png)

## Google Maps API

This tutorial is about the Google Maps API (Application Programming Interface).

Google Maps API lets you customize maps, and the information on maps.

## Google Maps Basic

### Create a Basic Google Map

This example creates a Google Map centered in London, England:

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_first)

	<!DOCTYPE html>
	<html>
	<head>
	<script
	src="http://maps.googleapis.com/maps/api/js">
	</script>

	<script>
	function initialize() {
	  var mapProp = {
	    center:new google.maps.LatLng(51.508742,-0.120850),
	    zoom:5,
	    mapTypeId:google.maps.MapTypeId.ROADMAP
	  };
	  var map=new google.maps.Map(document.getElementById("googleMap"), mapProp);
	}
	google.maps.event.addDomListener(window, 'load', initialize);
	</script>
	</head>

	<body>
	<div id="googleMap" style="width:500px;height:380px;"></div>

	</body>
	</html>

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_first)	

the rest of this page describes the example above, step by step.

## 1. Load the Google API

The Google Maps API is a JavaScript library. It can be added to a web page with a &lt;script&gt; tag:

	<script src="http://maps.googleapis.com/maps/api/js"></script>

## 2. Set Map Properties

Create a function to initialize the map:

	function initialize() {
	}	

In the initialize function, create an object (mapProp) to define the properties for the map:

	 var mapProp = {
	  center:new google.maps.LatLng(51.508742, -0.120850),
	  zoom: 7,
	  mapTypeId: google.maps.MapTypeId.ROADMAP
	};	

The **center** property specifies where to center the map. Create a LatLng object to center the map on a specific point. Pass the coordinates in the order: latitude, longitude.

The **zoom** property specifies the zoom level for the map. zoom: 0 shows a map of the Earth fully zoomed out. Higher zoom levels zoom in at a higher resolution.

The **mapTypeId** property specifies the map type to display. The following map types are supported:

* ROADMAP (normal, default 2D map)
* SATELLITE (photographic map)
* HYBRID (photographic map + roads and city names)
* TERRAIN (map with mountains, rivers, etc.)

## 3. Create a Map Container

Create a &lt;div&gt; element to hold the map. Use CSS to size the element:

	<div id="googleMap" style="width:500px;height:380px;"></div>

Note	The map will always "inherit" its size from its container element.

## 4. Create a Map Object

	var map=new google.maps.Map(document.getElementById("googleMap"), mapProp);

or do like this:

 	var loc = document.getElementById("googleMap");
  	var map=new google.maps.Map(loc, mapProp);	

The code above creates a new map inside the &lt;div&gt; element with id="googleMap", using the parameters that are passed (mapProp).

## 5. Add an Event Listener to Load the Map

Add a DOM listener that will execute the initialize() function on window load (when the page is loaded):

	google.maps.event.addDomListener(window, 'load', initialize);

## Asynchronously Loading

It is also possible to load the Google Maps API on demand.

The example below uses window.onload to load the Google Maps API after the page has fully loaded.

The loadScript() function creates the Google Maps API &lt;script&gt; tag. In addition, the callback=initialize parameter is added to the end of the URL to execute the initialize() function after the API is fully loaded:

Example

	function loadScript() {
	  var script = document.createElement("script"); 
	  script.src = "http://maps.googleapis.com/maps/api/js?callback=initialize";
	  document.body.appendChild(script);
	}

	window.onload = loadScript;

Detail Code

	<script>
		function initialize()
		{
		  var mapProp = {
		    center: new google.maps.LatLng(51.508742,-0.120850),
		    zoom:7,
		    mapTypeId: google.maps.MapTypeId.ROADMAP
		  };
		  var map = new google.maps.Map(document.getElementById("googleMap"),mapProp);
		}

		//create API link
		function loadScript()
		{
		  var script = document.createElement("script"); //to create element div
		  script.type = "text/javascript";
		  script.src = "http://maps.googleapis.com/maps/api/js?key=&sensor=false&callback=initialize";
		  document.body.appendChild(script);
		}

		window.onload = loadScript;
	</script>

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_async)

## Multiple Maps

The example below defines four maps on one web page (four maps with different map types):

Example

	var map1 = new google.maps.Map(document.getElementById("googleMap1"), mapProp1);
	var map2 = new google.maps.Map(document.getElementById("googleMap2"), mapProp2);
	var map3 = new google.maps.Map(document.getElementById("googleMap3"), mapProp3);
	var map4 = new google.maps.Map(document.getElementById("googleMap4"), mapProp4);

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_many)	

## Google API Key

Google allows your web site to call any Google API, many thousand times per day.

If you plan for heavier traffic, you should get a free API key from Google.

Go to https://console.developers.google.com to get a free key.

Google Maps expects to find the API key in the key parameter when loading an API:

	<script src="http://maps.googleapis.com/maps/api/js?key=YOUR_KEY"></script>

## Google Maps Overlays	

![](http://res.cloudinary.com/medio/image/upload/v1468717498/goomap_ue8gqd.png)

Overlays are objects on the map that are bound to latitude/longitude coordinates.

Google Maps has several types of overlays:

* Marker - Single locations on a map. Markers can also display custom icon images
* Polyline - Series of straight lines on a map
* Polygon - Series of straight lines on a map, and the shape is "closed"
* Circle and Rectangle
* Info Windows - Displays content within a popup balloon on top of a map
* Custom overlays

## Google Maps - Add a Marker

The Marker constructor creates a marker. (Note that the position property must be set for the marker to display).

Add the marker to the map by using the setMap() method:

Example

	var marker=new google.maps.Marker({
	  position:myCenter,
	  });

	marker.setMap(map);

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_overlays_marker)

## Google Maps - Animate the Marker

The example below shows how to animate the marker with the animation property:

Example

	var marker=new google.maps.Marker({
	  position:myCenter,
	  animation:google.maps.Animation.BOUNCE
	  });

	marker.setMap(map);

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_overlays_animate)	

## Google Maps - Icon Instead of Marker

The example below specifies an image (icon) to use instead of the default marker:

Example

	var marker=new google.maps.Marker({
	  position:myCenter,
	  icon:'pinkball.png'
	  });

	marker.setMap(map);

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_overlays_icon)

## Google Maps - Polyline

A Polyline is a line that is drawn through a series of coordinates in an ordered sequence.

A polyline supports the following properties:

* path - specifies several latitude/longitude coordinates for the line
* strokeColor - specifies a hexadecimal color for the line (format: "#FFFFFF")
* strokeOpacity - specifies the opacity of the line (a value between 0.0 and 1.0)
* strokeWeight - specifies the weight of the line's stroke in pixels
* editable - defines whether the line is editable by users (true/false)

Example

	var myTrip = [stavanger,amsterdam,london];
	var flightPath = new google.maps.Polyline({
	  path:myTrip,
	  strokeColor:"#0000FF",
	  strokeOpacity:0.8,
	  strokeWeight:2
	});

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_overlays_polygon)

## Google Maps - Circle

A circle supports the following properties:

* center - specifies the google.maps.LatLng of the center of the circle
* radius - specifies the radius of the circle, in meters
* strokeColor - specifies a hexadecimal color for the line around the circle (format: "#FFFFFF")
* strokeOpacity - specifies the opacity of the stroke color (a value between 0.0 and 1.0)
* strokeWeight - specifies the weight of the line's stroke in pixels
* fillColor - specifies a hexadecimal color for the area within the circle (format: "#FFFFFF")
* fillOpacity - specifies the opacity of the fill color (a value between 0.0 and 1.0)
* editable - defines whether the circle is editable by users (true/false)

Example

	var myCity = new google.maps.Circle({
	  center:amsterdam,
	  radius:20000,
	  strokeColor:"#0000FF",
	  strokeOpacity:0.8,
	  strokeWeight:2,
	  fillColor:"#0000FF",
	  fillOpacity:0.4
	});

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_overlays_circle)

## Google Maps - InfoWindow

Show an InfoWindow with some text content for a marker:

Example

	var infowindow = new google.maps.InfoWindow({
	  content:"Hello World!"
	  });

	infowindow.open(map,marker);

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_overlays_infowindow)

## Google Maps - Overlays Reference

[Google Maps API Reference.](http://www.w3schools.com/googleapi/google_maps_ref.asp)

## Google Maps Events

### Click the marker to zoom - attach event handlers to Google maps.

### Click The Marker to Zoom

We still use the map from the previous page: a map centered on London, England.

Now we want to zoom when a user is clicking on the marker (We attach an event handler to a marker that zooms the map when clicked).

Here is the added code:

Example

	// Zoom to 9 when clicking on marker
	google.maps.event.addListener(marker,'click',function() {
	  map.setZoom(9);
	  map.setCenter(marker.getPosition());
	  });

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_marker_click)

We register for event notifications using the addListener() event handler. That method takes an object, an event to listen for, and a function to call when the specified event occurs.

## Pan Back to Marker

Here, we add an event handler to the map for changes to the 'center' property and pan the map back to the marker after 3 seconds on a center_changed event:

Example

	google.maps.event.addListener(map,'center_changed',function() {
	  window.setTimeout(function() {
	    map.panTo(marker.getPosition());
	  },3000);
	});

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_marker_pan)

## Open an InfoWindow When Clicking on The Marker

Click on the marker to show an infowindow with some text:

Example

	var infowindow = new google.maps.InfoWindow({
	  content:"Hello World!"
	  });

	google.maps.event.addListener(marker, 'click', function() {
	  infowindow.open(map,marker);
	  });

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_marker_infowindow)	  

## Set Markers and Open InfoWindow for Each Marker

Run a function when the user clicks on the map.

The **placeMarker()** function places a marker where the user has clicked, and shows an infowindow with the latitudes and longitudes of the marker:

Example

	google.maps.event.addListener(map, 'click', function(event) {
	  placeMarker(event.latLng);
	  });

	function placeMarker(location) {
	  var marker = new google.maps.Marker({
	    position: location,
	    map: map,
	  });
	  var infowindow = new google.maps.InfoWindow({
	    content: 'Latitude: ' + location.lat() +
	    '<br>Longitude: ' + location.lng()
	  });
	  infowindow.open(map,marker);
	}

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_marker_infowindow2)

## Google Maps - Events Reference

[Google Maps API Reference.](http://www.w3schools.com/googleapi/google_maps_ref.asp)

## Google Maps Controls

A Google map - with the default control set:

### Google Maps - The Default Controls

When showing a standard Google map, it comes with the default control set:

# Zoom - displays a slider or "+/-" buttons to control the zoom level of the map
# Pan - displays a pan control for panning the map
# MapType - lets the user toggle between map types (roadmap and satellite)
# Street View - displays a Pegman icon which can be dragged to the map to enable Street View

### Google Maps - More Controls

In addition to the default controls, Google Maps also has:

* Scale - displays a map scale element
* Rotate - displays a small circular icon which allows you to rotate maps
* Overview Map - displays a thumbnail overview map reflecting the current map viewport within a wider area.

You can specify which controls to show when creating the map (inside MapOptions) or by calling setOptions() to change the map's options.

### Google Maps - Disabling The Default Controls

You may instead wish to turn off the default controls.

To do so, set the Map's disableDefaultUI property (within the Map options object) to true:

Example

	disableDefaultUI:true

Detail Code

	function initialize()
	{
	  var mapProp = {
	    center: new google.maps.LatLng(51.508742,-0.120850),
	    zoom:7,
	    disableDefaultUI:true,
	    mapTypeId: google.maps.MapTypeId.ROADMAP
	  };
	  var map = new google.maps.Map(document.getElementById("googleMap"),mapProp);
	}
	google.maps.event.addDomListener(window, 'load', initialize);

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_controls_disable)

### Google Maps - Turn On All Controls

Some controls appear on the map by default; while others will not appear unless you set them.

Adding or removing controls from the map is specified in the Map options object.

Set the control to true to make it visible - Set the control to false to hide it.

The following example turns "on" all controls:

Example

	panControl:true,
	zoomControl:true,
	mapTypeControl:true,
	scaleControl:true,
	streetViewControl:true,
	overviewMapControl:true,
	rotateControl:true

[Test Code](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_controls_add)

### Google Maps - Modifying Controls

Several of the map controls are configurable.

The controls can be modified by specifying control options fields.

For example, options for modifying a Zoom control are specified in the zoomControlOptions field. The zoomControlOptions field may contain:

google.maps.ZoomControlStyle.SMALL - displays a mini-zoom control (only + and - buttons)
google.maps.ZoomControlStyle.LARGE - displays the standard zoom slider control
google.maps.ZoomControlStyle.DEFAULT - picks the best zoom control based on device and map size

Example

	zoomControl:true,
	zoomControlOptions: {
	    style:google.maps.ZoomControlStyle.SMALL
	}

[](http://www.w3schools.com/googleapi/tryit.asp?filename=tryhtml_map_controls_modify1)	

last http://www.w3schools.com/googleapi/google_maps_controls.asp