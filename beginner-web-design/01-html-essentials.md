# HTML Essentials

##  First look at HTML

  *	HTML = Content
  *	CSS = Style
  *	Pages are made up of elements (headers, paragraphs, etc…)
  *	`<h1>Example Content</h1>`
  *	h1-heading level 1
  *	h6-heading level 6
  *	p-paragraph
  *	img-image
  *	ul-unordered list
  *	ol-ordered list
  *	li-list item
  
##  Creating your first html file

  *	Finding a text editor
    *	Do not use a word processor
    *	text editors allow for “plain text”
  *	File extension
    *	.html = webpage
  *	File save
    *	Control + S

##  Russian Stacking Dolls-Bulleted Lists
  ```
  <h1>My Grocery List</h1>
  <ul>
    <li>Milk</li>
    <li>Eggs</li>
    <li>Bread</li>
    <ul>
      <li>Cinnamon raisin bread</li>
    </ul>
  </ul>
  ```

•	HTML Doc structure
  ```
  <!DOCTYPE html> --> tells web browser to use recent html
  <html>
    <head>
      <meta charset=”utf-8”> --> English charset
      <title>Example Page</title> --> changes tab name
    </head>
    <body>
      <h1>Sample Page</h1>
      <p>a paragraph</p>
    </body>
  </html>
  ```
  
•	Linking one page to another
  * `<p> I like <a href = “index.html”>html</a></p>`
  *	href redirects user to site when clicked
