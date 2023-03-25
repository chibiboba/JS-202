# References

[HTML5 Element FLowchart](..\..\..\..\Downloads\h5d-sectioning-flowchart.pdf) 

[HTML Validator](https://validator.w3.org/#validate_by_input)

[CSS Validator](https://jigsaw.w3.org/css-validator/)

[HTML Standard](https://html.spec.whatwg.org/multipage/)

[Dom Standard](https://dom.spec.whatwg.org/)

[Web-safe fonts](http://web.mit.edu/jmorzins/www/fonts.html) 

# Extra to read 

- The article about selectors https://learn.shayhowe.com/advanced-html-css/complex-selectors/

- learn about CSS inheritance when you're ready to learn more.

  - CSS inheritance isn't like class inheritance in an OOP language like Ruby, and, for the most part, is beyond the scope of this course. Don't let the vocabulary confuse you, though. Make a note to read about CSS inheritance when you're ready to learn more.

- Browsers use a serif typeface by default. Serif fonts have flared end-points on most characters; sans-serif do not:

  ![Serif and Non-Serif Fonts](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/serifs-01.png)

  The font you choose is mainly a matter of preference, or rather, the preferences of your designer. Mainstream use today seems to favor serif fonts for headlines and other attention-grabbing items and sans-serif for paragraph-based text.

  [This short but helpful guide](http://web.mit.edu/jmorzins/www/fonts.html) includes information on Web-safe fonts and displays examples of each. You don't have to read it right now, but bookmark it for reference.

# HTML and CSS Validators

Always check your HTML with [W3C's HTML Validator](https://validator.w3.org/#validate_by_input). The validator ensures that your HTML is valid and helps catch potential issues before they become mystifying bugs. You can tell W3C to link directly to a page if you have it online, upload the HTML file from your local filesystem, or copy and paste the HTML to the direct input tab. Most students find that copy and paste is a good solution for this course.

Validate your HTML often:

- after the first draft of your HTML
- after any significant changes to your HTML
- when you're having problems with the way your page renders
- before submitting your HTML for a code review
- before deploying your HTML

[W3C's CSS Validator](https://jigsaw.w3.org/css-validator/#validate_by_input) provides similar functionality for validating CSS. Check your CSS when you validate your HTML, and also when you make significant changes to your CSS.

Don't underestimate the value of validation. It may seem like a pain at times, but validation **will** save you much grief. Small errors in your HTML and CSS can cause confusing and subtle bugs; the validators help you find and fix problems before they become bugs.

# Linters

- **Linters** check computer code for errors, misuse, and style issues. Unlike the W3C validators, linters look at style and usage rather than conformance to standards. The validators find uses of deprecated elements, poor element nesting, and non-standard attributes and properties; linters detect poor indentation and formatting as well as failures to follow best practices.

- You can find linters for most development languages, and HTML is no exception. 

- CSS also has linters, though good ones are a bit difficult to find. Unfortunately, we are no longer able to find one we like. If you find one you like, suggest it via the Feedback button!

CSS liter

- download stylelint locally `npm install stylelint --save-dev`

HTML linter

- install eslint with HTML lint plugin (for git bash)

```yml
# Last update: 05 Oct 2020
root: true
parser: babel-eslint
parserOptions:
  ecmaVersion: 6
  ecmaFeatures:
    impliedStrict: true
env:
  browser: true
  es6: true
  jest: true
  jquery: true
  node: true
extends:
  - eslint:recommended
globals:
  alert: true
  define: true
  document: true
  global: true
  location: true
  require: true
  window: true
  Handlebars: true
rules:
  accessor-pairs: error
  array-callback-return: error
  arrow-spacing: error
  block-scoped-var: error
  brace-style:
    - error
    - 1tbs
    - allowSingleLine: true
  camelcase: error
  complexity: error
  consistent-return: error
  constructor-super: error
  eqeqeq: error
  id-length:
    - error
    - exceptions:
      - _
      - a
      - b
      - x
      - y
      - z
      min: 2
      properties: never
  indent:
    - error
    - 2
    - SwitchCase: 1
  keyword-spacing: error
  linebreak-style: ["error", "windows"]
  max-depth: error
  max-len:
    - error
    - code: 80
      tabWidth: 2
      ignoreRegExpLiterals: false
      ignoreStrings: true
      ignoreTemplateLiterals: true
      ignoreTrailingComments: true
      ignoreUrls: true
  max-lines-per-function:
    - error
    - max: 20
      skipBlankLines: true
      skipComments: true
  max-nested-callbacks:
    - error
    - max: 4
  max-statements:
    - error
    - max: 15
    - ignoreTopLevelFunctions: true
  max-statements-per-line: error
  new-parens: error
  no-array-constructor: error
  no-async-promise-executor: error
  no-bitwise: error
  no-buffer-constructor: error
  no-caller: error
  no-class-assign: error
  no-confusing-arrow:
    - error
    - allowParens: true
  no-console: 'off'
  no-const-assign: error
  no-constant-condition:
    - error
    - checkLoops: false
  no-debugger: 'off'
  no-dupe-class-members: error
  no-duplicate-imports: error
  no-eq-null: error
  no-eval: error
  no-extend-native: error
  no-implicit-globals: error
  no-implied-eval: error
  no-inner-declarations:
    - error
    - both
  no-iterator: error
  no-label-var: error
  no-lonely-if: error
  no-loop-func: error
  no-misleading-character-class: error
  no-mixed-operators: error
  no-multi-assign: error
  no-multi-str: error
  no-multiple-empty-lines: error
  no-nested-ternary: error
  no-new: error
  no-new-func: error
  no-new-object: error
  no-new-require: error
  no-new-symbol: error
  no-new-wrappers: error
  no-octal-escape: error
  no-process-env: error
  no-process-exit: error
  no-prototype-builtins: 'off'
  no-restricted-syntax:
    - error
    - message: Do not use `with` statement.
      selector: WithStatement
  no-return-assign: error
  no-return-await: error
  no-script-url: error
  no-self-assign:
    - error
    - props: true
  no-self-compare: error
  no-sequences: error
  no-shadow-restricted-names: error
  no-tabs: error
  no-template-curly-in-string: error
  no-this-before-super: error
  no-throw-literal: error
  no-trailing-spaces: error
  no-unmodified-loop-condition: error
  no-unneeded-ternary: error
  no-unused-expressions: error
  no-unused-vars:
    - error
    - args: all
      argsIgnorePattern: "^_"
      caughtErrors: all
      caughtErrorsIgnorePattern: "^_"
      vars: local
  no-use-before-define:
    - error
    - functions: false
  no-useless-call: error
  no-useless-catch: error
  no-useless-computed-key: error
  no-useless-rename: error
  no-useless-return: error
  no-with: error
  nonblock-statement-body-position: error
  one-var-declaration-per-line: error
  operator-assignment: error
  prefer-promise-reject-errors: error
  quote-props:
    - error
    - consistent-as-needed
  radix: error
  require-await: error
  require-yield: error
  semi:
    - error
    - always
    - omitLastInOneLineBlock: true
  semi-spacing: error
  semi-style: error
  space-before-blocks: error
  space-infix-ops: error
  space-unary-ops:
    - error
    - words: true
      nonwords: false
  vars-on-top: error
  
env:
  browser: true

plugins:
  - html

parserOptions:
  ecmaVersion: 2020

extends:
  - eslint:recommended
  - plugin:html/recommended
```

# Topics

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

# Tutorial 1

# Difference between HTML and CSS

- *HTML*, HyperText Markup Language, gives content structure and meaning by defining that content as, for example, headings, paragraphs, or images. *CSS*, or Cascading Style Sheets, is a presentation language created to style the appearance of content—using, for example, fonts or colors.
- The two languages—HTML and CSS—are independent of one another and should remain that way. CSS should not be written inside of an HTML document and vice versa. As a rule, HTML will always represent content, and CSS will always represent the appearance of that content.

# Common HTML Terms

## Elements

- **Elements** are designators that define the structure and content of objects within a page. 
  - Elements are identified by the use of less-than and greater-than angle brackets, `< >`, surrounding the element name. Thus, an element will look like the following: `<a>`
- An HTML element includes either:
  - A self-closing tag
  - An opening tag and its corresponding closing tab, including everything between the two. The content may need nested elements.
- https://developer.mozilla.org/en-US/docs/Web/HTML/Element

#### Common elements

- **Paragraphs** are the primary organizational construct for text on web pages. (identified as the `<p>` element):
  - The `p` element provides the ability to define paragraphs; it wraps a single paragraph and displays it in a separate area below the previous content, along with a bit of vertical spacing above and below it for visual distinctiveness:
- **Anchors** represent links to other pages. `<a>`
  - `<a href=""> the text </a>`

- **Headings** occur on most pages. (identified as `<h1>` through `<h6>` elements)
- The list goes on to include the `<a>`, `<div>`, `<span>`, `<strong>`, and `<em>` elements, and many more. `<a>`

#### Anchor is Hyperlink

- HTML uses the term **anchor** to refer to hyperlinks, and it uses the `a` element to code anchors. The `a` element requires a URL for the link, and some content that the browser can display as a clickable item. The `<a>` tag uses the `href` attribute to designate the link URL, and the link description goes between the open and close tags:

- This is an example of an anchor link.
  - The anchor element is declared with the opening `<a>` and closing `</a>` tags encompassing the text, and the hyperlink reference attribute and value are declared with `href="http://shayhowe.com"` in the opening tag.
  - HTML syntax outline including an element, attribute, and tag:


![image-20230313153739933](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313153739933.png)



#### Other Elements

- The external style sheet `stylesheet` is identified with a `<link>` tag which tells the browser it should load CSS style information from an external file located on the server. The `link` tag belongs inside the `<head>...</head>` element.

- Text-based elements & elements for building structure.
- `<div` and `<span>` are generic containers.

- Void element

  - Empty/ void element

  - Chatgpt: Anchor elements in HTML are defined using the `<a>` tag, which is an example of an empty element or a void element. This means that the `<a>` tag doesn't have a closing tag, and it doesn't contain any content or child elements.

  - In HTML, the `>` character is used to denote the end of a tag, so it's not necessary to include it after the opening `<a>` tag. For example, the correct syntax for creating a hyperlink using an anchor element is:

```html
<a href="something.com">Click here</a>
```

- `<ol`: ordered list element
  - The [**`<ol>`**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) HTML element represents an ordered list of items — typically rendered as a numbered list.

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230316171019050.png" alt="image-20230316171019050" style="zoom:50%;" />

- `<ul>` unordered list element

  No bullets

  ```css
  ul {
  	list-style: none;
  	padding-left: 0;
  }
  ```

## Tags

- An HTML tag begins with `<` and ends with `>` and contains an element name inside the angle brackets.

- The use of less-than and greater-than angle brackets surrounding an element creates what is known as a *tag*. Tags most commonly occur in pairs of opening and closing tags.

#### There are 3 types of tags

- An **opening tag** marks the beginning of an element. It consists of a less-than sign followed by an element’s name, and then ends with a greater-than sign;
  - for example, `<p>` or `<a>` 
- A **closing tag** marks the end of an element. It consists of a less-than sign followed by a forward slash and the element’s name, and then ends with a greater-than sign
  - For example, `</div>`, `</p>` or `</a>`.

  - The content that falls between the opening and closing tags is the **content** of that element. 

  - The closing tag is defined for most, but not all, elements.

- A **self closing tag**  -- tags that don't have content. Most tags are not self closing. 
  - Chatgpt: ``<br>` or, incorrectly, `<br />`` tag is an empty tag that creates a line break in the content, but doesn't have any content of its own, so it is self closing. 
  - `<link>` is another example of a self closing tag that is used to link external stylesheets.


Anchor Link

- An **anchor link**, for example, will have an opening tag of `<a>` and a closing tag of `</a>`. What falls between these two tags will be the content of the anchor link.

  - So, anchor tags will look a bit like this:

  ```html
  <a>...</a>
  ```

## Attributes

- **Attributes** are properties used to provide additional information about an element. They are ways to identify certain elements. 
- Launch school focuses on these 3 attributes: 

  - `classes`
  - `id`
  - `name`
- The most common attributes include 

  - `id` attribute: which identifies an element
  - `class` attribute: which classifies an element
  - `src` attribute: which specifies a source for embeddable content
  - `href` attribute: which provides a hyperlink reference to a linked resource.
  - `rel` attribute: defines the relationship between a linked resource and the current document. 

- Attributes are defined within the opening tag, after an element’s name. Generally attributes include a name and a value. The format for these attributes consists of the attribute name followed by an equals sign and then a quoted attribute value. 

  - For example, an `<a>` anchor element including an `href` attribute would look like the following:

  ```html
  <a href="http://shayhowe.com/">Shay Howe</a>
  ```

- Note: when defining attribute for an element don't "close the first tag" right away.  

#### Classes

- The `class` attribute identifies a set of page elements that you wish to style consistently. 
  - The `class` attribute identifies a group of elements that have something in common. Elements that have the same name in the `class` attribute belong to the same class. Any tag can belong to one or more classes, and each class may apply to multiple tags.
- For instance, if you want to display a list of students, but highlight students who serve as Teaching Assistants, you can apply a class of `teaching-assistant` to each TA's data:

html

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

css

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

<u>Rules regarding`class` attribute</u>

- Use the `class` attribute to assign a class or classes to an element.
- Any number of elements may belong to the same class.
- Any element can belong to one or more classes. List all the names separated by spaces in the `class` attribute, e.g., `class="executive management full-time"`.
- Prefer semantic class names; they should provide meaning. For instance, use `teaching-assistant` rather than `yellow-background`.
- Use CSS class selectors (`.classname`) to select elements by class, e.g., `.teaching-assistant`.
- Class selectors have lower CSS specificity than ID selectors, but higher than tag name selectors. Thus, the `.teaching-assistant` selector overrides the `tr` selector. See [Getting to Know CSS](https://learn.shayhowe.com/html-css/getting-to-know-css/#cascade).

#### IDs

- The `id` attribute applies a unique identification string to a single element, such as a headline. 
- `id` attributes **must be unique on the page**: no two elements can have an `id` attribute with the same value.

```html
<h1>This is a plain h1 heading</h1>
<h1 id="headline">This is my headline</h1>
```

You can now give the headline some styling that is unique to it:

```css
#headline {
  color: red;
  font-size: 48px;
}
```



![Headline Example](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/headline-01.png)

<u>Rules regarding `id` attribute</u>

- Use the `id` attribute to assign an ID to an element.
- `id` attributes **must be unique on the page**: no two elements can have an `id` attribute with the same value.
- Each element can have one ID or none.
- Use semantic ID names; they should provide meaning. For instance, use an ID name of `headline` rather than `big-font`.
- Use CSS ID selectors (`#idname`) to select elements by ID, e.g., `#headline`.
- ID selectors have higher CSS specificity than class selectors (an ID selector can override a class selector). 

<u>ID vs Class attribute</u>

- In general, you should use the `class` attribute when you want to group elements together based on their shared characteristics or styles, and use the `id` attribute when you want to target a specific element for styling or manipulation with JavaScript.

<u>Debugging: ID duplication</u>

- The browser won't tell you when you use the same ID on more than one element. 

- In fact, it may even apply your styles to several tags with the same ID. You will run into problems with JavaScript, though, if you try to take advantage of this behavior. 

- Use the W3C HTML validator to catch accidental ID duplication.

- Note: Use CSS ID selectors sparingly, this will help avoid issues in the CSS. 

<u>Recommendation</u>

- Some developers argue that you should never use ID selectors in your CSS, and there are good arguments for this. However, the arguments on the other side balance them out.
- Feel free to use ID selectors here at Launch School. However, we recommend using them sparingly - that will help avoid specificity issues in your CSS.

#### Names

- The `name` attribute is that it ties **form** elements to data on the server - it typically doesn't play a role in styling. 
- You can use the `[name="field-name"]` selector to select elements by name, but you should use a class or ID selector instead. 

When you submit a form, the browser sends the form data to the server using name/value pairs in which each name comes from the associated `name` attribute. 

For instance:

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

`name` attribute rules

- Use the `name` attribute to assign a name to a form data element that the server can use to obtain the value.
- Not all tags accept the `name` attribute; it applies to input controls in forms. Some other elements have a `name` attribute, too, but with a different meaning.
- Always use a `name` attribute on form elements that accept it.
- Each name in a form should be unique to that form except for radio buttons and checkboxes that belong to a single group.
- Use descriptive `name` values, not semantic. For instance, use `name="last-name"` instead of `name="input-field"`.
- Avoid trying to select elements in CSS by using the `name` attribute.

#### Referencing css

- `<link>` is used to specify the relationship between the current document and external resource, most commonly used to link to external stylesheets.

  - elements work with the attributes `href` (the URL of the resource), `rel` (the relationship between the current document and the linked resource), and `type` (the MIME type of the linked resource).

- `target` attribute: used when there are multiple possible targets for the ending resource, such as when the parent document is embedded within an HTML document.

  | Value         | `_self` | `_parent` | `_top` | `_blank` | `<XML-Name>` |
  | :------------ | ------------------------------------------------------ |
  | Default value | `_self`                                                |
  | Animatable    | Yes                                                    |

# Ambiguity

### Tags vs Elements

- We may refer to tags and elements with or without angle brackets, so long as the usage is unambiguous. For instance, we may talk of the `<p>` tag as the `p` tag, but we may also say `p` elemnt instead of `<p>...<p>` element. 
- We may sometimes abbreviate that even further and say `p` without saying whether we are talking about a tag or element. The writing style is merely convenience, though: you must use angle brackets when coding HTML.

### Attributes

For instance:

```html
<a href="another_page.html">Next page</a>
```

- In this code, `href` is an attribute of the `<a>` tag, and it has the value `another_page.html`. You may use either double quotes, as shown above, or single quotes:

```html
<a href='another_page.html'>Next page</a>
```

- You may even omit the quotes in some cases, which is handy in machine-generated HTML, but most style guides don't recommend this. You should use double quotes when possible.

- Later, we'll introduce **boolean attributes**; they don't need an `=` or a value.

- Every HTML element may contain one or more attributes or none at all. Some, such as `class`, which we'll talk about soon, are global; you can use them anywhere. However, most are specific to individual tags.

Debugging difficulty

- Note that browsers do not check whether your attributes are valid: they ignore them, which can make debugging difficult.

# Setting up HTML document structure

- HTML documents are saved with .html file extension rather than a .txt file extension.
- Two of the more popular plain text editors for writing HTML and CSS are Dreamweaver and Sublime Text. Free alternatives also include Notepad++ for Windows and TextWrangler for Mac.
- All HTML documents have a required structure that includes the following declaration and elements: `<!DOCTYPE html>`, `<html>`, `<head>`, and `<body>`.

### HTML Skeleton

- **boilerplate code** or just **boilerplate** are sections of code that are repeated in multiple places with little to no variation.
- A **boilerplate** in HTML is a template you will add at the start of your project. You should add this boilerplate to all of your HTML pages.
- In vs code, type !, then hit `tab` key for a skeleton. 

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

### Declaration and Elements

- HTML pages typically require these 4 items. 

`<!DOCTYPE html>`

- The document type declaration, or `<!DOCTYPE html>`, informs web browsers which version of HTML is being used and is placed at the very beginning of the HTML document.
- Requirement: It is required at the very beginning of an html file, otherwise the browser won't see the file as a doctype. 
- This is a **Document Type Definition**, aka, **DTD**, or **DOCTYPE**. Officially the DOCTYPE isn't part of HTML so it isn't a tag or element. It's a message that tells browser what specific markup language to expect -- for example, XML.
- Because we’ll be using the latest version of HTML, our document type declaration is simply `<!DOCTYPE html>`, which uses HTML5. We will use this version the most often unless we're writing for older browsers or an XML or XHTML application.

Side notes

- Casing: Some developers use lowercase instead (`<!doctype ...>`); you must use uppercase when defining versions of HTML before HTML5 or non-HTML languages such as XML. HTML5 doesn't care whether you use uppercase or lowercase, so some developers are moving to the lowercase form. You may use either style at Launch School.
- HTML5 doesn't have DTD but rather refers to document type items as a DOCTYPE. HTML3 and HTML4 do though.

`<html>` element

- The `html` element encloses the entire HTML document. 
- The `lang="en"` attribute informs the user's browser that the web page uses the English language for text. 
- Everything else about the page, both its content and related meta-information, must be between the opening and closing `html` tags.

`<head>` element

- The `head` element encloses the document header, which consists of elements that provide additional information (meta-information) to the browser. 
- The browser doesn't necessarily display meta-information in the page content area. 
  - Here, the `title` gives the page a title, while `<meta charset="utf-8">` tells the browser to expect the UTF-8 character encoding (most web pages use this encoding). 
  - Most browsers display the title in the title bar or tab, so be sure you always provide a `title` element for a web page.
  - There may be links to any external files, or any other beneficial metadata.
- Requirement: The standards allow the developer to omit the `<head>` and `<meta charset="utf-8">` elements, but you *should* use both as a matter of best practice.

`<body>` element

- All of the visible content within the web page will fall within the `<body>` element. 
  - The `body` element is the content area of the page. The browser renders the HTML inside the `body` in the browser content area.
  - Most editors have a shortcut to display a file in a browser, and most browsers provide a File, Open File menu item that does the same.
- `<article>` `<section>` `<header>` should all be here

### Indentation

- Note that we add two spaces of indentation after each open tag, then remove two when closing it. Developers often use this style when writing HTML from scratch - the indentation helps show the structure of your document and makes it easier to read and edit. 

- Self-closing tags (like `<meta>`) do not alter the indentation. 
- It's also common to omit the indentation for the `head` and `body` elements; align them both with the `html` element if you prefer:

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

### Self closing elements

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

### Code Validation

- No matter how careful we are when writing our code, we will inevitably make mistakes. Thankfully, when writing HTML and CSS we have validators to check our work. The W3C has built both [HTML](http://validator.w3.org/) and [CSS](http://jigsaw.w3.org/css-validator/) validators that will scan code for mistakes. Validating our code not only helps it render properly across all browsers, but also helps teach us the best practices for writing code.

### Tutorial: typical html structure



# Tutorial 2: HTML semantics

[Getting to Know HTML](https://learn.shayhowe.com/html-css/getting-to-know-html/) discusses some basic HTML concepts, notably semantics, headings, paragraphs, simple HTML-based styling, and the general structure of an HTML document. It also examines hyperlinks and URLs.

## What are semantics

- How to choose a semantic tag
  - Flow chart to help with HTML semantics: [excellent flowchart](http://html5doctor.com/downloads/h5d-sectioning-flowchart.pdf)
  - Consider the context and intent when trying to choose a semantic tag.

- So what exactly are semantics?
  - [Semantics within HTML](http://boagworld.com/dev/semantic-code-what-why-how/) is the practice of giving content on the page meaning and structure by using the proper element. Semantic code describes the **value** of content on a page, regardless of the style or appearance of that content. 
  - There are several benefits to using semantic elements, including enabling computers, screen readers, search engines, and other devices to adequately read and understand the content on a web page. Additionally, semantic HTML is easier to manage and work with, as it shows clearly what each piece of content is about.

- Which elements are semantic?
  - In HTML5, all content tags except `<div>` and `<span>` have semantic meaning. In particular, both `<b>` and `<i>` have [semantic meaning](http://html5doctor.com/i-b-em-strong-element/). 
  - Some developers may tell you otherwise, but that's a holdover from HTML4, in which both elements are non-semantic. 
  - Note, though, that the semantic meanings of `<b>` and `<i>` in HTML5 are somewhat subtle. Avoid using them solely for stylistic purposes, and be sure you understand when they are appropriate.
- Using elements/tags semantically
  - Use HTML tags semantically - each tag name should describe the type of information you intend to display. A header needs an `h1`, `h2`, etc. tag; a paragraph needs a `p` tag; a link needs an `a` tag. Don't use a `p` tag to render a small header; use one of the `h#` headers instead, and adjust the appearance as needed with CSS.

## Identifying Divisions and Spans

- Divisions or `<div>`s and `<span>`s are two HTML elements that act as generic containers for styling purposes only. They don't hold any semantic value.
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
  - **Spacing**: Remember that with in-line elements just like `<strong>` and `<a>` does, they respect white spaces around the character and in between then. And the white space collapses to a single white space character. So multiple space characters would render as one space character.
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

# Using Text-based Elements

Many different forms of media and content exist online; however, text is predominant. Accordingly, there are a number of different elements for displaying text on a web page. For now we’ll focus on the more popular elements, including headings, paragraphs, bold text to show importance, and italics for emphasis. Later, within Lesson 6, “[Working with Typography](https://learn.shayhowe.com/html-css/working-with-typography/),” we’ll take a closer look at how to style text.

### Headings

- Headings are block-level elements, and they come in six different rankings, `<h1>` through `<h6>`, representing different fonts for the headings. 
  - Headings help to quickly break up content and establish hierarchy, and they are key identifiers for users reading a page. 

  - They also help search engines to index and determine the content on a page.

  - Each heading has some vertical spacing above and below to separate it from the surrounding content.

- Headings should be used in an order that is relevant to the content of a page. 
  - The primary heading of a page or section should be marked up with an `<h1>` element, and subsequent headings should use `<h2>`, `<h3>`, `<h4>`, `<h5>`, and `<h6>` elements as necessary.

- Use heading levels semantically. 
  - Don't use `h1`, `h2`, etc. solely because you want to change font sizes. 
  - The numbered heading elements have semantic meaning; using them for their font sizes makes it harder for search engines and assistive technologies to understand your code and present it in a useful format. Misusing HTML for its stylistic effects also makes it hard for other developers to understand your code.


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

### Paragraphs

- Headings are often followed by supporting paragraphs. 
- Paragraphs are defined using the `<p>` block-level element. Paragraphs can appear one after the other, adding information to a page as desired. Here is an example of how to set up paragraphs.

```html
<p>Steve Jobs was a co-founder and longtime chief executive officer at Apple. On June 12, 2005, Steve gave the commencement address at Stanford University.</p>

<p>In his address Steve urged graduates to follow their dreams and, despite any setbacks, to never give up&ndash;advice which he sincerely took to heart.</p>
```

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313200005228.png" alt="image-20230313200005228" style="zoom:50%;" />

### Formatting Text

- Elements we can use to format text. 
  - Most change how the content looks and also change the semantic meaning. 
  - Here are useful formatting elements to use inside "container" elements like paragraph and heading elements. 

| Element | Description                                                  |
| :------ | :----------------------------------------------------------- |
| strong  | The text has greater importance than the surrounding text; most browsers use boldface. Example: You **must** remember to turn the light off. |
| em      | Adds emphasis to the text; most browsers use italics. Example: We do them because they are *hard*! |
| b       | Stylistically offset text, such as keywords. Example: ES6 adds the keywords **const** and **let**. |
| i       | Alternate voice text. Example: I said "Hello." She said *"Goodbye."* |

- Note: all of the above are semantic elements.
- Before HTML5, the `b` and `i` elements were non-semantic elements that provided boldface and italic text, respectively. As of HTML5, `b` and `i` are semantic elements, and the meaning has changed. 
  - If you intend to use boldface for important text, use `<strong>` instead of `<b>`
  - if you wish to use italics for emphasis, use `<em>` instead of `<i>`.

### Bold Text with Strong

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

### Italicize Text with Emphasis

- To italicize text, thereby placing emphasis on it, we’ll use the `<em>` inline-level element. As with the elements for bold text, there are two different elements that will italicize text, each with a slightly different semantic meaning.

  - The `<em>` element is used semantically to place a **stressed emphasis** on text; it is thus the most popular option for italicizing text. 

  - The other option, the `<i>` element, is used semantically to convey text in an *a**lternative voice or tone***, almost as if it were placed in quotation marks. 

- Again, we will need to gauge the significance of the text we want to italicize and choose an element accordingly.

- Note: (chatgpt) Both "font-style: italic" and "<em>" in HTML can be used to indicate emphasized text and display it in italics. However, it is generally recommended to use the semantic HTML tag "<em>" to indicate emphasis, as it carries meaning beyond just changing the font style. Using semantic HTML helps improve the accessibility and structure of the document for both humans and machines.

Here’s the HTML code for italicizing:

```html
<!-- Stressed emphasis -->
<p>I <em>love</em> Chicago!</p>

<!-- Alternative voice or tone -->
<p>The name <i>Shay</i> means a gift.</p>
```

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230313200126714.png" alt="image-20230313200126714" style="zoom:50%;" />

These text-level elements are quite handy for bringing our content to life. In addition to these, there are structurally based elements. 

# Example of html structure

- [Flowchart](file:///C:/Users/jenny/Downloads/h5d-sectioning-flowchart.pdf)

  

# Structural Elements

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

### Header

- The `<header>` element, like it sounds, is used to identify the top of a page, article, section, or other segment of a page. It provides semantic meaning to the elements it contains.
- In general, the `<header>` element may include a heading, introductory text, and even navigation.
- You should use `header` consistently with any part of your page that you think of either a page header or a section header.

```html
<header>
  <h1>Heading</h1>
  <p>Introductory text</p>
  <nav>Major Navigation</nav>
</header>
```

<u>`<header>` vs. `<head>` vs. `<h1>` through `<h6>` Elements</u>

- It is easy to confuse the `<header>` element with the `<head>` element or the **heading elements**, `<h1>` through `<h6>`. They all have different semantic meanings and should be used according to their meanings. For reference.

- The `<header>` element is a structural element that outlines the heading of a segment of a page. It falls within the `<body>` element.

- The `<head>` element is not displayed on a page and is used to outline metadata, including the document title, and links to external files. It falls directly within the `<html>` element.

- **Heading** elements, `<h1>` through `<h6>`, are used to designate multiple levels of text headings throughout a page.

### Navigation

- The `<nav>` element identifies a section of *major* navigational links on a page. 
  - The `<nav>` element should be reserved for primary navigation sections only, such as global navigation, a table of contents, previous/next links, or other noteworthy groups of navigational links.
  - Most commonly, links included within the `<nav>` element will link to other pages within the same website or to parts of the same web page. 

- Miscellaneous one-off links should not be wrapped within the `<nav>` element; they should use the anchor element, `<a>`, and the anchor element alone.

```html
<nav>...</nav>
```

### Article

- The `<article>` element is used to identify a section of independent, self-contained content that may be independently distributed or reused. 
  - We’ll often use the `<article>` element to mark up blog posts, newspaper articles, user-submitted content, and the like.

- When deciding whether to use the `<article>` element, we must determine if the content within the element could be replicated elsewhere without any confusion. 
  - If the content within the `<article>` element were removed from the context of the page and placed, for example, within an email or printed work, that content should still make sense.

```html
<article>...</article>  
```

### Section

- `<section>` is also a block level element that represents a generic standalone section of document, which doesn't have a more specific semantic element to represent it. Sections should always a heading, with very few exceptions.
- The `<section>` is part of the main document flow to identify a group of content, but is not a standalone block like an `article`. 
- The `<section>` element is commonly used to break up and provide hierarchy to a page.

```html
<section>...</section>
```

### Deciding Between `<article>`, `<section>`, or `<div>` Elements

- At times it becomes fairly difficult to decide which element—`<article>`, `<section>`, or `<div>`—is the best element for the job based on its semantic meaning. The trick here, as with every semantic decision, is to look at the content.

- Both the `<article>` and `<section>` elements contribute to a document’s structure and help to outline a document. If the content is being grouped solely for styling purposes and doesn’t provide value to the outline of a document, use the `<div>` element.

- If the content adds to the document outline and it can be independently redistributed or syndicated, use the `<article>` element.

- If the content adds to the document outline and represents a thematic group of content, use the `<section>` element.

### Aside

- The `<aside>` element holds content, such as sidebars, inserts, or brief explanations, that is tangentially related to the content surrounding it. 
  - When used within an `<article>` element, for example, the `<aside>` element may identify content related to the author of the article.
- We may instinctively think of an `<aside>` element as an element that appears off to the left or right side of a page. 

- We have to remember that all of the structural elements including `<aside>` are block-level elements so they will appear on a new line, occupying the full available width of their parent element(the element they are nested in), or the full width of the page. 

```html
<aside>...</aside>
```

- We’ll discuss how to change the position of an element, perhaps placing it to the right or left of a group of content, in Lesson 5, “[Positioning Content](https://learn.shayhowe.com/html-css/positioning-content/).”

### Footer

- The `<footer>` element identifies the closing or end of a page, article, section, or other segment of a page. 
  - Generally the `<footer>` element is found at the bottom of its parent. 
  - Content within the `<footer>` element should be relative information and should not diverge from the document or section it is included within.

```html
<footer>...</footer>
```

With structural elements and text-based elements under our belts, our HTML knowledge is really starting to come together. Now is a good time to revisit our Styles Conference website and see if we can provide it with a little better structure.

### Encoding Special Characters

- Special characters include various punctuation marks, accented letters, and symbols. When typed directly into HTML, they can be misunderstood or mistaken for the wrong character; thus they need to be encoded.
- All **character entities** (encoded character) follow the pattern of an ampersand (`&`) followed by one or more alphanumeric characters terminated by a semicolon (`;`). 
  - All have numeric versions, and most have alphanumeric names, e.g., `&#38` also represents an ampersand (`&amp`); you should use the alphanumeric name when you can, though.

Debug

- Your browser won't complain if you leave a bare `<`, `>`, or `&` in your HTML. Neither will W3C validator. You won't know that you forgot to use an entity until it causes a problem on your page. 

Examples

- For example, we would encode the word “resumé” as `resumé`. Within our header we have encoded both en and em dashes, and within our footer we have encoded the copyright symbol. For reference, a long list of character encodings may be found at [Copy Paste Character](http://copypastecharacter.com/).

- For example `<`'s character entity is `&lt;` and `>`'s character entity is `&gt;`. 

Replacing Ampersand with special entity

- HTML5 handles ampersands as regular characters in most cases, but if that `&` includes some non-whitespace characters between it and the next semicolon (`;`), the browser may try to interpret it as an entity. 
- For safety, most developers replace `&` with `&amp` even when they don't need to do so:

Entities for other special characters

- You must use `&quot` if you need to embed a double quote inside a double-quoted attribute value. 

```html
<img src="hello-world.jpg" alt="Greetings: &quot;Hello, World&quot;">
```

- It's also common practice to replace `"` with `&quot;` when using an external source of strings inside your HTML; since you can't know in advance which strings will need `&quot;` and which won't, you use `&quot;` everywhere.

### Other elements for building structure

#### `<blockquote>`

- Extended quotations should use `<blockquote>`
  - Wrap the entire `<blockquote>` in an article `<article>`. 

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

#### `<address>`

#### `<main>` 

- The **`<main>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents the dominant content of the `<body>`of a document.
  - `<main>` can be the master container.
  - The main content area consists of content that is directly related to or expands upon the central topic of a document, or the central functionality of an application.

# Creating Hyperlinks

- HTML uses the term **anchor** to refer to hyperlinks, and it uses the `a` element to code anchors. The `a` element requires a URL for the link, and some content that the browser can display as a clickable item. The `<a>` tag uses the `href` attribute to designate the link URL, and the link description goes between the open and close tags:

------

Along with text, one of the core components of the Internet is the hyperlink

- Hyperlink provides the ability to link from one web page or resource to another.
- Hyperlinks are established using the **anchor**, `<a>`, inline-level element. 
- In order to create a link from one page (or resource) to another, the `href` attribute, known as a hyperlink reference, is required. The `href` attribute value identifies the destination of the link.

For example, clicking the text “Shay,” which is wrapped inside the anchor element with the `href` attribute value of `http://shayhowe.com`, will take users to my website.

```html
<a href="http://shayhowe.com">Shay</a>
```

### Creating Hyperlinks Demo

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314144941968.png" alt="image-20230314144941968" style="zoom:33%;" />

### Wrapping Block-Level Elements with Anchors

- By nature the anchor element, `<a>`, is an inline element, and, according to web standards, inline-level elements may not wrap block-level elements. 

- With the introduction of HTML5, however, anchor elements specifically have permission to wrap either block-, inline-, or any other level elements. This is a break from the standard convention, but it’s permissible in order to enable entire blocks of content on a page to become links.

### Relative & Absolute Paths

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

### Linking to an Email Address

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

### Opening Links in a New Window

One feature available with hyperlinks is the ability to determine where a link opens when clicked. Typically, links open in the same window from which they are clicked; however, links may also be opened in new windows.

- `target` attribute: used when there are multiple possible targets for the ending resource, such as when the parent document is embedded within an HTML document.

  - Value `_blank` means a new un-named window or tab is requested for the display of the linked content.
  - For example this causes the link to open in a new tab or window.

  ```html
  <a href="https://example.com" target="_blank">Example</a>
  ```

  - Where as this allows the browser to replace the current page with the linked page.

  ```html
  <a href="https://example.com">Example</a>
  ```

### Linking to Parts of the Same Page

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

# Common CSS Terms

## Selectors

- In CSS our rule set begins with the **selector**, which is immediately followed by curly brackets. Within these curly brackets are declarations consisting of property and value pairs. Each declaration begins with a **property**, which is followed by a colon, the **property value**, and finally a semicolon.
- It is a common practice to indent property and value pairs within the curly brackets. As with HTML, these indentations help keep our code organized and legible.

![CSS Syntax Outline](https://learn.shayhowe.com/assets/images/courses/html-css/building-your-first-web-page/css-syntax-outline.png)

- Selectors are extremely powerful, and the selectors outlined here are the most common selectors we’ll come across. These selectors are also only the beginning. Many more [advanced selectors](https://learn.shayhowe.com/advanced-html-css/complex-selectors/) exist and are readily available. When you feel comfortable with these selectors, don’t be afraid to look into some of the more advanced selectors.

## Basic Selectors

- MDN: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors
  
- Practice: https://flukeout.github.io/
  
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

#### Type Selectors

- Type selectors target elements by their element type. 

Example

- For example, should we wish to target all division elements, `<div>`, we would use a type selector of `div`. 

- The following code shows a type selector for division elements as well as the corresponding HTML it selects.

CSS

```cs
div { ... }
```

The HTML it selects.

```html
<div>...</div>          
<div>...</div>
```

- We use the `body` selector to apply the CSS to most elements on the page.

#### Class Selectors

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

#### ID Selectors

- Note: Use ID selectors sparingly, this will help avoid issues like duplicate IDs in the CSS. 

- **ID selectors** are even more precise than class selectors, as they target only one unique element at a time. 

- ID selectors use an element’s `id` attribute value as a selector, just like how class selectors use an element’s `class` attribute value as the selector. 

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

#### Universal Selector

- **Universal Selector**
  - `A *` : all elements in A.
  - `*`

#### Attribute Selector

- Select all elements that have a specific attribute

- `[attribute]`

- Attributes appear inside the opening tag of an element, like this: span attribute="value". An attribute does not always have a value, it can be blank!

- Examples

  - [class] is not a specific attribute.

  - a[href] selects all a elements that have a href="anything" attribute

  - [type] selects all elements that have a type="anything". attribute

- Combine the attribute selector with another selector (like the tag name selector) by adding it to the end.

  - a[href] selects all a elements that have a href="anything" attribute.

| Example                        | Classification                 | Explanation                                                  |
| :----------------------------- | :----------------------------- | :----------------------------------------------------------- |
| `a[target]`                    | Attribute Present Selector     | Selects an element if the given attribute is present         |
| `a[href="http://google.com/"]` | Attribute Equals Selector      | Selects an element if the given attribute value exactly matches the value stated |
| `a[href*="login"]`             | Attribute Contains Selector    | Selects an element if the given attribute value contains at least once instance of the value stated |
| `a[href^="https://"]`          | Attribute Begins With Selector | Selects an element if the given attribute value begins with the value stated |
| `a[href$=".pdf"]`              | Attribute Ends With Selector   | Selects an element if the given attribute value ends with the value stated |
| `a[rel~="tag"]`                | Attribute Spaced Selector      | Selects an element if the given attribute value is whitespace-separated with one word being exactly as stated |
| `a[lang|="en"]`                | Attribute Hyphenated Selector  | Selects an element if the given attribute value is hyphen-separated and begins with the word stated |

- **Attribute Value Selector**
  - Select all elements that have a specific attribute value `[attribute = "value"]`
  - Attribute selectors are case sensitive, each character must match exactly.
  - input[type="checkbox"] selects all checkbox input elements.
- **Attribute begins with selector** 
  - `[attribute^="value"]`
  - Select all elements with an attribute value that starts with specific characters
- **Attribute Ends with Selector** 
  - `[attribute$="value"]`
  - Select all elements with an attribute value that ends with specific characters
- **Attribute Wildcard Selector**
  - `[attribute*="value"]`
  - A useful selector if you can identify a common pattern in things like `class`, `href` or `src` attributes.

## Grouping Selectors

#### Selector list

- **Selector list** `,` 
  - The CSS **selector list** (`,`) selects all the matching nodes. A selector list is a comma-separated list of selectors.
  - You can combine any selectors this way, and you can specify more than two.
  - p, .fun selects all p elements as well as all elements with class="fun"

## Combinators

#### Descendant & Child Combinator

| Example       | Classification        | Explanation                                                  |
| :------------ | :-------------------- | :----------------------------------------------------------- |
| `article h2`  | Descendant Selector   | Selects an element that resides anywhere within an identified ancestor element |
| `article > p` | Direct Child Selector | Selects an element that resides immediately inside an identified parent element |

- **Descendant selector** matches every element that follows an identified ancestor. The descendant element does not have to come directly after the ancestor element inside the document tree but may fall anywhere within the ancestor element. 

  - The `article h2` selector is a descendant selector, only selecting `h2` elements that fall inside of an `article` element. 

- **Child Combinator** / **child selector**(`>`) is placed between two CSS selectors. It matches only those elements matched by the second selector that are **direct children** of elements matched by the first.

  - Every element except the html element is a **direct child** of precisely one other element. For example:

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

  - The last li element is not a direct child of the ol.
  - `ul li` tells the browser to select all `li` elements that are a **descendant** of a `ul`, no matter how deeply nested the `li` elements are. By changing that to `ul > li`, we tell the browser that we want direct children of `ul`; nothing else.

#### Sibling Combinator

| Example  | Classification            | Explanation                                                  |
| :------- | :------------------------ | :----------------------------------------------------------- |
| `h2 ~ p` | General Sibling Selector  | Selects an element that follows anywhere after the prior element, in which both elements share the same parent |
| `h2 + p` | Adjacent Sibling Selector | Selects an element that follows directly after the prior element, in which both elements share the same parent |

- **General Sibling Selector `A ~ B`**
  - You can select all siblings of an element that follow it. This is like the Adjacent Selector (A + B) except it gets all of the following elements instead of one.
- **Adjacent sibling selector**
  - Elements that follow one another are called siblings. They're on the same level, or depth. The **adjacent sibling combinator** (`+`) separates two selectors and matches the second element only if it *immediately* follows the first element, and both are children of the same parent [`element`](https://developer.mozilla.org/en-US/docs/Web/API/Element).

## Pseudo-classes and Pseudo-elements

#### Pseudo-Classes

- A [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **pseudo-class** is a keyword added to a selector that specifies a special state of the selected element(s). 

| Example                    | Classification                     | Explanation                                                  |
| :------------------------- | :--------------------------------- | :----------------------------------------------------------- |
| `a:link`                   | Link Pseudo-class                  | Selects a link that has not been visited by a user           |
| `a:visited`                | Link Pseudo-class                  | Selects a link that has been visited by a user               |
| `a:hover`                  | Action Pseudo-class                | Selects an element when a user has hovered their cursor over it |
| `a:active`                 | Action Pseudo-class                | Selects an element when a user has engaged it                |
| `a:focus`                  | Action Pseudo-class                | Selects an element when a user has made it their focus point |
| `:fullscreen`              | Element display state pseudo-class | These pseudo-classes enable the selection of elements based on their display states. |
| `:fullscreen`              | Element display state pseudo-class | Matches an element that is currently in fullscreen mode.     |
| `input:enabled`            | State Pseudo-class                 | Selects an element in the default enabled state              |
| `input:disabled`           | State Pseudo-class                 | Selects an element in the disabled state, by way of the disabled attribute |
| `input:checked`            | State Pseudo-class                 | Selects a checkbox or radio button that has been checked     |
| `input:indeterminate`      | State Pseudo-class                 | Selects a checkbox or radio button that neither been checked or unchecked, leaving it in an indeterminate state |
| `li:first-child`           | Structural Pseudo-class            | Selects an element that is the first within a parent         |
| `li:last-child`            | Structural Pseudo-class            | Selects an element that is the last within a parent          |
| `div:only-child`           | Structural Pseudo-class            | Selects an element that is the only element within a parent  |
| `p:first-of-type`          | Structural Pseudo-class            | Selects an element that is the first of its type within a parent |
| `p:last-of-type`           | Structural Pseudo-class            | Selects an element that is the last of its type within a parent |
| `img:only-of-type`         | Structural Pseudo-class            | Selects an element that is the only of its type within a parent |
| `li:nth-child(2n+3)`       | Structural Pseudo-class            | Selects an element that matches the given number or expression, counting all elements from the beginning of the document tree |
| `li:nth-last-child(3n+2)`  | Structural Pseudo-class            | Selects an element that matches the given number or expression, counting all elements from the end of the document tree |
| `p:nth-of-type(3n)`        | Structural Pseudo-class            | Selects every nth element, counting only elements of its type from the beginning of the document tree |
| `p:nth-last-of-type(2n+1)` | Structural Pseudo-class            | The nth-of-type formula selects every nth element, starting the count at a specific instance of that element. |
| `section:target`           | Target Pseudo-class                | Selects an element whose ID attribute value matches that of the URI fragment identifier |
| `div:empty`                | Empty Pseudo-class                 | Selects an element that does not contain any children or text nodes |
| `div:not(.awesome)`        | Negation Pseudo-class              | Selects an element not represented by the stated argument    |

- `:first-child`

  - The **`:first-child`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) represents the first element among a group of sibling elements.

  - To select the first child element inside of another element using CSS, you can use the `:first-child` pseudo-class along with the parent element's selector. Here's an example:

    ```css
    cssCopy code.parent-element > :first-child {
    }
    ```

- Only Child Pseudo-selector `:only-child`

  - You can select any element that is the only element inside of another one.

    ```css
    parent-element > :only-child
    ```

- `:last-child` pseudo-class

  - Select an element that is the last child element inside of another element.

  - ```css
    .table > #fancy > .small,
    .table > .small:last-child {
      /* CSS styles for small apple and pickle */
    }
    ```

  - In this example, `.table` selects the `table` element, `> #fancy` selects the element with the ID `fancy` that is a direct child of the `table` element

  - `> .small` selects any element with the class `small` that is a direct child of the element with the ID `fancy`, and `:last-child` selects the last child element with the class `small` that is a direct child of the `table` element.

- Nth Child Pseudo-selector `:nth-child(A)`

  - Selects the nth (Ex: 1st, 3rd, 12th etc.) child element in another element.

  - :nth-child(8) selects every element that is the 8th child of another element.

  - For example

    ```css
    .table > :nth-child(3)
    ```

    In this example, `.table` selects the `table` element, `> :nth-child(3)` selects the 3rd child element that is a direct child of the `table` element. The `:nth-child` pseudo-class selects elements based on their position among their siblings, with the specified value indicating the index of the child element to select.

    Note that the `:nth-child` pseudo-class is 1-indexed, meaning that the first child has an index of 1, not 0. Also note that this selector would only select the 3rd plate element and not any other elements. If there are no 3rd plate elements, the selector would not select anything.

- Nth Last Child Selector `:nth-last-child`

  - Selects the children from the bottom of the parent. This is like nth-child, but counting from the back!
  - :nth-last-child(2) selects all second-to-last child elements.

- `:first-of-type` selector

  - Selects the first element of that type within another element.

- `nth-of-type` Selects a specific element based on its type and order in another element - or even or odd instances of that element.

  - div:nth-of-type(2) selects the second instance of a div.
  - .example:nth-of-type(odd) selects all odd instances of a the example class.

- Nth-of-type Selector with Formula `:nth-of-type(An+B)`

  - The nth-of-type formula selects every nth element, starting the count at a specific instance of that element.
  - For example: span:nth-of-type(6n+2) selects every 6th instance of a span, starting from (and including) the second instance.

- `only-of-type` Selects the only element of its type within another element.

- `last-of-type` Selects each last element of that type within another element. Remember type refers the kind of tag, so p and span are different types.

- `empty` selector: Selects elements that don't have any other elements inside of them.

- `Negation Pseudo-class`: Select all elements that don't match the negation selector:not(X)

  - You can use this to select all elements that do not match selector "X".

#### Textual pseudo-elements

| Example               | Classification          | Explanation                                                  |
| :-------------------- | :---------------------- | :----------------------------------------------------------- |
| `.alpha:first-letter` | Textual Pseudo-elements | Selects the first letter of text within an element           |
| `.bravo:first-line`   | Textual Pseudo-elements | Selects the first line of text within an element             |
| `div:before`          | Generated Content       | Creates a pseudo-element inside the selected element at the beginning |
| `a:after`             | Generated Content       | Creates a pseudo-element inside the selected element at the end |
| `::selection`         | Fragment Pseudo-element | Selects the part of a document which has been selected, or highlighted, by a users’ actions |

## Properties

- Once an element is selected, a **property** determines the styles that will be applied to that element. 
  - Property names fall after a selector, within the curly brackets, `{}`, and immediately preceding a colon, `:`. 
  - There are numerous properties we can use, such as `background`, `color`, `font-size`, `height`, and `width`, and new properties are often added. 

Example properties

- In the following code, we are defining the `color` and `font-size` properties to be applied to all `<p>` elements.

```cs
p {
  color: ...;
  font-size: ...;
}
```

## Values

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

# Referencing CSS

There are three main ways to use CSS in a web page: inline, internal, and external:

- **Inline** CSS uses the `style` attribute on individual HTML tags.

- **Internal** CSS uses the `style` element to store all of the CSS in one place in the file.

- **External** CSS stores the CSS in a file that is separate from the HTML file.

## Inline CSS

- Adding a `style` attribute applies some CSS styling to the single HTML element identified by the tag. 
  
  - you can't use selectors with inline styles. 
  
- Drawbacks

  - Chatgpt: It allows you to specify styles for an individual element directly within the element itself, rather than in a separate CSS file or in the `head` section of the HTML document.
  - However, defining styles one at a time is tedious, error-prone, and difficult maintenance, and it mixes the presentation information with the content. You will see inline styles in production code sometimes, but principally in conjunction with dynamically generated web pages.
  - Internal and external CSS are better ways to handle styling. 

- The `style` attribute lists all the CSS properties you want to use together as a single string. 
  - We use a colon (`:`) to separate each property name from its associated value; we separate the property name/value pairs from each other with a semicolon (`;`). 
  - The whitespace after each colon and semicolon is optional but recommended for readability.

- Example

  ```html
  <strong style="color: blue; text-decoration: underline;">HTML</strong>
  ```

## Internal CSS

- Instead of scattering your style information all over the page with `style` attributes, you can list it all in the `style` element, which belongs inside the `head` element. 

  - The `style` element is easy to use, and it puts everything together in one place, which makes it most convenient when you need the CSS for a single page.

  - We'll use internal CSS often in this course: placing the HTML and CSS together in a simple project is convenient for both teaching and learning.

- Example

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

  - The code between the open and closing `style` tags is CSS. 

  - The structure and syntax of CSS are straightforward and consistent. 

  - The first part, `strong`, is a **selector**, which tells the browser that it should select and style all `strong` elements in the document as a group. 

  - The braces (`{}`) enclose information that the browser can use to style those elements. 
    - In this case, the `color` property sets the text color, while the `text-decoration` property tells the browser to underline the text. Colons (`:`) separate each property name ( `color`) from its value  `blue`), while semi-colons (`;`) mark the end of each property/value pair. 
    - Most developers include 2-4 spaces of indentation within the braces.

- Use HTML tags semantically - each tag name should describe the type of information you intend to display. 

  - A header needs an `h1`, `h2`, etc. tag. A paragraph needs a `p` tag. A link needs an `a` tag. Don't use a `p` tag to render a small header; use one of the `h#` headers instead, and adjust the appearance as needed with CSS.
  - For example 

  ```css
  p {
    font-size: 24px; /* the font is 24 pixels high */
  }
  ```

- Use ID selectors sparingly to avoid specificity issues like duplicate IDs in our CSS.

  ```css
  #final-paragraph {
    text-decoration: underline;
  }
  ```

  

## External CSS

- In order to get our CSS talking to our HTML, we need to reference our CSS file within our HTML. 

- The best practice for referencing our CSS is to include all of our styles in a single **external style sheet**, which is referenced from within the `<head>` element of our HTML document.

- The `<link>` tag is used in the head section of an HTML document to link to external resources such as stylesheets, scripts, or icons. 

  - It is an empty tag that doesn't have a closing tag, and it includes attributes such as 

    - `href`: identify the URL of the resource.

    - `rel`: identify the relationship between the current document and the linked resource.
    - `type`: the MIME type of the linked resource.

  - Using a single external style sheet allows us to use the same styles across an entire website and quickly make changes sitewide.

- External CSS is the preferred way to include CSS in most web pages because

  - It lets you share CSS between multiple pages, and makes maintenance of the CSS code separate from that of the HTML. Browsers can also cache external CSS files, which can reduce page load times. 
  - For most of this course, though, we'll stick with the internal technique; feel free to use external files if you wish.

- Example

  ```js
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

# Using CSS Resets

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

[Getting to Know CSS](https://learn.shayhowe.com/html-css/getting-to-know-css/) brings CSS into the mix, introducing the cascade, specificity, selectors, and an assortment of properties.

CSS is a complex language that packs quite a bit of power.

- It allows us to add layout and design to our pages, and it allows us to share those styles from element to element and page to page. Before we can unlock all of its features, though, there are a few aspects of the language we must fully understand.

- First, it’s crucial to know exactly how styles are rendered.
  - Specifically, we’ll need to know how different types of selectors work and how the order of those selectors can affect how our styles are rendered. 
  - We’ll also want to understand a few common property values that continually appear within CSS, particularly those that deal with color and length.

Let’s look under the hood of CSS to see exactly what is going on.

# Tutorial 3: Getting to know CSS

## The Cascade

We’ll begin breaking down exactly how styles are rendered by looking at what is known as the cascade and studying a few examples of the cascade in action. 

- Within CSS, all styles **cascade** from the top of a style sheet to the bottom, allowing different styles to be **added or overwritten** as the style sheet progresses. Styles later in the cascade takes precedence over earlier ones.

- For example, 

  - Say we select all paragraph elements at the top of our style sheet and set their background color to `orange` and their font size to `24` pixels. 

  - Then towards the bottom of our style sheet, we select all paragraph elements again and set their background color to `green`, as seen here.

```css
p {
  background: orange;
  font-size: 24px;
}
p {
  background: green;
}
```

- Because the paragraph selector that sets the background color to `green` comes after the paragraph selector that sets the background color to `orange`, it will take precedence in the cascade. 

  - All of the paragraphs will appear with a `green` background.

  - The font size will remain `24` pixels because the second paragraph selector didn’t identify a new font size.

#### Cascading Properties

- The cascade also works with properties inside individual selectors. 

- Again, for example, 

  - say we select all the paragraph elements and set their background color to `orange`. 

  - Then directly below the `orange` background property and value declaration, we add another property and value declaration setting the background color to `green`, as seen here.

```css
p {
  background: orange;
  background: green;
}
```

- Because the `green` background color declaration comes after the `orange` background color declaration, it will overrule the `orange` background, and, as before, our paragraphs will appear with a `green` background.

- All styles will cascade from the top of our style sheet to the bottom of our style sheet. 

## CSS Specificity

- The order of the rules is significant but depends upon the **cascade, specificity, and inheritance rules**. 
  - **Cascade**: Within CSS, all styles cascade from the top of a style sheet to the bottom, allowing different styles to be added or overwritten as the style sheet progresses.
  - **Selectors**: type- class- id 
  - **Inheritance rules**: child elements have higher specificity than parent elements.


## Calculating Specificity

- There are, however, times where the cascade doesn’t play so nicely. Those times occur when different types of selectors are used and the **specificity of those selectors breaks the cascade**. 
- Every selector in CSS has a **specificity weight**. A selector’s specificity weight, along with its placement in the cascade, identifies how its styles will be rendered.
- **In general, the higher our specificity weights rise, the more likely our cascade is to break**.

In Lesson 1, “[Building Your First Web Page](https://learn.shayhowe.com/html-css/building-your-first-web-page/),” we talked about three different types of selectors: the type, class, and ID selectors.

- Each of these selectors has a different specificity weight.

  - The **type selector** has the lowest specificity weight and holds a point value of `0-0-1`. 

  - **The class selector** has a medium specificity weight and holds a point value of `0-1-0`. 

  - Lastly, the **ID selector** has a high specificity weight and holds a point value of `1-0-0`. 

As we can see, specificity points are calculated using three columns. The first column counts ID selectors, the second column counts class selectors, and the third column counts type selectors.

What’s important to note here is that the ID selector has a higher specificity weight than the class selector, and the class selector has a higher specificity weight than the type selector.

------

##### Specificity Points

Specificity points are intentionally hyphenated, as their values are not computed from a base of 10. Class selectors do not hold a point value of 10, and ID selectors do not hold a point value of 100. Instead, these points should be read as `0-1-0` and `1-0-0` respectively. We’ll take a closer look at why these point values are hyphenated shortly, when we combine selectors.

------

- The higher the specificity weight of a selector, the more superiority the selector is given when a styling conflict occurs. 
- For example, if a paragraph element is selected using a type selector in one place and an ID selector in another, the ID selector will take precedence over the type selector regardless of where the ID selector appears in the cascade.

HTML

```html
<p id="food">...</p>
```

CSS

```css
#food {
  background: green;
}
p {
  background: orange;
}
```

- Here we have a paragraph element with an `id` attribute value of `food`. 
  - Within our CSS, that paragraph is being selected by two different kinds of selectors: one type selector and one ID selector. 
  - Although the type selector comes after the ID selector in the cascade, the ID selector takes precedence over the type selector because it has a higher specificity weight; consequently the paragraph will appear with a `green` background.

- **The specificity weights of different types of selectors are incredibly important to remember**. At times styles may not appear on elements as intended, and chances are the specificity weights of our selectors are breaking the cascade, therefore our styles are not appearing properly.

Understanding how the cascade and specificity work is a huge hurdle, and we’ll continue to cover this topic. For now, let’s look at how to be a little more particular and intentional with our selectors by combining them. Keep in mind that as we combine selectors, we’ll also be changing their specificity.

## Combining Selectors

So far we’ve looked at how to use different types of selectors individually, but we also need to know how to use these selectors together. 

- By combining selectors we can be more specific about which element or group of elements we’d like to select.
- Combining selectors also changes their specificity. 

- For example, 
  - say we want to select all paragraph elements that reside within an element with a class attribute value of `hotdog` and set their background color to `brown`. 
  - However, if one of those paragraphs happens to have the class attribute value of `mustard`, we want to set its background color to `yellow`. Our HTML and CSS may look like the following:

HTML

```HTML
<div class="hotdog">
  <p>...</p>
  <p>...</p>
  <p class="mustard">...</p>
</div>
```

CSS

```CSS
.hotdog p {
  background: brown;
}
.hotdog p.mustard { 
  background: yellow;
}
```

- When selectors are combined they should be **read from right to left**. 
  - In general, it is best to write CSS selectors from right to left, **starting with the most specific selector and ending with the least specific one**.
  - The selector farthest to the right, directly before the opening curly bracket, is known as the **key selector**. The key selector identifies exactly which element the styles will be applied to. 
  - Any selector to the left of the key selector will serve as a **prequalifier**.
  
- The first combined selector above, `.hotdog p`, includes two selectors: a class and a type selector. These two selectors are separated by a single space. 
  - The **key selector** (`<p>`)is a type selector targeting paragraph elements. 
  - And because this type selector is **prequalified** with a class selector of `hotdog`, the full combined selector will only select paragraph elements that reside within an element with a class attribute value of `hotdog`.

- The second selector above, `.hotdog p.mustard`, includes three selectors: two class selectors and one type selector. 
  - The only difference between the second selector and the first selector is the addition of the class selector of `mustard` to the end of the paragraph type selector. 
  - The **key selector** is the class selector `mustard` because it falls all the way to the right of the combined selector. All of the individual selectors coming before it are now **prequalifiers**.

------

Example: combining link and list selectors

```css
li a {
  color: purple;
}
```

- Browsers give links a different color in their default settings, so changing the text color elsewhere doesn't affect the link color. 
- Hovered and active links still turn a different color when you do this, but that's what you want, probably.
- On the other hand, browsers don't change the default `font-family` property for links, so when we change it for `li`, the links inside each list item inherit the `font-family`.

------

##### Spaces Within Selectors

Within the previous combined selector, `.hotdog p.mustard`, there is a space between the `hotdog` class selector and the paragraph type selector but not between the paragraph type selector and the `mustard` class selector. The use, and omission, of spaces makes a large difference in selectors.

- Since there isn’t a space between the paragraph type selector and the `mustard` class selector that means the selector will only select paragraph elements with the class of `mustard`. 
  - If the paragraph type selector was removed, and the `mustard` class selector had spaces on both sides of it, it would select any element with the class of `mustard`, not just paragraphs.

- **The best practice is to not prefix a class selector with a type selector**. Generally we want to select any element with a given class, not just one type of element. 
- And following this best practice, our new combined selector would be better as `.hotdog .mustard`.
  - Reading the combined selector from right to left, it is targeting paragraphs with a class attribute value of `mustard` that reside within an element with the class attribute value of `hotdog`.

------

Different types of selectors can be combined to target any given element on a page. As we continue to write different combined selectors, we’ll see their powers come to life. Before we do that, though, let’s take a look at how combining selectors changes a selector’s specificity weight.

#### Specificity Within Combined Selectors

- When selectors are combined, so are the specificity weights of the individual selectors. These combined specificity weights can be calculated by counting each different type of selector within a combined selector.

Looking at our combined selectors from before, 

- The first selector, `.hotdog p`, had both a class selector and a type selector. Knowing that the point value of a class selector is `0-1-0` and the point value of a type selector is `0-0-1`, the total combined point value would be `0-1-1`, found by adding up each kind of selector.

- The second selector, `.hotdog p.mustard`, had two class selectors and one type selector. Combined, the selector has a specificity point value of `0-2-1`. The `0` in the first column is for zero ID selectors, the `2` in the second column is for two class selectors, and the `1` in the last column is for one type selector.

Comparing the two selectors, 

- the second selector, with its two classes, has a noticeably higher specificity weight and point value. As such it will take precedence within the cascade. 
- If we were to flip the order of these selectors within our style sheet, placing the higher-weighted selector above the lower-weighted selector as shown here, the appearance of their styles would not be affected due to each selector’s specificity weight.

```css
.hotdog p.mustard {
  background: yellow;
}
.hotdog p {
  background: brown;
}
```

In general we want to always keep an eye on the specificity weights of our selectors. 

- The higher our specificity weights rise, the more likely our cascade is to break.

## Layering Styles with Multiple Classes

- We should layer cascading downwards, with the upper layers being more general.
  - This means that styles that apply to all elements should be defined first, followed by more specific styles for individual elements or groups of elements. 

------

- One way to keep the specificity weights of our selectors low is to be as **modular** as possible, sharing similar styles from element to element. 

  - And one way to be as modular as possible is to layer on different styles by using multiple classes.


  - Elements within HTML can have **multiple class attribute values** so long as each value is **space separated**. 

  - With that, we can place certain styles on all elements of one sort while placing other styles only on specific elements of that sort.

- **We can tie styles we want to continually reuse to one class and layer on additional styles from another class.**
  - Using multiple classes, we can layer on as many styles as we wish, keeping our code lean and our specificity weights low.
  - Chatgpt says it's better to layer classes than combine selectors.
- Let’s take a look at buttons, for example. 
  - Say we want all of our buttons to have a font size of `16` pixels, but we want the background color of our buttons to vary depending on where the buttons are used. 
  - We can create a few classes and layer them on an element as necessary to apply the desired styles.

HTML

```HTML
<a class="btn btn-danger">...</a>
<a class="btn btn-success">...</a>
```

CSS

```CSS
.btn {
  font-size: 16px;
}
.btn-danger {
  background: red;
}
.btn-success {
  background: green;
}
```

- Here you can see two anchor elements, both with multiple class attribute values. 
  - The first class, `btn`, is used to apply a font size of `16` pixels to each of the elements. 
  - Then, the first anchor element uses an additional class of `btn-danger` to apply a `red` background color. 
  - The second anchor element uses an additional class of `btn-success` to apply a `green` background color. Our styles here are clean and modular.

Much like understanding the cascade and calculating specificity, this is a practice that will take time to fully absorb, but we’ll get better with each lesson.

## Common CSS Properties

- Memorize `color`, `background-color`, `font-family`, and `font-size`.
- `text-align` property align text: `left`, `right`, `center`, and `justified` are the main alignment values.
  - [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align): The **`text-align`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the horizontal alignment of the inline-level content inside a block element or table-cell box. This means it works like [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) but in the horizontal direction.
  - For example `text-align: center`: the inline contents are **center-justified** within the line box.
  - `justify` :The inline contents are justified. Text should be spaced to line up its left and right edges to the left and right edges of the line box, except for the last line.
- `background-color` property. 
  - **Most** elements use a transparent background color by default, so the background color for the body applies to most page elements. Here, everything uses the same background.
- `color` property denotes the foreground color, the color of text.
  - The **`color`** CSS property sets the foreground [color value](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) of an element's text and [text decorations](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration), and sets the [`currentcolor`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#currentcolor_keyword) value. 
  - The `color` property is **inheritable**, which means that applying `color` to an element also applies it to every descendant of that element. There are exceptions, though. For instance, your links didn't inherit the text color. This seeming failure occurs since the browser sets separate colors for links, which prevents them from inheriting the primary text color.
- `font-style`: italics
- The **`margin`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) shorthand property sets the [margin area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model#margin_area) on all four sides of an element.(in px)
  - The **`margin-bottom`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the [margin area](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model#margin_area) on the bottom of an element. A positive value places it farther from its neighbors, while a negative value places it closer.
- `text-decoration` underlining
- `text-transform`: uppercase 
- 

#### Shorthand Properties

- [Shorthand Properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties)

  - ```html
    <style>
    	body {
    		/* font-size: 20px;
    		font-family: Tahoma, "Trebuchet MS", Verdana, sans-serif;
    		font-style: italic;
        font-weight: bold;
        line-height: 2.5; */
        font: italic bold 20px/2.5 Verdana, "TrebuchetMS", Tahoma, sans-serif;
    	}
    </style>
    ```

  - The order of the values for each property in the **`font` shorthand property** is flexible, but it is important to specify the `font-size` and `font-family` values, as they are required. Additionally, it is common to include a **fallback font family** that comes after the preferred font family in case the preferred font is not available.

#### Font-family

[`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family)

- The **`font-family`** CSS property specifies a prioritized **list** of one or more font family names and/or generic family names for the selected element.

- The best place to put the `font-family` property is in a CSS selector that applies to the `<body>` tag.

- The font you choose is mainly a matter of preference, or rather, the preferences of your designer. 

- serif vs sans-serif font

  - Mainstream use today seems to favor serif fonts for headlines and other attention-grabbing items and sans-serif for paragraph-based text.  
  - Browsers use a **serif typeface** by default. Serif fonts have flared end-points on most characters; **sans-serif** do not:

  ![Serif and Non-Serif Fonts](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_1/serifs-01.png)

  - Mainstream use today seems to favor serif fonts for headlines and other attention-grabbing items and sans-serif for paragraph-based text.- 

- [Guide to web-safe fonts](http://web.mit.edu/jmorzins/www/fonts.html) includes information on Web-safe fonts and displays examples of each. You don't have to read it right now, but bookmark it for reference.

## Common CSS Property Values

We’ve used a handful of common CSS property values already, such as the keyword color values of `red` and `green`. You may not have thought too much about them; that’s okay. We’re going to take time now to go over some previously used property values as well as to explore some of the more common property values that we’ll soon be using.

Specifically, we’ll look at property values that relate to colors and length measurements.

## Colors

- All color values within CSS are defined on an sRGB (or standard red, green, and blue) color space. 
  - Colors within this space are formed by mixing red, green, and blue color channels together, mirroring the way that televisions and monitors generate all the different colors they display. 
  - By mixing different levels of red, green, and blue, we can create millions of colors—and find nearly any color we’d like.

- Currently there are four primary ways to represent sRGB colors within CSS: keywords, hexadecimal notation, and RGB and HSL values.

#### Keyword Colors

- Keyword color values are names (such as `red`, `green`, or `blue`) that map to a given color. These keyword names and their corresponding colors are determined by the CSS specification. Most common colors, along with a few oddities, have keyword names.

A complete list of these keyword names can be found within the [CSS specification](http://www.w3.org/TR/css3-color/).

| Color | Name      | Hex Values | RGB Values           | HSL Values            |
| :---- | :-------- | :--------- | :------------------- | :-------------------- |
|       | `black`   | `#000000`  | `rgb(0, 0, 0)`       | `hsl(0, 0%, 0%)`      |
|       | `silver`  | `#c0c0c0`  | `rgb(192, 192, 192)` | `hsl(0, 0%, 75%)`     |
|       | `gray`    | `#808080`  | `rgb(128, 128, 128)` | `hsl(0, 0%, 50%)`     |
|       | `white`   | `#ffffff`  | `rgb(255, 255, 255)` | `hsl(0, 100%, 100%)`  |
|       | `maroon`  | `#800000`  | `rgb(128, 0, 0)`     | `hsl(0, 100%, 25%)`   |
|       | `red`     | `#ff0000`  | `rgb(255, 0, 0)`     | `hsl(0, 100%, 50%)`   |
|       | `purple`  | `#800080`  | `rgb(128, 0, 128)`   | `hsl(300, 100%, 25%)` |
|       | `fuchsia` | `#ff00ff`  | `rgb(255, 0, 255)`   | `hsl(300, 100%, 50%)` |
|       | `green`   | `#008000`  | `rgb(0, 128, 0)`     | `hsl(120, 100%, 25%)` |
|       | `olive`   | `#808000`  | `rgb(128, 128, 0)`   | `hsl(60, 100%, 25%)`  |
|       | `lime`    | `#00ff00`  | `rgb(0, 255, 0)`     | `hsl(120, 100%, 50%)` |
|       | `yellow`  | `#ffff00`  | `rgb(255, 255, 0)`   | `hsl(60, 100%, 50%)`  |
|       | `navy`    | `#000080`  | `rgb(0, 0, 128)`     | `hsl(240, 100%, 25%)` |
|       | `blue`    | `#0000ff`  | `rgb(0, 0, 255)`     | `hsl(240, 100%, 50%)` |
|       | `teal`    | `#008080`  | `rgb(0, 128, 128)`   | `hsl(180, 100%, 25%)` |
|       | `aqua`    | `#00ffff`  | `rgb(0, 255, 255)`   | `hsl(180, 100%, 50%)` |

Here we are applying a `maroon` background to any element with the `task` class attribute value and a `yellow` background to any element with the `count` class attribute value.

```css
.task {
  background: maroon;
}
.count {
  background: yellow;
}
```

While keyword color values are simple in nature, they provide limited options and thus are not the most popular color value choice.

#### Hexadecimal Colors

- Hexadecimal color values consist of a pound, or hash, `#`, followed by a three- or six- character figure. The figures use the numbers `0` through `9` and the letters `a` through `f`, upper or lower case. These values map to the red, green, and blue color channels.
- In six-character notation, the first two characters represent the red channel, the third and fourth characters represent the green channel, and the last two characters represent the blue channel.
- In three-character notation, the first character represents the red channel, the second character represents the green channel, and the last character represents the blue channel.

Matching pair

- Six-character hexadecimal values may be written as three-character hexadecimal values when the red, green, and blue color channels each contain a repeating character. 
  - If in six-character notation the first two characters are a matching pair, the third and fourth characters are a matching pair, and the last two characters are a matching pair, the six-character figure may be shortened to a three-character figure. 
- To do this the repeated character from each pair should be used once. For example, a shade of orange represented by the hexadecimal color `#ff6600` could also be written as `#f60`.

![Hexadecimal Color Syntax](https://learn.shayhowe.com/assets/images/courses/html-css/getting-to-know-css/hexadecimal-syntax.png)



- The character pairs are obtained by converting `0` through `255` into a base-16, or hexadecimal, format. 
- The math is a little tricky—and worthy of its own book—but it helps to know that `0` equals black and `f` equals white.

------

#### The Millions of Hexadecimal Colors

There are millions of hexadecimal colors, over 16.7 million to be exact. Here’s how…

There are 16 options for every character in a hexadecimal color, `0` through `9` and `a` through `f`. With the characters grouped in pairs, there are 256 color options per pair (16 multiplied by 16, or 16 squared).

And with three groups of 256 color options we have a total of over 16.7 million colors (256 multiplied by 256 multiplied by 256, or 256 cubed).

------

To create the same `maroon` and `yellow` background colors from before, we could replace the keyword color values with hexadecimal color values, as seen here.

```css
.task {
  background: #800000;
}
.count {
  background: #ff0;
}
```

Hexadecimal color values have been around for a while, and they have become fairly popular because they offer a large number of color options. They are, however, a little difficult to work with, especially if you’re not too familiar with them. Fortunately Adobe has created [Adobe Color](https://color.adobe.com/create/color-wheel), a free application that provides a color wheel to help us find any color we want and its corresponding hexadecimal value.

Additionally, most image editing applications, such as Adobe Photoshop, provide the capability to locate hexadecimal color values.

![Adobe Photoshop Color Picker](https://learn.shayhowe.com/assets/images/courses/html-css/getting-to-know-css/photoshop-color-picker.png)

**Fig 3**.02

The color picker tool within Adobe Photoshop displays the hexadecimal and RGB color values

#### RGB & RGBa Colors

- RGB color values are stated using the `rgb()` function, which stands for red, green, and blue. 

  - The function accepts three comma-separated values, each of which is an integer from `0` to `255`. 
  - A value of `0` would be pure black; a value of `255` would be pure white.

  - As we might expect, the first value within the `rgb()` function represents the red channel, the second value represents the green channel, and the third value represents the blue channel.

Examples

- If we were to recreate the shade of orange from before as an RGB color value, it would be represented as `rgb(255, 102, 0)`.

- Also, using the same `maroon` and `yellow` background colors from before, we could replace the keyword or hexadecimal color values with RGB color values.

```css
.task {
  background: rgb(128, 0, 0);
}
.count {
  background: rgb(255, 255, 0);
}
```

RGBa

- RGB color values may also include an **alpha**, or **transparency**, channel by using the `rgba()` function. 
  - The `rgba()` function requires a fourth value, which must be a number between `0` and `1`, including decimals. A value of `0` creates a fully **transparent** color, meaning it would be invisible, and a value of `1` creates a fully **opaque** color.
  - Any decimal value in between `0` and `1` would create a semi-transparent color.

Examples

- If we wanted our shade of orange to appear 50% opaque, we would use an RGBa color value of `rgba(255, 102, 0, .5)`.

- We can also change the opacity of our `maroon` and `yellow` background colors. The following code sets the `maroon` background color to 25% opaque and leaves the `yellow` background color 100% opaque.

```css
.task {
  background: rgba(128, 0, 0, .25);
}
.count {
  background: rgba(255, 255, 0, 1);
}
```

RGB color values are becoming more popular, especially due to the ability to create semi-transparent colors using RGBa.

#### HSL & HSLa Colors

- HSL color values are stated using the `hsl()` function, which stands for **hue**, **saturation**, and **lightness**. Within the parentheses, the function accepts three comma-separated values, much like `rgb()`.

- The first value, the **hue**, is a unitless number from `0` to `360`. The numbers `0` through `360` represent the color wheel, and the value identifies the degree of a color on the color wheel.

- The second and third values, the saturation and lightness, are percentage values from `0` to `100%`. 
  - The **saturation** value identifies how saturated with color the hue is, with `0` being grayscale and `100%` being fully saturated. 
  - The **lightness** identifies how dark or light the hue value is, with `0` being completely black and `100%` being completely white.

Returning to our shade of orange, as an HSL color value it would be written as `hsl(24, 100%, 50%)`.

Our `maroon` and `yellow` background colors can also be stated as HSL color values, as shown here.

```CSS
.task {
  background: hsl(0, 100%, 25%);
}
.count {
  background: hsl(60, 100%, 50%);
}
```

HSLa

- HSL color values, like RGBa, may also include an alpha, or transparency, channel with the use of the `hsla()` function. The behavior of the alpha channel is just like that of the `rgba()` function. 
- A fourth value between `0` and `1`, including decimals, must be added to the function to identify the degree of opacity.

Example

- Our shade of orange as an HSLa color set to 50% opaque would be represented as `hsla(24, 100%, 50%, .5)`.

- The same 25% opaque `maroon` background color and 100% opaque `yellow` background color from before would look like the following as HSLa color values.

```css
.task {
  background: hsla(0, 100%, 25%, .25);
}
.count {
  background: hsla(60, 100%, 50%, 1);
}
```

Popularity

- The HSL color value is the newest color value available within CSS. Due to its age and support within browsers, though, it isn’t as widely used as the other values.
- For the time being, hexadecimal color values remain the most popular as they are widely supported; though when an alpha channel for transparency is needed, RGBa color values are preferred. These preferences may change in the future, but for now we’ll use hexadecimal and RGBa color values.

## Lengths

Length values within CSS are similar to colors in that there are a handful of different types of values for [length](https://developer.mozilla.org/en-US/docs/Web/CSS/length), all of which serve distinct purposes. Length values come in two different forms, absolute and relative, each of which uses different units of measurement.

We’re going to stick to the more common—and more straightforward—values at the moment, as more complex values will provide much more power than we need for now.

#### Absolute Lengths

- **Absolute length** values are the simplest length values, as they are fixed to a physical measurement, such as inches, centimeters, or millimeters. 
- The most popular absolute unit of measurement is known as the pixel and is represented by the `px` unit notation.

##### Pixels

- The **pixel** is equal to 1/96th of an inch; thus there are 96 pixels in an inch. The exact measurement of a pixel, however, may vary slightly between high-density and low-density viewing devices.

- Pixels have been around for quite some time and are commonly used with a handful of different properties. The code here is using pixels to set the font size of all paragraphs to `14` pixels.

```css
p {
  font-size: 14px;
}
```

With the changing landscape of viewing devices and their varying screen sizes, pixels have lost some of their popularity. As an absolute unit of measurement, they don’t provide too much flexibility. Pixels are, however, trustworthy and great for getting started. We’re going to lean on them quite a bit as we’re learning the ropes of HTML and CSS.

#### Relative Lengths

In addition to absolute length values, there are also relative length values. 

- **Relative length values** are a little more complicated, as they are not fixed units of measurement; they rely on the length of another measurement.

##### Percentages

- **Percentages**, represented by the `%` unit notation, are one of the most popular relative values. **Percentage lengths** are defined in relation to the length of another object. 
- Percentages are extremely helpful for setting the height and width of elements and building out a web page’s layout. We’re going to rely on them often to help us out in these areas.

Example

For example, to set the `width` of an element to `50%`, we have to know the width of its parent element, the element it is nested within, and then identify `50%` of the parent element’s width.

```css
.col {
  width: 50%;
}
```

Here we’ve set the width of the element with the class attribute value of `col` to `50%`. That `50%` will be calculated relative to the width of the element’s parent.

##### Em

The em unit is also a very popular relative value. 

- The **em unit** is represented by the `em` unit notation, and its length is calculated based on an element’s font size. (value x font-size)

- A single em unit is equivalent to an element’s font size. So, for example, if an element has a font size of `14` pixels and a `width` set to `5em`, the width would equal `70` pixels (`14` pixels multiplied by 5).

```css
.banner {
  font-size: 14px;
  width: 5em;
}
```

- When a font size is not explicitly stated for an element, the em unit will be relative to the font size of the closest parent element with a stated font size.

- The em unit is often used for styling text, including font sizes, as well as spacing around text, including margins and paddings. We’ll explore text a bit more in Lesson 6, “[Working with Typography](https://learn.shayhowe.com/html-css/working-with-typography/).”

There are a lot more absolute and relative units of measurement than those mentioned here. However, these three—pixels, percentages, and em units—are the most popular and the ones we’re going to primarily use.

# CSS to HTML

```html
<style>
	body {
    font-size: 20px;
    font-family: Tahoma, "Trebuchet MS", Verdana, sans-serif;
    font-style: italic;
    font-weight: bold;
    line-height: 2.5;
	}
</style>
```

HTML version

```html
```



## Summary

Sadly our Styles Conference website lay dormant this lesson. We focused on the foundations of CSS, covering exactly how it works and some common values we’re sure to use.

To briefly recap, within this lesson we’ve discussed the following:

- How style sheets cascade from the top to the bottom of a file
- What specificity is and how we can calculate it
- How to combine selectors to target specific elements or groups of elements
- How to use multiple classes on a single element to layer on different styles for more modular code
- The different color values available to use within CSS, including keyword, hexadecimal, RGB, and HSL values
- The different length values available to use within CSS, including pixels, percentages, and em units

We still have a lot to cover, but the fundamentals are starting to fall into place. Within the next few lessons we’ll continue to dive in to CSS, and our website will really begin to take shape.

# Chrome Inspector

- At this stage, you should begin using the Inspector as you move through the course, primarily as a debugging and experimentation tool. 
  - For instance, if you are having problems with the box model (discussed in the next lesson), the Inspector is where you will find the information you need to diagnose the issue. 
  - You can even use it to experiment with several different settings to see if they fix the problem you're having. A great way to practice using the inspector is to find web pages that do something like what you want to do and see how they handled the problem. 

## Viewing and changing the dom

https://developer.chrome.com/docs/devtools/dom/#scroll2

- The **DOM ** is a tree of objects that represents the page's content.
- How to determine font-size
  - To determine this value with Chrome's Developer Tools, you must first locate the underlined element in the Elements tab. The easiest way to do this is to right-click on the desired text, then select Inspect. 
  - Chrome will open the Elements tab of the inspector with the appropriate element selected on the left. If you look to the right under Styles, you'll see several rules, one of which (the `.xyz` rule) has an enabled font-size, and a value of 1.3rem. Since you want the size in pixels, you must look at the Computed sub-tab on the right side. There you will find that the font size is 26px.


## View Properties of DOM objects

https://developer.chrome.com/docs/devtools/dom/properties/

- Bolded properties are own properties

- Additionally, prototype-specific properties are shown only on prototypes, not on objects. This makes it easier to diagnose objects.

- Click **Show all** to see properties with `null` and `undefined` values.

- Properties that correspond to DOM nodes

  - The Document Object Model (DOM) is a hierarchical structure of nodes that represents the content of an HTML, XML or SVG document. Each element, attribute, and text node in the document is represented by a corresponding DOM node. In order to interact with DOM nodes programmatically, we need to access their properties and methods. Each DOM node has a set of properties that allow us to read or modify its attributes, content, or position within the document tree.

  - When you click on a link that corresponds to a DOM node property, it will usually trigger an event that selects that node in the DOM tree. For example, if you click on a link that corresponds to the "innerHTML" property of a DOM element, the browser will select that element and highlight its content in the page.

    Here are some examples of DOM node properties that you can access by clicking on links:

    - innerHTML: the HTML content of an element
    - className: the CSS class(es) of an element
    - style: the inline CSS styles of an element
    - parentNode: the parent node of an element
    - childNodes: a list of child nodes of an element
    - tagName: the tag name of an element
    - id: the ID of an element

  - By accessing these properties, you can manipulate the content and structure of the DOM tree dynamically, allowing you to create dynamic web applications that respond to user interactions in real-time.

## View and Change CSS

https://developer.chrome.com/docs/devtools/css/

- `.cls` is used for adding classes to the selected element.

# HTML5 Syntax Rules

- Correct nesting

  ```html
  b><i>Bold and Italic</i></b>i>
  ```

  

# HTML and CSS Style Guide

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

  ```html
  <!-- Good -->
  <br>
  <img src="picture.jpg">
  
  <!-- Bad -->
  <br />
  <img src="picture.jpg" />
  ```

- When using Flex or Grid (we'll talk about these later), consider placing the most significant content blocks near the top of the file, and the least important at the bottom.

## HTML Coding Practices

https://learn.shayhowe.com/html-css/writing-your-best-code/

The guidelines described here provide a brief introduction to HTML coding practices; this is by no means an exhaustive list.

### Write Standards-Compliant Markup

- HTML, by nature, is a forgiving language that allows poor code to execute and render to varying levels of accuracy. Successful rendering, however, does not mean that our code is semantically correct or guarantee that it will validate as standards compliant. In addition, poor code is unpredictable, and you can’t be certain what you’re going to get when it renders. 

- We have to pay close attention when writing HTML and be sure to nest and close all elements correctly, to use IDs and classes appropriately, and to always validate our code.

The code that follows has multiple errors, including using the `intro` ID attribute value multiple times when it should be a unique value, closing the `<p>` and `<strong>` elements in the wrong order within the first paragraph, and not closing the `<p>` element at all in the second paragraph.

Bad Code

```html
<p id="intro">New items on the menu today include <strong>caramel apple cider and breakfast crepes</p>.</strong>
<p id="intro">The caramel apple cider is delicious.
```

Good code

```html
<p class="intro">New items on the menu today include <strong>caramel apple cider and breakfast crepes</strong>.</p>
<p class="intro">The caramel apple cider is delicious.</p>
```

### Make Use of Semantic Elements

- The library of elements in HTML is fairly large, with well over 100 elements available for use. Deciding which elements to use to describe different content may be difficult, but these elements are the backbone of semantics. We need to research and double-check our code to ensure we are using the proper semantic elements. 
- Users will thank us in the long run for building a more accessible website, and your HTML will arguably be easier to style. If you are ever unsure of your code, find a friend to help out and perform routine code reviews.

Here the HTML doesn’t use the proper heading and paragraph elements; instead, it uses meaningless elements to style and group content.

Bad Code

```html
<span class="heading"><strong>Welcome Back</span></strong>
<br><br>
It has been a while. What have you been up to lately?
<br><br>    
```

Good Code

```html
<h1>Welcome Back</h1>
<p>It has been a while. What have you been up to lately?</p>
```

### Use the Proper Document Structure

- As previously mentioned, HTML is a forgiving language and, therefore, pages will render without the use of the `<!DOCTYPE html>` doctype or `<html>`, `<head>`, and `<body>` elements. Without a doctype and these structural elements, pages will not render properly in every browser.

- We must always be sure to the use proper document structure, including the `<!DOCTYPE html>` doctype, and the `<html>`, `<head>`, and `<body>` elements. Doing so keeps our pages standards compliant and fully semantic, and helps guarantee they will be rendered as we wish.

Bad Code

```html
<html>
  <h1>Hello World</h1>
  <p>This is a web page.</p>
</html> 
```

Good Code

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Hello World</title>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>This is a web page.</p>
  </body>
</html>
```

### Keep the Syntax Organized

As pages grow, managing HTML can become quite a task. Thankfully there are a few quick rules that can help us keep our syntax clean and organized. These include the following:

- Use lowercase letters within element names, attributes, and values
- Indent nested elements
- Strictly use double quotes, not single or completely omitted quotes
- Remove the forward slash at the end of self-closing elements
- Omit the values on Boolean attributes

Observing these rules will help keep our code neat and legible. Looking at the two sets of HTML here, the good code is easier to digest and understand.

Bad Code

```html
<Aside>
<h3>Chicago</h3>
<H5 HIDDEN='HIDDEN'>City in Illinois</H5>
<img src=chicago.jpg alt="Chicago, the third most populous city in the United States" />
<ul>
<li>234 square miles</li>
<li>2.715 million residents</li>
</ul>
</ASIDE>
```

Good Code

```html
<aside>
  <h3>Chicago</h3>
  <h5 hidden>City in Illinois</h5>
  <img src="chicago.jpg" alt="Chicago, the third most populous city in the United States">
  <ul>
    <li>234 square miles</li>
    <li>2.715 million residents</li>
  </ul>
</aside>
```

### Use Practical ID & Class Values

- Creating ID and class values can be one of the more difficult parts of writing HTML. These values need to be practical, relating to the content itself, not the style of the content. 
- Using a value of `red` to describe red text isn’t ideal, as it describes the presentation of the content. Should the style of the text ever need to be changed to blue, not only does the CSS have to be changed, but so does the HTML in every instance where the class `red` exists.

The HTML here assumes that the alert message will be red. However, should the style of the alert change to orange the class name of `red` will no longer make sense and will likely cause confusion.

Bad Code

```html
<p class="red">Error! Please try again.</p>
```

Good Code

```html
<p class="alert">Error! Please try again.</p>
```

### Use the Alternative Text Attribute on Images

- Images should always include the `alt` attribute. Screen readers and other accessibility software rely on the `alt` attribute to provide context for images.

- The `alt` attribute value should be very descriptive of what the image contains. If the image doesn’t contain anything of relevance, the `alt` attribute should still be included; however, the value should be left blank so that screen readers will ignore it rather than read the name of the image file.

Additionally, if an image doesn’t have a meaningful value—perhaps it is part of the user interface, for example—it should be included as a CSS background image if at all possible, not as an `<img>` element.

Bad Code

```html
<img src="puppy.jpg">
```

Good Code

```html
<img src="puppy.jpg" alt="A beautiful, two-year-old hound mix puppy">
```

### Separate Content from Style

- Never, ever, use inline styles within HTML. Doing so creates pages that take longer to load, are difficult to maintain, and cause headaches for designers and developers. 
- Instead, use external style sheets, using classes to target elements and apply styles as necessary.

Here, any desired changes to styles within the bad code must be made in the HTML. Consequently, these styles cannot be reused, and the consistency of the styles will likely suffer.

Bad Code

```html
<p style="color: #393; font-size: 24px;">Thank you!</p>
```

Good Code

```html
<p class="alert-success">Thank you!</p>   
```

### Avoid a Case of “Divitis”

- When writing HTML, it is easy to get carried away adding a `<div>` element here and a `<div>` element there to build out any necessary styles. While this works, it can add quite a bit of bloat to a page, and before too long we’re not sure what each `<div>` element does.

- We need to do our best to keep our code lean and to reduce markup, tying multiple styles to a single element where possible. Additionally, we should use the HTML5 structural elements where suitable.

Bad Code

```html
<div class="container">
  <div class="article">
    <div class="headline">Headlines Across the World</div>
  </div>
</div>     
```

Good Code

```html
<div class="container">
  <article>
    <h1>Headlines Across the World</h1>
  </article>
</div>      
```

### Continually Refactor Code

Over time websites and code bases continue to evolve and grow, leaving behind quite a bit of cruft. Remember to remove old code and styles as necessary when editing a page. Let’s also take the time to evaluate and refactor our code after we write it, looking for ways to condense it and make it more manageable.

## CSS Style

- Don't put more than one property on the same line.

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

  ```css
  p {
    background-color: yellow;
    color: red;
    width: 50%; width: 50vw; /* fallback to 50% if 50vw not recognized */
  }
  ```

- Indent property names and values by two spaces, four spaces, or hard tabs. (Be consistent.)

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

- The order of the rules is significant but depends upon the tricky **cascade, specificity, and inheritance rules**. 

  - List your selectors in functional groups. For instance, put all of the header-specific selectors together, all of the article-specific selectors, etc.--try to keep things grouped by function, and you will probably do fine. 
  - If one or more selectors don't seem to work, start looking at the cascade, specificity, and inheritance rules. Linters like stylelint can detect potential problems and save you a great deal of debugging time.

- Avoid using tag/type selectors (`h1`, `p`, etc.) and ID selectors (`#title`) as much as possible. Note that the specificity rules give tag selectors the lowest priority and ID selectors the highest. 

  - Therefore, if you have the following code:

  ```html
  <h1 class="heading" id="my-heading">Hello</h1>
  ```

  ```css
  h1 { color: red; }
  #my-heading { color: blue; }
  .heading { color: green; }
  ```

  then the `#my-heading` selector will win out, and the heading will be blue. 

  - If you use class selectors as much as possible, you will have fewer specificity issues to worry about.

## CSS Coding Practices

Similar to those for HTML, the coding practices for CSS focus on keeping code lean and well organized. CSS also has some additional principles regarding how to work with some of the intricacies of the language.

### Organize Code with Comments

- CSS files can become quite extensive, spanning hundreds of lines. These large files can make finding and editing our styles nearly impossible. Let’s keep our styles organized in logical groups. 
- Then, before each group, let’s provide a comment noting what the following styles pertain to.

- Should we wish, we can also use comments to build a table of contents at the top of our file. Doing so reminds us—and others—exactly what is contained within the file and where the styles are located.

Bad Code

```css
header { ... }
article { ... }
.btn { ... }
```

Good Code

```css
/* Primary header */
header { ... }

/* Featured article */
article { ... }

/* Buttons */
.btn { ... }   
```

### Write CSS Using Multiple Lines & Spaces

- When writing CSS, it is important to place each selector and declaration on a new line. Then, within each selector we’ll want to indent our declarations.

- After a selector and before the first declaration comes the opening curly bracket, `{`, which should have a space before it. Within a declaration, we need to put a space after the colon, `:`, that follows a property and end each declaration with a semicolon, `;`.

Doing so makes the code easy to read as well as edit. When all of the code is piled into a single line without spaces, it’s hard to scan and to make changes.

Bad Code

```css
a,.btn{background:#aaa;color:#f60;font-size:18px;padding:6px;}
```

Good Code

```css
a,
.btn {
  background: #aaa;
  color: #f60;
  font-size: 18px;
  padding: 6px;
}      
```

------

#### Comments & Spacing

- These two recommendations, organizing code with comments and using multiple lines and spaces, are not only applicable to CSS, but also to HTML or any other language. 
- Overall we need to keep our code organized and well documented. If a specific part of our code is more complex, let’s explain how it works and what it applies to within comments. Doing so helps others working on the same code base, as well as ourselves when we revisit our own code down the road.

------

### Use Proper Class Names

- Class names (or values) should be **modular** and should pertain to content within an element, not appearance, as much as possible. These values should be written in such a way that they resemble the syntax of the CSS language. 
- Accordingly, class names should be all lowercase and should use hyphen delimiters.

Bad Code

```css
.Red_Box { ... }
```

Good Code

```css
.alert-message { ... }         
```

### Build Proficient Selectors

CSS selectors can get out of control if they are not carefully maintained. They can easily become too long and too location specific.

- The longer a selector is and the more prequalifies it includes, the higher specificity it will contain. And the higher the specificity the more likely a selector is to break the CSS cascade and cause undesirable issues.

- Also in line with keeping the specificity of our selectors as low as possible, let’s not use IDs within our selectors. IDs are overly specific, quickly raise the specificity of a selector, and quite often break the cascade within our CSS files. The cons far outweigh the pros with IDs, and we are wise to avoid them.

- Let’s use shorter and primarily direct selectors. Nest them only two to three levels deep, and remove as many location-based qualifying selectors as possible.

Bad Code

```css
#aside #featured ul.news li a { ... }
#aside #featured ul.news li a em.special { ... }1
```

Good Code

```css
.news a { ... }
.news .special { ... }      
```

### Use Specific Classes When Necessary

- There are times when a CSS selector is so long and specific that it no longer makes sense. It creates a performance lag and is strenuous to manage. In this case, using a class alone is advised. While applying a class to the targeted element may create more code within HTML, it will allow the code to render faster and will remove any managing obstacles.

- For example, if an `<em>` element is nested within an `<h1>` element inside of an `<aside>` element, and all of that is nested within a `<section>` element, the selector might look something like aside h1 em. Should the `<em>` element ever be moved out of the `<h1>` element the styles will no longer apply. A better, more flexible selector would use a class, such as text-offset, to target the `<em>` element.

Bad Code

```css
section aside h1 em { ... }   
```

Good Code

```css
.text-offset { ... }
```

### Use Shorthand Properties & Values

- One feature of CSS is the ability to use shorthand properties and values. Most properties and values have acceptable shorthand alternatives. 
  - As an example, rather than using four different `margin`-based property and value declarations to set the margins around all four sides of an element, use one single `margin` property and value declaration that sets the values for all four sides at once. 
  - Using the shorthand alternative allows us to quickly set and identify styles.

- When we’re only setting one value, though, shorthand alternatives should not be used. 
  - If a box only needs a bottom `margin`, use the `margin-bottom` property alone. Doing so ensures that other margin values will not be overwritten, and we can easily identify which side the `margin` is being applied to without much cognitive effort.

Bad Code

```css
img {
  margin-top: 5px;
  margin-right: 10px;
  margin-bottom: 5px;
  margin-left: 10px;
}
button {
  padding: 0 0 0 20px;
}         
```

Good Code

```css
img {
  margin: 5px 10px;
}
button {
  padding-left: 20px;
}       
```

### Use Shorthand Hexadecimal Color Values

- When available, use the three-character shorthand hexadecimal color value, and always use lowercase characters within any hexadecimal color value. 
- The idea, again, is to remain consistent, prevent confusion, and embrace the syntax of the language the code is being written in.

Bad Code

```css
.module {
  background: #DDDDDD;
  color: #FF6600;
}         
```

Good Code

```css
.module {
  background: #ddd;
  color: #f60;
}
```

### Drop Units from Zero Values

One way to easily cut down on the amount of CSS we write is to remove the unit from any zero value. No matter which length unit is being used—pixels, percentages, em, and so forth—zero is always zero. Adding the unit is unnecessary and provides no additional value.

Bad Code

```css
div {
  margin: 20px 0px;
  letter-spacing: 0%;
  padding: 0px 5px;
}          
```

Good Code

```css
div {
  margin: 20px 0;
  letter-spacing: 0;
  padding: 0 5px;
}        
```

### Group & Align Vendor Prefixes

With CSS3, vendor prefixes gained some popularity, adding quite a bit of code to CSS files. The added work of using vendor prefixes is often worth the generated styles; however, they have to be kept organized. In keeping with the goal of writing code that is easy to read and modify, 

- it’s best to group and indent individual vendor prefixes so that the property names stack vertically, as do their values.

- Depending on where the vendor prefix is placed, on the property or the value, the alignment may vary. 

For example, the following good code keeps the `background` property aligned to the left, while the prefixed `linear-gradient()` functions are indented to keep their values vertically stacked. Then, the prefixed `box-sizing` property is indented as necessary to keep the `box-sizing` properties and values vertically stacked.

As always, the objective is to make the styles easier to read and to edit.

Bad Code

```css
div {
  background: -webkit-linear-gradient(#a1d3b0, #f6f1d3);
  background: -moz-linear-gradient(#a1d3b0, #f6f1d3);
  background: linear-gradient(#a1d3b0, #f6f1d3);
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}       
```

Good Code

```css
div {
background: -webkit-linear-gradient(#a1d3b0, #f6f1d3);
background:    -moz-linear-gradient(#a1d3b0, #f6f1d3);
background:         linear-gradient(#a1d3b0, #f6f1d3);
-webkit-box-sizing: border-box;
   -moz-box-sizing: border-box;
        box-sizing: border-box;
}        
```

------

#### Vendor Prefixes

- When using vendor prefixes we need to make sure to place an unprefixed version of our property and value last, after any prefixed versions. 
  - Doing so ensures that browsers that support the unprefixed version will render that style according to its placement within the cascade, reading styles from the top of the file to the bottom.

- The good news is that browsers are largely moving away from using vendor prefixes. Over time this will become less of a concern; however, for now we’re well advised to double-check which styles require a vendor prefix and to keep those prefixes organized.

------

### Modularize Styles for Reuse

- CSS is built to allow styles to be reused, specifically with the use of classes. For this reason, styles assigned to a class should be modular and available to share across elements as necessary.

> **modular** in css means the practice of breaking down the styles for a website or application into smaller, reusable parts or modules.

If a section of news is presented within a box that includes a border, background color, and other styles, the class of `news` might seem like a good option. However, those same styles may also need to be applied to a section of upcoming events. The class of `news` doesn’t fit in this case. A class of `feat-box` would make more sense and may be widely used across the entire website.

Bad Code

```css
.news {
  background: #eee;
  border: 1px solid #ccc;
  border-radius: 6px;
}
.events {
  background: #eee;
  border: 1px solid #ccc;
  border-radius: 6px;
}     
```

Good Code

```css
.feat-box { /* feature box*/
  background: #eee;
  border: 1px solid #ccc;
  border-radius: 6px;
}
```

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