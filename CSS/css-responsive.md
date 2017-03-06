Using The width Property
========================
If the width property is set to 100%, the image will be responsive and scale up and down:

    <!DOCTYPE html>
    <html>
    <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
    img {
        width: 100%;
        height: auto;
    }
    </style>
    </head>
    <body>

    <img src="img_chania.jpg" width="460" height="345">
    <p>Resize the browser window to see how the image will scale.</p>

    </body>
    </html>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Using The max-width Property
============================
If the max-width property is set to 100%, the image will scale down if it has to, but never scale up to be larger than its original size:


    <!DOCTYPE html>
    <html>
    <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        img {
            max-width: 100%;
            height: auto;
        }
    </style>
    </head>
    <body>

    <img src="img_chania.jpg" width="460" height="345">
    <p>Resize the browser window to see how the image wil scale when the width is less than 460px.</p>

    </body>
    </html>

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~



MEMBUAT UKURAN COL 

    <!DOCTYPE html>
    <html>
    <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
    * {
        box-sizing: border-box;
    }
    img {
        width: 100%;
        height: auto;
    }
    .row:after {
        content: "";
        clear: both;
        display: block;
    }
    [class*="col-"] {
        float: left;
        padding: 15px;
        width: 100%;
    }
    @media only screen and (min-width: 600px) {
        .col-s-1 {width: 8.33%;}
        .col-s-2 {width: 16.66%;}
        .col-s-3 {width: 25%;}
        .col-s-4 {width: 33.33%;}
        .col-s-5 {width: 41.66%;}
        .col-s-6 {width: 50%;}
        .col-s-7 {width: 58.33%;}
        .col-s-8 {width: 66.66%;}
        .col-s-9 {width: 75%;}
        .col-s-10 {width: 83.33%;}
        .col-s-11 {width: 91.66%;}
        .col-s-12 {width: 100%;}
    }
    @media only screen and (min-width: 768px) {
        .col-1 {width: 8.33%;}
        .col-2 {width: 16.66%;}
        .col-3 {width: 25%;}
        .col-4 {width: 33.33%;}
        .col-5 {width: 41.66%;}
        .col-6 {width: 50%;}
        .col-7 {width: 58.33%;}
        .col-8 {width: 66.66%;}
        .col-9 {width: 75%;}
        .col-10 {width: 83.33%;}
        .col-11 {width: 91.66%;}
        .col-12 {width: 100%;}
    }
    html {
        font-family: "Lucida Sans", sans-serif;
    }
    .header {
        background-color: #9933cc;
        color: #ffffff;
        padding: 15px;
    }
    .menu ul {
        list-style-type: none;
        margin: 0;
        padding: 0;
    }
    .menu li {
        padding: 8px;
        margin-bottom: 7px;
        background-color :#33b5e5;
        color: #ffffff;
        box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
    }
    .menu li:hover {
        background-color: #0099cc;
    }
    .aside {
        background-color: #33b5e5;
        padding: 15px;
        color: #ffffff;
        text-align: center;
        font-size: 14px;
        box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
    }
    .footer {
        background-color: #0099cc;
        color: #ffffff;
        text-align: center;
        font-size: 12px;
        padding: 15px;
    }
    </style>
    </head>
    <body>

    <div class="header">
    <h1>Chania</h1>
    </div>

    <div class="row">
    <div class="col-3 col-s-3 menu">
    <ul>
    <li>The Flight</li>
    <li>The City</li>
    <li>The Island</li>
    <li>The Food</li>
    </ul>
    </div>

    <div class="col-6 col-s-9">
    <h1>The City</h1>
    <p>Chania is the capital of the Chania region on the island of Crete. The city can be divided in two parts, the old town and the modern city.</p>
    <img src="img_chania.jpg" width="460" height="345">
    </div>

    <div class="col-3 col-s-12">
    <div class="aside">
    <h2>What?</h2>
    <p>Chania is a city on the island of Crete.</p>
    <h2>Where?</h2>
    <p>Crete is a Greek island in the Mediterranean Sea.</p>
    <h2>How?</h2>
    <p>You can reach Chania airport from all over Europe.</p>
    </div>
    </div>

    </div>

    <div class="footer">
    <p>Resize the browser window to see how the content respond to the resizing.</p>
    </div>

    </body>
    </html>



~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Background Images
=================
Background images can also respond to resizing and scaling.

Here we will show three different methods:

1. If the background-size property is set to "contain", the background image will scale, and try to fit the content area. However, the image will keep its aspect ratio (the proportional relationship between the image's width and height):

    <!DOCTYPE html>
    <html>
    <head>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
    div {
        width: 100%;
        height: 400px;
        background-image: url('img_flowers.jpg');
        background-repeat: no-repeat;
        background-size: contain;
        border: 1px solid red;
    }
    </style>
    </head>
    <body>

    <p>Resize the browser window to see the effect.</p>

    <div></div>

    </body>
    </html>


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


2. If the background-size property is set to "100% 100%", the background image will stretch to cover the entire content area:

div {
    width: 100%;
    height: 400px;
    background-image: url('img_flowers.jpg');
    background-size: 100% 100%;
    border: 1px solid red;
}

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

3. If the background-size property is set to "cover", the background image will scale to cover the entire content area. Notice that the "cover" value keeps the aspect ratio, and some part of the background image may be clipped:

div {
    width: 100%;
    height: 400px;
    background-image: url('img_flowers.jpg');
    background-size: cover;
    border: 1px solid red;
}


````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````````

Different Images for Different Devices
A large image can be perfect on a big computer screen, but useless on a small device. Why load a large image when you have to scale it down anyway? To reduce the load, or for any other reasons, you can use media queries to display different images on different devices.

Here is one large image and one smaller image that will be displayed on different devices:

read this more:
http://www.w3schools.com/css/css_rwd_images.asp





















