# W3c Games Tutorial

## Game Canvas

The HTML &lt;canvas&gt; element is displayed as a rectangular object on a web page:

### HTML Canvas

* The &lt;canvas&gt; element is perfect for making games in HTML.

* The &lt;canvas&gt; element offers all the functionality you need for making games.

* Use JavaScript to draw, write, insert images, and more, onto the &lt;canvas&gt;.

### .getContext("2d")

The &lt;canvas&gt; element has a built-in object, called the getContext("2d") object, with methods and properties for drawing.

You can learn more about the &lt;canvas&gt; element, and the getContext("2d") object, in our Canvas Tutorial.	

### Get Started

To make a game, start by creating a gaming area, and make it ready for drawing:

	<style>
	canvas {
	    border: 1px solid #d3d3d3;
	    background-color: #f1f1f1;
	}
	</style>
	</head>
	
	<body onload="startGame()">
	
	<script>

	function startGame() {
	    myGameArea.start();
	}

	var myGameArea = {
	    canvas : document.createElement("canvas"),
	    // create method start
	    start : function() {
	        this.canvas.width = 480;
	        this.canvas.height = 270;
	        this.context = this.canvas.getContext("2d");
	        document.body.insertBefore(this.canvas, document.body.childNodes[0]);
	    }
	}

	</script>

The object **myGameArea** will have more properties and methods later in this tutorial.

The function **startGame()** invokes the method **start()** of the **myGameArea** object.

The **start()** method creates a **&lt;canvas&gt;** element and inserts it as the first childnode of the **&lt;body&gt;** element.

## Game Components

### Add a Component

Make a component constructor, which lets you add components onto the gamearea.

The object constructor is called component, and we make our first component, called myGamePiece:
