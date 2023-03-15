# Lesson 1

# Welcome

Welcome to the first Front-end course at Launch School! This course introduces you to the basics of HTML and CSS. Along the way, we'll explore the tools and technologies you will use throughout the front-end section of the curriculum.

## A Few Words About Mastery and This Course

When you visit a website, you see the result of HTML and CSS coding. Without HTML or something like it, the Web wouldn't exist; there would be no way to display content. Without CSS, pages would be dull, lifeless, and primitive. If you were on the Internet in the 1990s, you probably remember how crude websites looked. They weren't pretty, and often they did not work across different browsers. Before CSS and the browser advances we enjoy today, HTML development was the Wild West, with no rules to guide developers. Different browsers - sometimes even different versions of a browser - displayed elements in different ways, and there was no way to normalize the appearance or tailor the presentation to your needs. To some extent, these differences continue today, but, thanks to standardization and CSS, most are subtle and easy to work around.

Most front-end jobs expect that you know HTML and CSS well. However, it's not essential for most engineering jobs. Unlike every other topic we cover at Launch School, employers seldom quiz engineering applicants on HTML and CSS. They will quiz you on almost everything else, but not HTML and CSS.

In light of this, we don't expect the same degree of mastery in this course that we look for elsewhere. In fact, there is no assessment.

That said, we still recommend trying to master the material as much as possible, but don't get bogged down trying to do so. There's a lot of content, but familiarity will almost always be enough to help you find the information you need.

## Where to Find More Information

Engineers sometimes need to do front-end work, but you don't always need to be an HTML and CSS expert. In fact, you can do almost everything with a small portion of the features available. We'll take advantage of that in this course, and focus on the most used parts of HTML and CSS.

We're going to leave material out. The best time to learn more about HTML and CSS is when you find that you need a feature you've never used. We intend to make use of this, and we'll expect you to learn details on your own, sometimes without telling you. Don't panic, but be ready to find information.

[Google](https://google.com/) (or whatever search engine you prefer) is your leading resource when you have a problem or question. Often, all you have to do is ask a question, and one of the top results will provide an answer. For example, try "How do I create superscripts in HTML?" It's also helpful to provide `mdn` or `w3c` in your search to access two of the most useful resources:

- The [Mozilla Developer Network](https://developer.mozilla.org/), or **MDN**, is perhaps the best resource for extensive and accessible information about the Web, specifically HTML, CSS, and JavaScript. In fact, it's so good that we suggest that you get in the habit of adding **mdn** to your searches. For instance, `mdn form tag` will find the MDN documentation on the `<form>` tag. If MDN fails to help, a more global search will often turn up a video, tutorial, or Stack Overflow question that provides all the information you need.

  MDN is free and continually updated. Mozilla, the makers of the Firefox Web browser, maintains the site. MDN isn't official, but it's up-to-date, generally accurate, and easier to use than the official specification documents at W3C.

- The [W3C](http://www.w3.org/), the World Wide Web Consortium, is the standards body for Web technologies, so it serves as the official source of information for HTML and CSS. The content is often dry and academic, but it's an essential resource that you shouldn't ignore. You can add the word **w3c** to your searches to find W3C information about specific topics, e.g., `w3c textarea tag`.

- In mid-2019, W3C announced that it would collaborate with the Web Hypertext Application Technology Working Group, [WHATWG](https://whatwg.org/), on future HTML and DOM standards, effectively giving up control over those standards. The effects of this collaboration are still unclear at this time. However, it may lead to more rapid development of HTML and DOM standards. The most recent standards documents for the HTML and browser DOM standards can be located at the WHATWG site:

  - [HTML Standard](https://html.spec.whatwg.org/multipage/)
  - [DOM Standard](https://dom.spec.whatwg.org/)

If you omit "mdn" or "w3c" from the search query, the first result is often from a website called W3 Schools. Material from this site is frequently outdated and incorrect. We suggest that you steer clear of those results.

Don't confuse W3 Schools with W3C; W3C has no affiliation with W3 Schools.

# Introduction

In this lesson, we'll take a brief, fast-paced tour of both HTML and CSS. You'll learn about the most used HTML tags, as well as how to apply some of the simplest and oft-used CSS properties. Along the way, you'll learn how to write coherent HTML and CSS, and then build two simple web pages, one which you will do on your own (but with a bit of help).

Please follow along with the text, videos, and external reading. When you see code examples in the assignments, you should write that code in files on your development system and display them in your browser so you can see it in operation. Don't copy and paste the code; write it out line-by-line. Yes, typing is tedious, but it helps train your "muscle memory" and helps solidify the concepts in your mind. It also provides experience using the syntax that you'll use when writing HTML and CSS.

Some project videos in this course differ from the assignments and completed projects. It's not always possible to update videos when we become aware of differences or make changes, so the videos become outdated with time. Where there are discrepancies, the written material, design files, and completed projects take precedence over the videos.

This lesson has more projects and practice problems than most to give you plenty of practice as you start out. Most remaining lessons have fewer practice opportunities until we get near the end of the course.

## What to Focus On

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

# Install Software

We'll get the ball rolling on this course with a brief introduction to some of the software you may want or need to install before you proceed.

## Browser

If you haven't already done so, you should install [Google Chrome](https://www.google.com/chrome/browser/desktop/index.html) on your system. You don't have to use Google Chrome as you work through this course, but most assignments assume that you are using it.

## HTML and CSS Validators

Always check your HTML with [W3C's HTML Validator](https://validator.w3.org/#validate_by_input). The validator ensures that your HTML is valid and helps catch potential issues before they become mystifying bugs. You can tell W3C to link directly to a page if you have it online, upload the HTML file from your local filesystem, or copy and paste the HTML to the direct input tab. Most students find that copy and paste is a good solution for this course.

Validate your HTML often:

- after the first draft of your HTML
- after any significant changes to your HTML
- when you're having problems with the way your page renders
- before submitting your HTML for a code review
- before deploying your HTML

[W3C's CSS Validator](https://jigsaw.w3.org/css-validator/#validate_by_input) provides similar functionality for validating CSS. Check your CSS when you validate your HTML, and also when you make significant changes to your CSS.

Don't underestimate the value of validation. It may seem like a pain at times, but validation **will** save you much grief. Small errors in your HTML and CSS can cause confusing and subtle bugs; the validators help you find and fix problems before they become bugs.

## Linters

**Linters** check computer code for errors, misuse, and style issues. Unlike the W3C validators, linters look at style and usage rather than conformance to standards. The validators find uses of deprecated elements, poor element nesting, and non-standard attributes and properties; linters detect poor indentation and formatting as well as failures to follow best practices.

You can find linters for most development languages, and HTML is no exception. Here are some you can install in the Sublime Text editor; similar tools exist for most code editors, and you can run most linters from the command line if your editor doesn't support them directly.

- [SublimeLinter-contrib-htmlhint Package for Sublime Text](https://packagecontrol.io/packages/SublimeLinter-contrib-htmlhint)
- [SublimeLinter-html-tidy Package for Sublime Text](https://packagecontrol.io/packages/SublimeLinter-html-tidy)

CSS also has linters, though good ones are a bit difficult to find. Unfortunately, we are no longer able to find one we like. If you find one you like, suggest it via the Feedback button!

## ESLINT (my notes)

Download node.js and npm on WSL

Download eslint

Download plugin extension for html

Create a `.eslintrc` file and put code in it.

# Getting Started

In this assignment, you'll read the first part of a tutorial that introduces you to the vocabulary and fundamental concepts you need when working with HTML and CSS. The tutorial shows you how to build simple HTML pages and style them with CSS.

## Before You Start

The primary takeaways from the first three sections of the tutorial include:

- The vocabulary
- The syntax of HTML and CSS
- The HTML elements discussed
- The CSS selectors and properties covered
- The `class` and `id` attributes, and the corresponding class and ID selectors (`.class-name`, `#id-name`).

Of lesser importance, but still important enough to study, pay attention to the following:

- How to write comments in HTML and CSS
- The difference between `<header>`, `<head>`, and `<h1>` through `<h6>`
- Relative & absolute paths
- The CSS cascade and specificity

While you read the tutorial, you may want to browse the associated MDN documentation for each HTML tag or CSS property you encounter. To find the documentation for the `<a>` tag, for instance, search Google for `mdn html a`; to locate the documentation for the `color` property, search for `mdn css color`. Get in the habit of reading MDN as you learn each new element or property, but don't worry if you don't understand everything in each section.

We will revisit most of the topics discussed in the tutorial later, so don't waste time trying to memorize everything. It's more important to know what's available, and how to look up information when you need it.

## Read the Tutorial

Learn to Code: HTML & CSS by Shay Howe is an extensive free tutorial that introduces most HTML and CSS concepts. To begin this lesson, please read the **first three sections** of the tutorial:

- [Building Your First Web Page](https://learn.shayhowe.com/html-css/building-your-first-web-page/) introduces the vocabulary of HTML and CSS and demonstrates a few of the most common tags and rules.

- [Getting to Know HTML](https://learn.shayhowe.com/html-css/getting-to-know-html/) discusses some basic HTML concepts, notably semantics, headings, paragraphs, simple HTML-based styling, and the general structure of an HTML document. It also examines hyperlinks and URLs.

- [Getting to Know CSS](https://learn.shayhowe.com/html-css/getting-to-know-css/) brings CSS into the mix, introducing the cascade, specificity, selectors, and an assortment of properties.

Be sure to try the CODEPEN demos while you read through the tutorial. You can modify the demo code to see what various changes accomplish; that will help you understand those features. Don't be afraid of breaking anything.

If you're unfamiliar with HTML and CSS, we recommend working through the "In Practice" sections. You may skip them if you're already comfortable with both languages, but please look them over to ensure you don't miss anything.

## Afterthoughts

It's common to see **element** and **tag** used interchangeably; there is a difference, though:

- An HTML tag begins with

   

  ```
  <
  ```

   

  and ends with

   

  ```
  >
  ```

   

  and contains an element name inside the angle brackets. There are three types of tags:

  - An opening tag (`<p>`)
  - A closing tag (`</p>`) -- defined for most, but not all, elements
  - A self-closing tag (`<br>` or, incorrectly, `<br />`) -- most tags are not self-closing

- An HTML element includes either:

  - A self-closing tag
  - An opening tag and its corresponding closing tag, including everything between the two. The content may contain nested elements.

We may refer to tags and elements with or without angle brackets, so long as the usage is unambiguous. For instance, we may talk of the `<p>` tag as the `p` tag, but we may also say `p` element instead of `<p>...</p>` element. We may sometimes abbreviate that even further and say `p` without saying whether we are talking about a tag or element. This writing style is merely a convenience, though: you must use the angle brackets when coding HTML.

We expect you to use the correct term, but keep in mind that you may encounter less precise material. We'll even slip from time to time ourselves -- let us know via Feedback if you spot a misuse.

One more item to consider is attributes. For instance:

```html
<a href="another_page.html">Next page</a>
```

In this code, `href` is an attribute of the `<a>` tag, and it has the value `another_page.html`. You may use either double quotes, as shown above, or single quotes:

```html
<a href='another_page.html'>Next page</a>
```

You may even omit the quotes in some cases, which is handy in machine-generated HTML, but most style guides don't recommend this. You should use double quotes when possible.

Later, we'll introduce boolean attributes; they don't need an `=` or a value.

Every HTML element may contain one or more attributes or none at all. Some, such as `class`, which we'll talk about soon, are global; you can use them anywhere. However, most are specific to individual tags.

Note that browsers do not check whether your attributes are valid: they ignore them, which can make debugging difficult.

## The Rest of the Tutorial

We won't cover the rest of this tutorial since it doesn't quite fit into the structure of this course. It gets into some topics in far more depth than you need to know right now. If you want to learn more, you should complete the tutorial after you've completed the course. Later still, you can check out the [Advanced HTML and CSS Tutorial](https://learn.shayhowe.com/advanced-html-css/).

# Creating an HTML Skeleton

Building a new web page often begins with creating an HTML file that contains some minimal HTML. Most developers like to create the skeleton of an HTML file and put it someplace where they can readily use it to create new HTML files without having to write a bunch of boilerplate. We'll call this file your **HTML skeleton** or the **HTML scaffold**.

## Creating the HTML Skeleton

Here's a typical HTML skeleton, based on the simple document you worked on in the Shay Howe tutorial.

skeleton.html

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>your page title goes here</title>
    <meta charset="utf-8">
  </head>
  <body>
  </body>
</html>
```

As time goes on, you'll want to expand this skeleton a bit and add some more boilerplate, such as the location of your CSS styles, some keywords, and other entities that you want to add to nearly every new web page. For now, let's start as shown above. You can do one of the following:

- Create a file named `skeleton.html` with the above content on your local computer.
- Define a "snippet" in your editor that you can insert into your code when needed. See the editor's documentation for more information.
- Create a personal Gist that contains the skeleton and copy and paste it from there.

We saw a similar file in the Shay Howe tutorial. This file isn't identical, but the differences are minor. Let's break it down:

- `<!DOCTYPE html>`: this is a **Document Type Definition**, aka, **DTD** or **DOCTYPE**. Officially, the DOCTYPE isn't part of HTML; it isn't a tag or element, even though it looks like one. In fact, it's merely a message that tells the browser what specific markup language to expect -- for example, XML. This particular version of the DOCTYPE specifies that the document uses HTML5; it's the one you'll use most often unless you're writing for older browsers or an XML or XHTML application.

  The DOCTYPE *must* be the first item in an HTML document; not even whitespace can precede it.

  > Some developers use lowercase instead (`<!doctype ...>`); you must use uppercase when defining versions of HTML before HTML5 or non-HTML languages such as XML. HTML5 doesn't care whether you use uppercase or lowercase, so some developers are moving to the lowercase form. You may use either style at Launch School.

  > Technically, HTML5 does not have something called the DTD, though HTML3 and HTML4 do. The HTML5 standards documentation refers to the document type items as a DOCTYPE. Few people will argue with you if you call it a DTD though.

- The `html` element encloses the entire HTML document. The `lang="en"` attribute informs the user's browser that the web page uses the English language for text. Everything else about the page, both its content and related meta-information, must be between the opening and closing `html` tags.

- The `head` element encloses the document header, which consists of elements that provide additional information (sometimes called meta-information) to the browser; the browser ordinarily does not display meta-information in the page content area. Here, the `title` gives the page a title, while `<meta charset="utf-8">` tells the browser to expect the UTF-8 character encoding (most web pages use this encoding). Most browsers display the title in the title bar or tab, so be sure you always provide a `title` element for a web page.

  > The `<meta>` tag uses a self-closing tag: it doesn't have a closing tag, e.g., `</meta>`. Instead, the tag ends with `/>` instead of a lone closing `>` symbol. You may also see the terms "self-closing element", "self-contained element", "empty element", or "void element" to describe self-closing tags.

  > **NOTE**: The use of `/>` at the end of a self-closing tag is now seen as incorrect HTML, and using the W3C HTML validator on code that contains self-closing tags may result in warnings. Thus, instead of `<meta />`, you should now just use `<meta>`. As a result, we have removed the `/>` from most code in this course. However, you may still encounter it, both in downloadable code, and in code on non-Launch School sites.

- The `body` element is the content area of the page. The browser renders the HTML inside the `body` in the browser content area. In this case, we have no content, so this page renders as a blank page. Try viewing the file in your browser.

  Most editors have a shortcut to display a file in a browser, and most browsers provide a File, Open File menu item that does the same.

Technically, HTML pages require all four of the above items. In practice, you can omit any or all of them from your HTML, and most browsers will do the right thing. You should not rely on this behavior, though, since omitting them may lead to problems in some browsers. However, you'll often see them left out in training materials where brevity wins out over correctness.

### Indentation

Note that we add two spaces of indentation after each open tag, then remove two when closing it. Developers often use this style when writing HTML from scratch - the indentation helps show the structure of your document and makes it easier to read and edit. Self-closing tags (like `<meta>`) do not alter the indentation. It's also common to omit the indentation for the `head` and `body` elements; align them both with the `html` element if you prefer:

skeleton.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <title>your page title goes here</title>
  <meta charset="utf-8">
</head>
<body>
</body>
</html>
```

We'll talk a bit more about HTML style later in this lesson.

# Classes, IDs, and Names

HTML provides three ways to identify certain elements: classes, ids, and names. Any element can use a `class` or `id` attribute, and a variety of elements can use the `name` attribute. Some elements can use all three at once:

Copy Code

```html
<input type="submit" name="save" id="save-button" class="default-button">
```

We review each attribute below. Don't concern yourself with the elements we use: you can look up unfamiliar elements if you want, but you don't need to know what they do or how to use them at this point. Our focus here is on these three attributes.

## Classes

The `class` attribute identifies a set of page elements that you wish to style consistently. For instance, if you want to display a list of students, but highlight students who serve as Teaching Assistants, you can apply a class of `teaching-assistant` to each TA's data:

Copy Code

```html
<table>
  <tbody>
    <tr class="teaching-assistant">
      <td>Elizabeth</td>
      <td>JS230</td>
    </tr>

    <tr>
      <td>Nancy</td>
      <td>RB101</td>
    </tr>

    <tr>
      <td>Joe</td>
      <td>RB120</td>
    </tr>

    <tr class="teaching-assistant">
      <td>Pete</td>
      <td>JS225</td>
    </tr>

    <tr>
      <td>Kim</td>
      <td>LS202</td>
    </tr>
  </tbody>
</table>
```

Copy Code

```css
tr {
  background-color: lime;
  font-size: 200%;
}

.teaching-assistant {
  background-color: yellow;
}
```



![Classes example](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/class-01.png)



Here you can see that each row has a background color: `lime` for most rows, and `yellow` for the TAs.

- Use the `class` attribute to assign a class or classes to an element.
- Any number of elements may belong to the same class.
- Any element can belong to one or more classes. List all the names separated by spaces in the `class` attribute, e.g., `class="executive management full-time"`.
- Prefer semantic class names; they should provide meaning. For instance, use `teaching-assistant` rather than `yellow-background`.
- Use CSS class selectors (`.classname`) to select elements by class, e.g., `.teaching-assistant`.
- Class selectors have lower CSS specificity than ID selectors (an ID selector overrides a class selector), but higher than tag name selectors (a class selector overrides a tag selector). Thus, the `.teaching-assistant` selector overrides the `tr` selector. See [Getting to Know CSS](https://learn.shayhowe.com/html-css/getting-to-know-css/#cascade).

## IDs

The `id` attribute applies a unique identification string to a single element, such as a headline; no other `id` attributes on the page should have the same ID.

Copy Code

```html
<h1>This is a plain h1 heading</h1>
<h1 id="headline">This is my headline</h1>
```

You can now give the headline some styling that is unique to it:

Copy Code

```css
#headline {
  color: red;
  font-size: 48px;
}
```



![Headline Example](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/headline-01.png)



- Use the `id` attribute to assign an ID to an element.
- Each ID on a page must be unique.
- Each element can have one ID or none.
- Use semantic ID names; they should provide meaning. For instance, use an ID name of `headline` rather than `big-font`.
- Use CSS ID selectors (`#idname`) to select elements by ID, e.g., `#headline`.
- ID selectors have higher CSS specificity than class selectors (an ID selector can override a class selector).

The browser won't tell you when you use the same ID on more than one element. In fact, it may even apply your styles to several tags with the same ID. You will run into problems with JavaScript, though, if you try to take advantage of this behavior. Use the W3C HTML validator to catch accidental ID duplication.

## Names

We won't use the `name` attribute until much later in this course. For now, all you must know about the `name` attribute is that it ties form elements to data on the server - it typically doesn't play a role in styling. You can use the `[name="field-name"]` selector to select elements by name, but you should use a class or ID selector instead. When you submit a form, the browser sends the form data to the server using name/value pairs in which each name comes from the associated `name` attribute. For instance:

```html
<form method="get" action="#">
  <label for="first-name-field">First name:</label>
  <input type="text" name="first-name" id="first-name-field">

  <label for="last-name-field">Last name:</label>
  <input type="text" name="last-name" id="last-name-field">

  <input type="submit" value="Search">
</form>
```

When you submit this form, the browser constructs a query string that looks like this:

```plaintext
first-name=Joe&last-name=Jones
```

Note that the browser does not send the `id` attribute value to the server.

Since the `for` attribute references an ID (as we'll see later), it's accepted practice to use both a `name` and an `id` on form elements and to use the same value for both:

```html
<form method="get" action="#">
  <label for="first-name">First name:</label>
  <input type="text" name="first-name" id="first-name">

  <label for="last-name">Last name:</label>
  <input type="text" name="last-name" id="last-name">

  <input type="submit" value="Search">
</form>
```

- Use the `name` attribute to assign a name to a form data element that the server can use to obtain the value.
- Not all tags accept the `name` attribute; it applies to input controls in forms. Some other elements have a `name` attribute, too, but with a different meaning.
- Always use a `name` attribute on form elements that accept it.
- Each name in a form should be unique to that form except for radio buttons and checkboxes that belong to a single group.
- Use descriptive `name` values, not semantic. For instance, use `name="last-name"` instead of `name="input-field"`.
- Avoid trying to select elements in CSS by using the `name` attribute.

# Practice Problems: Semantics

This set of practice problems covers the basics of semantic HTML: using HTML to show the structure and purposes of the document, not its presentation.

While working on these problems and dealing with semantics in HTML, you may want to open this [excellent flowchart](http://html5doctor.com/downloads/h5d-sectioning-flowchart.pdf) to help decide what tags should be used in which situations. We recommend keeping this flowchart handy.

1. Which of these tags are semantic, and which are not?

   |             |            |            |             |
   | :---------: | :--------: | :--------: | :---------: |
   | `<article>` | `<aside>`  |   `<b>`    |   `<div>`   |
   | `<footer>`  |   `<h3>`   | `<header>` | `<section>` |
   |  `<span>`   | `<strong>` |            |             |

   Solution

   **Semantic**: `<article>`, `<aside>`, `<b>`, `<footer>`, `<h3>`, `<header>`, `<section>`, `<strong>`

   **Non-Semantic**: `<div>`, `<span>`

   In HTML5, all content tags except `<div>` and `<span>` have semantic meaning. In particular, both `<b>` and `<i>` have [semantic meaning](http://html5doctor.com/i-b-em-strong-element/). Some developers may tell you otherwise, but that's a holdover from HTML4, in which both elements are non-semantic. Note, though, that the semantic meanings of `<b>` and `<i>` in HTML5 are somewhat subtle. Avoid using them solely for stylistic purposes, and be sure you understand when they are appropriate.

2. Given the following HTML, would `<section>`, `<aside>`, `<article>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

   Copy Code

   ```html
   <sometag>
     <h1>Lincoln's Gettysburg Address</h1>
     <p>
       Four score and seven years ago our fathers brought forth on this
       continent, a new nation, conceived in Liberty, and dedicated to the
       proposition that all men are created equal.
     </p>
     <p>
       Now we are engaged in a great civil war, testing whether that nation,
       or any nation so conceived and so dedicated, can long endure. We are
       met on a great battle-field of that war. We have come to dedicate a
       portion of that field, as a final resting place for those who here gave
       their lives that that nation might live. It is altogether fitting and
       proper that we should do this.
     </p>
     <p>
       But, in a larger sense, we can not dedicate—we can not consecrate—we
       can not hallow—this ground. The brave men, living and dead, who
       struggled here, have consecrated it, far above our poor power to add or
       detract. The world will little note, nor long remember what we say
       here, but it can never forget what they did here. It is for us the
       living, rather, to be dedicated here to the unfinished work which they
       who fought here have thus far so nobly advanced. It is rather for us
       to be here dedicated to the great task remaining before us—that from
       these honored dead we take increased devotion to that cause for which
       they gave the last full measure of devotion—that we here highly
       resolve that these dead shall not have died in vain—that this nation,
       under God, shall have a new birth of freedom—and that government of
       the people, by the people, for the people, shall not perish from the
       earth.
     </p>
   </sometag>
   ```

   Solution

   Based on what we see here, an `<article>` may be the best choice since Abraham Lincoln's Gettysburg Address would make sense if we extracted it from the page and put it elsewhere. That is, it's self-contained and reusable.

   However, semantics depend on context and intent, so whether we treat the Gettysburg address as an `<article>` or `<section>` or `<aside>` may vary from one page to another.

3. Given the HTML from question 2, would it be appropriate to replace `<sometag>` with `<address>` or `<blockquote>`? If so, which one?

   Solution

   Extended quotations like this should use `<blockquote>`. This quotation is also a standalone item, though, so `<article>` is also appropriate. The best solution may be to replace `sometag` with `blockquote`, then wrap the entire `<blockquote>` in an `<article>`:

   Copy Code

   ```html
   <article>
     <blockquote>
       <h1>Lincoln's Gettysburg Address</h1>
       <p>Four score and seven years ago ...</p>
       <p>Now we are engaged in a great civil war...</p>
       <p>But, in a larger sense, we can not dedicate...</p>
     </blockquote>
   </article>
   ```

   `<address>`, of course, is inappropriate; it identifies contact information, not speeches.

4. Given the following HTML, would `<section>`, `<aside>`, `<article>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

   Copy Code

   ```html
   <sometag>
     <h3>Text-align Property</h3>
     <p>
       Given the width of the paragraph, the heading looks odd hanging out on
       the left side of the screen. Let's center it instead; we'll do this
       with the text-align property:
     <p>
   
     <pre>
       <h1 style="color: orange; text-align: center;">Hello, Internet!</h1>
     </pre>
   </sometag>
   ```

   Solution

   This time, a `<section>` tag may be the best choice. The text appears to be part of a larger body of work, but it isn't a standalone block like an `article`. It's also not an `aside` since it appears to be part of the main document flow.

   As with question 2, semantics depend on content and intent. Thus, it may be possible to argue for a different answer to this question.

5. Given the following HTML, would `<aside>`, `<section>`, `<blockquote>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

   Copy Code

   ```html
   <h3>Hex Colors</h3>
   
   <p>
     Most graphics and design applications like Photoshop and Pixelmator
     display colors in hexadecimal format, so it's easy to copy and paste
     color values you need from one program into your editor as a CSS
     property.
   </p>
   
   <sometag>
     <p>
       If you're unfamiliar with the hexadecimal numbering system, it uses 16
       different digits instead of the ten the decimal system uses. The hex
       digits are 0 through 9, as in the decimal system, but also include a
       through f (or A through F) as valid digits.
     </p>
   </sometag>
   ```

   Solution

   The text in the `<sometag>` element feels like a comment added as an aside, rather than part of the main text, so an `<aside>` tag would be the most appropriate.

   Once again, consider the context and intent when trying to choose a semantic tag.

> If you're feeling a little fuzzy about these answers, that's okay. It's normal, in fact. It isn't always easy to pick the right semantic tag, and there can be more than one correct answer as we saw in several questions. Sometimes, you may even need to nest them, as in item 3. Avoid the non-semantic tags and try not to misuse the semantic ones and you should be okay.

# Walkthrough Project: A Simple Web Page

In this walkthrough project, we'll learn the basic mechanics of constructing a new web page using HTML alone. The final result will look like this:



![Hello Internet!](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/a_simple_web_page_01.png)



Feel free to try this project on your own if you know HTML well already. Take some time to read through the entire assignment afterward, though; you don't want to miss any fundamental concepts. Note that "HTML" and "CSS" in the first paragraph use boldfacing to identify them as important words, while "Launch School" is a hyperlink. The word "terrific" uses italics for emphasis.

## Adding a Title

We'll begin this project by creating a new file named `hello.html`, and populate it with the content of the HTML skeleton you created in the previous assignment.

All web content goes inside the `body` element, but most web pages need at least one update to the `head` element: every page should have a title. Replace the dummy title from your skeleton file with an appropriate title, such as `Welcome!`:

hello.html

Copy Code

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Welcome!</title>
    <meta charset="utf-8">
  </head>
  <body>
  </body>
</html>
```

Your browser should display this HTML as a blank page, but you should see the title "Welcome!" in your title bar or page tab. Most browsers cut off long titles, so try to keep them short.

## Adding Content

Next, let's put some content on the page. As mentioned earlier, all content must be inside the `body` element, so lets put it there:

hello.html

Copy Code

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Welcome!</title>
    <meta charset="utf-8">
  </head>
  <body>
    Hello, Internet!
  </body>
</html>
```

Reload the page in your browser; this time, the browser should **render** (display) the content in a finished web page. With this code, you should see the text "Hello, Internet!" appear at the top left of the page. The browser does not display any of the tags; it interprets them as instructions for rendering the page, not information that it should show the user.

## Add Paragraph-Based Content

Let's see if we can modify our page. Right now, we have a single welcome sentence, but nothing else. Let's provide some additional content:

hello.html

Copy Code

```html
<body>
  Hello, Internet!

  Welcome to my website! It's a work in progress as I learn HTML and CSS from a
  terrific class I'm taking at Launch School. I'm learning a lot! Why don't you
  join me?

  There's not a lot of material on this page as I'm playing around with HTML &
  CSS. When I'm done, these last two paragraphs will take on a lighter color
  than the first - the "class" attribute on the two <p> tags and a bit of CSS
  will help accomplish that.

  This is the final paragraph. It also uses the `class` attribute as well as an
  `id` attribute. We'll use some CSS and the `id` attribute to underline the
  entire paragraph.
</body>
```

Take a look at the result in your browser now.



![Mashed Paragraphs](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/paragraphs-01.png)



For some reason, the paragraphs run together with but one visible break, not separated as we intended. What happened to those empty lines? The browser swallowed them; by default, the browser compresses all whitespace down to a single space character, so we lose all those paragraph breaks.

Wait, though: there is a line break between the words `two` and `tags`. How come? It looks like we meant to write `<p>` instead, but the `<p>` is missing. The problem is that `<p>` is an HTML tag for a paragraph, so the browser tried to interpret it as such, and started a new paragraph. It doesn't display the tag, of course: it uses them to structure the content, but it doesn't include them as part of it.

As you can see, web browsers don't handle pre-formatted text well. It is possible to pre-format text using the `<pre>` tag, but, in general, it's a poor choice. Since you have no idea how wide or narrow a user's window will be when she reads your page, it's impossible to pre-format the text in a readable way on all windows.

Let's fix the paragraph problem. The `p` element provides the ability to define paragraphs; it wraps a single paragraph and displays it in a separate area below the previous content, along with a bit of vertical spacing above and below it for visual distinctiveness:

hello.html

Copy Code

```html
<body>
  <p>Hello, Internet!</p>

  <p>
    Welcome to my website! It's a work in progress as I learn HTML and CSS from
    a terrific class I'm taking at Launch School. I'm learning a lot! Why don't
    you join me?
  </p>

  <p class="more-text">
    There's not a lot of material on this page as I'm playing around with HTML &
    CSS. When I'm done, these last two paragraphs will take on a lighter color
    than the first - the "class" attribute on the two <p> tags and a bit of CSS
    will help accomplish that.
  </p>

  <p class="more-text" id="final-paragraph">
    This is the final paragraph. It also uses the `class` attribute as well as
    an `id` attribute. We'll use some CSS and the `id` attribute to underline
    the entire paragraph.
  </p>
</body>
```

We'll discuss the `class` and `id` attributes in the next assignment. For now, they won't alter what you see in your browser.

When you reload the page this time, it will look pretty close to what we want. However, that `<p>` embedded in the second paragraph is still a problem. The browser interpreted it as HTML and started a new paragraph. To fix this problem, we need to replace the `<` and `>` characters in `<p>` with special HTML **character entities**:

Copy Code

```html
the "class" attribute on the two &lt;p&gt; tags
```

The browser will replace `<` and `>` with literal `<` and `>` characters. Entities exist for thousands of special characters, but most developers need a dozen or so and can look them up as needed. In particular, you must use them when you need to include literal `<` and `>` characters in a page.

When you reload the page now, it should display the way you intended, with blank lines between each paragraph.



![Sliced Paragraphs](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/paragraphs-02.png)



Though this page looks good, there is one more character that you should replace with an entity: the ampersand (`&`)). HTML5 handles ampersands as regular characters in most cases, but if that `&` includes some non-whitespace characters between it and the next semicolon (`;`), the browser may try to interpret it as an entity. For safety, most developers replace `&` with `&` even when they don't need to do so:

hello.html

Copy Code

```html
<p class="more-text">
  There's not a lot of material on this page as I'm playing
  around with HTML &amp; CSS. When I'm done, these last two
  paragraphs will take on a lighter color than the first - the "class" attribute
  on the two &lt;p&gt; tags and a bit of CSS will help accomplish that.
</p>
```

You may need entities for several other special characters. For instance, you must use `"` if you need to embed a double quote inside a double-quoted attribute value.

Copy Code

```html
<img src="hello-world.jpg" alt="Greetings: &quot;Hello, World&quot;">
```

It's also common practice to replace `"` with `"` when using an external source of strings inside your HTML; since you can't know in advance which strings will need `"` and which won't, you use `"` everywhere.

All entities follow the pattern of an ampersand (`&`) followed by one or more alphanumeric characters terminated by a semicolon (`;`). All have numeric versions, and most have alphanumeric names, e.g., `&` also represents an ampersand (`&`); you should use the alphanumeric name when you can, though.

Your browser won't complain if you leave a bare `<`, `>`, or `&` in your HTML. Neither will the W3C validator, which we'll discuss below. You won't know that you forgot to use an entity until it causes a problem on your page.

## Add a Heading

We're going to treat the first sentence as our page heading - this is an arbitrary decision since it isn't obviously a heading, but most web pages should have a heading. We will choose this sentence to be that heading.

In most cases, the page heading should use the `<h1>` tag:

hello.html

Copy Code

```html
<body>
  <h1>Hello, Internet!</h1>

  <p>
    Welcome to my website! It's a work in progress as I learn...
  </p>

  <!-- rest of HTML -->
</body>
```

Reload the page to see the result. You should see that the heading text increased in size and may also appear bolder.



![Baked Paragraphs](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/paragraphs-03.png)



Why does the `h1` tag end with a `1`? With HTML, you can think of pages as textbook chapters. Each chapter has a title, the main heading, along with subheadings for each section. Each section, in turn, may also have a titled subsection. Often, the publisher uses a different size typeface, or *font*, for each heading level; chapter titles often use large fonts, while subheadings use progressively smaller sizes based on depth. Each heading has some vertical spacing above and below to separate it from the surrounding content.

With HTML, you can have up to six levels of headings. The `h1` element provides the top-level heading; the first subheading level uses the `h2` element, the next level uses `h3`, and the last uses `h6`. Three levels are enough in most cases, but if you work with complex legal or academic documents, you may need all six levels.

Don't use `h1`, `h2`, etc. solely because you want to change font sizes. The numbered heading elements have semantic meaning; using them for their font sizes makes it harder for search engines and assistive technologies to understand your code and present it in a useful format. Misusing HTML for its stylistic effects also makes it hard for other developers to understand your code.

## Formatting Some Text

By now, you're probably wondering what other HTML elements you can use to format text. We'll take a brief glance at some in this section, but there are plenty. Most change how the content looks, and most also change the semantic meaning. Here are some useful formatting elements that you can use inside "container" elements like the paragraph and heading elements. (We'll discuss containers in more detail later.)

| Element | Description                                                  |
| :------ | :----------------------------------------------------------- |
| strong  | The text has greater importance than the surrounding text; most browsers use boldface. Example: You **must** remember to turn the light off. |
| em      | Adds emphasis to the text; most browsers use italics. Example: We do them because they are *hard*! |
| b       | Stylistically offset text, such as keywords. Example: ES6 adds the keywords **const** and **let**. |
| i       | Alternate voice text. Example: I said "Hello." She said *"Goodbye."* |

Before HTML5, the `b` and `i` elements were non-semantic elements that provided boldface and italic text, respectively. As of HTML5, `b` and `i` are semantic elements, and the meaning has changed. If you intend to use boldface for important text, use `<strong>` instead of `<b>`; if you wish to use italics for emphasis, use `<em>` instead of `<i>`.

We'll cover other formatting elements later in this course. For now, give the `strong` and `em` elements a try on your simple HTML page. Use `strong` to mark the words "HTML" and "CSS" as important words, and use `em` to provide emphasis to the word "terrific":

hello.html

Copy Code

```html
<p>
  Welcome to my website! It's a work in progress as I learn
  <strong>HTML</strong> and <strong>CSS</strong> from a <em>terrific</em> class
  I'm taking at Launch School. I'm learning a lot! Why don't you join me?
</p>
```

## Adding a Hyperlink

Let's convert the words "Launch School" to a hyperlink (or, more succinctly, a link).

HTML uses the term **anchor** to refer to hyperlinks, and it uses the `a` element to code anchors. The `a` element requires a URL for the link, and some content that the browser can display as a clickable item. The `<a>` tag uses the `href` attribute to designate the link URL, and the link description goes between the open and close tags:

hello.html

Copy Code

```html
<p>
  Welcome to my website! It's a work in progress as I learn
  <strong>HTML</strong> and <strong>CSS</strong> from a <em>terrific</em> class
  I'm taking at
  <a href="https://launchschool.com">Launch School</a>. I'm
  learning a lot! Why don't you join me?
</p>
```

Now, when you reload the page, you can click on "Launch School"; your browser should take you to the Launch School website.

## Using the W3C HTML Validator

Take a minute to run your finished code through the [W3C HTML Validator](https://validator.w3.org/#validate_by_input). Try to fix any errors or warnings that arise. Here's our final version of the code:

hello.html

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>Welcome!</title>
    <meta charset="utf-8">
  </head>

  <body>
    <h1>Hello, Internet!</h1>

    <p>
      Welcome to my website! It's a work in progress as I learn
      <strong>HTML</strong> and <strong>CSS</strong> from a <em>terrific</em>
      class I'm taking at <a href="https://launchschool.com">Launch School</a>.
      I'm learning a lot! Why don't you join me?
    </p>

    <p class="more-text">
      There's not a lot of material on this page as I'm playing around with HTML
      &amp; CSS. When I'm done, these last two paragraphs will take on a lighter
      color than the first - the "class" attribute on the two &lt;p&gt; tags and
      a bit of CSS will help accomplish that.
    </p>

    <p class="more-text" id="final-paragraph">
      This is the final paragraph. It also uses the `class` attribute as well as
      an `id` attribute. We'll use some CSS and the `id` attribute to underline
      the entire paragraph.
    </p>
  </body>
</html>
```

Try breaking your code, then re-run the validator with the broken code to see how it responds. Here are some suggestions to try:

- Remove the first `<p>` tag, but leave the `</p>` closing tag.
- Replace `<em>terrific</em>` with `<strong><em>terrific</strong></em>`.
- Replace the `h1` element with an (illegal) `h7` element.
- Remove the `>` from `<em>`.

## What's Next?

You now know how to do some simple book-like formatting of a Web page. It's not attractive, but HTML doesn't provide the tools you need to do much about that. Instead, you need CSS to style the content. We'll get started using CSS in the next assignment.

# Walkthrough Project: Adding Style to Your Web Page

This project shows you how to use CSS to perform some basic styling for a document. We'll update the presentation for the `hello.html` file we worked on in the previous assignment, starting with this code:

hello.html

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>Welcome!</title>
    <meta charset="utf-8">
  </head>

  <body>
    <h1>Hello, Internet!</h1>

    <p>
      Welcome to my website! It's a work in progress as I learn
      <strong>HTML</strong> and <strong>CSS</strong> from a <em>terrific</em>
      class I'm taking at <a href="https://launchschool.com">Launch School</a>.
      I'm learning a lot! Why don't you join me?
    </p>

    <p class="more-text">
      There's not a lot of material on this page as I'm playing around with HTML
      &amp; CSS. When I'm done, these last two paragraphs will take on a lighter
      color than the first - the "class" attribute on the two &lt;p&gt; tags and
      a bit of CSS will help accomplish that.
    </p>

    <p class="more-text" id="final-paragraph">
      This is the final paragraph. It also uses the `class` attribute as well as
      an `id` attribute. We'll use some CSS and the `id` attribute to underline
      the entire paragraph.
    </p>
  </body>
</html>
```

The final result will look like this:



![Hello Internet!](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/a_simple_web_page_02.png)



If you feel like you know CSS well enough to reproduce the above display on your own, go ahead and try. You should still take some time to read through the entire assignment; you don't want to miss any fundamental concepts.

You'll need the following information:

- Font size for paragraphs: `24px`
- Color for final 2 paragraphs: `gray`
- Color for the heading: `orange`
- Color for important text: `blue`
- Color for emphasized text: `red`
- Background color: `#ffffe0`

## Applying CSS

There are three main ways to use CSS in a web page: inline, internal, and external:

- **Inline** CSS uses the `style` attribute on individual HTML tags.
- **Internal** CSS uses the `style` element to store all of the CSS in one place in the file.
- **External** CSS stores the CSS in a file that is separate from the HTML file.

### Inline CSS

Adding a `style` attribute applies some CSS styling to the single element identified by the tag. However, defining styles one at a time is tedious and error-prone, and it mixes the presentation information with the content. You will see inline styles in production code sometimes, but principally in conjunction with dynamically generated web pages.

We'll start styling our project with a `style` attribute to underline the first `strong` element and color it blue.

hello.html

Copy Code

```html
<p>
  Welcome to my website! It's a work in progress as I learn
  <strong style="color: blue; text-decoration: underline;">HTML</strong>
  and <strong>CSS</strong> from a <em>terrific</em> class I'm taking at
  <a href="https://launchschool.com">Launch School</a>. I'm learning a lot! Why
  don't you join me?
</p>
```

Here, we've given the first `strong` element blue text and underlined it. If you load the page in your browser, the word HTML should appear as blue, underlined, boldface text; the boldface comes from the default styles applied to `strong` elements. Note, however, that the other `strong` text (the word "CSS") does not gain these new styles. If you want to apply these attributes to both of these `strong` elements, you need to apply the `style` attributes to both. Applying duplicate `style` attributes is tedious and makes for difficult maintenance. Internal and external CSS are better ways to handle styling.

The `style` attribute lists all the CSS properties you want to use together as a single string. We use a colon (`:`) to separate each property name from its associated value; we separate the property name/value pairs from each other with a semicolon (`;`). The whitespace after each colon and semicolon is optional but recommended for readability.

### Internal CSS

Instead of scattering your style information all over the page with `style` attributes, you can list it all in the `style` element, which belongs inside the `head` element. The `style` element is easy to use, and it puts everything together in one place, which makes it most convenient when you need the CSS for a single page.

We'll use internal CSS often in this course: placing the HTML and CSS together in a simple project is convenient for both teaching and learning.

Let's remove those `style` attributes from the most recent version of our code:

hello.html

Copy Code

```html
<p>
  Welcome to my website! It's a work in progress as I learn
  <strong>HTML</strong> and <strong>CSS</strong> from a <em>terrific</em> class
  I'm taking at <a href="https://launchschool.com">Launch School</a>. I'm
  learning a lot! Why don't you join me?
</p>
```

Now, let's use the `style` element to apply the desired styles to the `strong` elements:

hello.html

Copy Code

```html
<head>
  <title>Welcome!</title>
  <meta charset="utf-8">
  <style>
    strong {
      color: blue;
      text-decoration: underline;
    }
  </style>
</head>
```

When you redisplay the page, your browser will underline *both* `strong` elements and color them blue, in addition to applying the usual boldface styling.

The code between the open and closing `style` tags is CSS. The structure and syntax of CSS are straightforward and consistent. The first part, `strong`, is a **selector**, which tells the browser that it should select and style all `strong` elements in the document as a group. The braces (`{}`) enclose information that the browser can use to style those elements. In this case, the `color` property sets the text color, while the `text-decoration` property tells the browser to underline the text. Colons (`:`) separate each property name (e.g., `color`) from its value (e.g., `blue`), while semi-colons (`;`) mark the end of each property/value pair. Most developers include 2-4 spaces of indentation within the braces.

We can apply styles to other elements. All we need do is specify the appropriate tag name in the selector. For instance, we can make `h1` header orange and the `em` elements red with this code:

hello.html

Copy Code

```html
<style>
  strong {
    color: blue;
    text-decoration: underline;
  }

  h1 {
    color: orange;
  }

  em {
    color: red;
    font-style: italic;
  }
</style>
```

Next, let's increase the font size for the paragraphs on this page. At first, you may feel tempted to replace the `p` tags with `h1` or `h2` tags; this works, and effectively increases the size of each paragraph's font. However, it violates a simple principle: don't use HTML tags for the way your browser renders them.

Use HTML tags semantically - each tag name should describe the type of information you intend to display. A header needs an `h1`, `h2`, etc. tag; a paragraph needs a `p` tag; a link needs an `a` tag. Don't use a `p` tag to render a small header; use one of the `h#` headers instead, and adjust the appearance as needed with CSS.

Here, we'll adjust the font-size for all paragraphs:

hello.html

Copy Code

```css
p {
  font-size: 24px; /* the font is 24 pixels high */
}
```

We can also use the `text-align` property to align text: `left`, `right`, `center`, and `justified` are the main alignment values. For instance, to center-justify the `h1` heading, we can do this:

hello.html

Copy Code

```css
h1 {
  color: orange;
  text-align: center;
}
```

`text-align` can be a little tricky to use properly. Be sure you read the MDN documentation when you're ready to use it.

We can use the `background-color` property to set the background color for our page to a pale yellow:

hello.html

Copy Code

```css
body {
  background-color: #ffffe0;
}
```

Suppose we want to style the last two paragraphs differently from the others. Note that both have a `class` attribute with a value of `more-text`.

hello.html

Copy Code

```html
<p class="more-text">
  There's not a lot of material on this page as I'm playing around with HTML
  &amp; CSS. When I'm done, these last two paragraphs will take on a lighter
  color than the first - the "class" attribute on the two &lt;p&gt; tags and a
  bit of CSS will help accomplish that.
</p>

<p class="more-text" id="final-paragraph">
  This is the final paragraph. It also uses the `class` attribute as well as an
  `id` attribute. We'll use some CSS and the `id` attribute to underline the
  entire paragraph.
</p>
```

We can use this class to apply some CSS styling to both paragraphs at once without also affecting the paragraph that does not have a class:

hello.html

Copy Code

```css
.more-text {
  color: gray;
}
```

When you display the page now, the last two paragraphs take on a gray color.

The `class` attribute identifies a group of elements that have something in common. Elements that have the same name in the `class` attribute belong to the same class. Any tag can belong to one or more classes, and each class may apply to multiple tags.

The last requirement for this project is to underline the final paragraph. That paragraph uses a `p` element, but we have two other `p` elements that we style differently. Thus, we can't use a simple `p` selector. Two paragraphs also use the `more-text` class, so we can't use that to select the paragraph we want. What makes that paragraph unique, though, is that it has an `id` attribute, which means we can use an ID selector:

hello.html

Copy Code

```css
#final-paragraph {
  text-decoration: underline;
}
```

`id` attributes **must be unique on the page**: no two elements can have an `id` attribute with the same value.

Some developers argue that you should never use ID selectors in your CSS, and there are good arguments for this. However, the arguments on the other side balance them out. Feel free to use ID selectors here at Launch School. However, we recommend using them sparingly - that will help avoid specificity issues in your CSS.

### External CSS

Placing CSS in a separate file and identifying that file as a `stylesheet` with a `<link>` tag tells the browser that it should load CSS style information from an external file located on the server. The `link` tag belongs inside the `<head>...</head>` element.

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>Welcome!</title>
    <meta charset="utf-8">
    <link rel="stylesheet" href="my.css">
  </head>
  <body>
  </body>
</html>
```

Here, the browser will request the file `my.css` from the server, and use its content to provide the CSS for the page. You can specify multiple files if needed; use one `link` tag for each CSS file.

External CSS is the preferred way to include CSS in most web pages since it lets you share CSS between multiple pages, and makes maintenance of the CSS code separate from that of the HTML. Browsers can also cache external CSS files, which can reduce page load times. For most of this course, though, we'll stick with the internal technique; feel free to use external files if you wish.

For practice, let's extract the CSS from the HTML file and place it in a separate file. We'll use a name of `my.css` for the CSS file.

hello.html

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>Welcome!</title>
    <meta charset="utf-8">
    <link rel="stylesheet" href="my.css">
  </head>

  <body>
    <h1>Hello, Internet!</h1>

    <p>
      Welcome to my website! It's a work in progress as I learn
      <strong>HTML</strong> and <strong>CSS</strong> from a <em>terrific</em>
      class I'm taking at <a href="https://launchschool.com">Launch School</a>.
      I'm learning a lot! Why don't you join me?
    </p>

    <p class="more-text">
      There's not a lot of material on this page as I'm playing around with HTML
      &amp; CSS. When I'm done, these last two paragraphs will take on a lighter
      color than the first - the "class" attribute on the two &lt;p&gt; tags and
      a bit of CSS will help accomplish that.
    </p>

    <p class="more-text" id="final-paragraph">
      This is the final paragraph. It also uses the `class` attribute as well as
      an `id` attribute. We'll use some CSS and the `id` attribute to underline
      the entire paragraph.
    </p>
  </body>
</html>
```

my.css

Copy Code

```css
strong {
  color: blue;
  text-decoration: underline;
}

h1 {
  color: orange;
  text-align: center;
}

em {
  color: red;
  font-style: italic;
}

p {
  font-size: 24px;
}

body {
  background-color: #ffffe0;
}

.more-text {
  color: gray;
}

#final-paragraph {
  text-decoration: underline;
}
```

## Using the W3C CSS Validator

Take a minute to run your finished CSS code through the [W3C CSS Validator](https://jigsaw.w3.org/css-validator/#validate_by_input). Try to fix any errors or warnings that it identifies.

Try breaking your code, then re-run the validator with the broken code to see how it responds. Here are some suggestions:

- Remove the `p` selector, but leave the rest of the rule intact.
- Remove the `:` from one of the property names.
- Change the `color` for `strong` to an invalid value (`#f0f0995`).
- Remove the `;` after `color: orange` in the `h1` rule.

# Guided Project: A Personal Profile

You should now understand how to construct a web page and should be able to build a simple one without much trouble. Let's use that knowledge to create a page with some basic information about somebody special: you. Think of it as a profile page that you might see on a social networking site. It will show your name, title (future front-end developer!), GitHub link, and a list of your five favorite links. This short video shows the finished product:

Remember: the videos may differ from the written instructions and the completed example. The written instructions take precedence.

<video id="video_aacb480cd27c_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/overview_your_first_web_page_8c2d9c_s42/overview_your_first_web_page_8c2d9c_s42.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 818.944px; height: 460.647px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/overview_your_first_web_page_8c2d9c_s42/overview_your_first_web_page_8c2d9c_s42.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/overview_your_first_web_page_8c2d9c_s42/overview_your_first_web_page_8c2d9c_s42.sbv)

Duration: **0:42**

A second video at the bottom of this page walks you through the entire process of building the page; you should try to create this page using the guided steps first, then refer to the video to see how you did. Don't worry if your code is different; as long as the final page looks close to the desired project, you're doing well.

As you move through the project, be sure to view the page after each step so you can verify that you're on the right track.

For reference, here's another look at the final project:



![Personal Profile](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/profile-01.png)



## Creating the HTML

Complete the following steps:

1. Start a new HTML file with your HTML skeleton, and change the page title to "My Profile."

2. Add your content to the document's `body`. Use plain text for now; we'll add the HTML below. The content should include your:

   - name, e.g., `Joe Lindt`
   - job title, e.g., `Future Front-end Developer`
   - Your GitHub link (e.g., `https://github.com/joelindtisnotarealperson`)
   - a list of five web page links identified as `My Top 5 Links`

   The content won't be pretty at this point, but that's okay.

3. Convert the name to an `h1` heading.

4. Convert the job title to an `h2` heading.

5. Convert the GitHub profile to a link (an anchor).

6. Use a `strong` element to give the GitHub link a label, `GitHub Profile:`, that has some visual importance.

7. Wrap the label and link for your GitHub profile in a paragraph.

8. Enclose the "My Top 5 Links" title in an `h3` heading.

9. Convert the descriptions for each of your top 5 links to an anchor.

10. Enclose your list of top links (not including the heading) in an ordered list (`ol` element). Feel free to look up ordered lists in the MDN documentation or elsewhere on the Web.

11. Validate your HTML at W3C!

Your HTML should now look something like this:

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <title>My Profile</title>
  </head>

  <body>
    <h1>Joe Lindt</h1>

    <h2>Future Front-end Developer</h2>

    <p>
      <strong>GitHub Link:</strong>
      <a href="https://github.com/joelindtisnotarealperson" target="_blank">
        Joe Lindt
      </a>
    </p>

    <h3>My Top 5 Links</h3>
    <ol>
      <li>
        <a href="http://www.html5rocks.com/en/" target="_blank">HTML5 Rocks</a>
      </li>
      <li><a href="http://caniuse.com/" target="_blank">Can I Use?</a></li>
      <li>
        <a href="http://www.w3.org/html/wg/drafts/html/master/" target="_blank">
          HTML5 Spec
        </a>
      </li>
      <li>
        <a href="http://www.w3.org/TR/css3-selectors/" target="_blank">
          CSS3 Selectors
        </a>
      </li>
      <li>
        <a href="https://developer.mozilla.org/en-US/" target="_blank">
          Mozilla Developer Network
        </a>
      </li>
    </ol>
  </body>
</html>
```

The content and HTML may differ, but as long as the results match, it should be fine.

Now that we have the HTML, or markup, completed, we can move on to the styling.

### The Target Attribute

Our solution shows a `target="_blank"` attribute on all our links. This attribute tells the browser that it should open the link in a separate tab or window.

The use of `target="_blank"` is slightly controversial. Some developers believe you should use it when linking to a different site, while others believe that you should never use it (which lets the user choose instead). We typically use it when linking to a different site, but you can make your own choice.

## Styling Your Profile

We'll continue to use the `<style>` tag for now.

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <title>My Profile</title>
    <style>
    </style>
  </head>

  <!-- rest of HTML -->
</html>
```

When styling pages, it's often easiest to follow a simple plan in deciding what and where to style:

- Start by adding some simple properties, primarily color and font, to the `body` selector to give the page an overall look and feel that focuses on your content.
- Set the position and size of the organizational components of the page: header, footer, sidebars, etc. to match your desired page structure.
- Apply your background and font colors to those parts of the page that need non-default styling.
- By now, your page should look a lot like your final product. Finish by concentrating on each component individually and make any adjustments you need to make to achieve the desired look.

Given this approach, complete the following steps:

1. Set the background color for the page to a dark blue color (`#01304b`).

   **Most** elements use a transparent background color by default, so the background color for the body applies to most page elements. Here, everything uses the same background.

2. The page is now close to unreadable. Set the foreground color (the text color) for the page to a light gray (`#eee`).

3. The links are still hard to read. Change them to a golden color (`#c3b802`).

   The `color` property is inheritable, which means that applying `color` to an element also applies it to every descendant of that element. There are exceptions, though. For instance, your links didn't inherit the text color. This seeming failure occurs since the browser sets separate colors for links, which prevents them from inheriting the primary text color.

   CSS inheritance isn't like class inheritance in an OOP language like Ruby, and, for the most part, is beyond the scope of this course. Don't let the vocabulary confuse you, though. Make a note to read about CSS inheritance when you're ready to learn more.

4. Let's try using a sans-serif font for this page. Set the default font for this page to be one of `Arial`, `Helvetica`, or the generic `sans-serif` font.

   Hint

   Browsers use a serif typeface by default. Serif fonts have flared end-points on most characters; sans-serif do not:

   

   ![Serif and Non-Serif Fonts](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/serifs-01.png)

   

   The font you choose is mainly a matter of preference, or rather, the preferences of your designer. Mainstream use today seems to favor serif fonts for headlines and other attention-grabbing items and sans-serif for paragraph-based text.

   [This short but helpful guide](http://web.mit.edu/jmorzins/www/fonts.html) includes information on Web-safe fonts and displays examples of each. You don't have to read it right now, but bookmark it for reference.

5. The list items for the top 5 links seem cramped; add 10 pixels of line spacing between elements.

   Hint

   Use one of the various margin properties to add the spacing.

   The walkthrough video at the bottom of this page uses padding instead of margin to give some spacing to the list items; in this case, they work similarly. However, in general, they serve different purposes. We will discuss margins and padding later; for now, either will work in this project.

6. Validate your CSS at W3C!

Your HTML should now look something like this:

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <meta charset="utf-8">
    <title>My Profile</title>
    <style>
      body {
        background-color: #01304b; /* dark blue */
        color: #eee;               /* light gray */
        font-family: Arial, Helvetica, sans-serif;
      }

      a {
        color: #c3b802;            /* gold */
      }

      li {
        margin-bottom: 10px;
      }
    </style>
  </head>

  <body>
    <h1>Joe Lindt</h1>

    <h2>Future Front-end Developer</h2>

    <p>
      <strong>GitHub Link:</strong>
      <a href="https://github.com/joelindtisnotarealperson" target="_blank">
        Joe Lindt
      </a>
    </p>

    <h3>My Top 5 Links</h3>
    <ol>
      <li>
        <a href="http://www.html5rocks.com/en/" target="_blank">HTML5 Rocks</a>
      </li>
      <li><a href="http://caniuse.com/" target="_blank">Can I Use?</a></li>
      <li>
        <a href="http://www.w3.org/html/wg/drafts/html/master/" target="_blank">
          HTML5 Spec
        </a>
      </li>
      <li>
        <a href="http://www.w3.org/TR/css3-selectors/" target="_blank">
          CSS3 Selectors
        </a>
      </li>
      <li>
        <a href="https://developer.mozilla.org/en-US/" target="_blank">
          Mozilla Developer Network
        </a>
      </li>
    </ol>
  </body>
</html>
```

## Walkthrough Video

Even if your page came out perfect, take some time to watch our video walkthrough for this project:

<video id="video_619c23bc237c_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/your_first_web_page_4847b5_s783/your_first_web_page_4847b5_s783.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 818.944px; height: 460.647px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/your_first_web_page_4847b5_s783/your_first_web_page_4847b5_s783.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/your_first_web_page_4847b5_s783/your_first_web_page_4847b5_s783.sbv)

Duration: **13:03**

# Practice Problems: Text Formatting

These practice problems focus on HTML and CSS that deal with text, like the font family, style, color, and size.

1. Create an HTML page with a single paragraph of text. Write CSS to set the font size for most elements on the page to 20px (you may ignore headers, subscripts, and other items that often have a different size).

   Solution

   Copy Code

   ```html
   <body>
     <p>
       Mollit cupidatat sunt aliqua. Consectetur in aute adipisicing sit qui
       nostrud. Laborum enim sit velit ipsum enim ullamco incididunt sint.
       Officia exercitation proident voluptate cupidatat elit culpa dolore ut
       excepteur.
     </p>
   </body>
   ```

   Copy Code

   ```css
   body {
     font-size: 20px;
   }
   ```

   We use the `body` selector to apply the CSS to most elements on the page.

2. Change the font family for the page from the previous problem to a sans-serif font.

   Solution

   Copy Code

   ```css
   body {
     font-family: sans-serif;
     font-size: 20px;
   }
   ```

3. Change the CSS for the previous problem to give the browser a choice of one of three fonts (Tahoma, Trebuchet MS, Verdana), depending on what is available, before it uses the default sans-serif font.

   Solution

   Copy Code

   ```css
   body {
     font-family: Verdana, "Trebuchet MS", Tahoma, sans-serif;
     font-size: 20px;
   }
   ```

4. Change the text from the previous problem to italic.

   Solution

   Copy Code

   ```css
   body {
     font-family: Verdana, "Trebuchet MS", Tahoma, sans-serif;
     font-size: 20px;
     font-style: italic;
   }
   ```

5. Change the CSS from the previous problem to boldface (keep the italics).

   Solution

   Copy Code

   ```css
   body {
     font-family: Verdana, "Trebuchet MS", Tahoma, sans-serif;
     font-size: 20px;
     font-style: italic;
     font-weight: bold;
   }
   ```

6. Change the CSS from the previous problem to increase the line height to 2.5 times its default height.

   Solution

   Copy Code

   ```css
   body {
     font-family: Verdana, "Trebuchet MS", Tahoma, sans-serif;
     font-size: 20px;
     font-style: italic;
     font-weight: bold;
     line-height: 2.5;
   }
   ```

7. Change the CSS you wrote in questions 1-6 to a shorthand form that uses precisely one property. The output should not change.

   Solution

   Copy Code

   ```css
   body {
     /* font-family: Verdana, "Trebuchet MS", Tahoma, sans-serif; */
     /* font-size: 20px; */
     /* font-style: italic; */
     /* font-weight: bold; */
     /* line-height: 2.5; */
     font: italic bold 20px/2.5 Verdana, "Trebuchet MS", Tahoma, sans-serif;
   }
   ```

8. Change the CSS from the previous problem to right-align the text within the paragraph:

   Solution

   Copy Code

   ```css
   body {
     text-align: right;
   }
   ```

9. Change the CSS from the previous problem to center-align the text within the paragraph:

   Solution

   Copy Code

   ```css
   body {
     text-align: center;
   }
   ```

10. Change the CSS from the previous problem to fully justify the text within the paragraph:

    Solution

    Copy Code

    ```css
    body {
      text-align: justify;
    }
    ```

11. Change the CSS from the previous problem to indent the start of the paragraph by 4em.

    Solution

    Copy Code

    ```css
    body {
      text-indent: 4em;
    }
    ```

12. Write the CSS needed to reproduce this screenshot:

    

    ![Example of completed problem](https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_basic_css/css_1.jpg)

    

    You should use this HTML:

    Copy Code

    ```html
    <article>
      <header>
        <h1>Finessing `feColorMatrix`</h1>
      </header>
      <p>
        Harness the power of <code>feColorMatrix</code> to create detailed
        filters, with Una Kravets as your guide.
      </p>
    </article>
    ```

    The `h1` heading uses the `Georgia` font while the `code` element uses the browser's default `monospace` font. The remaining text uses a 14px sans-serif font, with Helvetica and Arial preferred.

    Solution

    Copy Code

    ```css
    body {
      font: normal 14px Helvetica, Arial, sans-serif;
    }
    
    h1 {
      font-family: Georgia, serif;
    }
    
    code {
      font-family: monospace;
      font-style: italic;
      text-decoration: underline;
    }
    ```

13. Change the CSS from the previous problem to display the `h1` element text in blue, and the `code` text in green.

    Solution

    Copy Code

    ```css
    h1 {
      color: blue;
    }
    
    code {
      color: green;
    }
    ```

14. Write the CSS needed to reproduce this screenshot:

    

    ![Example of completed problem](https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_basic_css/css_2.jpg)

    

    You should use this HTML:

    Copy Code

    ```html
    <p>That episode was <mark>un<strong>be<em>lieve</em></strong>able</mark>!</p>
    ```

    The font highlighted in yellow is `Courier`; use a backup font of `monospace`. The text uses four font sizes - `12px`, `15px`, `18px` and `20px`.

    Solution

    Copy Code

    ```css
    body {
      font-size: 18px;
    }
    
    mark {
      background-color: yellow;
      font-family: Courier, monospace;
      font-size: 12px;
    }
    
    strong {
      font-size: 15px;
    }
    
    em {
      font-size: 20px;
      text-transform: uppercase;
    }
    ```

15. Create some HTML with this paragraph:

    Copy Code

    ```html
    <p>
      The Creating Hyperlinks section of Getting to Know HTML discusses
      hyperlinks, or anchors. Be sure to work both "In Practice" sections; they
      pick up from where you left off in an earlier reading assignment.
    </p>
    ```

    Convert the text `Getting to Know HTML` to a hypertext link to this URL:

    Copy Code

    ```html
    http://learn.shayhowe.com/html-css/getting-to-know-html/#creating-hyperlinks
    ```

    The link should open in a new browser tab or window. Add CSS to remove the underline and change the color to red.

    Solution

    Copy Code

    ```html
    <p>
      The Creating Hyperlinks section of
      <a href="http://learn.shayhowe.com/html-css/getting-to-know-html/#creating-hyperlinks"
         target="_blank">Getting to Know HTML</a>
      discusses
      hyperlinks, or anchors. Be sure to work both "In Practice" sections; they
      pick up from where you left off in an earlier reading assignment.
    </p>
    ```

    Copy Code

    ```css
    a {
      color: red;
      text-decoration: none;
    }
    ```

You marked this topic or exercise as completed.

# On Your Own: Creating a Simple Page

For this project, you'll build a simple web page that describes your day.

You have the following HTML and CSS and text to begin this project.

Copy Code

```html
<h1>My Day At a Glance</h1>
<h2>Morning</h2>
<p>
  Get up. Feed cats. Eat breakfast. Brush my teeth. Shower. Feed lizard. Commute
  to my recliner. Sit down. Pet cats. Go to work.
</p>

<h2>Afternoon</h2>
<p>Eat lunch. Take a nap. Study for Launch School. Avoid work.</p>

<h2>Evening</h2>
<ul>
  Feed cats.
  Have dinner.
  Study.
  Study for Launch School.
  Watch TV.
  Feed fish.
  Watch more TV.
  Go to bed.
</ul>
```

Copy Code

```css
body {
  margin-left: 25px;
}

ul {
  padding-left: 0;
}
```

Modify your code so that your browser renders it as close as possible to the following image:



![Day At A Glance](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/day_at_a_glance.png)



Your project should meet the following requirements:

- For best results, set your browser to 600 pixels width and use the default fonts for your browser.
- Your browser/tab title should be `My Day at a Glance`.
- Display the Morning, Afternoon, and Evening items as black, blue, and purple text respectively.
- Display the Morning items with boldfaced text.
- Display the Afternoon items with italicized text.
- Display the Evening items without bullets or indentation.
- Include all required HTML elements, e.g., `<html>`, `<head>`, etc.
- Use the UTF-8 character set with English as the page language.
- Use HTML5.
- Pass both W3C HTML and CSS validators.

You may use the `style` element, but do not use the `style` *attribute*. Do not remove or alter the `body` or `ul` styles provided above.

Some of these items require that you modify the HTML; others want you to update the CSS. It's your choice for each. You may have to search the Internet (and MDN in particular) for assistance.

Solution

Copy Code

```html
<h1>My Day At a Glance</h1>
<h2 id="morning">Morning</h2>
<p id="morning-tasks">
  Get up. Feed cats. Eat breakfast. Brush my teeth. Shower. Feed lizard. Commute
  to my recliner. Sit down. Pet cats. Go to work.
</p>

<h2 id="afternoon">Afternoon</h2>
<p id="afternoon-tasks">
  Eat lunch. Take a nap. Study for Launch School. Avoid work.
</p>

<h2 id="evening">Evening</h2>
<ul>
  <li>Feed cats.</li>
  <li>Have dinner.</li>
  <li>Study.</li>
  <li>Study for Launch School.</li>
  <li>Watch TV.</li>
  <li>Feed fish.</li>
  <li>Watch more TV.</li>
  <li>Go to bed.</li>
</ul>
```

Copy Code

```css
body {
  margin-left: 25px;
}

ul {
  padding-left: 0;
}

#morning-tasks {
  font-weight: bold;
}

#afternoon {
  color: blue;
}

#afternoon-tasks {
  font-style: italic;
}

#evening {
  color: purple;
}

li {
  list-style: none;
}
```

Your code may differ from ours, and that's fine provided you achieved a good match for the intended results. HTML/CSS problems almost always have multiple solutions. The one we've chosen is simple and doesn't stray too far from the ideal practices of using HTML and CSS, and it doesn't stray too far from the material we've already covered:

- We use `id` attributes and ID selectors to give styles to the three different `h2` headers.
- We also use `id` and ID selectors to give styles to the morning and afternoon task listings. We could have used `strong`, `em`, `b`, and `i` elements instead, but none of these seem to be semantically correct in these situations; there's no meaning behind the use of boldface or italic type here.
- We need to add some `<li>` tags to the evening list elements.

If your code differs considerably from our solution, please feel free to ask for a Code Review. Be sure to ask questions or explain why you took a different approach.

# Practice Problems: CSS Selectors

Use the following prepared HTML file to complete this problem set:

Prepared HTML

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>CSS Selectors</title>
    <meta charset="utf-8">
    <style>
      /* Make all your changes here */
    </style>
  </head>
  <body>
    <header>
      <h1>Site Title</h1>

      <ul>
        <li>
          <a href="#">Nav Category 1</a>
          <ol>
            <li><a href="#">Sub category item 1</a></li>
            <li><a href="#">Sub category item 2</a></li>
            <li><a href="#">Sub category item 3</a></li>
          </ol>
        </li>

        <li>
          <a href="#">Nav Category 2</a>
          <ol>
            <li><a href="#">Sub category item 1</a></li>
            <li><a href="#">Sub category item 2</a></li>
          </ol>
        </li>
      </ul>
    </header>

    <main>
      <h1>Main Page</h1>

      <p id="intro">
        Site introduction lorem ipsum dolor sit amet, consectetur adipiscing
        elit. Cras non ultricies augue.
      </p>

      <article>
        <h2 class="subheading">First Article</h2>

        <p>
          Sed non nunc quam. Fusce vitae dui ut ante gravida posuere. Phasellus
          arcu nibh, posuere ac dignissim tincidunt, interdum placerat nisi.
          Nunc sagittis odio arcu, id suscipit enim maximus sit amet.
        </p>

        <ul>
          <li>ac turpis</li>
          <li>mauris</li>
          <li>ultrices</li>
          <li>laoreet</li>
        </ul>

        <p>
          Nunc ac turpis a mauris ultrices laoreet porta quis tellus. Phasellus
          pellentesque imperdiet erat quis suscipit. Proin vitae varius felis.
          Morbi at lacus mattis, vestibulum neque at, pretium libero.
        </p>
      </article>

      <article>
        <h2>Second Article</h2>

        <p>
          Et venenatis ligula volutpat et. Proin purus nibh, efficitur et
          porttitor in, ultrices et sapien.
        </p>

        <ol>
          <li>Vivamus</li>
          <li>luctus</li>
          <li>molestie</li>
        </ol>
      </article>

      <article>
        <h2>Third Article</h2>

        <p>
          Sint do consequat fugiat duis aute incididunt. Dolor reprehenderit
          est fugiat exercitation. In Lorem laborum mollit velit laborum
          occaecat laboris exercitation.
        </p>

        <ul>
          <li>
            Famous Mariners
            <ol>
              <li>Ishmael</li>
              <li>Captain Hook</li>
              <li>The Ancient Mariner</li>
            </ol>
          </li>
          <li>
            Former Mariners
            <ol>
              <li>Ken Griffey, Jr</li>
              <li>Ichiro Suzuki</li>
              <li>Randy Johnson</li>
            </ol>
          </li>
        </ul>
      </article>
    </main>
  </body>
</html>
```

Add the required CSS to the `style` element at the top of the document. **Don't change the HTML**.

Use [this section of the Shay Howe tutorial](https://learn.shayhowe.com/html-css/getting-to-know-css/) and [this MDN page](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Combinators_and_multiple_selectors) as you work this problem set. You should know how to use the basic selectors (tag, class, and id), but you're not expected to memorize the more complicated selectors. However, you should know how to find them.

1. Set the width of the page body to `600px`.

   Solution

   Copy Code

   ```css
   body {
     width: 600px;
   }
   ```

2. Set the font size on all paragraphs to `18px`.

   Solution

   Copy Code

   ```css
   p {
     font-size: 18px;
   }
   ```

   This code changes the paragraph fonts, but it doesn't change the size elsewhere.

3. Change the font for all list items (the `li` tags) to a `monospace` font, and give them a color of `purple`.

   Solution

   Copy Code

   ```css
   li {
     color: purple;
     font-family: monospace;
   }
   ```

   This code does not alter the color of the list items under `Site Title`, though it does change the color of the bullets and numbers. It fails to change the list item color, however, since the list items are links. Browsers give links a different color in their default settings, so changing the text color elsewhere doesn't affect the link color. You can, if you want, explicitly set the color of the links inside list items like this:

   Copy Code

   ```css
   li a {
     color: purple;
   }
   ```

   Hovered and active links still turn a different color when you do this, but that's what you want, probably.

   On the other hand, browsers don't change the default `font-family` property for links, so when we change it for `li`, the links inside each list item inherit the `font-family`.

4. Remove the underlines from all links on the page.

   Hint

   You've already seen how to add underlines to text. Now you have to reverse that.

   Solution

   Copy Code

   ```css
   a {
     text-decoration: none;
   }
   ```

5. Change the `li` selector from problem 3 so that it no longer styles the lists inside the `header` section. Don't add any new CSS, but you can modify the selector for an existing rule. Afterward, the list items in the header should be blue with a proportional (non-monospace) font, and the numbers should be black. All remaining list items should be purple and monospace.

   Hint

   You need to select some `li` elements while leaving others unselected. Examine the HTML to determine which `li` elements you need, and what makes them different from the list items you don't want. Use this information to construct a selector that limits the results to the ones you want.

   Solution

   Copy Code

   ```css
   main li {
     color: purple;
     font-family: monospace;
   }
   ```

   The list items we want to style are all in the `main` section. We can use a `main li` selector to select the `li` elements inside the `main` section.

6. Set the color on all paragraphs that are inside an `article` element to `brown`.

   Solution

   Copy Code

   ```css
   article p {
     color: brown;
   }
   ```

7. Add the background color `#e0e0e0` to the "First Article" heading.

   Solution

   Copy Code

   ```css
   .subheading {
     background-color: #e0e0e0;
   }
   ```

   This solution makes use of the `subheading` class on the desired heading.

8. Set the font size for the element with ID `intro` to `24px`.

   Solution

   Copy Code

   ```css
   #intro {
     font-size: 24px;
   }
   ```

9. **Challenge:** Change the color for all list items directly within an unordered list in the `main` section to `green`. Be careful not to change any of the list items that don't belong to an unordered list, nor any of the list items in the `header` element.

   Hint

   This problem uses ordered and unordered lists (`ol` and `ul`) and their corresponding list items (`li`). You don't have to understand these lists to solve the problem - all you need know is that you need to select the `li` elements that are **direct children** of a `ul` element within the `main` element while excluding other `li` elements.

   Every element except the `html` element is a direct child of precisely one other element. For example:

   Copy Code

   ```html
   <main>
     <p>content 1<p>           <!-- direct child of `main` -->
     <p>content 2<p>           <!-- direct child of `main` -->
     <ol>                      <!-- direct child of `main` -->
       <li>content 3</li>      <!-- direct child of `ol` -->
       <li>                    <!-- direct child of `ol` -->
         <ul>                  <!-- direct child of `li` -->
           <li>content 4</li>  <!-- direct child of `ul` -->
         </ul>
       </li>
     </ol>
   </main>
   ```

   The last `li` element is not a direct child of the `ol`.

   Solution

   Copy Code

   ```css
   main ul > li {
     color: green;
   }
   ```

   Writing the selector for this problem is a bit tricky. To begin, since we want to select `li` items, we need a `li` selector. However, we want to restrict the results to list items inside unordered lists. We can try using a selector of `ul li`. That, however, adds the color to the ordered lists in the "Third Article" since `ul li` tells the browser to select all `li` elements that are a **descendant** of a `ul`, no matter how deeply nested the `li` elements are. By changing that to `ul > li`, we tell the browser that we want direct children of `ul`; nothing else.

   For the last step, we add `main` to the selector to restrict the selected elements to those inside `main`; if we don't do this, the numbers in the `header` would be green instead of the default black.

Completed Page Appearance

The final result for this page should look like this:



![Final Result](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/css_selectors-01.png)

# CSS Diner

Do you need more practice? We found an interesting site called the [CSS Diner](https://flukeout.github.io/) that will give you some practice constructing CSS selectors. The Diner presents you with a series of problems, each of which shows an image with some plates and food, a CSS Editor, and an HTML Viewer. There's also a panel on the right that provides information that you'll need for the current problem. At the top of the screen is a short description of what you're supposed to select.

Your job is to write the CSS selector you need to select the item or items mentioned. At first, the trickiest part is realizing that you're not working with real HTML. It feels a little odd to enter a selector `bento`, but that's what you're supposed to do. The problems get steadily harder as you move through them, so, if they seem too easy at first, feel free to skip ahead.

If you get stuck, be sure to refer to the MDN documentation for selectors.

# Using the Chrome Inspector

You'll sometimes want to determine what styles an element on a web page uses, and how it got those styles. The complex rules of the cascade, specificity, inheritance, and importance sometimes make this determination hard. In modern browsers, a tool called the **Inspector** provides you with all the information the browser has for each element. It lets you look at each element's current CSS settings, determine how it received those styles, and even permits changing their values temporarily.

The Inspector is part of a larger and more powerful tool often called the **Developer Tools**, such as that found in Google Chrome. Since we're using Chrome as our primary development browser, we'll take some time now to learn how to use these tools in Chrome.

Use one of these methods to open the tools.

- Select the Developer Tools option from Chrome's menus. At the time of this writing, you can find this option under View, Developer on Macs; the location may be different on other systems and may change in the future.
- Right-click any page element and select Inspect.
- Use Command-Option-I (on Macs) or Control-Shift-I (other systems).

Since the Developer Tools change often, we will refer you to the official documentation rather than try to teach you how to use it. Going directly to the source ensures that you're learning how to use the most recent version of the tools. Please take some time to read a small part of [the documentation](https://developers.google.com/web/tools/chrome-devtools/) now. There's a lot of material there; for now, you should read the [Get Started With Viewing And Changing The DOM](https://developer.chrome.com/docs/devtools/dom/), [View the properties of DOM objects](https://developer.chrome.com/docs/devtools/dom/properties/), and the [View and change CSS](https://developer.chrome.com/docs/devtools/css/) sections.

The remaining documentation focuses primarily on matters you won't encounter until you start working with JavaScript and other tools, so it's way too soon to spend much time reading about the Tools.

The documentation talks about **DOM Nodes** or **nodes**. For the time being, you can assume that nodes are another way to refer to HTML elements. You'll learn more about nodes in another course.

At this stage, you should begin using the Inspector as you move through the course, primarily as a debugging and experimentation tool. For instance, if you are having problems with the box model (discussed in the next lesson), the Inspector is where you will find the information you need to diagnose the issue. You can even use it to experiment with several different settings to see if they fix the problem you're having. A great way to practice using the inspector is to find web pages that do something like what you want to do and see how they handled the problem.

> If you wish to use another browser for development, it's your responsibility to learn how to use the corresponding tools in that browser. Using another browser platform shouldn't be difficult: most look and act similarly, so once you learn one, it's easy to learn another.

Most developers prefer to undock the Tools or to dock them on the left or right side of the browser window. The default configuration docks the Tools on the bottom of the screen. See the [Chrome Devtools Documentation](https://developer.chrome.com/docs/devtools/) for information on how to configure the docking state of the Tools.

# HTML and CSS Style Guide

Both HTML and CSS have a simple syntax without a lot of rules. Even so, using them haphazardly can lead to impenetrable code that is nearly impossible to read or alter. You don't need a complete style guide to use them well, but a handful of simple guidelines will go a long way toward producing readable code.

The Shay Howe tutorial ends with a section on [Writing Your Best Code](http://learn.shayhowe.com/html-css/writing-your-best-code/). We recommend looking this over (don't worry about unfamiliar material right now) and following the advice as much as possible.

We have some other rules you may want to consider.

## HTML Style

- Avoid cramming more than two elements on a single line.

  ```html
  <!-- Legal but hard to read -->
  <nav><ul><li>Home</li><li>Sign Up</li><li>Log In</li><li>Log Out</li></ul></nav>
  
  <!-- Good -->
  <nav>
    <ul>
      <li>Home</li>
      <li>Sign Up</li>
      <li>Log In</li>
      <li>Log Out</li>
    </ul>
  </nav>
  
  <!-- Acceptable, but a bit hard to read -->
  <li><a href="home.html">Home</a></li>
  <a href="home.html"><img src="home.gif"></a>
  ```
  
- Indent nested tags by two spaces, four spaces, or hard tabs. (Be consistent.)

  Copy Code

  ```html
  <!-- Legal but hard to read and maintain -->
    <section>
  <blockquote>
  the quote
              </blockquote>
  </section>
  
  <!-- Easier to read, but doesn't reveal structure -->
  <section>
  <blockquote>
  the quote
  </blockquote>
  </section>
  
  <!-- Good -->
  <section>
    <blockquote>
      the quote
    </blockquote>
  </section>
  ```

- Don't indent the `<html>` tag.

  Copy Code

  ```html
  <!-- Legal, but non-standard -->
  <!DOCTYPE html>
    <html lang="en-US">
      <!-- rest of HTML -->
    </html>
  
  <!-- Okay -->
  <!DOCTYPE html>
  <html lang="en-US">
    <!-- rest of HTML -->
  </html>
  ```

- **DO NOT** use `/>` with **self-closing** tags (`<br>`, `<img />`, etc.). There has been some back and forth on this issue, but, since the W3C validator no longer approves of `/>` on self-closing tags, we recommend not using it.

  Copy Code

  ```html
  <!-- Good -->
  <br>
  <img src="picture.jpg">
  
  <!-- Bad -->
  <br />
  <img src="picture.jpg" />
  ```

- When using Flex or Grid (we'll talk about these later), consider placing the most significant content blocks near the top of the file, and the least important at the bottom.

## CSS Style

- Don't put more than one property on the same line.

  Copy Code

  ```css
  /* Legal but hard to read and maintain */
  p {
    background-color: yellow; border: 3px dashed #888; color: red;
  }
  
  /* Okay */
  p {
    background-color: yellow;
    border: 3px dashed #888;
    color: red;
  }
  ```

- An exception to the above rule occurs when using **fallbacks**. To support older browsers, CSS developers must sometimes provide two or more different values for a property; one that applies to contemporary browsers, and another for older browsers. You can list fallbacks on the same line to show when you are using one:

  Copy Code

  ```css
  p {
    background-color: yellow;
    color: red;
    width: 50%; width: 50vw; /* fallback to 50% if 50vw not recognized */
  }
  ```

- Indent property names and values by two spaces, four spaces, or hard tabs. (Be consistent.)

  Copy Code

  ```css
  /* Legal but hard to read */
  p {
  background-color: yellow;
                border: 3px dashed #888;
          color: red;
  }
  
  /* Okay */
  p {
    background-color: yellow;
    border: 3px dashed #888;
    color: red;
  }
  ```

- Put the opening `{` on the same line as the selector. Put the closing `}` on a line by itself or at the end of the last property.

  Copy Code

  ```css
  /* Legal but hard to read */
  p
      {
    color: red;}
  
  /* Okay */
  p {
    color: red;
  }
  
  /* Also okay */
  p
  {
    color: red;
  }
  
  /* Also okay */
  p { color: red; }
  
  /* Also okay, but unusual */
  p {
    color: red;
    width: 500px; }
  ```

- Include a space after the `:` in `property: value;`. Don't use spaces before the `:`.

  Copy Code

  ```css
  /* Legal but hard to read */
  p {
    background-color:orange;
    border  :3px solid green;
    color:black;
  }
  
  /* Okay */
  p {
    background-color: orange;
    border: 3px solid green;
    color: black;
  }
  ```

- Don't use spaces before the `;`.

  Copy Code

  ```css
  /* Legal but not common usage */
  p {
    background-color: orange ;
  }
  
  /* Okay */
  p {
    background-color: orange;
  }
  ```

- The order of properties in each rule is *typically* insignificant; you can use them in any order. However, be mindful of how related shortcuts and long-form items like `margin` and `margin-left` interact; the property listed second will override the first, either wholly or in part.

  Copy Code

  ```css
  p {
      margin: 25px;
      margin-right: 10px;
      /* Partial override: `margin: 25px 10px 25px 25px;` */
  }
  
  blockquote {
      margin-right: 10px;
      margin: 25px;
      /* Complete override: `margin: 25px;` */
  }
  ```

  We order our properties alphabetically to make them easy to find, but you don't have to.

- The order of the rules is significant but depends upon the tricky cascade, specificity, and inheritance rules. List your selectors in functional groups. For instance, put all of the header-specific selectors together, all of the article-specific selectors, etc.--try to keep things grouped by function, and you will probably do fine. If one or more selectors don't seem to work, start looking at the cascade, specificity, and inheritance rules. Linters like stylelint can detect potential problems and save you a great deal of debugging time.

- Avoid using tag selectors (`h1`, `p`, etc.) and ID selectors (`#title`) as much as possible. Note that the specificity rules give tag selectors the lowest priority and ID selectors the highest. Therefore, if you have the following code:

  Copy Code

  ```html
  <h1 class="heading" id="my-heading">Hello</h1>
  ```

  Copy Code

  ```css
  h1 { color: red; }
  #my-heading { color: blue; }
  .heading { color: green; }
  ```

  then the `#my-heading` selector will win out, and the heading will be blue. If you use class selectors as much as possible, you will have fewer specificity issues to worry about.

# Summary

We've started with a bit more hand-holding than we offer throughout most of this course, and we'll continue doing that through most of the next lesson, though we will stop telling you when to validate your code or view the results.

In this lesson, you learned the bare basics of HTML and CSS:

## HTML

- HTML is an acronym for Hypertext Markup Language.
- HTML uses markup to organize your content and give it semantic meaning.
- Elements are the basic building blocks of HTML.
- We use tags in HTML to represent elements.
- Tags may have attributes that add details to the element.
- The Document Type Definition (DTD or DOCTYPE) tells the browser what subset of HTML you intend to use.
- All documents require a DOCTYPE.
- All documents should have `html`, `head`, `title`, and `body` tags, and should also include a `meta` tag that defines the character set. The standard does not require these tags, but always using them will keep you out of trouble.
- HTML attributes `id`, `class`, and `name` assign different kinds of identification information to HTML elements.
- The `p`, `a`, `em`, `strong`, and `h1`..`h6` tags; you should memorize these. You should also be familiar with the `header`, `main`, `article`, `section`, `aside`, `div` and `span` tags, but you don't have to recognize them yet; you will through repeated use, though.
- HTML character entities, and how to use them in place of the literal `<`, `>`, and `&` characters.

## CSS

- CSS is an acronym for Cascading Style Sheets.
- CSS tells your browser how to present content with spacing, colors, sizing, font styles, background images, placement, and much more.
- CSS properties have a name and value.
- CSS rules have a selector that describes what elements to style and a list of zero or more properties that define how the browser should render them.
  - CSS tag selectors select HTML elements by element (tag) name, e.g., `h1`
  - CSS class selectors select HTML elements by class name. The selector consists of a `.` followed by the class name, e.g., `.highlight`.
  - CSS ID selectors select HTML elements by ID name. The selector consists of a `#` followed by the ID, e.g., `#intro`.
  - You can concatenate CSS selectors to make them more specific, e.g., `strong.highlight`.
- CSS has both specificity and inheritance rules that control the notion of the cascade; together, these rules define how CSS rules with different selectors interact.
- CSS font stacks tell the browser which font to use by providing a list of candidate fonts along with an optional "fallback" font family.
- The difference between serif and sans-serif fonts.
- The differences, benefits, and problems with inline, internal, and external CSS.
- How to set text and background colors, font families, and font sizes.