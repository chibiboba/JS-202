

# Topics to focus on

Understanding HTML and CSS, and being proficient enough to construct attractive web pages, either from scratch or a provided design, is a fundamental skill for web developers of all kinds. However, not everybody must be an expert; in fact, few are. Thus, our goal is to provide a solid foundation to get you started, not to make you an expert.

Use the following guidelines to focus your study and practice as you move through this lesson:

### Vocabulary

As with everything else in the developer's world, there's a wealth of specialized terminology you must learn to converse with other developers and designers. The vocabulary you need here, though, is small compared to most languages, and most terms are easy to learn. In particular, you should become comfortable with:

- element and tag
- self-closing tag
- document type definition (DOCTYPE, DTD)
- attribute
- selector
- property
- id, class, and name

### The Difference Between HTML and CSS

These two technologies are so intertwined in contemporary Web pages that it seems like they do the same thing, and that they are dependent on each other. However, they are distinct and independent with different purposes. 

- HTML provides the structure and content of a web page; CSS describes the appearance, or presentation, of the page. 

There is a bit of overlap that can lead to some confusion: CSS can dictate the apparent structure, while HTML can inform the browser of some presentation elements.

### HTML and CSS Syntax

HTML and CSS both have simple syntax; you can learn nearly all you need for each language in a few minutes. Take the time you need to learn it well, and both HTML and CSS will become routine in no time.

For the most part, you shouldn't worry about the specific tags, attributes, selectors, and properties yet. Instead, focus on how to put these items together to create well-formed HTML and CSS. The rest will come with time and practice.

### Structure of a Web Page

All web pages start with some routine code that defines the basic layout of the document. It includes a DOCTYPE (we'll explain this later), an `<html>`, `<head>`, and `<body>` element, and a few other tags in the `<head>` section. Learn what this **boilerplate** code does, and how to use it in your web pages.

### Basic HTML Elements

The best way to learn HTML is to use it. The more you use it, the less often you'll need to refer to the documentation; however, you'll probably never learn it all, so don't try.

Start by learning to use the `<p>` (paragraph), `<a>` (anchor), and `<h1>`-`<h6>` elements. 

- Paragraphs are the primary organizational construct for text on web pages.
- anchors represent links to other pages.
- headings occur on most pages. 

These elements are so common that you want to learn them as soon as possible, so go ahead and memorize them.

You should also become familiar with these elements:

- `<em>`, `<strong>`
- `<header>`, `<main>`
- `<article>`, `<section>`, `<aside>`
- `<div>` and `<span>`

You don't have to know them by heart; you will remember them through repeated use.

### Using CSS With HTML

Become familiar with the three ways to use CSS in an HTML document: inline, internal, and external. For now, you should learn to use the `<style>` tag to provide internal CSS.

### Basic CSS Selectors

CSS has three primary types of selectors (tag, id, and class) that select elements based on the tag name, `id` attribute, or `class` attribute. Learn the syntax for these three selectors, but don't get bogged down trying to memorize how you can combine them. For now, rely on the documentation.

### CSS Properties

Stick to the documentation as you start out; don't try to memorize CSS properties until you've used them a few times and seen how they work and interact with your HTML. This way, you'll learn the features you need most often without spending a lot of time absorbing material that you may never use.

- The most important properties introduced in this lesson are `color`, `background-color`, `font-family`, and `font-size`; we recommend memorizing these. 

The other properties you see in this lesson will become familiar with time and practice.

### Use Your Browser's Inspector

Much of your work in this course involves looking at the structure and styling of web pages: sometimes in your web pages, sometimes from another site. Either way, the best way to examine these features and determine how the HTML and CSS work is with your browser's Inspector software (this may be an add-on in some browsers).

### Study From The Summary

Spend time with the Summary at the end of this lesson. It reviews the topics and terminology you should master before moving on.

# Tutorial Notes

[Building Your First Web Page](https://learn.shayhowe.com/html-css/building-your-first-web-page/) introduces the vocabulary of HTML and CSS and demonstrates a few of the most common tags and rules.

## Difference between HTML and CSS

- *HTML*, HyperText Markup Language, gives content structure and meaning by defining that content as, for example, headings, paragraphs, or images. *CSS*, or Cascading Style Sheets, is a presentation language created to style the appearance of content—using, for example, fonts or colors.
- The two languages—HTML and CSS—are independent of one another and should remain that way. CSS should not be written inside of an HTML document and vice versa. As a rule, HTML will always represent content, and CSS will always represent the appearance of that content.

## Common HTML Terms

#### Elements

- **Elements** are designators that define the structure and content of objects within a page. 
  - Elements are identified by the use of less-than and greater-than angle brackets, `< >`, surrounding the element name. Thus, an element will look like the following: `<a>`
- Common elements: 
  - **Paragraphs** are the primary organizational construct for text on web pages. (identified as the `<p>` element)
  - **Anchors** represent links to other pages. `<a>`
  - **Headings** occur on most pages. (identified as `<h1>` through `<h6>` elements)
  - The list goes on to include the `<a>`, `<div>`, `<span>`, `<strong>`, and `<em>` elements, and many more. `<a>`

#### Tags

- **Tags**: The use of less-than and greater-than angle brackets surrounding an element creates what is known as a *tag*. Tags most commonly occur in pairs of opening and closing tags.

- An **opening tag** marks the beginning of an element. It consists of a less-than sign followed by an element’s name, and then ends with a greater-than sign; for example, 

  ```html
  <a>
  ```

- A **closing tag** marks the end of an element. It consists of a less-than sign followed by a forward slash and the element’s name, and then ends with a greater-than sign; for example, `</div>`.

- The content that falls between the opening and closing tags is the **content** of that element. 

- An **anchor link**, for example, will have an opening tag of `<a>` and a closing tag of `</a>`. What falls between these two tags will be the content of the anchor link.

  - So, anchor tags will look a bit like this:

  ```html
  <a>...</a>
  ```

#### Attributes

- **Attributes** are properties used to provide additional information about an element.

- The most common attributes include 

  - `id` attribute, which identifies an element
  - `class` attribute, which classifies an element
  - `src` attribute, which specifies a source for embeddable content
  - `href` attribute, which provides a hyperlink reference to a linked resource.

- Attributes are defined within the opening tag, after an element’s name. Generally attributes include a name and a value. The format for these attributes consists of the attribute name followed by an equals sign and then a quoted attribute value. 

  - For example, an `<a>` element including an `href` attribute would look like the following:

  ```html
  <a href="http://shayhowe.com/">Shay Howe</a>
  ```

Example of anchor link

- This is an example of an anchor link. The element is an anchor. 
- The anchor element is declared with the opening `<a>` and closing `</a>` tags encompassing the text, and the hyperlink reference attribute and value are declared with `href="http://shayhowe.com"` in the opening tag.
- HTML syntax outline including an element, attribute, and tag:

![image-20230313153739933](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313153739933.png)

## Setting up HTML document structure

- HTML documents are saved with .html file extension rather than a .txt file extension.
- Two of the more popular plain text editors for writing HTML and CSS are Dreamweaver and Sublime Text. Free alternatives also include Notepad++ for Windows and TextWrangler for Mac.
- All HTML documents have a required structure that includes the following declaration and elements: `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`.

Declaration and Elements

- The document type declaration, or `<!DOCTYPE html>`, informs web browsers which version of HTML is being used and is placed at the very beginning of the HTML document. 
  - Because we’ll be using the latest version of HTML, our document type declaration is simply `<!DOCTYPE html>`. 
  - Following the document type declaration, the `<html>` element signifies the beginning of the document.
- Inside the `<html>` element, the `<head>` element identifies the top of the document, including any metadata (accompanying information about the page). 
  - The content inside the `<head>` element is not displayed on the web page itself. Instead, it may include the document title (which is displayed on the title bar in the browser window), links to any external files, or any other beneficial metadata.
- All of the visible content within the web page will fall within the `<body>` element. A breakdown of a typical HTML document structure looks like this:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Hello World</title>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a web page.</p>
  </body>
</html>
```

- The preceding code shows the document beginning with the document type declaration, `<!DOCTYPE html>`, followed directly by the `<html>` element. Inside the `<html>` element come the `<head>` and `<body>` elements. The `<head>` element includes the character encoding of the page via the `<meta charset="utf-8">` tag and the title of the document via the `<title>` element. The `<body>` element includes a heading via the `<h1>` element and a paragraph via the `<p>` element. Because both the heading and paragraph are nested within the `<body>` element, they are visible on the web page.

- When an element is placed inside of another element, also known as nested, it is a good idea to indent that element to keep the document structure well organized and legible. In the previous code, both the `<head>` and `<body>` elements were nested—and indented—inside the `<html>` element. The pattern of indenting for elements continues as new elements are added inside the `<head>` and `<body>` elements.

#### Self closing elements

- **Self closing elements**: In the previous example, the `<meta>` element had only one tag and didn’t include a closing tag. Fear not, this was intentional. Not all elements consist of opening and closing tags. Some elements simply receive their content or behavior from attributes within a single tag. The `<meta>` element is one of these elements. The content of the previous `<meta>` element is assigned with the use of the charset attribute and value. 
- Other common selfclosing elements include
  - `<br>`
  - `<embed>`
  - `<hr>`
  - `<img>`
  - `<input>`
  - `<link>`
  - `<meta>`
  - `<param>`
  - `<source>`
  - `<wbr>`

#### Code Validation

- No matter how careful we are when writing our code, we will inevitably make mistakes. Thankfully, when writing HTML and CSS we have validators to check our work. The W3C has built both [HTML](http://validator.w3.org/) and [CSS](http://jigsaw.w3.org/css-validator/) validators that will scan code for mistakes. Validating our code not only helps it render properly across all browsers, but also helps teach us the best practices for writing code.

## Common CSS Terms

#### Summary

- In CSS our rule set begins with the **selector**, which is immediately followed by curly brackets. Within these curly brackets are declarations consisting of property and value pairs. Each declaration begins with a **property**, which is followed by a colon, the **property value**, and finally a semicolon.
- It is a common practice to indent property and value pairs within the curly brackets. As with HTML, these indentations help keep our code organized and legible.

![CSS Syntax Outline](https://learn.shayhowe.com/assets/images/courses/html-css/building-your-first-web-page/css-syntax-outline.png)

#### Selectors

- As elements are added to a web page, they may be styled using CSS. 
- A ***selector*** is used to target one or more HTML elements to apply styles to. (Styles such as color, size, or position). 
- Selectors may include a combination of different qualifiers to select unique elements, all depending on how specific we wish to be. 
  - For example, we may want to select every paragraph on a page, or we may want to select only one specific paragraph on a page.

- Selectors generally target an attribute value, such as an `id` or `class` value, or target the type of element, such as `<h1>` or `<p>`.

- Within CSS, selectors are followed with curly brackets, `{}`, which encompass the styles to be applied to the selected element. 
- The selector here is targeting all `<p>` elements.

```css
p { ... }
```

#### Properties

- Once an element is selected, a **property** determines the styles that will be applied to that element. 
  - Property names fall after a selector, within the curly brackets, `{}`, and immediately preceding a colon, `:`. 
  - There are numerous properties we can use, such as `background`, `color`, `font-size`, `height`, and `width`, and new properties are often added. 
- In the following code, we are defining the `color` and `font-size` properties to be applied to all `<p>` elements.

```cs
p {
  color: ...;
  font-size: ...;
}
```

#### Values

- A value determines the behavior of that property. 
  - Values can be identified as the text between the colon, `:`, and semicolon, `;`.
- So far we’ve selected an element with a selector and determined what style we’d like to apply with a property. Now we can determine the behavior of that property with a value. 
- Here we are selecting all `<p>` elements and setting the value of the `color` property to be `orange` and the value of the `font-size` property to be `16` pixels.

```css
p {
  color: orange;
  font-size: 16px;
}
```

##### Type Selectors

##### Class Selectors

ID Selectors

##### Additional Selectors

#### Referencing CSS

#### Using CSS Resets

