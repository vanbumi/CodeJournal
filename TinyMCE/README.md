# TinyMCE

[Getting Started](https://www.tinymce.com/docs/get-started/first-steps/)

## Install Plugin

	<!--tinyMCE-->
    <script src='//cdn.tinymce.com/4/tinymce.min.js'></script>
    <script>
      tinymce.init({
        selector: "textarea",  // change this value according to your HTML
        plugins: [
          "image", "code", "media", "emoticons"
        ],
        toolbar: [
          "newdocument | bold | italic | underline | strikethrough | alignleft | aligncenter | alignright | alignjustify | styleselect | formatselect | fontselect | fontsizeselect | cut | copy | paste | bullist | numlist | outdent | indent | blockquote | undo | redo | removeformat | subscript | superscript | image | emoticons | code | media |",
        ]
      });
    </script>

## Content Appearance

Configure the appearance of content inside TinyMCe's editable area.

[content_css](https://www.tinymce.com/docs/configure/content-appearance/#content_css)
