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

Until quite recently, it was common to use an image for the main banner heading of a website because browsers rely on the fonts installed on the visitor’s computer to render text. As a web designer, you might have many fonts installed on your computer, but you can’t rely on everyone else having as many. Consequently, you were restricted to a limited range of "web-safe" fonts. The situation has changed thanks to all browsers now supporting fonts that can be embedded in a web page. So, instead of using an image for the header banner, you’ll use HTML and style it with CSS and a web font.

### Create the main heading and tag line

Dreamweaver makes it easy to create headings and paragraphs using the correct HTML markup.

1. In index.html, click anywhere inside the placeholder text for the header &lt;div&gt;.
2. Make sure the HTML button is selected in the Property inspector, and select Heading 1 as the Format (see Figure 20).
3. Now The placeholder text for the header &lt;div&gt; is displayed in a large, bold font. **Select and replace it** with the single word **Check**.
4. Make sure the insertion point (your cursor) is at the end of the line after the letter "k" and press Enter (Windows) or Return (Mac OS X).
5. The insertion point is now on a new line. Type **Fashion + Lifestyle**.
6. Click the Split button to examine the HTML code that Dreamweaver has generated. Your page should look like Figure 21.
7. Save index.html.

### Adding the navigation links

One of the most common ways of creating a navigation menu is to use a bulleted list—or unordered list, as it’s called in HTML—and style it with CSS.

1. In Design view, place your cursor at the end of the "Fashion + Lifestyle" paragraph, and press Enter (Windows) or Return (Mac OS X) to move to a new line.
2. Look in Split view. Dreamweaver has inserted the following code:
<p>&nbsp;</p>
This is a new pair of paragraph tags with what’s known as an HTML entity for a nonbreaking space between them.
3. Type **Features**. As soon as you start typing, Dreamweaver removes the nonbreaking space, which was there simply as a placeholder, and replaces it with the text you typed.
4. Make sure the HTML button is selected in the Property inspector, and click the Unordered List icon (see Figure 22).
5. Check in Split view, the paragraph tags around "Features" have been replaced with different HTML tags like this:

	<ul>
		<li>Features</li>
	</ul>

The &lt;ul&gt; tags tell the browser to create an unordered list. The &lt;li&gt; tags are wrapped around each list item.
6. With the insertion point at the end of "Features" in Design view, press Enter (Windows) or Return (Mac OS X) to add a new list item. Dreamweaver adds a new pair of &lt;li&gt; tags in the underlying HTML. Type **Fashion** in Design view.
7. Repeat the process to add three more items to the unordered list: **Lifestyle, Calendar, and News**. Your page should now look like Figure 23.
8. Normally, when you have finished an unordered list, you press Enter (Windows) or Return (Mac OS X) twice to exit the list and create a new paragraph. However, in this case, you don’t need anything else in the header &lt;div&gt;. If you accidentally created a paragraph at the end of the list, press Ctrl+Z (Windows) or Cmd+Z (Mac OS X) twice to remove it.
9. You now need to convert the list items into links. Select "Features" in Design view. You can either drag to **select it**, or **double-click**.
10. At the moment, there are no pages to link to. So, create a dummy link by typing # in the Link field of the Property inspector.
11. Do the same for the other items in the unordered list. Each list item will turn blue and be underlined, indicating it’s a link. In the underlying HTML, the unordered list should now look like this:

	<ul>
	  <li><a href="#">Features</a></li>
	  <li><a href="#">Fashion</a></li>
	  <li><a href="#">Lifestyle</a></li>
	  <li><a href="#">Calendar</a></li>
	  <li><a href="#">News</a></li>
	</ul>

10. Save the page.

### Insert the main image as background

Images can be added to a web page either directly in the HTML using the &lt;img&gt; tag or as a background image using CSS. By default, browsers turn off background images when a page is printed. If an image is important, you should put it directly in the HTML markup. However, text will be added in front of the main image in this layout, so I think it’s fine to use CSS to insert it as a background image to the main_image &lt;div&gt;.

This time, you’ll use the New CSS Rule and CSS Rule Definition dialog boxes to create the necessary style rule.

1. Place the insertion point in the main_image &lt;div&gt;, and delete all the placeholder text.
After you've deleted the last character, it will look like the &lt;div&gt; has completely disappeared. Don't worry, it's still there. Check in Split view that the insertion point is between these two tags:
&lt;div id="main_image"&gt;&lt;/div&gt;
Don’t click anywhere in the Document window before proceeding to the next step.
2. In the lower right-hand corner of the CSS Styles panel, click the New CSS Rule icon (see Figure 24).

As long as your Insertion point was in the main_image &lt;div&gt; when you clicked the icon, the New CSS Rule dialog box should automatically suggest appropriate settings for the CSS selector (see Figure 25).

Dreamweaver detects that the Insertion point is in the main_image &lt;div&gt;, which is nested inside the container &lt;div&gt;, and it suggests using the compound selector #container #main_image. The text area below the Selector Name describes the meaning of this selector.

Although it’s correct, everything in the page is nested inside the container &lt;div&gt;, so you don’t need to be so specific.

3. Click the **Less Specific** button once. This changes the Selector Name value to #main_image, which is exactly what you want.
4. Make sure check_cs6.css is selected from the Rule Definition pop-up menu. Then click OK.
The CSS Rule Definition dialog box appears, indicating that you are defining properties for the new #main_image rule.
5. Select the Background category in the Category column.
6. In the Background category, click the Browse button next to Background-image.
7. In the Select Image Source dialog box, navigate to the images folder inside the Check Magazine site.
8. Select the main.jpg graphic and click OK (Windows) or Choose (Mac).
9. Select no-repeat as the Background-repeat setting.

The main.jpg graphic is now defined as the background image for the main_image <div> (see Figure 26).

10. Select the Box category in the Category column.
 
In the Box category, do the following:

* Type 968 as the Width and select px from the pop-up menu to the right.
* Type 376 as the Height and select px from the pop-up menu to the right.
* Click OK.

The main.jpg graphic appears in the main_image <div>, and the dimensions of the <div> are set.
Normally, it’s not a good idea to give a <div> a fixed height, because a <div> expands or contracts automatically depending on the amount of text or other content inside it. However, in this case a fixed height is necessary, because you need the <div> to be the same height as the background image. Without the height declared in the CSS, the <div> would collapse to nothing, and the background image would not be displayed.

11. Choose File > Save All Related Files to save the page and the style sheet.

Figure 27 shows what your page should look like at this point in Design view.

### Position the columns

The last major task for the basic layout of index.html is to marshal into order the columns at the bottom of the page. CSS categorizes most HTML elements as block-level or inline. A block-level element begins on a new line of its own, and forces the following element onto the next line, whereas inline elements snuggle up alongside each other. Typical block-level elements include headings, paragraphs, and &lt;div&gt; tags. Text inside a paragraph and images are inline elements.

Before moving the columns into position, you need to do a little calculation. The main image is 968 pixels wide. That doesn’t divide evenly by 3, but you need a little breathing space between each column, say 10 pixels. So, if you divide 948 by 3, you get 316. That’s how wide each column needs to be. It also happens to be the width of the images at the top of each column.

1. If your monitor is wide enough, the best way to work is in Split view, using Dreamweaver’s related files feature.
2. Click check_cs6.css in the Related Files toolbar just below the tab for index.html. This opens the style sheet in Split view, while leaving index.html visible in Design view (see Figure 28).

You can now edit the style sheet, and see the changes in Design view.

> Note: If you’re cramped for space, drag the center bar to resize the windows. You can also make extra room by pressing F4 to hide all the panels. Press F4 again to restore them.

3. All columns need to be 316 pixels wide. You can apply the same width to all of them by creating a combined selector for the three &lt;div&gt; elements. Add the following style rule at the bottom of the style sheet:

4. Click in Design view (or press F5) to refresh the page. The columns are now much narrower, but they’re still stacked on top of each other. That’s because they’re block-level elements.
To get the columns to sit alongside each other, you need to use the float property.
5. Position the Insertion point after the semicolon at the end of the line that defines the width of each column, and press Enter (Windows) or Return (Mac). Dreamweaver displays code hints for the available properties. Type f and press Enter/Return to insert float:. Then type l (lowercase L) to bring up the code hint for left (see Figure 29).
6. Refresh Design view by clicking in it or pressing F5. The columns should now be alongside each other across the bottom of the page.
7. Finally, you need to add the margins between the columns. You do this by adding a 10-pixel left margin to the center and right columns. Add the following style rule at the bottom of the style sheet:
8. Choose File > Save All Related Files.

Your CSS page layout is now complete. If for some reason your layout does not look the way it's supposed to, double-check the spelling (including capitalization, if appropriate) of all your CSS rules. The most common causes for CSS layout errors are typographical ones, so you must make sure that the IDs in your external CSS file correspond exactly to the IDs in your index.html file. Also, don't forget to watch out for those extra spaces that can creep in before and after IDs when creating new CSS rules.

## Part 3: Styling the header and navigation menu
https://www.adobe.com/devnet/archive/dreamweaver/articles/first_website_pt3_cs6.html

Welcome to Part 3 of this six-part tutorial series on creating your first website. This tutorial shows you how to style the main heading using Adobe Edge Web Fonts, a library of hundreds of free fonts that you can use in your website. You’ll also learn how to eliminate the gap that often appears at the top of web pages, and how to convert an unordered list of links into a horizontal menu bar. The menu bar and main text will be maneuvered into position using a combination of relative and absolute positioning.

### Locate your files and review your task

In Part 1 and Part 2 of this tutorial series, you defined a site for Check Magazine, a fictional publication, and created the basic structure for the home page. If you completed the first two parts, continue working with your existing files. If you’re not sure whether your HTML and CSS is correct, you can download the first_website_pt3_begin.zip sample file, and use its contents to replace your existing files.

At the end of Part 2, the page was still very bare (see Figure 1).

In this tutorial, you'll style the header section, and add the main text area. Figure 2 shows what the page will look like in a browser when you’re done with Part 3.

### Style the main heading and tag line

You’ll start by using a web font for the main heading.

**Styling the heading with an Edge Web Font**

The main heading uses a font **called Sarina**, which is not available on most computers, but you can add it to your web page using **Adobe Edge Web Fonts**, a vast library of free web fonts from Adobe, Google, and designers around the world.

Open your browser and go to http://html.adobe.com/edge/webfonts/ (see Figure 3).

To access the full range of fonts, you need either a subscription-based or free Creative Cloud membership. However, you can access a limited range even without signing up, so that’s what you’ll do in this tutorial.

2. Scroll down to the Preview Edge Web Fonts section, and select Sarina.
The editable area below shows a preview of the font together with instructions on how to use it (see Figure 4).

The editable area below shows a preview of the font together with instructions on how to use it (see Figure 4).

Copy the &lt;script&gt; tags from the Edge Web Fonts site, and paste them into the &lt;head&gt; section of index.html in Dreamweaver just above the &lt;link&gt; that attaches the style sheet like this:

	<head>
		<meta charset="utf-8">
		<title>Check Magazine</title>
		<style type="text/css">
		</style>
		<script src="//use.edgefonts.net/sarina.js"></script>
		<link href="styles/check_cs6.css" rel="stylesheet" type="text/css">
	</head>

4. Also copy the CSS from the Edge Web Fonts page, and paste it into check_cs6.css after the existing styles. The example provided by the Edge Web Fonts site is for a level 1 heading, so it doesn’t need changing, but you would need to change the CSS selector if you want to use the font for other text elements.
5. Save both index.html and the style sheet.
6. **Unfortunately, the Dreamweaver Design view and Live view don’t support Edge Web Fonts**. So, **press F12** (Windows) or Opt+F12 (Mac OS X) to launch index.html in your default browser. As long as you’re connected to the Internet, the heading should now be styled using the web font (see Figure 5).	

The heading is too small, so amend the h1 style rule by setting font-size to 96px like this:

	h1 {
	    font-family: sarina, serif;
	    font-size: 96px;
	}

8. The background color of the header needs to be black, and the color of the text should be white.
In Design view, put your insertion point anywhere inside the header <div>, and click the New CSS Rule icon at the bottom-right of the CSS Styles panel.
9. The New CSS Rule dialog box suggests a compound selector depending on where your insertion point is. The styles need to apply to the whole of the header <div>, so change the value of Selector Type from Compound to ID. Dreamweaver CS6 automatically changes the value of Selector Name to header.

Note: If you’re using an earlier version of Dreamweaver, changing Selector Type to ID clears the Selector Name field. You need to type header manually.

10. Make sure Rule Definition is set to check_cs6.css, and click OK to open the CSS Rule Definition dialog box.
11. With Type selected in the Category list on the left of the CSS Rule Definition dialog box, click the color box alongside the Color field, and select white (#FFF) from the color picker (see Figure 6). This sets the color of the text.
12. Select Background in the Category list on the left of the CSS Rule Definition dialog box, and use the color picker to set Background-color to black (#000).
13. Click OK to close the CSS Rule Definition dialog box.
14. Save the style sheet, and refresh index.html in your browser. The header should now have white text on a black background (see Figure 7).

Although there is nothing above the header, it has been pushed down the page, leaving an ugly white gap at the top. Also, the links in the unordered list haven’t changed to white like the rest of the text. Both issues need to be fixed. First, you’ll deal with the gap above the heading.

**Fixing the gap above the header**
In this section, you’ll use **Inspect Mode** to investigate and fix the cause of the gap at the top of the page.

1. With index.html open in the Document window, click the Live button in the Document toolbar. Although Live View doesn’t display the Sarina font, there’s still a big gap at the top of the page.
2. Click the Inspect button to turn on Inspect Mode, and move your mouse pointer over the Check heading. Inspect Mode highlights margins in yellow. As Figure 8 shows, the heading has large top and bottom margins that browsers add by default.

An unusual feature of CSS is that adjacent vertical margins merge to the height of the largest one. As a result, the heading’s top margin extends beyond the header &lt;div&gt;, pushing it away from the top of the page.

Notice also that there’s a narrow white strip above the top margin. That’s caused by browsers adding a default eight-pixel margin around the &lt;body&gt; element. You need to fix both issues.

3. Click the heading to freeze Inspect Mode. The Inspect button pops out, but the highlighting remains in Live View.
4. In the CSS Styles panel, make sure that the All button is selected. Then select h1 in the All Rules pane to display the properties for the heading.
5. In the lower pane, click Add Property (see Figure 9).
6. In the text field that opens, start typing mar. Then click the down arrow to the side of the field to reveal a list of CSS properties, and select margin.
7. Type 0 in the field that opens to the right of the property name (see Figure 10).
8. Press Enter (Windows) or Return (Mac OS X) to confirm the value. This removes the margins on all sides of the heading.
9. Check in Live View. The heading is still highlighted in blue, but the yellow margins have gone, and there’s only a narrow gap at the top of the page.
10. You now need to create a rule for the <body> element to remove the default margin around the page. Click the New CSS Rule icon at the bottom right of the CSS Styles panel.
11. In the New CSS Rule dialog box, set Selector Type to Tag (Redefines An HTML Element).
12. Click the down arrow on the right of the Selector Name field, and select body.
13. Make sure Rule Definition is set to check_cs6.css, and click OK to open the CSS Rule Definition dialog box.	
14. Most rules set on the <body> element are inherited by the rest of the page. So, in addition to removing the default margin, it’s a good idea to set the default font, text color, and background color.
With Type selected in the Category list, click the down arrow to the right of the Font-family field, and select Trebuchet MS, Arial, Helvetica, sans-serif.
15. Accessibility experts recommend against using pure black text on white because the contrast is too strong. So, I’m going to use a dark gray for the text.
Type #3B3B3B in the Color field. (Don’t forget the hash sign at the beginning—it’s part of the hexadecimal code for the color.)
16. Click the Apply button to see the effect of the changes. Notice that the font has changed for all the text except the main heading. Also note that the color of the text in the header <div> is unchanged because you set a different color in the #header style rule earlier (see Figure 11).
17. Select Background in the Category list on the left of the CSS Rule Definition dialog box, and use the color picker to set Background-color to white (#FFF).
18. Select the Box category. Leave the Same For All check boxes selected, and type 0 in the Top field under Margin. Then click Apply. This removes the default margin on each side of the page, and the gap at the top disappears.
19. Click OK to close the CSS Rule Definition dialog box.
20. Choose File > Save All Related Files to save the changes to the style sheet.

**Styling the tag line**
The Fashion + Lifestyle tag line needs to sit alongside the Check heading. The tag line is in a paragraph, while the heading is in an &lt;h1&gt; tag. CSS treats both as block-level elements that occupy a new line. To move them alongside each other, you need to apply the **float** property to the **heading**. This moves it to the side, allowing other elements to move up alongside. Once the tag line moves into the space next to the heading, you can adjust its padding and margins to move it into position.

1. In the CSS Styles panel, select h1 in the All Rules pane.
2. Click Add Property in the lower pane, and type float.
3. Press Tab to move into the field alongside the property name, and click the down arrow on the right of the field to reveal the available values. Select left.
Don’t worry that the header moves away from the top of the page. It’s because the Fashion + Lifestyle tag line has moved up alongside the heading, and its top margin now overlaps the header <div>.
4. Click anywhere inside the Fashion + Lifestyle paragraph. Make sure Live View is turned on.
5. Click the New CSS Rule icon at the bottom-right of the CSS Styles panel.
6. The New CSS Rule dialog box suggests #container #header p as the Selector Name. You don’t need #container. So, click **Less Specific** once to change the selector to #header p.
7. Make sure Rule Definition is set to check_cs6.css, and click OK.
8. In the Type category of the CSS Rule Definition dialog box, set Font-family to Lucida Sans Unicode, Lucida Grande, sans-serif.
9. Set Font-size to 30px.
10. Set Font-variant to small-caps.
11. Select the Box category from the list on the left of the CSS Rule Definition dialog box.
12. Deselect the Same For All check box under Margin, and type 0 in the Top and Bottom fields.
13. Click Apply. Setting the top margin to 0 removes the gap at the top of the page, but the tag line is too high.
14. Deselect the Same For All check box under Padding, and type 15 in the Top field.
15. Click Apply. Your settings and the page should look like **Figure 12**. Padding is added inside an element, so the tag line moves down, but no longer causes a gap at the top of the page.
16. Click OK to close the CSS Rule Definition dialog box, and save the style sheet.

### Style the navigation bar

The final stage of fixing the header &lt;div&gt; involves converting the unordered list of links into a horizontal navigation bar. You’ll start by giving the the links a different color and font styles.

**Giving links a unique style**
The links in the navigation bar need to have a style that won’t be shared by other links in the page. You do this with a selector that targets only links in the header &lt;div&gt;.

1. Click anywhere in one of the links in the header <div>, and then click the New CSS Rule icon at the bottom-right of the CSS Styles panel.
2. The New CSS Rule dialog box suggests #container #header ul li a as the Selector Name. Although this does what you want, it’s more efficient to simplify the selector.
3. Click Less Specific once to change the selector to #header ul li a. Again, this is accurate, but all you need to target links inside the header <div> is #header a.
Click inside the Selector Name field, and delete ul li. As you edit the selector, the description below the field changes to show you which elements will be styled (see Figure 13).

![](http://res.cloudinary.com/medioxtra/image/upload/v1481684791/Screenshot_32_o9nmof.png)

4. Click OK to open the CSS Rule Definition dialog box.
5. Set the following values in the Type category:

* Font-size: 20px
* Font-weight: bold
* Font-variant: small-caps
* Color: #FFF (white)
* Text-decoration: none

6. Click OK to close the CSS Rule Definition dialog box and apply the new styles. Setting Text-decoration to none removes the underline from the links, which are now displayed in bold, white, small capitals.
7. Select some of the placeholder text in one of the columns at the foot of the page, and type # in the Link field of the Property inspector. It’s styled differently from the links in the header because the #header a style rule that you have just created affects only links in the header <div> (see Figure 14).

![](http://res.cloudinary.com/medioxtra/image/upload/v1481685043/Screenshot_31_zowcuw.png)

8. Save index.html and the style sheet.

#### Converting the unordered list into a navigation bar

To convert the links in the unordered list into a horizontal navigation bar, you need to remove the bullets, give the links a width, and turn them into block-level elements so that the full width of the link becomes clickable. Finally, you need to float them to the left.

1. Click anywhere inside one of the links in the header <div>. Then select <ul> in the Tag selector at the bottom of the Document window (see Figure 15). This highlights the whole unordered list.

![Screenshot_35](http://res.cloudinary.com/medioxtra/image/upload/v1481686303/Screenshot_35_gd0fps.png)

2. Click the New CSS Rule icon at the bottom-right of the CSS Styles panel. Dreamweaver suggests #container #header ul as the Selector Name.
3. Click Less Specific once to change the Selector Name to #header ul. Then click OK to create a style rule for the unordered list in the header <div>.
4. You need to remove all margins and padding from the list, so select Box from the Category list in the CSS Rule Definition dialog box. Leave Same For All selected for both Padding and Margin, and type 0 in both Top fields.
5. Select the List category, and set List-style-type to none.
6. Click OK to close the CSS Rule Definition dialog box and apply the styles. The bullets disappear from the unordered list.
7. You need to add some extra properties to the style rule for the links, so select #header a in the All Rules pane of the CSS Styles panel. Then click the Edit Rule icon at the bottom-right of the panel (see Figure 16) to reopen the CSS Rule Definition dialog box.

![Screenshot_34](http://res.cloudinary.com/medioxtra/image/upload/v1481686531/Screenshot_34_lfcxq0.png)

8. In the Block category, set Text-align to center, and Display to block.
9. In the Box category, set Width to 100px.
10. Click OK to close the dialog box and make the changes. The links are now stacked under the main heading.

! [Screenshot_36](http://res.cloudinary.com/medioxtra/image/upload/v1481687089/Screenshot_36_kjvbne.png)

11. Click inside any of the links in the header <div>, and select <li> in the Tag selector at the bottom of the Document window. This selects the whole list item so you can define a style rule for list items in the header.
12. Click the New CSS Rule icon at the bottom-right of the CSS Styles panel, and click the Less Specific button once to change the Selector Name to #header ul li. Then click OK.

![Screenshot_37](http://res.cloudinary.com/medioxtra/image/upload/v1481687397/Screenshot_37_a0xsj6.png)

13. The list items need to be floated left. So, select the Box category, and set Float to left.
14. When you click OK, don’t panic if the design goes haywire. It should look similar to Figure 17.

![Screenshot_38](http://res.cloudinary.com/medioxtra/image/upload/v1481687449/Screenshot_38_ovgemv.png)

The problem is caused by **both the main heading and the navigation bar floating**. When items float, they’re no longer constrained by the element they’re nested inside—in this case, the header &lt;div&gt;.

15. Select #header in the All Rules pane of the CSS Styles panel, and click the Edit Rule icon.
16. In the Box category, set Height to 100px, and click Apply. The navigation bar should reappear and the main image move further left (see Figure 18).

![Screenshot_39](http://res.cloudinary.com/medioxtra/image/upload/c_scale,w_900/v1481687769/Screenshot_39_kwlm53.png)

Note: Don’t worry that the main image is still off to the right. Design view doesn’t always show an accurate representation of page layout.

17. Click OK to close the dialog box, and activate Live view. The main image should be centered under the header.
18. Save the style sheet.

### Use absolute positioning (AP Elements)

The layout design calls for the menu to be at the bottom-right of the header.  To move it into position, you’re going to use **absolute positioning**. Before showing you how to do it, I must sound a word of warning. *Many beginners fall into the trap of trying to lay out their entire design with absolute positioning* (or AP Elements, as Dreamweaver calls them).

The attraction of absolute positioning is that you can place an element precisely on a page, making web design feel almost like desktop publishing. However, the web is a fluid medium. People view pages on different size screens, and at different resolutions. Absolutely positioned elements behave in a very different way from other elements. They stay where you put them, and don’t interact with the rest of the page. This often creates the illusion that the absolutely positioned element moves. In fact, the opposite happens; the rest of the page moves in relation to the absolutely positioned element. Also, an absolutely positioned element might disappear off screen on a mobile device without generating a scrollbar, making vital information inaccessible.

Although absolute positioning presents problems for laying out entire pages, it can be very effective when you want to align an element with another. You specify the position as one or two offsets from the element’s sides. For example, if you set the left offset to 150px and the top offset to 100px, the left and top sides of the element are positioned exactly that distance away from the element’s containing block (see Figure 19).

![Screenshot_40](http://res.cloudinary.com/medioxtra/image/upload/v1481692135/Screenshot_40_mehkyf.png)

Note: The offsets can be positive or negative. As Figure 19 shows, a positive 150px left offset moves the element 150px to the right away from the left of the containing block. A negative offset moves the element in the opposite direction outside its containing block, which is simply the point from which the offsets are calculated.

The **secret** to using **absolute positioning** successfully is understanding the principle of the containing block. Usually, an element’s containing block is the nearest block-level element higher up the HTML structure. In the case of the navigation bar, this is the header &lt;div&gt;. However, absolute positioning is different. The containing block is the nearest element higher up the HTML structure that has its position property set to absolute, fixed, or relative. If no such element exists, the page becomes the containing block.

To fix the navigation bar at the bottom-right of the header, the bottom and right offsets need to be set to 0. However, without first defining a containing block, the navigation bar would end up at the bottom-right of the page. To calculate the offsets from the header &lt;div&gt;, you need to set its position property to relative. Relative positioning is similar to absolute positioning, except the offsets are calculated from the element’s normal position in the document. So, if you make an element relatively positioned, but don’t set any offsets, it remains in its normal position, but with the crucial difference that it acts as the containing block for any absolute elements nested inside. It sounds complicated, but it’s very simple to implement.

**Moving the navigation bar into place**
So much for the theory. Now you can put it into practice to dispel any doubts you might have about the preceding explanation.
1. In the **All Rules** pane of the CSS Styles panel, select the rule that controls the unordered list, #header ul, and click the Edit Rule icon.
2. In the CSS Rule Definition dialog box, select the Positioning category and set the following values:
* Position: absolute
* Placement Right: 0px
* Placement Bottom: 0px
3. Click OK to make the changes and close the CSS Rule Definition dialog box.

If the navigation bar is still visible, click the Live button to activate Live view. The menu disappears. It’s actually at the bottom-right of the Document window, but you likely can’t see it because the text is white.

To verify what’s happened to the menu, select the rule that styles the links in the navigation bar, **#header a**, in the All Rules pane of the CSS Styles panel.

Move your mouse pointer to the left of the color property in the lower pane to reveal an icon with a tooltip that reads Disable CSS Property. Then click the icon to temporarily disable the color of the links. You should now see the navigation bar at the bottom-right of the Document window (see Figure 20).

The navigation bar doesn’t have a positioned containing block, so the offsets are calculated from the bottom and right of the page rather than the header &lt;div&gt;.

![](http://res.cloudinary.com/medioxtra/image/upload/v1481703437/Screenshot_41_uuhhlo.png)

7. Click the icon alongside the color property again to re-enable the property.
8. To anchor the navigation bar inside the header <div>, you need to make the <div> relatively positioned. Select the #header rule in the All Rules pane of the CSS Styles panel.
9. Click Add Property in the lower pane, and type **position** in the field that opens.
10. Press Tab to move into the field where you set the property’s value, click the down arrow to reveal the available options, and select **Relative**. The navigation bar jumps into place at the bottom right of the header <div> (see Figure 21).

![Screenshot_42](http://res.cloudinary.com/medioxtra/image/upload/v1481703832/Screenshot_42_ki3wpg.png)

11. Exit Live view, and save the style sheet.

Note: Design view sometimes gets confused by positioned elements. If the header disappears in Design view, close and reopen index.html.

### Position text over the main image

Although the main_image &lt;div&gt; looks as though it’s filled with a large image, there’s actually nothing inside the &lt;div&gt;. The image is simply the background. The design calls for a block of text with a white background to be placed close to the white cross at the bottom-right of the image. You’ll use the same technique as for the navigation bar to move the text into position using a combination of relative and absolute positioning.

**Adding the text**
The text consists of two headings and a paragraph, so you need to create a **&lt;div&gt**; to hold them all together, and nest it inside the **main_image &lt;div&gt;**.
The most accurate way of inserting a new &lt;div&gt; is to use the options in the **Insert Div Tag dialog box**. It doesn’t matter where the Insertion point is, the options enable you to insert the &lt;div&gt; accurately, as long as your page elements have IDs.

1. Open the Insert Div Tag dialog box by clicking Div or Insert Div Tag in the Insert panel.

Alternatively, use the Insert menu. In the Creative Cloud update, choose Insert > Div. In earlier versions of Dreamweaver, choose Insert > Layout Objects > Div Tag.

2. Click the down arrow of the Insert pop-up menu to reveal the options (see Figure 22).

**The options available are**:

* **At insertion point**. The new &lt;div&gt; is inserted wherever the Insertion point currently is.
* **Before tag**. The new <div> is inserted immediately before the specified element’s opening tag.
* **After start of tag**. The new <div> is inserted immediately after the specified element’s opening tag.
* **Before end of tag**. The new <div> is inserted immediately before the specified element’s closing tag.
* **After tag**. The new <div> is inserted immediately after the specified element’s closing tag.
* Wrap around selection. This option is displayed only when something is selected in the document window. The new <div> is wrapped around the selected element(s).

3. The new &lt;div&gt; needs to be nested inside the main_image &lt;div&gt;, so it needs to go **after the starting tag of main_image**. Set the Insert pop-up menu to **After Start Of Tag**. (Because the main_image &lt;div&gt; is empty, you could also use Before End Of Tag in this case.)

This activates a new pop-up menu to the right of the Insert pop-up menu.

4. Click the down arrow of the new pop-up menu to reveal its contents. It lists the &lt;body&gt; tag, along with all other page elements that have an ID (see Figure 23).

![Screenshot_43](http://res.cloudinary.com/medioxtra/image/upload/v1481705400/Screenshot_43_l8uiqt.png)

5. Select &lt;div id="main_image"&gt; from the list.
6. Type **main_text** as the ID.
7. Click New CSS Rule at the bottom of the Insert Div Tag dialog box. This opens the New CSS Rule dialog box.
8. Dreamweaver automatically selects the correct values for Selector Type (ID) and Selector Name (#main_text). However, you need to check that Rule Definition is set to check_cs6.css. If it says This Document Only, select check_cs6.css from the Rule Definition list.

![Screenshot_44](http://res.cloudinary.com/medioxtra/image/upload/v1481705743/Screenshot_44_pbp9qa.png)

9. Click OK to open the **CSS Rule Definition dialog box**, and select Background from the Category list on the left.
10. Click the Background-color color, and select white (#FFF).
11. Select Box from the Category list on the left.
12. Type 300 in the Width text box, and make sure the pop-up menu alongside is set to px. This sets the width of the main_text <div> to 300 pixels.
13. Click OK. This saves the new CSS rule, and brings you back to the Insert Div Tag dialog box.
Click OK to close the Insert Div Tag dialog box. This inserts the main_text <div> with some placeholder text.
Click anywhere in the Document window away from the new <div> to deselect the placeholder text. The top-left of the main_image <div> should now have a 300-pixel wide, white box containing placeholder text (see Figure 24).

![Screenshot_45](http://res.cloudinary.com/medioxtra/image/upload/v1481706089/Screenshot_45_vzrn13.png)

The white background of the main_text div covers the background image, so the text can be clearly read.

16. Now, it’s time to insert the final text. In the Files panel (**Window > Files**), expand the assets folder, and double-click the main.txt file to open it.
17. Select the entirety of the last block of text in the file, everything from "OPERATIVE WORDS" up to and including ". . . hiding in his bathroom."
18. Copy the text by choosing Edit > Copy, by right-clicking and selecting Copy from the context menu, or by pressing Ctrl+C/Cmd+C.
19. Close the main.txt file.
20. Select the placeholder text for the main_text <div>, and paste the text from your clipboard by pressing Ctrl+V/Cmd+V or choosing Edit > Paste.

The text you copied from main.txt replaces the placeholder text, and the main_text &lt;div&gt; automatically expands vertically to accommodate it (see Figure 25).

![Screenshot_46](http://res.cloudinary.com/medioxtra/image/upload/v1481706651/Screenshot_46_t3ayym.png)

Choose File > Save All Related Files to save index.html and the style sheet.

**Moving the main text into position**

The main_text &lt;div&gt; will be absolutely positioned with the main_image &lt;div&gt; as its containing block. Although the technique is the same as used for the navigation menu, you need to **work out the offsets** from the bottom and right of the main_image &lt;div&gt;. You could try to judge the distance by eye and keep adjusting the values until you get it right. A more efficient way is to use **guides in the Dreamweaver Document window** to measure the distance accurately.

1. Make sure the Document window is in Design view. Click the Design button if it isn’t.
2. (Optional) Press F4 to hide the panels. You need a good view of the page layout, particularly of the main image.
3. Choose **View > Rulers > Show**. This adds rulers measured in pixels at the top and left of the Document window.
4. Click inside the top ruler and drag down. As you drag, you’ll see a thin, green, horizontal line move down the page, with a yellow tooltip indicating how many pixels it is from the top of the page (see Figure 26).
5. Continue dragging until the green line is flush with the bottom of the main image (around 485px).
6. Drag another guide from the top ruler until it’s in line with the position above the white cross where you would like the bottom of the main_text <div> to be. The exact position isn’t important. Use your eye to judge what looks good.
7. Make sure your cursor pointer is between the green guides you have just positioned on the page, and hold down the Ctrl key (Windows) or the Cmd key (Mac). Dreamweaver displays the distance in pixels between the two guides (see Figure 27).

![Screenshot_47](http://res.cloudinary.com/medioxtra/image/upload/c_scale,w_900/v1481709048/Screenshot_47_ojdgz6.png)

8. Make a note of the value.
9. Drag two guides from the left ruler, and position them 'one' in line with the right edge of the main image and 'second' where you would like the right edge of the main_text <div> to be.

![Screenshot_48](http://res.cloudinary.com/medioxtra/image/upload/v1481709842/Screenshot_48_pjpvvq.png)

10. Position your cursor pointer between the vertical guides and **hold down the Ctrl key** (Windows) or the Cmd key (Mac), to make a note of the distance**.
11. The white cross is equidistant from the bottom and right edges of the main image, so the horizontal and vertical distances should be the same. I find that 60 pixels is about right.

Note: If you have difficulty positioning the guides, double-click one of the guides to open the Move Guide dialog box, and set the position by typing a value in the Location text box. Use 425px for the horizontal guide. The value for the vertical guide will depend on the size of the Document window. Double-click the guide on the right edge of the main image to find its position, subtract 60, and use that value for the main_text vertical guide.

12. You need to make the main_image &lt;div&gt; the containing block for the main_text &lt;div&gt;, so **select #main_image** in the All Rules pane of the CSS Styles panel.
13. Click **Add Property** in the lower pane, **type position** in the field that opens. Then press Tab, and select **Relative** from the list of values in the list on the right.
14. Select #main_text and click the Edit Rule icon to reopen the CSS Rule Definition dialog box for the #main_text style rule.
15. Select Positioning from the Category list on the left, and add the following settings:
* Set Position to Absolute.
* Type 60 in the Right and Bottom text boxes under Placement, and make sure the pop-up menus alongside are set to px.

16. Click OK to close the CSS Rule Definition dialog box, and choose File > Save All Related Files to save the style sheet.

17. Activate Live view by clicking the Live button. The main_text <div> should move into position.
18. Turn off Live view. The right and bottom edges of the main_text <div> should be aligned precisely with the green guides, as shown in Figure 28.

![Screenshot_49](http://res.cloudinary.com/medioxtra/image/upload/c_scale,w_900/v1481710722/Screenshot_49_cmwgfo.png)

Note: If the main_text area still doesn’t move. Try closing index.html and reopening it.

19. You no longer need the guides, so dismiss them by choosing **View > Guides > Clear Guides**.

## Part 4: Inserting images and styling text
https://www.adobe.com/devnet/archive/dreamweaver/articles/first_website_pt4_cs6.html





