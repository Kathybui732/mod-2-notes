# B2 Intermission Work

Answer these Check for Understanding questions as you work through the assignments.

## HTML

1. What is HTML?
  * HTML stands for Hypertext Markup Language. HTML is the standard markup language for Web pages. You use HTML to create your own website. Regulated standards by the  World Wide Web Consortium (W3C). The purpose of a web browser is to read the HTMl docutments and display them correctly.

2. What is an HTML element?
  * The `<html>` element is the root element and it defines the whole HTML document. It has a start tag `<html>` and an end tag `</html>`. An HTML element is defined by a starting tag. If the element contains other content, it ends with a closing tag. For example, `<p>` is starting tag of a paragraph and `</p>` is closing tag of the same paragraph but `<p>`This is paragraph`</p>` is a paragraph element. `<br>` is an empty element (doesn't have content and no end tag).

3. What is an HTML attribute?* An attribute is used to define the characteristics of an HTML element and is placed inside the element's opening tag. All attributes are made up of two parts − a name and a value. **name="value"*** The **name** is the property you want to set. For example, the paragraph `<p>` element in the example carries an attribut whose name is align, which you can use to indicate the alignment of paragraph on the page.* The **value** is what you want the value of the property to be set and always put within quotations. The below example shows three possible values of align attribute: left, center and right.* Attribute names and attribute values are case-insensitive.
  * All HTML elements can have attributes
    * The href attribute of `<a>` specifies the URL of the page the link goes to
    * The src attribute of `<img>` specifies the path to the image to be displayed
    * The width and height attributes of `<img>` provide size information for images
    * The alt attribute of `<img>` provides an alternate text for an image
    * The style attribute is used to add styles to an element, such as color, font, size, and more
    * The lang attribute of the `<html>` tag declares the language of the Web page
    * The title attribute defines some extra information about an element

4. What is the difference between a class and an id? When would you use one vs. the other?
  **id** used to create a bookmarks within a page. Used to specify a unique id for an HTML element (the value must be unique within the HTML document). The value of the id attribute must be unique within the HTML document. The id attribute can be used on any HTML element.  The id value is case-sensitive. The id value must contain at least one character, and must not contain whitespace (spaces, tabs, etc.).
  **class** is used to define equal styles for elements with the same class name. It's so that you can format things with the same "class" can have the same attributes so that they are formatted the same way.
  **difference** Class attributes can be used by multiple HTML elements while an id has to be unique within the page.

5. What HTML would you write to create a form for a new dog with a "name" and an "age"?
  ```<!DOCTYPE html>
<html>
<body>

<h2>New dog</h2>

<form action="/action_page.php">
  <label for="name">Name:</label><br>
  <input type="text" id="name" name="name"><br>
  <label for="age">Age:</label><br>
  <input type="text" id="age" name="age"><br><br>
  <input type="submit" value="Submit">
</form>

</body>
</html>
```

6. What are semantic tags? When would you use them over a `div`?
  Semantic element clearly describes its meaning to both the browser and the developer. That is they tell us and the browser about their content and their purpose, whereas 'div' does not tell us anything about their contents. Using systematic elements helps the engines to read the pafe and find the required info faster. 'div' do not do this.

7. Block level elements in HTML:
  * A container for all HTML elements. They section out a whole block on html by occupying the whole entire space of its parent element. They can take up one line or a multiple lines. Black level tags are: 'h1', 'h6', 'ol', 'ul', 'dl', 'li'.  

8. Explain what each of the following HTML tags do and when you would use them:
  * `<!DOCTYPE html>` Document type declaration. All HTML documents must start with a document type declaration. Not case sensitive
  * `<html>` and `</html>` - How all html documents start. The root element - defines the whole HTML document.
  * `<h1>`, `<h2>`, etc. - Headings. With 1 being the most important and 6 the least.
  * `<p>` - Paragraphs
  * `<body>` - visible part of the HTML document. The headers/title all of that is not visible. Only what is between the body
  * `<a>` and the `href` attribute `<a>` is the link tag. href is the link's destination. Link can be image or any other HTML element.
  * `<img>` and the `src` attribute - `<img>` is the image tag. src, alt, width and height are attributes. src is the source file. alt is alternative text. It's like when you want to name your link something else for the click.
  * `<br>` - line break. empty element. No body content. No need for an end tag.
  * `<hr>` - thematic break in an HTML page. Displayed as the horizontal rule. element is used to separate content (or define a change) in an HTML page. It's the `--------` we keep leaving before/after paragraphs to help with visual spacing.
  * `<pre>` - preformatted text. displayed in a fixed-width font (usually Courier), and it preserves both spaces and line breaks. So, it comes out kind of like the way you wrote it without having to use `br` to force line breaks.
  * `<img>` -	Defines an image
  * `<map>` -	Defines an image-map - Think about it like when you tag things/people in an IG photo.
  * `<area>` -	Defines a clickable area inside an image-map
  * `<picture>` -	Defines a container for multiple image resources
  * `<ul>` - unordered list has list items that start with `<li>`
  * `<ol>` - unordered list has list items that start with `<li>` Can create nested ones by adding anew `<ol>` and more `<li>`
  * `<div>` - block level element - defines a block of the element
  * `<span>` - Defines a section in a document like `<div>`, but, it is inline
  * `<section>` - Defines a section of a document. A thematic grouping of content, typically with a heading.
  * `<form>` - A form that is used to collect user input. Form elements are different types of input elements, like: text fields, checkboxes, radio buttons, submit buttons, and more.
  * `<input>` - takes in user input depending in the type i.e. text, radio buttons or a submit button.
  * `<label>` - label for the elements.

 ## CSS

1. What is CSS?
  CSS stands for Cascading Style Sheets. HTML was created to describe the contents of a webpage, whereas CSS was created to style formatting. CSS is a language that describes the style of an HTML document. It describes how HTML elements should be displayed. It controls the layout of multiple web pages. You can use different stylesheets to format the html differently.
1. What is a CSS selector? How do you use the ID selector? The class selector?
  A selector points to the HTML element you want to style. Selectors are used to "find" the HTML elements you want to style. CSS selectors can be divided into 5 categories:
   * simple selectors: select elements based on name, id and class
   * Combinatior selectors: selects elements based on a specific relationship between them
   * Pseudo-class selectors: selects elements based on state
   * Pseudo-element selectors: selects and styles part of an element
   * Attribute selectors: selects elements based on the attribute or attribute value. 
  An id selector uses the id sttribute of HTML element to select a specific element. id's are unique within a page which is why you can use an id selector to find id attributes. In order to use the id selector, you have to put a # before the id name. 
  A class selector selects an HTML element with a specific class attribute. To use a class selector, you use a period (.) before the class name. 
1. What are the three ways to include CSS in your HTML documents? What are the pros and cons of each?
   1. External CSS
   1. Internal CSS
   1. Inline CSS
1. What is the Box Model? Describe each component of the Box Model.

## SQL

### Jumpstart Lab Tutorial

1. What is a database?
1. What is SQL?
1. What is SQLite3?
1. What is a Table?
1. What is a primary key?
1. What is a foreign key?
1. Explain what each of the following SQL commands do:
  * insert
  * select
  * where
  * order by
  * inner join

### PG Exercises

1. How can you limit which columns you select from a table?
1. How can you limit which rows you select from a table?
1. How can you give a selected column a different name in your output?
1. How can you sort your output from a SQL statement?
1. What is joining? When do you need to join?
1. What is an aggregate function?
1. List three aggregate functions and what they do.
1. What does the `group` statement do?
1. How does the `group` statement relate to aggregates?

## Rails Tutorial: Task Manager

**Copy and Paste the link to your Task Manager repo here:**
**Copy and Paste the link to your Static Challenge here:**

1. Define CRUD.
1. Define MVC.
1. What three files would you need to create/modify for a Rails application to respond to a `GET` request to `/tasks`, assuming you have a `Task` model.
1. What are params? Where do they come from?
1. Check out your routes. Why do we need two routes each for creating a new Task and editing an existing Task?
