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

Given the variety of lists on the Web, you may find it surprising to learn that HTML provides a mere six tags to implement the three list types: **unordered,** **ordered,** and **description.**

# Lists

## Unordered Lists

- Unordered lists contain a series of unordered items. By unordered, we mean that there is no visual numbering or naming system for the items in the list. 
- The content itself may have an implicit ordering, perhaps alphabetical, but the browser displays a **bullet** -- a glyph that looks like a small dot, disc, circle, or square -- instead of a number or letter before each item. 
  - The bullets change at different levels. Most browsers will cycle through several different bullets as you nest unordered lists more deeply. 
- By default, browsers render unordered lists vertically, each preceded by a bullet. However, you can choose a horizontal display and hide the bullets. You can even use custom bullets.

HTML uses the `<ul>` and `<li>` tags to construct unordered lists. Here's a simple example:

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

- **Ordered lists** have ordered content; that is, they have a sequence that is a visual component of the list. 
- By default, most browsers render a vertical list of numbered items, but you can change this to roman numbers as well as alphabetic letters, including foreign alphabets. 
- Examples of ordered lists include a numbered list of the top 10 programming languages or a numbered list of the steps required to make a pot of coffee.

- HTML uses the `<ol>` and `<li>` tags to construct ordered lists. Here's a simple example:

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

- **Description lists** (called definition lists before HTML5) contain a list of terms and definitions. Each item in the list includes one or more **terms** and one or more **definitions**. 
- Each grouping may have more than one term (`dt`) and more than one description (`dd`). The first item above has one term and two definitions, while the final includes two terms and one definition.
- Examples of description lists include dictionaries, bibliographies, and, that relic of the past, the phone book.

- HTML uses the `<dl>`, `<dt>` and `<dd>` tags to construct description lists. Here's a simple example:

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

## Nested Lists

- You can nest any list within another list, regardless of types. You can even mix and match them - put an unordered list inside a description list, for instance. 
- In the following example, we'll add an example of each type of list to the description items:

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
  backgro=und-color: blue;
}
```

![Nested lists](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/lists-overview-04.png)

One more example: here we nest unordered lists to show how the tags nest:

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

- Notice how the bullets change at different levels. Most browsers will cycle through several different bullets as you nest unordered lists more deeply. Neither ordered lists, nor definition lists, do anything similar.

- By the way; that `&#9608;` generates a solid rectangle character, █, the Unicode character for a full block. Most developers will never have a need for this character.

## Navigation Menus

#### Vertical List

- Developers frequently use unordered lists to construct navigation menus, both vertical and horizontal. Commonly, you start out with HTML and CSS that looks something like this:

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

```css
nav ul {
 background-color: powderblue;
 list-style-type: none;
 padding-left: 0; /* removes padding on left side of list container */
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

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230324161059024.png" alt="image-20230324161059024" style="zoom:25%;" />

Explaining the code above

- Our CSS removes the list bullets with the `list-style-type` property. 
- Drawing a highlight bar: It also uses the `:hover` and `:focus` **pseudo-classes** to draw a **highlight bar** on the menu at appropriate times.
  - CSS provides more than 30 pseudo-classes that you can use as selectors. 
  - Here, we use `:hover` to determine whether the user's mouse cursor is above one of our links
  - We use `:focus` to determine if the link has the current keyboard focus.

- Some pseudo-classes, like `:last-child`, let you select elements based on their relationship to other elements. Others, like `:hover`, let you detect and react to user activity on the page. Still others, like `:full-screen`, can detect the user's browser state. See the MDN page on [Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) for a complete list. We will use some of these elsewhere in this course.

#### Horizontal List

- Reset the width of the menu (`ul`).
- Set the font size for the list (`ul`) to 0, then restore it for the list items (`li`). This is to remove white space between list items.
- Set the list items to `inline-block`.
- Set the width of the list items to a value that will distribute the values the way you want them distributed (typically, you want a percentage width).
- Center the list items horizontally.

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

![image-20230324161043911](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230324161043911.png)

You will see this pattern of creating navigation lists often; learn it well.

## Styling Lists

- https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Styling_lists

- Bullet styles

  - `list-style-type: none`

- Controlling list counting

  - `reversed` : This Boolean attribute specifies that the list's items are in reverse order. Items will be numbered from high to low.

  - Before HTML5, you would have had to code this as:

    ```html
    <ol reversed="reversed">
    ```

    That's a bit contrived since the `reversed` attribute is new under HTML5. However, other boolean attributes have been around for a long time, so you will sometimes see this format.

- Use the `:hover` and `:focus` **pseudo-classes** to draw a **highlight bar** on the menu at appropriate times.

  - Use `:hover` to determine whether the user's mouse cursor is above one of our links
  - Use `:focus` to determine if the link has the current keyboard focus.

  ```css
  nav a:hover,
  nav a:focus {
   background-color: blue;
   color: white;
  }
  ```

- `padding-left` is specified within the parent element, but it affects the child elements.

  - For example, if you have a list of items (`<ul>` or `<ol>`), you can apply left padding to each list item (`<li>`) using the `padding-left` property in CSS. The `padding-left` value will be specified within the CSS rule for the parent `<ul>` or `<ol>` element, and it will be applied to each child `<li>` element.
  - Here's an example:

  ```css
  ul {
    padding-left: 20px; /* parent element */
  }
  
  ul li { /* child element */
    list-style: disc;
    margin: 5px 0;
  }
  ```

  - In this example, the `padding-left` property is specified within the CSS rule for the `<ul>` element, which is the parent element of the `<li>` elements. The `padding-left` value of 20px is applied to each child `<li>` element, creating a left indent for the list items.

# Tables Overview

- Today, you should use tables for strictly tabular data, not layout.
  - Using tables to lay out non-tabular data was a frowned-upon workaround and led to the development of CSS and, later, the introduction of flex and grid in CSS.

- Back in earliest days of web before CSS, developers used tables to implement layouts.
  - For instance, sites often used a format that had a banner at the top of the page, a footer at the bottom of the page, and two or three columns of content, navigation items, and ads between the two. Today, we use CSS to do that; back then, the solution required tables, so most developers learned how to use them for layout.
  - However, from the beginning, such code was a hack, and most people knew it. The HTML designers intended tables for use with tabular data - data in which the horizontal and vertical positions of each item were significant. For instance, consider this base-4 multiplication table:

|   *    | **04** | **14** | **24** | **34** |
| :----: | :----: | :----: | :----: | :----: |
| **04** |   04   |   04   |   04   |   04   |
| **14** |   04   |   14   |   24   |   34   |
| **24** |   04   |   24   |  104   |  124   |
| **34** |   04   |   34   |  124   |  214   |

- From this table, we can determine the base-4 product of 24 (2 base 4) times 34 by looking down the left column for 24, and then across to column 34, and read off the result: 124.

- A Launch School student found an interesting site that shows how tables were misused back in the early days. See [this forum post](https://launchschool.com/posts/65dbfc4a) for some comments and a link.

## Table Tags

HTML provides a variety of tags to construct tables. The ones you'll see most often are:

- The `<table>` tag defines a table.
- The `<tr>` tag defines a single row in a table.
- The `<td>` tag defines a single **cell of content** in a column of a table. Each row includes zero or more cells.
- The `<th>` tag defines a single heading. The first cell in a row or column is typically a heading, but this is not required.
  - We use `<th>` to define the column and row headings, and how the browser renders the heading cells differently from the data cells.
  - For semantics: Use`scope` attribute to identify `th` elements as **row heading** (`scope="row"`) or **column heading** (`scope="col"`).

- `<thead>`, `<tbody>`, and `<tfoot>` each define a set of one or more rows that comprise the header, body, and footer rows of a table.

Here, we define a simple table with no `thead`, `tbody`, or `tfoot` components:

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

```css
table {
  font-size: 1.5rem;
}
```

![Color table](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_4/tables-overview-01.png)



## Semantic Table HTML and Heading Scope

- You can use the `thead`, `tfoot`, and `tbody` elements to provide semantic identification of the header, footer, and body rows. 
- You can also add the `scope` attribute to identify `th` elements as **row heading** (`scope="row"`) or **column heading** (`scope="col"`). 

In the next example, we add these semantic features to the previous example, then use them as selectors in our CSS.

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

## Styling Tables

CSS properties

- Remove border of background color around the data cells. 

  - `border-collapse` css property sets whether cells inside a `table` have shared or separate borders.
  - `border-collapse: collapse` Adjacent cells have shared borders.

  - `border-collapse: separate`: Adjacent cells have distinct borders.

- `background-color` : background color of table.

- Change background color of rows.

  - Use class attribute, which requires updating both HTML and CSS

  - 

  - Use pseudo-class without updating HTML. The entire row in the table header `thead` is not counted.

  - For example: This code selects every data cell, in every 2nd row starting from the 2nd row. 

    ```css
    tr:nth-of-type(2n+2) td {
      background-color: yellow;
    }
    ```

    or This code selects the same data cells which are child elements of `tr`. 

    ```css
    tbody tr:nth-child(2n+1) {
      background-color: orange;
    }
    
    tbody tr:nth-child(2n+2) {
      background-color: yellow;
    }
    ```

    Error: why doesn't this code work? It's because child elements have more specificity than parent elements, so `td` overrides `tbody tr:nth-child(2n+2)`

    ```css
    td {
    	background-color: orange;
    }
    
    tbody tr:nth-child(2n + 2) {
    	background-color: yellow;
    }
    ```

- `rowspan` attribute of `<th>` or `<td>` which indicates for how many rows the cell extends. 

  - It's default value is `1`; if its value is set to `0`, it extends until the end of the t

  - able section (`<thead>`, `<tbody>`, `<tfoot>`, even if implicitly defined), that the cell belongs to. Values higher than 65534 are clipped down to 65534.

  - For example if you want `th` to span 3 rows in the code it will span across the next 3 rows, and the header `th` will be centered among the rows.

    <img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230325105311995.png" alt="image-20230325105311995" style="zoom: 50%;" />

    ```html
      <table>
          <thead>
            <tr>
              <th scope="col">Type</th>
              <th scope="col">Name</th>
              <th scope="col">Price</th>
              <td></td>
            </tr>
          </thead>
    
          <tbody>
            <tr>
              <th scope="row" rowspan="3">red</th>
              <td>Meiomi Pino Noir</td>
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
          </tbody>
        </table>
    ```

- Use the `colspan` attribute on the `td` tag for a single cell to span multiple columns.