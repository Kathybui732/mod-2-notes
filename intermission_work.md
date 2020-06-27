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
   1. External CSS - changes the look of an entire website. Uses .css extension file 
   1. Internal CSS - used if one single HTML page has a unique style. defined inside the `<style>`.
   1. Inline CSS - used for a unique style of one single element. This method loses the advantages of a style sheet by mixing content with presentation.
1. What is the Box Model? Describe each component of the Box Model.
"Box model" is used to talk about design and layout. It is essentially a box that wraps around every html element consisting of margins, borders, padding and the actual content. **content** is where the text and images appear. **padding** is the transparent area aroung the content. **border** is the border that goes around the padding and content. **margin** is the transparent area cleared out arounf the boarder. 

## SQL

### Jumpstart Lab Tutorial

1. What is a database?
  A database is a systematic collection of information that is organized in a way that it can easily be accessed, managed and updated. It stores and takes care of data. Computer database structures save, organize, protect and deliver data. Think: A library is a database that stores textual data.
   * **Database management system (DBM)** is a collection of programs that enable its users to access databases, manipulate data and help in represenation of the data.
     * hierarchical DBMS - parent-child relationship of storing data. Not as used anymore. Has nodes for records and branches for fields. 
     * Network DBMS - many to many relationships. RDM servers. 
     * Relational DBMS - builds relations via tables. Does not support many-to-many. Most popular. MySQL, Oracle, microsoft SQL server, sybase. 
     * Object oriented relation DBMS - supports storage of new datatypes in the form of objects. 
   * **Text database** when data is organized in a text file in rows and columns - can be used to store, organize, protect, and retrieve data. 
   * **Desktop Database Programs** a database that's more complex than a text database and is intended for a single user. Think excel. It allows users to enter data, store it, protect it, and retrieve it when needed. Allows you to store large amounts of data and manipulate and change them quickly. 
   * **Relational Database Management Systems** allows for multiple users to work with the same data at the same time. This creates an advanced security for access for the data. It also stores data in columns/rows in a table. 
1. What is SQL?
  Structures Query Language - standard language for dealing with relational databases. Effective in being able to insert, search, update, delete database records. It helps in optimizing and maitenance of databases. 
1. What is SQLite3?
  Compact free database that you can use to create and use a database. It's not the full featured database, but it's useful in jumpstarting how to learn SQL and follows a large set of SQL standards. 
1. What is a Table?
  A collection of related data held in rows (records) and columns (fields) within a database. 
1. What is a primary key?
  Uniquely identifies each record in a table. It contains unique vales and cannot contain null values. A table can only have one promary key which can consist of single or multiple columns. 
1. What is a foreign key?
  A key used to link two tables together. It is a field or collection of fields in one table that refers to the primary key in another table. It is used to prevent actions that would destroy the links between tables. 
1. Explain what each of the following SQL commands do:
  * INSERT - puts data into the database
  * SELECT - extracts data form a database
  * WHERE - used to filter records; used to extract only those records(rows) that fulfill a specified condition.
  * ORDER BY - used to sort the result-set in ascending or descending order. Order by keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword.
  * INNER JOIN - keyword selects records that have matching values in both tables.
  * UPDATE - updates data in a database
  * DELETE - deletes data from a database
  * CREATE DATABASE - creates a new database
  * ALTER DATABASE - modifies a database
  * CREATE TABLE - creates a new table
  * ALTER TABLE - modifies a table
  * DROP TABLE - deletes a table
  * CREATE INDEX - creates an index (search key)
  * DROP INDEX - deletes an index
  * LIKE - provides simple pattern matching on strings. Takes a string with the % character matching any string, and _ matching any single character
  * IN - Helps to match like the WHERE but, takes in a larger number of possible matches. 

### PG Exercises

1. How can you limit which columns you select from a table?
  `select [some set of columns] from [some table or group of tables]` The database will look at only the cloumns available in the from clause. Columns are separated by a comma. `*` is the shorthand for all columns.
1. How can you limit which rows you select from a table?
  `select [some set of columns] from [some table or group of tables] where [rows that fulfill a specific condition]` You can use and/or to specify ranges. 
1. How can you give a selected column a different name in your output?
  * different column with different row values - cost is the new column and expensive/cheap are the new values. 
    ```select [column header], 
            case when [condition] then
		               'expensive'
	           else
		               'cheap'
	           end as cost
	           from cd.facilities;
    ```
1. How can you sort your output from a SQL statement?
    ```select distinct [column] from [table] order by [column] limit 10;```
    * `distinct` removes duplicate rows.
    * `from` table
    * `order by` orders things in ascending order unless otherwise specified
    * `limit` limits the number of results retrieved
1. What is joining? When do you need to join?
  Join clauses are used to combine rows from two or more tables based on related columns between them. JOIN is needed to get details about the reference data. There are times when the data gets repeated in a table and you would not like to store it for every record repeatedly. Not only it will take extra space, but could lead to update/delete anomalies and thus having inconsistent/redundant data.
1. What is an aggregate function?
  It is used to extract information about whole groups of rows and allows us to easily ask questions yielding the most expensive facility or who has recommended the most new members.It preforms a calculation on a set of values and returns a single calue. Aggregate functions ignore null values. They are often used with the group by clause and select statement. All aggregate functions are deterministics. 
1. List three aggregate functions and what they do.
	* COUNT counts how many rows are in a particular column.
  	* SUM adds together all the values in a particular column.
  	* MIN and MAX return the lowest and highest values in a particular column, respectively.
  	* AVG calculates the average of a group of selected values.
1. What does the `group` statement do?
  Groups rows that have the same values into summary rows 
1. How does the `group` statement relate to aggregates?
  Group by statements are often used with aggregate functions (count, sum, min/max, avg) to group the result-set ny one or more columns. 

## Rails Tutorial: Task Manager

**Copy and Paste the link to your Task Manager repo here:**
**Copy and Paste the link to your Static Challenge here:**

1. Define CRUD.
   * C: Create
   * R: Read
   * U: Update
   * D: Delete
1. Define MVC.
   Model, view, controller. Allows for more dynamic pages. Basic structure which most web applications are built on.
1. What three files would you need to create/modify for a Rails application to respond to a `GET` request to `/tasks`, assuming you have a `Task` model.
	* app - This is where our MVC structure lives.
	* config - Inside this directory, in the routes.rb file is where we will tell our Rails app which HTTP requests to respond to.
	* db - Where our database structure will be set up.
1. What are params? Where do they come from?
	Params refers to the parameters being passed to the controller via a GET or POST request. It is the parameters method that comes from ActionController::Base, which is accessed by your application via ApplicationController.
1. Check out your routes. Why do we need two routes each for creating a new Task and editing an existing Task?
	We use routes to map a URL to a controller and an action. When the Rails router sees a request it dispatches it to a controller's action matching the URL.We need two different routes when creating a new task and editing an existing one because they're living in two different locations. If they routed to the same place, what you did would overwrite the previous thing. LIke, let's say we had an existing task, if we wrote a new one, that existing one would disappear and a new task would take its place if they had the same route. 
