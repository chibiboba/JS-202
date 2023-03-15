# Tutorial 1: 

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

  - For example, an `<a>` anchor element including an `href` attribute would look like the following:

  ```html
  <a href="http://shayhowe.com/">Shay Howe</a>
  ```

#### Example of anchor link

- This is an example of an anchor link. The element is an anchor. 
- The anchor element is declared with the opening `<a>` and closing `</a>` tags encompassing the text, and the hyperlink reference attribute and value are declared with `href="http://shayhowe.com"` in the opening tag.
- HTML syntax outline including an element, attribute, and tag:

![image-20230313153739933](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313153739933.png)

#### Void element

Empty/ void element

Chatgpt: Anchor elements in HTML are defined using the `<a>` tag, which is an example of an empty element or a void element. This means that the `<a>` tag doesn't have a closing tag, and it doesn't contain any content or child elements.

In HTML, the `>` character is used to denote the end of a tag, so it's not necessary to include it after the opening `<a>` tag. For example, the correct syntax for creating a hyperlink using an anchor element is:

```html
<a href="something.com">Click here</a>
```

## Setting up HTML document structure

- HTML documents are saved with .html file extension rather than a .txt file extension.
- Two of the more popular plain text editors for writing HTML and CSS are Dreamweaver and Sublime Text. Free alternatives also include Notepad++ for Windows and TextWrangler for Mac.
- All HTML documents have a required structure that includes the following declaration and elements: `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`.

#### Declaration and Elements

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

- **Self closing elements**: Not all elements consist of opening and closing tags. Some elements simply receive their content or behavior from attributes within a single tag. 
- The `<meta>` element is one of these elements: The content of the previous `<meta>` element is assigned with the use of the charset attribute and value. 
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

- As elements are added to a web page, they may be styled using CSS. A **selector** is used to target one or more HTML elements to apply styles to. (Styles such as color, size, or position). 
  - Selectors may include a combination of different qualifiers to select unique elements, all depending on how specific we wish to be. 
  - For example, we may want to select every paragraph on a page, or we may want to select only one specific paragraph on a page.

- Selectors generally target an attribute value, such as an `id` or `class` value, or target the type of element, such as `<h1>` or `<p>`.

- Within CSS, selectors are followed with curly brackets, `{}`, which encompass the styles to be applied to the selected element. 
- The selector here is targeting all `<p>` elements.

CSS

```css
p { ... }
```

##### Type Selectors

- Type selectors target elements by their element type. 
- For example, should we wish to target all division elements, `<div>`, we would use a type selector of `div`. 

- The following code shows a type selector for division elements as well as the corresponding HTML it selects.

CSS

```cs
div { ... }
```

The HTMl it selects.

```html
<div>...</div>          
<div>...</div>
```

##### Class Selectors

- **Class selectors** allow us to select an element based on the element’s `class` attribute value. Class selectors are a little more specific than type selectors, as they select a particular group of elements rather than all elements of one type.

- Class selectors allow us to apply the same styles to different elements at once by using the same `class` attribute value across multiple elements.

- Within CSS, classes are denoted by a leading period, `.`, followed by the `class` attribute value. Here the class selector will select any element containing the `class` attribute value of `awesome`, including both division and paragraph elements.

CSS

```css
.awesome { ... }
```

The HTML it selects.

```html
<div class="awesome">...</div>
<p class="awesome">...</p>
```

ID Selectors

- **ID selectors** are even more precise than class selectors, as they target only one unique element at a time. Just as class selectors use an element’s `class` attribute value as the selector, ID selectors use an element’s `id` attribute value as a selector.

- Regardless of which type of element they appear on, `id` attribute values can only be used once per page. If used they should be reserved for significant elements.

- Within CSS, ID selectors are denoted by a leading hash sign, `#`, followed by the `id` attribute value. Here the ID selector will only select the element containing the `id` attribute value of `shayhowe`.

CSS

```css
#shayhowe { ... }
```

the HTML it selects

```HTML
<div id="shayhowe">...</div>
```

##### Additional Selectors

- Selectors are extremely powerful, and the selectors outlined here are the most common selectors we’ll come across. These selectors are also only the beginning. Many more [advanced selectors](https://learn.shayhowe.com/advanced-html-css/complex-selectors/) exist and are readily available. When you feel comfortable with these selectors, don’t be afraid to look into some of the more advanced selectors.

- All right, everything is starting to come together. We add elements to a page inside our HTML, and we can then select those elements and apply styles to them using CSS. Now let’s connect the dots between our HTML and CSS, and get these two languages working together.

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

## Referencing CSS

- In order to get our CSS talking to our HTML, we need to reference our CSS file within our HTML. 
- The best practice for referencing our CSS is to include all of our styles in a single external style sheet, which is referenced from within the `<head>` element of our HTML document. Using a single external style sheet allows us to use the same styles across an entire website and quickly make changes sitewide.
- Other Options for Adding CSS
  - Other options for referencing CSS include using internal and inline styles. You may come across these options in the wild, but they are generally frowned upon, as they make updating websites cumbersome and unwieldy.

<u>Create external CSS style sheet</u>

- To create our external CSS style sheet, we’ll want to use our text editor of choice again to create a new plain text file with a `.css` file extension. 
  - Our CSS file should be saved within the same folder, or a subfolder, where our HTML file is located.
- Within the `<head>` element of the HTML document, the `<link>` element is used to define the relationship between the HTML file and the CSS file. 
  - Because we are linking to CSS, we use the `rel` attribute with a value of `stylesheet` to specify their relationship. `rel` attribute specifies the relationship between the current document and the linked document.
  - Furthermore, the `href` (or hyperlink reference) attribute is used to identify the location, or path, of the CSS file.

- Consider the following example of an HTML document `<head>` element that references a single external style sheet.

```html
<head>
  <link rel="stylesheet" href="main.css">
</head>  
```

- In order for the CSS to render correctly, the path of the `href` attribute value must directly correlate to where our CSS file is saved. In the preceding example, the `main.css` file is stored within the same location as the HTML file, also known as the root directory.

- If our CSS file is within a subdirectory or subfolder, the `href` attribute value needs to correlate to this path accordingly. For example, if our `main.css` file were stored within a subdirectory named `stylesheets`, the `href` attribute value would be `stylesheets/main.css`, using a forward slash to indicate moving into a subdirectory.

- At this point our pages are starting to come to life, slowly but surely. We haven’t delved into CSS too much, but you may have noticed that some elements have default styles we haven’t declared within our CSS. That is the browser imposing its own preferred CSS styles for those elements. Fortunately we can overwrite these styles fairly easily, which is what we’ll do next using CSS resets.

## Using CSS Resets

- Every web browser has its own default styles for different elements. How Google Chrome renders headings, paragraphs, lists, and so forth may be different from how Internet Explorer does. 
  - To ensure cross-browser compatibility, CSS resets have become widely used.

- CSS resets take every common HTML element with a predefined style and provide one unified style for all browsers. 
  - These resets generally involve removing any sizing, margins, paddings, or additional styles and toning these values down. 
  - Because CSS cascades from top to bottom—more on that soon—our reset needs to be at the very top of our style sheet. Doing so ensures that those styles are read first and that all of the different web browsers are working from a common baseline.

- There are a bunch of different resets available to use, all of which have their own fortes. One of the most popular resets is [Eric Meyer’s reset](http://meyerweb.com/eric/tools/css/reset/), which has been adapted to include styles for the new HTML5 elements.

- If you are feeling a bit more adventurous, there is also [Normalize.css](http://necolas.github.io/normalize.css/), created by Nicolas Gallagher. Normalize.css focuses not on using a hard reset for all common elements, but instead on setting common styles for these elements. It requires a stronger understanding of CSS, as well as awareness of what you’d like your styles to be.

Cross-Browser Compatibility & Testing

- As previously mentioned, different browsers render elements in different ways. It’s important to recognize the value in cross-browser compatibility and testing. Websites don’t need to look exactly the same in every browser, but they should be close. Which browsers you wish to support, and to what degree, is a decision you will need to make based on what is best for your website.

In all there are a handful of things to be on the lookout for when writing CSS. The good news is that anything is possible, and with a little patience we’ll figure it all out.

# Tutorial 2: HTML semantics

[Getting to Know HTML](https://learn.shayhowe.com/html-css/getting-to-know-html/) discusses some basic HTML concepts, notably semantics, headings, paragraphs, simple HTML-based styling, and the general structure of an HTML document. It also examines hyperlinks and URLs.

## What are semantics

- So what exactly are semantics?
  - [Semantics within HTML](http://boagworld.com/dev/semantic-code-what-why-how/) is the practice of giving content on the page meaning and structure by using the proper element. Semantic code describes the *value* of content on a page, regardless of the style or appearance of that content. 
  - There are several benefits to using semantic elements, including enabling computers, screen readers, search engines, and other devices to adequately read and understand the content on a web page. Additionally, semantic HTML is easier to manage and work with, as it shows clearly what each piece of content is about.
- Moving forward, as new elements are introduced, we’ll talk about what those elements actually mean and the type of content they best represent. Before we do that, though, let’s look at two elements—`<div>`s and `<span>`s—that actually don’t hold any semantic value. They exist for styling purposes only.

## Identifying Divisions and Spans

- Divisions or `<div>`s and `<span>`s are two HTML elements that act as generic containers for sytyling purposes only. They don't hold any semantic value. ly.
  - As **generic containers**, they do not come with any overarching meaning or semantic value. 
  - Paragraphs are **semantic** in that content wrapped within a `<p>` element is known and understood as a paragraph. `<div>`s and `<span>`s do not hold any such meaning and are simply containers.

- Both `<div>`s and `<span>`s, however, are extremely valuable when building a website in that they give us the ability to apply targeted styles to a contained set of content.

  - A `<div>` is a block-level element that is commonly used to identify large groupings of content, and which helps to build a web page’s layout and design. 

  - A `<span>`, on the other hand, is an inline-level element commonly used to identify smaller groupings of text within a block-level element.

- We’ll commonly see `<div>`s and `<span>`s with `class` or `id` attributes for styling purposes. Choosing a `class` or `id` attribute value, or name, requires a bit of care. We want to choose a value that refers to the content of an element, not necessarily the appearance of an element.

- Example
  - For example, if we have a `<div>` with an orange background that contains social media links, our first thought might be to give the `<div>` a `class` value of `orange`. What happens if that orange background is later changed to blue? Having a `class` value of `orange` no longer makes sense. A more sensible choice for a `class` value would be `social`, as it pertains to the contents of the `<div>`, not the style.

```html
<!-- Division -->
<div class="social">
  <p>I may be found on...</p>
  <p>Additionally, I have a profile on...</p>
</div>

<!-- Span -->
<p>Soon we'll be <span class="tooltip">writing HTML</span> with the best of them.</p>
```

#### Block vs. Inline Elements

- Most elements are either block- or inline-level elements. What’s the difference?
- **Block-level elements begin on a new line, stacking one on top of the other, and occupy any available width.** 
  - Block-level elements may be nested inside one another and may wrap inline-level elements. 
  - We’ll most commonly see block-level elements used for larger pieces of content (to create larger structures like paragraphs, headings, and lists.)

- **Inline-level elements do not begin on a new line.** 
  - They fall into the normal flow of a document, lining up one after the other, and only maintain the width of their content. Inline-level elements may be nested inside one another; however, they cannot wrap block-level elements. 
  - Inline-level elements are typically used to add emphasis or to provide additional information within a sentence or paragraph.
  - We’ll usually see inline-level elements with smaller pieces of content, such as a few words.
  - Some common inline-level elements include:
    - `<a>` - hyperlink
    - `<span>` - generic inline container
    - `<em>` - emphasis
    - `<strong>` - strong importance
    - `<img>` - image
    - `<input>` - input field


#### Comments within HTML & CSS

- HTML comments start with `<!-- and end with -->`. CSS comments start with `/*` and end with `*/`.

- The previous code includes exclamation points within the HTML, and that’s all right. Those are not elements, those are comments.

- HTML and CSS give us the ability to leave comments within our code, and any content wrapped within a comment will not be displayed on the web page. Comments help keep our files organized, allow us to set reminders, and provide a way for us to more effectively manage our code. Comments become especially useful when there are multiple people working on the same files.

## Using Text-based Elements

Many different forms of media and content exist online; however, text is predominant. Accordingly, there are a number of different elements for displaying text on a web page. For now we’ll focus on the more popular elements, including headings, paragraphs, bold text to show importance, and italics for emphasis. Later, within Lesson 6, “[Working with Typography](https://learn.shayhowe.com/html-css/working-with-typography/),” we’ll take a closer look at how to style text.

#### Headings

- Headings are block-level elements, and they come in six different rankings, `<h1>` through `<h6>`. Headings help to quickly break up content and establish hierarchy, and they are key identifiers for users reading a page. They also help search engines to index and determine the content on a page.

- Headings should be used in an order that is relevant to the content of a page. The primary heading of a page or section should be marked up with an `<h1>` element, and subsequent headings should use `<h2>`, `<h3>`, `<h4>`, `<h5>`, and `<h6>` elements as necessary.

- Each heading level should be used where it is semantically valued, and should not be used to make text bold or big—there are other, better ways to do that.

Here is an example of HTML for all the different heading levels and the resulting display on a web page.

```html
<h1>Heading Level 1</h1>
<h2>Heading Level 2</h2>
<h3>Heading Level 3</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>
```

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313195859409.png" alt="image-20230313195859409" style="zoom: 50%;" />

#### Paragraphs

- Headings are often followed by supporting paragraphs. 
- Paragraphs are defined using the `<p>` block-level element. Paragraphs can appear one after the other, adding information to a page as desired. Here is an example of how to set up paragraphs.

```html
<p>Steve Jobs was a co-founder and longtime chief executive officer at Apple. On June 12, 2005, Steve gave the commencement address at Stanford University.</p>

<p>In his address Steve urged graduates to follow their dreams and, despite any setbacks, to never give up&ndash;advice which he sincerely took to heart.</p>
```

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313200005228.png" alt="image-20230313200005228" style="zoom:50%;" />

#### Bold Text with Strong

- To make text bold and place a strong importance on it, we’ll use the `<strong>` inline-level element. There are two elements that will bold text for us: the `<strong>` and `<b>` elements. 
- It is important to understand the [semantic difference](http://html5doctor.com/i-b-em-strong-element/) between the two.
  - The `<strong>` element is semantically used to give **strong importance** to text, and is thus the most popular option for bolding text. 
  - The `<b>` element, on the other hand, semantically means to **stylistically offset** text, which isn’t always the best choice for text deserving prominent attention. 
- We have to gauge the significance of the text we wish to set as bold and to choose an element accordingly.

Here are the two HTML options for creating bold text in action

```html
<!-- Strong importance -->
<p><strong>Caution:</strong> Falling rocks.</p>

<!-- Stylistically offset -->
<p>This recipe calls for <b>bacon</b> and <b>baconnaise</b>.</p>
```

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313200043847.png" alt="image-20230313200043847" style="zoom:50%;" />

#### Italicize Text with Emphasis

- To italicize text, thereby placing emphasis on it, we’ll use the `<em>` inline-level element. As with the elements for bold text, there are two different elements that will italicize text, each with a slightly different semantic meaning.

  - The `<em>` element is used semantically to place a **stressed emphasis** on text; it is thus the most popular option for italicizing text. 

  - The other option, the `<i>` element, is used semantically to convey text in an *a**lternative voice or tone***, almost as if it were placed in quotation marks. 

- Again, we will need to gauge the significance of the text we want to italicize and choose an element accordingly.

Here’s the HTML code for italicizing:

```html
<!-- Stressed emphasis -->
<p>I <em>love</em> Chicago!</p>

<!-- Alternative voice or tone -->
<p>The name <i>Shay</i> means a gift.</p>
```

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313200126714.png" alt="image-20230313200126714" style="zoom:50%;" />

These text-level elements are quite handy for bringing our content to life. In addition to these, there are structurally based elements. 

## Building Structure

- Whereas text-based elements identify headings and paragraphs, structural elements identify groupings of content such as headers, articles, footers, and so forth. Let’s take a look.

- For the longest time the structure of a web page was built using divisions. The problem was that divisions provide no semantic value, and it was fairly difficult to determine the intention of these divisions. 

- Fortunately HTML5 introduced new [structurally based elements](http://dev.opera.com/articles/new-structural-elements-in-html5/), including the `<header>`, `<nav>`, `<article>`, `<section>`, `<aside>`, and `<footer>` elements.

  - All of these new elements are intended to give meaning to the organization of our pages and improve our structural semantics. 

  - They are all block-level elements and do not have any implied position or style. 

  - Additionally, all of these elements may be used multiple times per page, so long as each use reflects the proper semantic meaning.

Let’s roll up our sleeves and take a closer look.

<img src="https://learn.shayhowe.com/assets/images/courses/html-css/getting-to-know-html/building-structure.png" alt="Building Structure" style="zoom: 33%;" />

**Fig 2**

One possible example of HTML5 structural elements giving meaning to the organization of our pages

#### Header

- The `<header>` element, like it sounds, is used to identify the top of a page, article, section, or other segment of a page. In general, the `<header>` element may include a heading, introductory text, and even navigation.

```html
<header>...</header>
```

<u>`<header>` vs. `<head>` vs. `<h1>` through `<h6>` Elements</u>

- It is easy to confuse the `<header>` element with the `<head>` element or the **heading elements**, `<h1>` through `<h6>`. They all have different semantic meanings and should be used according to their meanings. For reference.

- The `<header>` element is a structural element that outlines the heading of a segment of a page. It falls within the `<body>` element.

- The `<head>` element is not displayed on a page and is used to outline metadata, including the document title, and links to external files. It falls directly within the `<html>` element.

- **Heading** elements, `<h1>` through `<h6>`, are used to designate multiple levels of text headings throughout a page.

#### Navigation

- The `<nav>` element identifies a section of *major* navigational links on a page. 
  - The `<nav>` element should be reserved for primary navigation sections only, such as global navigation, a table of contents, previous/next links, or other noteworthy groups of navigational links.
  - Most commonly, links included within the `<nav>` element will link to other pages within the same website or to parts of the same web page. 

- Miscellaneous one-off links should not be wrapped within the `<nav>` element; they should use the anchor element, `<a>`, and the anchor element alone.

```html
<nav>...</nav>
```

#### Article

- The `<article>` element is used to identify a section of independent, self-contained content that may be independently distributed or reused. 
  - We’ll often use the `<article>` element to mark up blog posts, newspaper articles, user-submitted content, and the like.

- When deciding whether to use the `<article>` element, we must determine if the content within the element could be replicated elsewhere without any confusion. 
  - If the content within the `<article>` element were removed from the context of the page and placed, for example, within an email or printed work, that content should still make sense.

```html
<article>...</article>  
```

#### Section

- The `<section>` element is used to identify a thematic grouping of content, which generally, but not always, includes a heading. The grouping of content within the `<section>` element may be generic in nature, but it’s useful to identify all of the content as related.

- The `<section>` element is commonly used to break up and provide hierarchy to a page.

```html
<section>...</section>
```

#### Deciding Between `<article>`, `<section>`, or `<div>` Elements

- At times it becomes fairly difficult to decide which element—`<article>`, `<section>`, or `<div>`—is the best element for the job based on its semantic meaning. The trick here, as with every semantic decision, is to look at the content.

- Both the `<article>` and `<section>` elements contribute to a document’s structure and help to outline a document. If the content is being grouped solely for styling purposes and doesn’t provide value to the outline of a document, use the `<div>` element.

- If the content adds to the document outline and it can be independently redistributed or syndicated, use the `<article>` element.

- If the content adds to the document outline and represents a thematic group of content, use the `<section>` element.

#### Aside

- The `<aside>` element holds content, such as sidebars, inserts, or brief explanations, that is tangentially related to the content surrounding it. 
  - When used within an `<article>` element, for example, the `<aside>` element may identify content related to the author of the article.
- We may instinctively think of an `<aside>` element as an element that appears off to the left or right side of a page. 

- We have to remember that all of the structural elements including `<aside>` are block-level elements so they will appear on a new line, occupying the full available width of their parent element(the element they are nested in), or the full width of the page. 

```html
<aside>...</aside>
```

- We’ll discuss how to change the position of an element, perhaps placing it to the right or left of a group of content, in Lesson 5, “[Positioning Content](https://learn.shayhowe.com/html-css/positioning-content/).”

#### Footer

- The `<footer>` element identifies the closing or end of a page, article, section, or other segment of a page. 
  - Generally the `<footer>` element is found at the bottom of its parent. 
  - Content within the `<footer>` element should be relative information and should not diverge from the document or section it is included within.

```html
<footer>...</footer>
```

With structural elements and text-based elements under our belts, our HTML knowledge is really starting to come together. Now is a good time to revisit our Styles Conference website and see if we can provide it with a little better structure.

#### Encoding Special Characters

- The `<h3>` element within our `<header>` element, as well as the `<small>` element within our `<footer>` element, has some interesting things going on. Specifically, a few special characters within these elements are being encoded.

- Special characters include various punctuation marks, accented letters, and symbols. When typed directly into HTML, they can be misunderstood or mistaken for the wrong character; thus they need to be encoded.

- Each encoded character will begin with an ampersand, `&`, and end with a semicolon, `;`. What falls between the ampersand and semicolon is a character’s unique encoding, be it a name or numeric encoding.

- For example, we would encode the word “resumé” as `resumé`. Within our header we have encoded both en and em dashes, and within our footer we have encoded the copyright symbol. For reference, a long list of character encodings may be found at [Copy Paste Character](http://copypastecharacter.com/).

## Creating Hyperlinks

Along with text, one of the core components of the Internet is the hyperlink

- Hyperlink provides the ability to link from one web page or resource to another.
- Hyperlinks are established using the **anchor**, `<a>`, inline-level element. 
- In order to create a link from one page (or resource) to another, the `href` attribute, known as a hyperlink reference, is required. The `href` attribute value identifies the destination of the link.

For example, clicking the text “Shay,” which is wrapped inside the anchor element with the `href` attribute value of `http://shayhowe.com`, will take users to my website.

```html
<a href="http://shayhowe.com">Shay</a>
```

#### Creating Hyperlinks Demo

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314144941968.png" alt="image-20230314144941968" style="zoom:33%;" />

#### Wrapping Block-Level Elements with Anchors

- By nature the anchor element, `<a>`, is an inline element, and, according to web standards, inline-level elements may not wrap block-level elements. 

- With the introduction of HTML5, however, anchor elements specifically have permission to wrap either block-, inline-, or any other level elements. This is a break from the standard convention, but it’s permissible in order to enable entire blocks of content on a page to become links.

#### Relative & Absolute Paths

- The two most common types of links are links to *other pages* of the same website and links to *other websites*. These links are identified by their `href` attribute values, also known as their paths.

Relative path

- Links pointing to other pages of the same website will have a **relative path**, which does not include the domain (.com, .org, .edu, etc.) in the `href` attribute value. Because the link is pointing to another page on the same website, the `href` attribute value needs to include only the filename of the page being linked to: `about.html`, for example.

- Should the page being linked to reside within a different directory, or folder, the `href` attribute value needs to reflect this as well. Say the `about.html` page resides within the `pages` directory; the relative path would then be `pages/about.html`.

Absolute Path

- Linking to other websites outside of the current one requires an *absolute path*, where the `href` attribute value must include the full domain. 
  - A link to Google would need the `href` attribute value of `http://google.com`, starting with http and including the domain, `.com` in this case.

- Here clicking on the text “About” will open the `about.html` page inside our browser. Clicking the text “Google,” on the other hand, will open `http://google.com/` within our browser.

```html
<!-- Relative Path -->
<a href="about.html">About</a>

<!-- Absolute Path -->
<a href="http://www.google.com/">Google</a>
```

#### Linking to an Email Address

Occasionally we may want to create a hyperlink to our email address—for example, hyperlink text that says “Email Me,” which when clicked opens a user’s default email client and pre-populates part of an email. 

- At a minimum the email address to which the email is being sent is populated; other information such as a subject line and body text may also be included.

- To create an [email link](https://developer.yoast.com/blog/guide-mailto-links/), the `href` attribute value needs to start with `mailto:` followed by the email address to which the email should be sent. To create an email link to `shay@awesome.com`, for example, the `href` attribute value would be `mailto:shay@awesome.com`.

- Additionally, subject, body text, and other information for the email may be populated. 

  - To add a subject line, we’ll include the `subject=` parameter after the email address. The first parameter following the email address must begin with a question mark, `?`, to bind it to the hyperlink path. Multiple words within a subject line require that spaces be encoded using `%20`.

  - Adding body text works in the same way as adding the subject, this time using the `body=` parameter in the `href` attribute value. Because we are binding one parameter to another we need to use the ampersand, `&`, to separate the two. As with the subject, spaces must be encoded using `%20`, and line breaks must be encoded using `%0A`.

- Altogether, a link to `shay@awesome.com` with the subject of “Reaching Out” and body text of “How are you” would require an `href` attribute value of `mailto:shay@awesome.com?subject=Reaching%20Out&body=How%20are%20you`.

Here’s the full breakdown:

```html
<a href="mailto:shay@awesome.com?subject=Reaching%20Out&body=How%20are%20you">Email Me</a>
```

#### Opening Links in a New Window

One feature available with hyperlinks is the ability to determine where a link opens when clicked. Typically, links open in the same window from which they are clicked; however, links may also be opened in new windows.

- To trigger the action of opening a link in a new window, use the `target` attribute with a value of `_blank`. The `target` attribute determines exactly where the link will be displayed, and the `_blank` value specifies a new window.

To open `http://shayhowe.com/` in a new window, the code would look like this:

```html
<a href="http://shayhowe.com/" target="_blank">Shay Howe</a>
```

#### Linking to Parts of the Same Page

Periodically we’ll see hyperlinks that link to part of the same page the link appears on. 

- A common example of these same-page links are “Back to top” links that return a user to the top of a page.

- We can create an on-page link by first setting an `id` attribute on the element we wish to link to, then using the value of that `id` attribute within an anchor element’s `href` attribute.

- Using the “Back to top” link as an example, we can place an `id` attribute value of top on the `<body>` element. Now we can create an anchor element with an `href` attribute value of `#top`, pound sign and all, to link to the beginning of the `<body>` element.

Our code for this same-page link would look like the following:

```html
<body id="top">
  ...
  <a href="#top">Back to top</a>
  ...
</body>
```

Hyperlinks are incredibly useful and have revolutionized how we use the Internet. So far we’ve covered how to link to other pages or websites, as well as how to create email links and links to parts of the same page. Before we go any further, let’s create some links of our own.

## Summary

Semantics, as discussed within this lesson, are essential for providing our HTML with structure and meaning. Moving forward we’ll periodically introduce new elements, all of which will come with their own semantic meaning. It is the meaning of all of these elements that will provide our content with the most value.

Once again, in this lesson we covered the following:

- What semantics are and why they are important
- `<div>`s and `<spans>`s, and the difference between block- and inline-level elements
- Which text-based elements best represent the content of a page
- The HTML5 structural elements and how to define the structure and organization of our content and page
- How to use hyperlinks to navigate between web pages or websites

Hopefully you’re starting to feel pretty good about HTML. There is still quite a bit to learn, but the foundation is in place. Next up, we’ll take a deeper look into CSS.

# Tutorial 3: Getting to Know CSS

