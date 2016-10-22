# CKEditor CDN

[Download](http://ckeditor.com/download)
[Usage](http://cdn.ckeditor.com/)

**Basic, Standard, Full Package**

	<script src="//cdn.ckeditor.com/4.5.11/basic/ckeditor.js"></script>

	<script src="//cdn.ckeditor.com/4.5.11/standard/ckeditor.js"></script>

	<script src="//cdn.ckeditor.com/4.5.11/full/ckeditor.js"></script>	

## Sample Usage

To start using CKEditor on your website, add a single &lt;script&gt; tag to your HTML page:

	<script src="//cdn.ckeditor.com/4.5.11/standard/ckeditor.js"></script>	

Quick example:

	<!DOCTYPE html>
	<html>
	    <head>
	        <meta charset="utf-8">
	        <title>CKEditor</title>
	        <script src="//cdn.ckeditor.com/4.5.11/standard/ckeditor.js"></script>
	    </head>
	    <body>
	        <textarea name="editor1"></textarea>
	        <script>
	            CKEDITOR.replace( 'editor1' );
	        </script>
	    </body>
	</html>	