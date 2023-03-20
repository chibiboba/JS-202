# Lesson 4 : Lists and Tables

# Introduction

People are list-makers. We all use lists to track the groceries we want to buy, the little jobs and errands we need to get done, who to invite to a party, and more. Even our writing system and mathematics got their starts because of our desire to write lists. It's no surprise then that HTML provides list capabilities, and that the web is awash in them. What's unusual about HTML lists is how much power and flexibility you can access with a handful of HTML tags and list-centric CSS properties.

In addition to being list makers, people also seem to enjoy creating tables for data: multiplication tables, tax tables, sports standings, and so on. Of course, HTML provides a way to create tables; in fact, the `table` element and its child members combine in a startling variety of ways to produce almost any type of tabular structure that you need.

This lesson focuses initially on lists and how Web pages use them. While web pages don't use them nearly as often as images, you can still find them almost every place you look. It isn't always apparent that you're looking at a list. After a little experience, though, you'll be able to spot most HTML lists at a glance.

After discussing lists, we'll move on to tables. While they once were ubiquitous on the web, most developers use them less often today. Still, they remain an integral part of the HTML toolset.

## What to Focus On

- Learn to construct simple lists and nested lists.
- Learn to create horizontal lists.
- Using pseudo-classes `:hover` and `:focus`.
- Construct simple tables with headers, body, and footers.

### List Types

- Understand the difference between ordered, unordered, and description lists.
- Explain when to use which list type.

### Table Structures

- Understand the differences between columns, rows, and cells.
- Use table headers, body, and footers.
- Know the differences between table headers, row headings, and column headings.

### Study From The Summary

Spend time with the Summary at the end of this lesson. It reviews the topics and terminology you should master before moving on.

# Lists Overview

Given the variety of lists on the Web, you may find it surprising to learn that HTML provides a mere six tags to implement the three list types: **unordered,** **ordered,** and **description.**

## Unordered Lists

Unordered lists contain a series of unordered items. By unordered, we mean that there is no visual numbering or naming system for the items in the list. The content itself may have an implicit ordering, perhaps alphabetical, but the browser displays a **bullet** -- a glyph that looks like a small dot, disc, circle, or square -- instead of a number or letter before each item. By default, browsers render unordered lists vertically, each preceded by a bullet. However, you can choose a horizontal display and hide the bullets. You can even use custom bullets.

HTML uses the `<ul>` and `<li>` tags to construct unordered lists. Here's a simple example:

Copy Code

```html
<ul>
  <li>Red</li>
  <li>Orange</li>
  <li>Yellow</li>
  <li>Green</li>
  <li>Blue</li>
  <li>Indigo</li>
  <li>Violet</li>
</ul>
```



![An unordered list](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-01.png)



## Ordered Lists

Ordered lists have ordered content; that is, they have a sequence that is a visual component of the list. By default, most browsers render a vertical list of numbered items, but you can change this to roman numbers as well as alphabetic letters, including foreign alphabets. Examples of ordered lists include a numbered list of the top 10 programming languages or a numbered list of the steps required to make a pot of coffee.

HTML uses the `<ol>` and `<li>` tags to construct ordered lists. Here's a simple example:

Copy Code

```html
<ol>
  <li>Red</li>
  <li>Orange</li>
  <li>Yellow</li>
  <li>Green</li>
  <li>Blue</li>
  <li>Indigo</li>
  <li>Violet</li>
</ol>
```



![An ordered list](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-02.png)



All we did here was change the `<ul>...</ul>` tag to `<ol>...</ol>`.

## Description Lists

Description lists (called definition lists before HTML5) contain a list of terms and definitions. Each item in the list includes one or more terms and one or more definitions. Examples of description lists include dictionaries, bibliographies, and, that relic of the past, the phone book.

HTML uses the `<dl>`, `<dt>` and `<dd>` tags to construct description lists. Here's a simple example:

Copy Code

```html
<dl>
  <dt>Unordered</dt>
  <dd>A simple list with bullets.</dd>
  <dd>A plain list with no bullets or sequence numbers.</dd>

  <dt>Ordered</dt>
  <dd>A simple list with sequence numbers or letters.</dd>

  <dt>Description</dt>
  <dt>Definition</dt>
  <dd>A list with terms and definitions.</dd>
</dl>
```



![A description list](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-03.png)



Each grouping may have more than one term (`dt`) and more than one description (`dd`). The first item above has one term and two definitions, while the final includes two terms and one definition.

## Nested Lists

You can nest any list within another list, regardless of types. You can even mix and match them - put an unordered list inside a description list, for instance. In the following example, we'll add an example of each type of list to the description items:

Copy Code

```html
<dl>
  <dt>Unordered</dt>
  <dd>A simple list with bullets.</dd>
  <dd>A plain list with no bullets or sequence numbers.</dd>
  <dd>
    <ul>
      <li>Red</li>
      <li>Green</li>
      <li>Blue</li>
    </ul>
  </dd>

  <dt>Ordered</dt>
  <dd>A simple list with a visible sequence.</dd>
  <dd>
    <ol>
      <li>Red</li>
      <li>Green</li>
      <li>Blue</li>
    </ol>
  </dd>

  <dt>Description</dt>
  <dt>Definition</dt>
  <dd>A list with terms and definitions.</dd>
  <dd>
    <dl>
      <dt>Red</dt>   <dd><div class="red"></div></dd>
      <dt>Green</dt> <dd><div class="green"></div></dd>
      <dt>Blue</dt>  <dd><div class="blue"></div></dd>
    </dl>
  </dd>
</dl>
```

Copy Code

```css
li, dd, dt {
  font-size: 1.25rem;
}

.red, .green, .blue {
  width: 50px;
  height: 25px;
}

.red {
  background-color: red;
}

.green {
  background-color: green;
}

.blue {
  background-color: blue;
}
```



![Nested lists](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-04.png)



One more example: here we nest unordered lists to show how the tags nest:

Copy Code

```html
<ul>
  <li class="red">
    Red
    <ul>
      <li>&#9608;&#9608;&#9608;</li>
      <li>#ff0000</li>
      <li>rgb(255, 0, 0)</li>
    </ul>
  </li>

  <li class="green">
    Green
    <ul>
      <li>&#9608;&#9608;&#9608;</li>
      <li>#00ff00</li>
      <li>rgb(0, 255, 0)</li>
    </ul>
  </li>

  <li class="blue">
    Blue
    <ul>
      <li>&#9608;&#9608;&#9608;</li>
      <li>#0000ff</li>
      <li>rgb(0, 0, 255)</li>
    </ul>
  </li>
</ul>
```

Copy Code

```css
.red {
  color: red;
}

.green {
  color: green;
}

.blue {
  color: blue;
}
```



![Nested lists](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-05.png)



Notice how the bullets change at different levels. Most browsers will cycle through several different bullets as you nest unordered lists more deeply. Neither ordered lists, nor definition lists, do anything similar.

By the way; that `█` generates a solid rectangle character, █, the Unicode character for a full block. Most developers will never have a need for this character.

## Navigation Menus

Developers frequently use unordered lists to construct navigation menus, both vertical and horizontal. Commonly, you start out with HTML and CSS that looks something like this:

Copy Code

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Projects</a></li>
    <li><a href="#">Team</a></li>
    <li><a href="#">Help</a></li>
  </ul>
</nav>
```

Copy Code

```css
nav ul {
 background-color: powderblue;
 list-style-type: none;
 padding-left: 0;
 width: 200px;
}

nav li {
 font-size: 1.25rem;
}

nav a {
 box-sizing: border-box;
 color: blue;
 display: inline-block;
 line-height: 2.5;
 padding: 0 10px;
 text-decoration: none;
 width: 100%;
}

nav a:hover,
nav a:focus {
 background-color: blue;
 color: white;
}
```

[Home](https://launchschool.com/lessons/8c6e03e3/assignments/c0a144c6#)[Projects](https://launchschool.com/lessons/8c6e03e3/assignments/c0a144c6#)[Team](https://launchschool.com/lessons/8c6e03e3/assignments/c0a144c6#)[Help](https://launchschool.com/lessons/8c6e03e3/assignments/c0a144c6#)

![image-20230314181726077](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314181726077.png)

Our CSS removes the list bullets with the `list-style-type` property, and uses the `:hover` and `:focus` **pseudo-classes** to draw a highlight bar on the menu at appropriate times.

CSS provides more than 30 pseudo-classes that you can use as selectors. Here, we use `:hover` to determine whether the user's mouse cursor is above one of our links, while we use `:focus` to determine if the link has the current keyboard focus.

Some pseudo-classes, like `:last-child`, let you select elements based on their relationship to other elements. Others, like `:hover`, let you detect and react to user activity on the page. Still others, like `:full-screen`, can detect the user's browser state. See the MDN page on [Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) for a complete list. We will use some of these elsewhere in this course.

If you want a horizontal list, you need a few more changes:

- Reset the width of the menu (`ul`).
- Set the font size for the list (`ul`) to 0, then restore it for the list items (`li`).
- Set the list items to `inline-block`.
- Set the width of the list items to a value that will distribute the values the way you want them distributed (typically, you want a percentage width).
- Center the list items horizontally.

Copy Code

```css
nav ul {
  font-size: 0;
  width: 100%;
}

nav li {
  display: inline-block;
  font-size: 1.25rem;
  text-align: center;
  width: 25%;
}
```

[Home](https://launchschool.com/lessons/8c6e03e3/assignments/c0a144c6#) [Projects](https://launchschool.com/lessons/8c6e03e3/assignments/c0a144c6#) [Team](https://launchschool.com/lessons/8c6e03e3/assignments/c0a144c6#) [Help](https://launchschool.com/lessons/8c6e03e3/assignments/c0a144c6#)

![image-20230314181742031](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314181742031.png)

You will see this pattern of creating navigation lists often; learn it well.

# Practice Problems: Lists

Use Google Chrome for these practice problems to ensure that your browser results look the same as ours. Your code doesn't have to be identical to ours, but the output should be as close as possible.

We may use some new HTML and CSS in some of these problems. Be sure to look up unfamiliar tags and properties as you encounter them.

1. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

   **Raw Text**

   Copy Code

   ```plaintext
   The Next Reckoning: Capitalism and Climate Change
   By NATHANIEL RICH
   The world’s most difficult problem has a solution so simple that it can be
   expressed in four words: Stop burning greenhouse gases. How exactly to pull
   this off is somewhat more complicated — just not as complicated as most
   Americans have been led to believe.
   
   Related articles
   What Survival Looks Like After the Oceans Rise
   How Big Business is Hedging Against the Apocalypse
   Climate Chaos is Coming–and the Pinkertons Are Ready
   ```

   **How it should look in your browser:**

   

   ![Climate Change Article](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/climatechange.png)

   

   Solution

   Copy Code

   ```html
   <header>
     <h1>The Next Reckoning: Capitalism and Climate Change</h1>
     <p>By NATHANIEL RICH</p>
   </header>
   
   <p>
     The world’s most difficult problem has a solution so simple that it can be
     expressed in four words: Stop burning greenhouse gases. How exactly to
     pull this off is somewhat more complicated — just not as complicated as
     most Americans have been led to believe.
   </p>
   
   <h2>Related articles</h2>
   <ul>
     <li>What Survival Looks Like After the Oceans Rise</li>
     <li>How Big Business is Hedging Against the Apocalypse</li>
     <li>Climate Chaos is Coming–and the Pinkertons Are Ready</li>
   </ul>
   ```

   The `header` provides [semantic meaning](https://developer.mozilla.org/en-US/docs/Glossary/Semantics) to the elements that it contains. Here, it shows that the `h1` and `p` tags are part of the page header. You should use `header` consistently with any part of your page that you think of either a page header or a section header.

2. Add CSS to your solution for the previous problem to remove the bullet character before each list item.

   Hint

   Use the `list-style-type` CSS property.

   Solution

   Copy Code

   ```html
   <style>
     ul {
       list-style-type: none;
     }
   </style>
   ```

3. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

   **Raw Text**

   Copy Code

   ```plaintext
   5 Reasons to Use jQuery
   Open Source
   Endless Tutorials
   Huge Library
   Cross-browser Compatibility
   Large Variety of Plugins
   ```

   **How it should look in your browser:**

   

   ![5 Reasons to Use jQuery](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/5reasons.jpg)

   

   Solution

   Copy Code

   ```html
   <h1>5 Reasons to Use jQuery</h1>
   <ol>
     <li>Open Source</li>
     <li>Endless Tutorials</li>
     <li>Huge Library</li>
     <li>Cross-browser Compatibility</li>
     <li>Large Variety of Plugins</li>
   </ol>
   ```

4. Add CSS to your solution for the previous problem to change the numbers from decimal to uppercase Roman digits (I, II, III, IV, V).

   Solution

   Copy Code

   ```html
   <style>
     ol {
       list-style-type: upper-roman;
     }
   </style>
   ```

5. Update your solution from the previous problem to number the items in descending order (V, IV, III, II, I).

   Solution

   Copy Code

   ```html
   <h2>5 Reasons to Use jQuery</h2>
   <ol reversed>
     <li>Open Source</li>
     <li>Endless Tutorials</li>
     <li>Huge Library</li>
     <li>Cross-browser Compatibility</li>
     <li>Large Variety of Plugins</li>
   </ol>
   ```

   Note the boolean attribute `reversed` in this code. This bare word may be your first encounter with a boolean (true or false) attribute. Before HTML5, you would have had to code this as:

   Copy Code

   ```html
   <ol reversed="reversed">
   ```

   That's a bit contrived since the `reversed` attribute is new under HTML5. However, other boolean attributes have been around for a long time, so you will sometimes see this format.

6. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

   **Raw Text**

   Copy Code

   ```plaintext
   HTML
   Hypertext Markup Language, a standardized system for tagging text files to
   achieve font, color, graphic, and hyperlink effects on World Wide Web pages.
   
   Semantic
   Relating to meaning in language or logic.
   
   CSS
   A style sheet language used for describing the presentation of a document
   written in a markup language.
   ```

   **How it should look in your browser:**

   

   ![Definitions](https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_basic_html/b3.jpg)

   

   Solution

   Copy Code

   ```html
   <dl>
     <dt>HTML</dt>
     <dd>
       Hypertext Markup Language, a standardized system for tagging text files
       to achieve font, color, graphic, and hyperlink effects on World Wide Web
       pages.
     </dd>
     <dt>Semantic</dt>
     <dd>
       Relating to meaning in language or logic.
     </dd>
     <dt>CSS</dt>
     <dd>
       A style sheet language used for describing the presentation of a
       document written in a markup language.
     </dd>
   </dl>
   ```

7. The following code is an attempt to create a vertical navigation list on a web page:

   Copy Code

   ```html
   <nav>
     <ul>
       <li>Home</li>
       <li>Projects</li>
       <li>Team</li>
       <li>Help</li>
     </ul>
   </nav>
   ```

   Copy Code

   ```css
   html {
     font-size: 20px;
   }
   
   nav ul {
     background-color: yellow;
     width: 200px;
   }
   
   nav li {
     color: blue;
   }
   
   nav a {
     box-sizing: border-box;
     line-height: 2.5;
     padding: 0 10px;
     text-decoration: none;
     width: 100%;
   }
   ```

   Modify the code to remove the bullets. Each item should be 10px from the left edge of the yellow box. When you point to any line in the menu, the browser should highlight the entire line inside the yellow box. The final result should look like this:

   

   ![Vertical navbar](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/vertical-nav.png)

   

   Try not to cheat by looking at the previous assignment, but feel free to look up information elsewhere.

   Solution

   Copy Code

   ```html
   <nav>
     <ul>
       <li><a href="#">Home</a></li>
       <li><a href="#">Projects</a></li>
       <li><a href="#">Team</a></li>
       <li><a href="#">Help</a></li>
     </ul>
   </nav>
   ```

   Copy Code

   ```css
   html {
     font-size: 20px;
   }
   
   nav ul {
     background-color: yellow;
     list-style-type: none;
     padding-left: 0;
     width: 200px;
   }
   
   nav a {
     box-sizing: border-box;
     display: inline-block;
     line-height: 2.5;
     padding: 0 10px;
     text-decoration: none;
     width: 100%;
   }
   
   nav a:hover,
   nav a:focus {
     background-color: green;
     color: yellow;
   }
   ```

8. Convert the solution from the last problem to a horizontal navigation bar that takes up the full width of the page. Again, try not to peek at the previous assignment. The final result should look like this:

   

   ![Horizontal navbar](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/horizontal-nav.png)

   

   Solution

   Copy Code

   ```css
   nav ul {
     font-size: 0;
     width: 100%;
   }
   
   nav li {
     display: inline-block;
     font-size: 1rem;
     text-align: center;
     width: 25%;
   }
   ```

# Tables Overview

Back in the earliest days of the web, long before CSS took off, most developers employed tables to implement layouts. For instance, sites often used a format that had a banner at the top of the page, a footer at the bottom of the page, and two or three columns of content, navigation items, and ads between the two. Today, we use CSS to do that; back then, the solution required tables, so most developers learned how to use them for layout.

However, from the beginning, such code was a hack, and most people knew it. The HTML designers intended tables for use with tabular data - data in which the horizontal and vertical positions of each item were significant. For instance, consider this base-4 multiplication table:

|   *    | **04** | **14** | **24** | **34** |
| :----: | :----: | :----: | :----: | :----: |
| **04** |   04   |   04   |   04   |   04   |
| **14** |   04   |   14   |   24   |   34   |
| **24** |   04   |   24   |  104   |  124   |
| **34** |   04   |   34   |  124   |  214   |

From this table, we can determine the base-4 product of 24 (2 base 4) times 34 by looking down the left column for 24, and then across to column 34, and read off the result: 124.

Using tables to lay out non-tabular data was a frowned-upon workaround and led to the development of CSS and, later, the introduction of flex and grid in CSS.

Today, you should use tables for strictly tabular data, not layout.

A Launch School student found an interesting site that shows how tables were misused back in the early days. See [this forum post](https://launchschool.com/posts/65dbfc4a) for some comments and a link.

## Table Tags

HTML provides a variety of tags to construct tables. The ones you'll see most often are:

- The `<table>` tag defines a table.
- The `<tr>` tag defines a single row in a table.
- The `<td>` tag defines a single cell of content in a table. Each row includes zero or more cells.
- The `<th>` tag defines a single heading. The first cell in a row or column is typically a heading, but this is not required.
- `<thead>`, `<tbody>`, and `<tfoot>` each define a set of one or more rows that comprise the header, body, and footer rows of a table.

Here, we define a simple table with no `thead`, `tbody`, or `tfoot` components:

Copy Code

```html
<table>
  <tr>                      <!-- row 1 -->
    <th>Color Name</th>       <!-- column header 1 -->
    <th>Color Hex</th>        <!-- column header 2 -->
    <th>Color Decimal</th>    <!-- column header 3 -->
  </tr>

  <tr>                      <!-- row 2 -->
    <th>red</th>              <!-- row header (column 1) -->
    <td>#f00</td>             <!-- data cell 1 (column 2) -->
    <td>255, 0, 0</td>        <!-- data cell 2 (column 3) -->
  </tr>

  <tr>                      <!-- row 3 -->
    <th>green</th>            <!-- row header (column 1) -->
    <td>#0f0</td>             <!-- data cell 1 (column 2) -->
    <td>0, 255, 0</td>        <!-- data cell 2 (column 3) -->
  </tr>

  <tr>                      <!-- row 4 -->
    <th>blue</th>             <!-- row header (column 1) -->
    <td>#00f</td>             <!-- data cell 1 (column 2) -->
    <td>0, 0, 255</td>        <!-- data cell 2 (column 3) -->
  </tr>
</table>
```

Copy Code

```css
table {
  font-size: 1.5rem;
}
```



![Color table](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/tables-overview-01.png)



We use `<th>` to define the column and row headings, and how the browser renders the heading cells differently from the data cells.

## Semantic Table HTML and Heading Scope

You can use the `thead`, `tfoot`, and `tbody` elements to provide semantic identification of the header, footer, and body rows. You can also add the `scope` attribute to identify `th` elements as row (`scope="row"`) or column (`scope="col"`) headings. In the next example, we add these semantic features to the previous example, then use them as selectors in our CSS.

Copy Code

```html
<table>
  <thead>                              <!-- heading rows -->
    <tr>                                 <!-- row 1 -->
      <th scope="col">Color Name</th>      <!-- column header 1 -->
      <th scope="col">Color Hex</th>       <!-- column header 2 -->
      <th scope="col">Color Decimal</th>   <!-- column header 3 -->
    </tr>
  </thead>

  <tbody>                              <!-- body rows -->
    <tr>                                 <!-- row 2 -->
      <th scope="row">red</th>             <!-- row header (column 1) -->
      <td>#f00</td>                        <!-- data cell 1 (column 2) -->
      <td>255, 0, 0</td>                   <!-- data cell 2 (column 3) -->
    </tr>

    <tr>                                 <!-- row 3 -->
      <th scope="row">green</th>           <!-- row header (column 1) -->
      <td>#0f0</td>                        <!-- data cell 1 (column 2) -->
      <td>0, 255, 0</td>                   <!-- data cell 2 (column 3) -->
    </tr>

    <tr>                                 <!-- row 4 -->
      <th scope="row">blue</th>            <!-- row header (column 1) -->
      <td>#00f</td>                        <!-- data cell 1 (column 2) -->
      <td>0, 0, 255</td>                   <!-- data cell 2 (column 3) -->
    </tr>
  </tbody>

  <tfoot>                              <!-- footer -->
    <tr>                                 <!-- row 5 -->
      <td>name</td>                        <!-- data cell 1 (column 1) -->
      <td>#rrggbb</td>                     <!-- data cell 2 (column 2) -->
      <td>red, green, blue</td>            <!-- data cell 3 (column 3) -->
    </tr>
  </tfoot>
</table>
```

Copy Code

```css
table {
  font-size: 1.5rem;
}

th {
  font-size: 1.75rem;
}

tbody tr {
  font-style: italic;
}

tbody tr:nth-child(1) {
  color: red;
}

tbody tr:nth-child(2) {
  color: green;
}

tbody tr:nth-child(3) {
  color: blue;
}

tfoot tr {
  font-size: 1rem;
}

tfoot td {
  border-top: 1px solid gray;
}

td {
  text-align: center;
}

[scope="col"] {
  padding: 0 10px;
  text-decoration: underline;
}

[scope="row"] {
  text-transform: uppercase;
}
```



![Enhanced color table](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/tables-overview-02.png)



Note our use of the `:nth-child()` pseudo-class to select the first, second, and third rows of the `tbody`.

# Practice Problems: Tables

Use Google Chrome for these practice problems to ensure that your browser results look the same as ours. Your code doesn't have to be identical to ours, but the output should be as close as possible.

1. Create a table with column headings for "Product," "Quantity," and "Price." Fill the table with this data:

   Copy Code

   ```plaintext
   Apple, 34, $3.99/lb
   Banana, 116, $1.69/lb
   Carrot, 42, $2.49/lb
   Kiwi, 18, $0.69 ea.
   ```

   **How it should look in the browser:**

   

   ![Produce prices](https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_basic_html/t1.jpg)

   

   Solution

   Copy Code

   ```html
   <table>
     <thead>
       <tr>
         <th>Product</th>
         <th>Quantity</th>
         <th>Price</th>
       </tr>
     </thead>
     <tbody>
       <tr>
         <td>Apple</td>
         <td>34</td>
         <td>$3.99/lb</td>
       </tr>
       <tr>
         <td>Banana</td>
         <td>116</td>
         <td>$1.69/lb</td>
       </tr>
       <tr>
         <td>Carrot</td>
         <td>42</td>
         <td>$2.49/lb</td>
       </tr>
       <tr>
         <td>Kiwi</td>
         <td>18</td>
         <td>$0.69 ea.</td>
       </tr>
     </tbody>
   </table>
   ```

2. Update your solution to the previous problem to make the background color of the entire table cyan.

   Solution

   Copy Code

   ```css
   table {
     background-color: cyan;
   }
   ```

3. Update your solution to the previous problem to make the background color of the individual data cells orange.

   Solution

   Copy Code

   ```css
   td {
     background-color: orange;
   }
   ```

4. The background color of the table in the previous problem bleeds through as a border around the data cells. Update your solution to remove that border.

   Hint

   You will need to read the MDN documentation for `<table>.`

   Solution

   Copy Code

   ```css
   table {
     border-collapse: collapse;
   }
   ```

5. Update your solution to the previous problem to change the background color for the Banana and Kiwi rows to yellow.

   Hint

   Technique 1: Use classes. You will need to update both the HTML and the CSS.

   Technique 2: You can use a pseudo-class without updating the HTML.

   Solution

   Copy Code

   ```html
   <tr class="odd-row">
     <td>Apple</td>
     <td>34</td>
     <td>$3.99/lb</td>
   </tr>
   <tr class="even-row">
     <td>Banana</td>
     <td>116</td>
     <td>$1.69/lb</td>
   </tr>
   <tr class="odd-row">
     <td>Carrot</td>
     <td>42</td>
     <td>$2.49/lb</td>
   </tr>
   <tr class="even-row">
     <td>Kiwi</td>
     <td>18</td>
     <td>$0.69 ea.</td>
   </tr>
   ```

   Copy Code

   ```css
   /* delete this rule
   td {
     background-color: orange;
   }
   */
   
   .odd-row {
     background-color: orange;
   }
   
   .even-row {
     background-color: yellow;
   }
   ```

   Our solution relies on giving each row a class name that varies depending on the color we want to assign to the row. A more reliable solution that doesn't need classes uses the `:nth-child()` pseudo-class that we introduced in the previous assignment:

   Copy Code

   ```css
   tbody tr:nth-child(2n+1) {
     background-color: orange;
   }
   
   tbody tr:nth-child(2n+2) {
     background-color: yellow;
   }
   ```

   This variation of `:nth-child()` uses the `2n+` part of the parameter to select every other row.

6. Create a table with both column and row headings. Use "Name," "Major," and "GPA" for the columns, and student names for the rows. Be sure to tell the browser which headings are for columns and which are for rows.

   Copy Code

   ```plaintext
   Chris Lee, Supply Chain Management, 3.7
   Shane Riley, Photojournalism, 3.8
   Kevin Wang, Computer Science, 4.0
   ```

   **How it should look in the browser:**

   

   ![College records](https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_basic_html/t2.jpg)

   

   Solution

   Copy Code

   ```html
   <table>
     <thead>
       <tr>
         <th scope="col">Name</th>
         <th scope="col">Major</th>
         <th scope="col">GPA</th>
       </tr>
     </thead>
     <tbody>
       <tr>
         <th scope="row">Chris Lee</th>
         <td>Supply Chain Management</td>
         <td>3.7</td>
       </tr>
       <tr>
         <th scope="row">Shane Riley</th>
         <td>Photojournalism</td>
         <td>3.8</td>
       </tr>
       <tr>
         <th scope="row">Kevin Wang</th>
         <td>Computer Science</td>
         <td>4.0</td>
       </tr>
     </tbody>
   </table>
   ```

   Don't forget to provide the `scope` attributes!

7. Without adding anything to the HTML, update the solution to the previous problem to set the column headings to green, and the row headings to blue.

   Hint

   You can select tags in CSS based on attribute values.

   Solution

   Copy Code

   ```css
   [scope="col"] {
     color: green;
   }
   
   [scope="row"] {
     color: blue;
   }
   ```

8. For this table, our data has categories to create subsets of data within the same table. We need "Type," "Name," and "Price" column headings. Each row represents one of three different wine types. All rows that share a wine type should use the same row heading. Your result should look like the image below.

   Copy Code

   ```plaintext
   Red    Meiomi Pinot Noir             $17.99
          Radius Cabernet               $9.99
          Apothic Red                   $7.97
   White  Cloud Break Chardonnay        $8.99
          Kendall Jackson Chardonnay    $9.97
          Kim Crawford Sauvignon Blanc  $9.97
   Sake   Gekkeikan Sake                $9.99
          Mura Mura Mountain Sake       $15.99
          TY KU Sake Junmai Ginjo Black $21.99
   ```

   **How it should look in the browser:**

   

   ![Wine prices](https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_basic_html/t3.jpg)

   

   Hint

   You will need the `rowspan` attribute to make each type value span three rows.

   Solution

   Copy Code

   ```html
   <table>
     <thead>
       <tr>
         <th scope="col">Type</th>
         <th scope="col">Name</th>
         <th scope="col">Price</th>
       </tr>
     </thead>
     <tbody>
       <!-- first group of 3 rows -->
       <tr>
         <th scope="row" rowspan="3">Red</th>
         <td>Meiomi Pinot Noir</td>
         <td>$17.99</td>
       </tr>
   
       <tr>
         <td>Radius Cabernet</td>
         <td>$9.99</td>
       </tr>
   
       <tr>
         <td>Apothic Red</td>
         <td>$7.97</td>
       </tr>
   
       <!-- second group of 3 rows -->
       <tr>
         <th scope="row" rowspan="3">White</th>
         <td>Cloud Break Chardonnay</td>
         <td>$8.99</td>
       </tr>
   
       <tr>
         <td>Kendall Jackson Chardonnay</td>
         <td>$9.97</td>
       </tr>
   
       <tr>
         <td>Kim Crawford Sauvignon Blanc</td>
         <td>$9.97</td>
       </tr>
   
       <!-- third group of 3 rows -->
       <tr>
         <th scope="row" rowspan="3">Sake</th>
         <td>Gekkeikan Sake</td>
         <td>$9.99</td>
       </tr>
   
       <tr>
         <td>Mura Mura Mountain Sake</td>
         <td>$15.99</td>
       </tr>
   
       <tr>
         <td>TY KU Sake Junmai Ginjo Black</td>
         <td>$21.99</td>
       </tr>
     </tbody>
   </table>
   ```

   It is also possible for a single cell to span multiple columns; use the `colspan` attribute on the `td` tag. (You may need this feature in the next assignment.)

9. It's difficult to tell which wines apply to each type in the output of the previous problem. Update your solution to display a 1-pixel wide gray border around all the table's cells and headings.

   Hint

   Use the CSS property `border: 1px solid gray;`.

   Solution

   Copy Code

   ```css
   table {
     border-collapse: collapse;
   }
   
   td, th {
     border: 1px solid gray;
   }
   ```

   We saw the `border-collapse` property in an earlier problem on this page. The `td, th` selector selects both the `td` and `th` tags; you can also specify selectors separately.

# On Your Own: Nutrition Facts Label

The project described in this assignment serves as a review of almost everything you've learned so far. While building it, you should expect to learn some new information on your own. Experienced developers often have to learn unfamiliar material while working on a project, and this project will exercise your ability to do that.

Some countries, including the USA, require nutrition facts labels on packaged food items. We'll use a version of the US nutrition label in this assignment.

While the US nutrition facts label looks simple, it packs a lot of information into a small space. It also uses a wide variety of styling, with horizontal rules of varying heights; a variety of font sizes and weights; indented content; and more. Creating the markup and styles for a web version of the label is more work than you may realize.

Your task for this project is to replicate the US-style label shown below (from Wikimedia). You should strive to make it look as much like the original as possible without purchasing fonts: your font stack can use Franklin Gothic Heavy for the main heading, and Helvetica Black and Helvetica for the remaining fonts. Keep in mind that not all systems supply these fonts, so add Arial to the list, and let the browser supply a default font if necessary.

The following label isn't the most current FDA (US Food and Drug Administration) design, but it's the design you should replicate.



![FDA Nutrition Facts Label](https://upload.wikimedia.org/wikipedia/commons/2/2b/FDA_Nutrition_Facts_Label_2006.jpg)



The size of the image as seen above is probably incorrect. Right click and download the image, then view it "actual size" in an image viewer.

You can see and use our [completed example here](https://d3jtzah944tvom.cloudfront.net/lesson_5/nutrition_facts_label/label.html).

Our CSS uses precisely one class, though the HTML applies it to more than one element. We use no other classes and no IDs at all. See how close you can get to this in your solution. The challenge of limiting class and id selectors will push you to find other ways to identify the elements you want to select. For instance, you may need to specify adjacent siblings, use pseudo-classes (e.g., `:first-of-type`), and use highly specific selectors to override existing styles. Read [the MDN pages on CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors) before starting, and keep it handy as you work.

While coding, be mindful of semantics; avoid the `div` and `span` elements, and supply as much semantic information as you can. Our solution does not use `div` or `span` at all; try to match that.

There is more than one way to build this project. Our hints point you in the direction we took for our solution.

Hint 1

If you load our completed solution in your browser and load yours in another tab, you can toggle back and forth (shift-tab and control-shift-tab in most browsers) to see where the pages differ. This so-called **blink comparison** is useful when trying to replicate a design. We'll talk more about blink comparisons in a later lesson.

Hint 2

Validate your HTML and CSS and test your code frequently. As your first big project, validation and testing are crucial.

Hint 3

Use description lists to show nutrient names and quantities, e.g.,

Copy Code

```html
<dl>
  <dt>Total Fat</dt>
  <dd>8g</dd>
</dl>
```

Hint 4

Bottom and top borders are useful for rendering horizontal lines.

Hint 5

You can use a table to represent the content that shows nutrition data with the minimum percentages, and another table for the part below the "Percent Daily Values" explanation.

Hint 6

Table cells can span multiple columns when you apply the `colspan` attribute to the `<td>` or `<th>` tag.

Hint 7

Use a class selector to apply indentation to the indented lines.

Hint 8

Use a 28px font as the document's root font; use `rem` units to define other fonts.

Hint 9

Remember to use margins for spacing between elements, and padding for spacing within elements.

Hint 10

Use the MDN documentation to find properties you didn't know existed.

Hint 11

If you must, feel free to peek at our solution, but try to do so as a last resort.

Compare your results against our completed solution.

This project is a good candidate for a code review. A code review is not mandatory, however. If you're happy with your code and your results, feel free to skip the code review. Otherwise, try to identify areas where you have questions or doubts, and direct our attention there; reviewing HTML and CSS line-by-line isn't feasible, so help us focus on areas where we can help.

# Summary

This lesson was unusually brief considering the importance of lists and the complexity of tables. As with images, you don't need to know much; this lesson covered most of what you will need in your career for both topics. What remains chiefly has to do with learning to be flexible with both structures.

In this lesson, we discussed using lists on Web pages, and, in particular, the three list types: unordered, ordered, and description. We learned the basic mechanics of assembling lists using HTML and saw some of the techniques used for styling them.

We also talked about how and when to use tables (and when not to use them). In particular, tables present tabular data; don't use them for layout purposes. We learned the basic table HTML (rows, columns, and cells), and also learned about headings, headers, footers, and bodies, as well as how one row can span multiple columns or one column can span multiple rows.

On your own, you learned a bit more about pseudo-classes, in particular, `:hover`, `:focus`, and `:last-of-type`, and how we can use them to apply dynamic effects to elements.

In the next lesson, we'll look at forms. We use forms everywhere: when you register for or log in to a website, ordering goods from online merchants, writing posts in forums, and more.