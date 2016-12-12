# Creating your first website 
## Part 1: Set up your site and project files

### Understanding Dreamweaver sites

In Dreamweaver, a site organizes on your local computer all the documents associated with your website and lets you track and maintain links, manage files, share files, and transfer your site files to a web server. Think of your Dreamweaver site as the "bucket" that contains all of the files and assets for your website.

A typical Dreamweaver site has at least two parts:

Local Folder: This is your working directory. Dreamweaver refers to this folder as your local site. The local folder is usually a folder on your hard drive.

Remote Folder: This is where you store your files on the computer that is running your web server. The computer running the web server is often (but not always) the computer that makes your site publicly available on the web.

For more information about Dreamweaver sites in general, see [Site management](https://helpx.adobe.com/dreamweaver/topics/site-management.html) in Dreamweaver Help.

### Set up your project files

When you create a local site, you can place any existing assets (images or other pieces of content) in the local site's root folder (the main folder for the site). That way when you add content to your pages, the assets are there and ready for you to use.
The sample files for this article contain assets for the sample website you'll build in this tutorial series. The first step is to copy these assets to an appropriate folder on your hard drive:

1. Decide where you want to store your website files on your hard drive. For example:
	* On Windows, you can use C:\Sites
	* On Mac OS X your home folder already includes a folder named Sites.
2. Download and unzip the first_website_pt1.zip sample files from the link at the top of this page if you haven't done so already. Copy the check_cs6 folder into the Sites folder.
3. You will use the check_cs6 folder as the root folder (main folder) for your Dreamweaver site.

### Define the local site folder for the Check Magazine site

1. Start Dreamweaver and choose Site > New Site. The Site Setup dialog box appears.
2. For the Site Name, type Check Magazine as the name of the site. The name is used internally by Dreamweaver to identify the site. It doesn’t matter if it contains spaces.
3. Click the folder icon next to Local Site Folder to browse to and select the check_cs6 folder (see Figure 1).
4. Click Save. That's it!

The Files panel in Dreamweaver now shows the new local root folder for your current site (see Figure 2). The file list in the Files panel acts as a file manager, enabling you to copy, paste, delete, move, and open files just as you would on a desktop.

### Best practices for naming files and folders in a website

* File and folder names in websites should never contain spaces or any of the following characters: /\?%*:|”<>.
* Although other special characters are permitted, it’s generally a good idea to use only alphanumeric characters, hyphens, and underscores.
* Most file and folder names end up as part of a web page’s URL, so keep them short, but meaningful. Long URLs are difficult for users to remember and type into browsers on a mobile device.

## Part 2: Creating the page structure

Part 2 explains how to create a **CSS-based** page layout in Adobe Dreamweaver CS6. *A page layout determines how your page will appear in the browser*, showing, for example, the placement of menus, images, and other kinds of content.

Laying out web pages with CSS (Cascading Style Sheets) has become the standard for modern web design. CSS offers superior flexibility and control over your layout, enabling you to create elements on the page and fine-tune their positions with pixel precision. However, CSS layouts can be difficult to understand and create, and it helps to have some background knowledge before building your first layout with CSS. You can start by reading [CSS page layout basics]()http://www.adobe.com/devnet/dreamweaver/articles/css_page_layout_basics.html, which is an overview of how CSS layouts work. But this reading is not required. If you're up for the challenge, you can just dive right into this tutorial to begin creating your first CSS-based layout.

Evaluate the task ahead

Typically, you don't begin building a website by opening Dreamweaver and laying out pages. The first steps to creating a website begin on a piece of paper or in a graphics-editing application such as Adobe Fireworks or Adobe Photoshop. Graphic designers usually sketch out a piece of comprehensive artwork (also known as a comp) for the website to show it to the client and make sure that the initial ideas for the site meet with their client's approval.

**Examine the comp**

A comp consists of any number of page elements that the client has requested for a website. For example, the client might say, "I want to have a logo at the top of the page, a navigation bar that links to these other pages, a section for an online store, and a place where I can insert video clips." Based on that discussion, the designer begins planning the layout of the site and creates sketches of sample pages that fulfill the client's requirements.
This tutorial provides you with the completed and approved comp for the home page of Check Magazine, a fictional publication that is in need of a website (see Figure 1). As the web designer, your job is to transform the comp into a working web page (most likely with the help of other graphic designers).

You'll notice that the graphic designer has provided you with a web page comp that includes a number of content areas, as well as some graphic ideas. Note also that the text is lorem ipsum text (fake Latin placeholder text) and that the headings in the bottom columns are not final (two of them are identical). Even though the page content is unknown at this point, you can still use Dreamweaver to lay out this design.
You can also open the original comp file if you want to see it in more detail. You can find the comp, check_comp.jpg, in the check_cs6/images folder that you copied to your hard drive in Part 1 of this tutorial series. You might even want to print the comp so that you can have it in front of you as you build your page.

More and more people are accessing websites on a wide range of screen resolutions from mobile phones through tablets to laptops and desktops. Creating a website design that adapts to different screen sizes requires considerable CSS knowledge and skills. To keep this tutorial relatively simple and focused on creating your first website, you’ll work with a fixed-width display designed for a desktop.

What to do if things go wrong

When learning new techniques or working with unfamiliar software, it’s easy to make mistakes. The instructions throughout this tutorial series try to anticipate common errors, and each part contains a ZIP file showing how the code should look when you have finished. If your page doesn’t look the way you expect, use the Dreamweaver File Compare feature to compare your files with the download versions. To use File Compare, you need a third-party file comparison utility, such as WinMerge for Windows. On a Mac, you can use the file comparison tool in TextWrangler. Both are free.

The most common causes of mistakes are accidentally skipping a step in the instructions and mistyping an ID or CSS property. Retrace your steps to see where you might have gone wrong. Sometimes, the best idea is to start again from scratch. It can be frustrating, but you can learn a great deal from your mistakes.
Of course, if you do get stuck, ask for help. The best place is in the Dreamweaver General Discussion Forum, where you’ll find experts and beginners alike helping each other.
Above all, enjoy yourself. Web design can sometimes be challenging, but it’s also a lot of fun.

### Create and save a new page

After you have set up a site and examined your comps (if any), you are ready to begin building web pages. You'll start by creating a new page, and saving it in the check_cs6 local root folder of your website. The page eventually becomes the home page for Check Magazine.

1. In Dreamweaver, make sure the Check Magazine site is selected in the Files panel (see Figure 2).
2. Choose File > New.
3. In the Blank Page category of the New Document dialog box, select HTML from the Page Type list, and <none> from the Layout list (these two options should already be selected by default).
4. Set DocType to HTML5 and click Create.
5. Choose File > Save, or press Ctrl+S (Windows) or Cmd+S (Mac OS X).
6. In the Save As dialog box, make sure you’re in the check_cs6 folder that you defined as the site's local root folder. Dreamweaver should have selected this automatically, but if a different folder is selected, click the Site Root button at the bottom of the dialog box (it’s on the right in Windows, and on the left in the Mac version).
7. Type index.html as the File Name and click Save. The file name now appears in the tab of your new document.
8. In the Document Title text box at the top of your new document, type Check Magazine (see Figure 3).
9. Click the page once to move the insertion point out of the Document Title text box. You'll see that an asterisk (*) appears next to the file name in the document's tab. This asterisk indicates that the contents of the file have changed and that you need to save the file if you want to keep the changes.
10. Choose File > Save to save your page.

### Build the basic page structure

If you did reading CSS page layout basics, then you already know that the &lt;div&gt; tag is the basic building block of a CSS layout. A &lt;div&gt; tag acts as a container for text, images, and other page elements, grouping them together so they can be styled in a consistent way. You use CSS to position them by adding horizontal and vertical space around them (margins) or inside them (padding). Compared to table cells, which exist only within the rows and columns of a table, &lt;div&gt; tags are much more flexible.

If you look at the design comp again (see Figure 1), you'll notice that the page is divided into distinct sections: a banner logo at the top of the page, a central graphic area in the center of the page, and then a third bottom section that contains three separate columns within it. These sections all correspond to separate <div> tags that act as containers for the content inside of them.

HTML5 adds new tags—such as <header>, <footer>, and <article>—that perform exactly the same function as a <div>. The only difference is that the new tags specify the role of the element in the page. Unfortunately, IE 6 through IE 8 won’t style the new tags with CSS unless you use JavaScript. To avoid problems with older browsers, this tutorial uses only <div> tags to group content.

Insert <div> tags

Start by creating the most basic, most important, and most common <div> tag for CSS layouts—the container. The container <div> contains all the other tags in the layout. If your CSS layout is like a sandbox, and you are going to place a beach ball, a bucket, some shells, and an umbrella in the sandbox, then the container tag is the outer rim of the sandbox. It defines the shape, dimension, and limitations of the sandbox, and holds everything together.
In this section, you’ll work in both Design view and Code view because it’s important to understand the underlying HTML code that Dreamweaver creates on your behalf.

1. Make sure the Design button is selected at the top left of the Document window, and click once on the page to ensure that the insertion point is in the upper-left corner of the page (see Figure 4).
2. Expand the Insert panel by clicking its tab or by choosing Window > Insert.
3. The default display for the Insert panel is the Common category. Make sure the Common category is selected, and click Div or Insert Div Tag—the name and position within the panel depends on which version of Dreamweaver you’re using (Figure 5 shows how it looks in the Creative Cloud Dreamweaver 12.1 update).
4. In the Insert Div Tag dialog box, leave At Insertion Point selected, leave the Class blank, and **type container as the ID**. Setting the <div> tag’s ID gives it a unique identity that will be used to apply CSS styles to it later.
Click OK.
5. The new <div> appears on your page, surrounded by a dotted line in Design view, and with some placeholder text inside (see Figure 6).

> Note: If you can’t see the dotted line surrounding the <div>, choose View > Visual Aids, and make sure there’s a check mark alongside CSS Layout Outlines. Clicking any of the options in the Visual Aids submenu toggles them on and off.

6. Select the placeholder text and delete it, making sure you delete only the text. If the outline of the <div> disappears, repeat step 4. The placeholder text should be automatically selected when the <div> is inserted, so all you need to do is to press Delete.
7. In the Insert panel, click Div or Insert Div Tag again.
8. In the Insert Div Tag dialog box, select After Start Of Tag as the insert point. This activates a new control, which lists the places where Dreamweaver can insert the new <div>. At the moment, the only candidates are the <body> tag and <div id="container">.
9. Leave the Class blank, **type header as the ID**, and click OK.
The new <div> appears on your page, and within it you can see the placeholder content for the header <div>. But where did the container <div> go? Well, it's there, you just can't see it in Design view. The best way to see it is to look at the code.
10. Click the Split view button (see Figure 8). Split view displays the underlying code on the left of the Document window. You can see the container <div> tag, and inside it is the new header <div> tag, just as planned (see Figure 9).

> Note: Working in Split view (formally called "Code and Design view") is a great way to learn how Dreamweaver generates code. When you insert something in Design view, you see the code that Dreamweaver writes in Code view. It’s particularly useful if you have a large monitor, because you can see the web page in Design view and the underlying code both at the same time.

11. Since you’re looking at the raw code, go ahead and continue working there. If you’re cramped for space in Split view, click the Code button at the top of the Document window.

Place the Insertion point after the closing </div> tag of the header <div> and press Enter (Windows) or Return (Mac OS X) to create a new line (see Figure 8).

> Note: Pay careful attention to where you create the new line. You should still be inside the container <div>. The closing tag of the container <div> is on line 12 of Figure 10.

12. With the Insertion point still on the new line, **Insert Div Tag** in the Insert panel.
13. In the Insert Div Tag dialog box, leave **At Insertion Point selected**, leave the Class blank, type **main_image** as the ID, and click OK.

The new <div> appears on your page, and within it you can see the placeholder text. This new <div> is inside the container <div>, on the same level as the header <div>.

> Note: When you create new IDs watch out for extra space either before or after the ID. For example, make sure that when you type the main_image ID, there is not an extra space after the "e" in image. If there is, it can lead to CSS problems later.

14. Place the Insertion point after the closing tag of the <div> you have just created and press Enter (Windows) or Return (Mac OS X).
15. In the Insert panel, click Div or Insert Div Tag.
16. In the Insert Div Tag dialog box, leave At Insertion Point selected, leave the Class blank, type left_column as the ID, and click OK.
17. Repeat steps 14–16 twice to create two more <div> elements. Give the first one the ID center_column, and the second one the ID right_column.
18. If you’re in Split view, press F5 or click in the Design view half of the Document window to update Design view. Alternatively, click the Design button to return to Design view.

All your <div> elements are stacked one on top of another and stretch the full width of the page. This is the default behavior until you create CSS rules for them.

19. Save the page (File > Save).

### Create an external style sheet

Now that you have your <div> tags in place, the next step is formatting and positioning them with CSS—a collection of formatting rules that control the appearance of content on a web page. Using CSS to format a page separates content from presentation. The content of your page—the HTML code—resides in the HTML file, and the CSS rules defining the presentation of the code reside in another file, the external style sheet.
You can also put CSS rules in the head section of a document, or inline with the code itself. However, an external file is the most efficient way of using CSS, because changes made to rules in an external style sheet are automatically applied to every page attached to it.

### Using CSS code hints

Dreamweaver has several tools that speed up styling your web pages. In this section, you’ll type the style rules directly into a style sheet to give you a feel for what CSS looks like. Don’t worry if you’re not keen on working directly with code. As you type, Dreamweaver displays code hints and auto-completes much of the code for you.

1. Choose File > New.
2. In the New Document dialog box, verify that the Blank Page category is selected, select CSS from the Page Type column (see Figure 12), and click Create.
3. A blank style sheet appears in the Document window. The Design view and Split view buttons are disabled. CSS files are text-only files—their contents are not meant to be viewed in a browser.
4. Choose File > Save.
In the Save As dialog box, create a new folder named styles in the site root, select the new folder, and save the file in the styles folder as check_cs6.css.
5. Five <div> elements in index.html are nested inside the container <div>. To center the content on the page, you need to create a style rule for the container <div> by giving it a width and setting its left and right margins to auto.
To create a style rule for an HTML element that has an ID, you prefix the ID with a hash sign (#). So the CSS selector for the container <div> is #container.

> Note: CSS selectors are case-sensitive. The spelling of the ID must be the same as you used when inserting the <div> tag. So, if you used an initial capital letter, the CSS selector would be #Container. Also, make sure there’s no space between the hash sign and the ID.

	#container {
	    width: 968px;
	    background: #FFF;
	    margin: 0 auto;
	    padding-left: 10px;
	    padding-right: 10px;
	    overflow: hidden;
	}

6. Save the style sheet.

Each of the properties in your new rule means something specific for the container <div>. The first one—width—is the most obvious. It sets the width of the container div to 968 pixels. You are setting the background color to white (#FFF), and declaring 0 pixels for the top and bottom margins of the container, and auto for the left and right margins of the container. (This effectively centers the container in the middle of the page when the user views it in a browser.) For the padding, you've specified 10 pixels on the right and the left, and you've specified a hidden overflow, which forces large assets like images to stay within the confines of their container tags.

### Attach the new style sheet

To attach the style sheet, follow these steps:

1. Click the tab for the index.html page and make sure you are looking at the page in Design view. (If you're still in Code view, click the Design view button.) Your page should look exactly like Figure 14.

> Even though you created a complex CSS rule for the container <div>, the page still looks the same as before. This is because the CSS style sheet is not yet attached to the page. When you attach the style sheet to the page, the #container rule that you created in the style sheet will format the <div> with the ID "container" on your web page.

2. Open the CSS Styles panel by clicking its tab. In the Designer workspace (the default Dreamweaver workspace), the CSS Styles panel group is located below the Insert panel. If it isn't, you can choose Window > CSS Styles to display it.
Make sure the All button is selected at the top-left of the panel.

You'll notice that the CSS Styles panel is empty except for the message, "(no styles defined)" because there are no CSS rules applied to this page.

3. (Optional) Double-click the Insert panel to close it and create more room.
4. In the lower right-hand corner of the CSS Styles panel, click the Attach Style Sheet icon (see Figure 15).
5. In the Attach External Style Sheet dialog box, click the Browse button. This launches the Select Style Sheet dialog box. Navigate to the check_cs6.css style sheet that you created in the styles folder, select it, and click OK (Windows) or Choose (Mac OS X).
6. Click OK to close the Attach External Style Sheet dialog box.

> Note what happened to the page. You can immediately see that the container <div> now has padding of 10 pixels on the left and right. Depending on the size of your Document window, you might also see that the container <div> looks centered on the page. That's because if you have extra room (in addition to the 968-pixel width you specified), the container will also have an "auto" margin on its left and right sides. This effectively means that the browser will create exactly the same amount of pixel space to the left and right of the container <div>, thus producing a centered effect.

7. Run your cursor over the border of the container <div> until you see a red line, and then click to select the container <div>. Figure 16 shows what you should see when the container div is selected.

Here Dreamweaver is giving you a nice visual rendering of how the CSS rule applies to the container element. The light gray shading on the left and right sides of the container <div> indicates the 10-pixel padding, and when you hover your cursor over the area, Dreamweaver displays a tooltip that tells you that. Similarly, the lighter blue areas at the outermost left and right sides of the container indicate the auto margins. Again, the amount of auto margin that displays in Dreamweaver depends on the size of your Document window. If you are working in the default Designer workspace, and you make your Document window smaller by dragging the docked panel area on the right, you should see the auto margin disappear as less space becomes available on the page.

> Note: If the visual rendering of the padding and margins fails to display, choose View > Visual Aids, and make sure the following options are selected: CSS Layout Box Model and CSS Layout Outlines.

9. Click the Live button at the top of the Document window (see Figure 17).

This turns on Live View in the Document window. The dotted outlines of the <div> elements disappear, and you see the page as it would look in a browser. In fact, you are looking at the page in a browser—Live View uses the WebKit browser engine that powers Safari and Google Chrome browsers.

10, When Live View is activated in Dreamweaver CS6, two new buttons—Live Code and Inspect—appear to the right of the Live button. (In CS5 and CS5.5, they’re in slightly different positions and always visible.) Click the Inspect button to turn on Inspect Mode (see Figure 18).

11. Move your cursor over the <div> elements in the center of the page. As you move up or down, each <div> is highlighted in light blue.
12. Move your cursor to the left of the placeholder text (see Figure 19).

This highlights the container <div>. The <div> itself is highlighted in blue. The 10-pixel padding on either side is highlighted in purple, and the auto margins are highlighted in yellow. When you can see the effect of your style rules like this it is much easier to understand how they change your layout.

13. Click the Live button to return to Design view and turn off Inspect Mode. In Dreamweaver CS6, the Live Code and Inspect buttons disappear.
14. Save index.html and close the check_cs6.css style sheet.

### Add the header content




