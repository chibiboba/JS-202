# Testing and Validation

1. Update your code.
2. Test the results in your browser.
3. Validate your HTML.
4. Validate your CSS.
5. **Check your page on other browsers.**
6. Go back to step 1.

Step 5 is new: different browsers and browser versions use different defaults for CSS styles and sometimes process HTML differently, which can lead to discrepancies when you view a site in another browser. 

- CSS resets (discussed later) and using the W3C validators help avoid these issues, but they don't prevent them. 

- As a rule, you should periodically check your pages in different browsers depending on which browsers your site intends to support. Checking for cross-browser issues is crucial if your app must work on phones, tablets, and older browsers. Check for cross-browser problems often; it can be hard to pin down the cause of a problem if you wait until the end of the project.

# What to Focus On

**CSS box model** describes the mechanism that browsers use to construct a web page from the seemingly unrelated HTML and CSS code. 

- The box model is probably the most crucial concept a web developer needs to understand; without it, you'll soon find yourself playing Whac-A-Mole. 
- Learn what to expect from the browser when it processes your HTML and CSS, and how that changes depending on the visual display model, box-sizing model, and the box properties. 
- Don't skim this lesson: read it several times until you're sure you understand the concepts.

### Vocabulary

You should be able to use the following terms properly when discussing the box model and how it works.

- the box model
  - box properties
    - width and height
    - padding and margins
    - borders
  - visual display models
    - `block`
    - `inline`
    - `inline-block`
  - box sizing model
    - `content-box`
    - `border-box`
- dimensions
  - absolute units
  - relative units

You should be familiar with the following terms, but you're not expected to discuss them in detail.

- container
- physical pixels
- CSS reference pixels

### Box Properties

- Every box has a width, height, padding, border, and margins; know the differences.
- Padding, borders, and margins have separate properties to set the left, right, top, and bottom of each element. You can use shortcut properties to specify all four sides at once.
- How does the visual display model interact with margins, borders, and padding?

### Visual Display Models

- Understand the differences between `inline`, `block`, and `inline-block`.
- Containers are almost always `block` elements, while non-containers are `inline`. When in doubt, check MDN.
- Don't try to memorize which HTML elements are `block` or `inline`.
- How and when can you change an element's visual display model?

### Box Sizing Models

- Understand the `content-box` and `border-box` sizing models.
- How and when can you change the box-sizing model for an element?

### Dimensions

- Know the differences between `px`, `em`, `rem`, `%`, and `auto`.
- Understand why we need to talk about CSS reference pixels and physical pixels. Don't try to memorize the details, but understand the topic well enough that you won't be too surprised the first time you encounter the differences in the wild.
- Use `auto` margins to center block elements horizontally.

### HTML

Don't try to memorize any new HTML elements you meet in this lesson.

### CSS

Become comfortable with the CSS `display`, `box-sizing`, `width`, `height`, `padding`, `border`, and `margin` properties. Memorize this list of properties so you can look up the details when needed.

### Try the Examples

Try all the code examples, but don't copy and paste them. Typing the code will help you develop that much desired "muscle memory" and help you remember the materials.

After trying the code examples, modify them to see what happens. You won't break anything but your pride.

### Using the Documentation

We will ask you several times in this lesson to use HTML elements and CSS properties and selectors that we don't explicitly present to you. We don't expect you to be or become an expert on these implicit topics. However, you should understand them enough to use them in the context presented. For instance, we may ask you to change the appearance of an ordered list; you don't have to know how to construct an ordered list, but you should be able to learn enough to apply a color, for example, to the text of the `<li>` elements inside the list.

Sometimes we'll give you a hint, and sometimes we won't. It's up to you to find the information you need. It may be challenging, but sources are readily available. Use this opportunity to learn how to search for it. It's how junior developers become senior developers.

### Study From The Summary

Spend time with the Summary at the end of this lesson. It reviews the topics and terminology you should master before moving on.

# My notes

# The Box Model

- new line
  - Word processing software ordinarily outputs one character at a time, moving from left-to-right or right-to-left as required by the document's language (we will ignore languages that use vertical text). As each line fills with words, the word processor automatically wraps down to the next line and starts adding characters to the beginning of a new line.
  - Your browser works in much the same way to render HTML pages: it displays "words" one at a time horizontally until it encounters a "word" that doesn't fit. At this point, the browser starts a new **line** -- one or more "words" at the same horizontal level in the current container element.
- Elements
  - **Elements** are objects that the web browser has to deal with and display. Web pages have images, media players, containers (which we'll discuss later), and other kinds of objects.
  - There may be more than one way to determine 

- Box model:
  -  The **box  size** is how much horizontal and vertical space -- a rectangle or **box** -- it needs to draw the item. There's more than one way to determine this size.
  - **CSS box model** or **box model**  describes how the browser calculates the box size for any given element using browser defaults and css.
  - Details: As the browser renders a document, it processes one element at a time. The browser determines the box size it needs to draw the item. It uses the browser defaults and your CSS to calculate the required dimensions. If there's enough horizontal space remaining on the current line, the browser places the element there; otherwise, it starts a new line. Each line uses enough vertical space to contain all its rectangles. This process repeats for every box on the page.
- Summary
  - Every element requires a box-shaped segment of the page.
  - Every character of text content also needs a boxed portion of the page.
  - **Box model**: The browser calculates the dimensions of that box by using the browser defaults and CSS.

# Box Properties

- Every box has a width, height, padding, border, and margins; know the differences.
- Padding, borders, and margins have separate properties to set the left, right, top, and bottom of each element. You can use shortcut properties to specify all four sides at once.
- How does the visual display model interact with margins, borders, and padding?

------

### width and height

- The **width** and **height** define how much horizontal and vertical space it needs for the *content area* of the box, which may or may not include the padding and borders. In most cases, the browser can determine the width and height automatically.

#### Example

To begin, let's assume that the box model treats elements as having a height and width and no other characteristics. Assume we have five elements with the following dimensions:

| Width in pixels | Height in pixels |
| :-------------: | :--------------: |
|       300       |       125        |
|       400       |       200        |
|       100       |       100        |
|       500       |        80        |
|       250       |        60        |

- We also assume that our elements have a `display` property of `inline-block`, which we'll discuss later. 
- For now, you should know that the browser lays out `inline-block` elements side by side up to the page width. If one doesn't fit, the browser starts a new line.

Figure 1 illustrates how this process works when the browser viewport (the part of the window where the browser displays content) is 800 pixels wide. Figure 2 shows the same information when the viewport is 700 pixels wide.

![Box layout at 800 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-1.png)

*Figure 1*: Element flow at 800 pixels

![Box layout at 700 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-2.png)

*Figure 2*: Element flow at 700 pixels

The vertical positioning of side-by-side boxes varies. Figures 1 and 2 show them aligned at the top, but the actual alignment varies based on the content and the CSS settings for each rectangle.

### padding and margins

- The **padding** is an area that surrounds the content area of the box and separates the content from its border. It is typically opaque and hides anything that it overlays.
- The **margin** is a transparent area that lies outside the border and supplies separation between elements.

### borders

- The **border** is a boundary that surrounds the padding.

## Summary

Every element box has the following properties (the browser may ignore some of them):

- The **width** and **height** define how much horizontal and vertical space it needs for the *content area* of the box, which may or may not include the padding and borders. In most cases, the browser can determine the width and height automatically.
- The **padding** is an area that surrounds the content area of the box and separates the content from its border. It is typically opaque and hides anything that it overlays.
- The **border** is a boundary that surrounds the padding.
- The **margin** is a transparent area that lies outside the border and supplies separation between elements.
- The **display** property determines how the browser lays out an element relative to its neighbors.

Pictorially, it looks like this:



![Chrome's box model](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/chrome_box_model.png)



This diagram shows an element that has a content area that:

- is 928 pixels wide and 168 high,
- has 10 pixels each of top and bottom padding plus 20 pixels each of left and right padding,
- has a border that is 1 pixel thick,
- has a 28-pixel bottom margin (the left, right, and top margins are 0).

You can see this diagram, or one like it, in the element inspector for your browser. The width, height, padding, border, and margin attributes can all take values of 0 - the box model allows this and collapses the box around the zeroed item.

# Visual Display Models

- Understand the differences between `inline`, `block`, and `inline-block`.
- Containers are almost always `block` elements, while non-containers are `inline`. When in doubt, check MDN.
- Don't try to memorize which HTML elements are `block` or `inline`.
- How and when can you change an element's visual display model?

------

## **Visual formatting model**

- How a browser lays out its elements is determined by the `display` property. The `display` property has more than two dozen values, but most CSS uses the values `block`, `inline`, and `inline-block`. We call this property the visual formatting model.
- Assumption: When we discussed how the browser lays out elements, our stated assumption was that all boxes have a `display` property of `inline-block`. We chose that property value since it's easy to understand, and best demonstrates how page layout works in a browser. 

### `block`

<u>Definition</u>

- [Block elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) appear on almost all web pages: headings, paragraphs, sections, tables, forms, lists, and more are `block` elements.

- Most `block` elements group one or more elements - some of which may themselves be `block`s - into areas of the page. 

  - For instance, `header` elements group together elements into a page header. 
  - **Containers** are  `block` elements such as a `header` that contain one ore more elements. The master container (the outermost) is the `body`; every other element belongs to a container.

  - We sometimes use the term **parent** to refer to a container, and use **child** to describe an element contained within a container. These relationship terms also let us talk about grandparents, ancestors, descendants, siblings, cousins, etc..

<u>Common Block Elements</u>

- Most elements are `block` elements by default. Here are some of the most common:

  - `section`, `article`, `aside`, `header`, `footer`

  - `p`

  - `h1` through `h6`

  - `blockquote`

  - `ul`, `ol`, `dl`

  - `figure` and `figcaption`

  - `form` and `fieldset`
  - See [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements) for a complete list of block elements.

<u>Spacing / Flow</u>

- Block-level elements begin on a new line, stacking one on top of the other, and occupy any available width. 
- By default, a `block` element occupies all horizontal space available within its container, with nothing to the left or right of the `block`. 
  - If your page contains 3 `block` elements directly inside the `body` element and nothing else, then all three elements will display one above the other like a stack of blocks. 
  - This behavior makes `block` elements predictable and easy to use.

<u>Box properties</u>

- `block` elements use the **box properties** (`width`, `height`, `padding`, `border`, `margin`) to determine the size of the element. The browser reserves a box of the right size on the page, and this is where it draws the content. 
  - If you want an element that is 928 pixels wide, 168 pixels high, with 20 pixels of left and right padding, 10 pixels of padding at the top and bottom, a 1-pixel border, and a 28-pixel bottom margin, all those properties will play a part in the overall dimensions of the element. 
  - Thus, the overall dimensions will be 970 x 218 pixels. (As we'll see later, it's possible to change the way the browser calculates the dimensions. This example assumes that you're using the browser defaults)
- Though a `block` element takes up an entire row in a container, this does not alter the width of the element. The browser renders the `block` element on a line by itself, but the element has the specified (or computed) width. 
  - For example, if you have a 500-pixel wide `blockquote` in a 900-pixel wide `section`, the `blockquote` element uses 500 pixels, but the browser will leave the remaining 400 pixels of the `section` empty.

<u>Width and height includes padding and border</u>

- As we'll see later, the `width` and `height` of an element may include the `padding` and `border` in addition to the content area. By default, `width` and `height` exclude the `padding` and `border` from the measured content area. We'll learn more about this fact in the next assignment when we learn about box sizing.

<u>Width and height excludes margins</u>

- Another item of note is that the height and width values never include the margins. Technically, margins provide spacing between elements but are not part of them. However, you do need to account for the margins when determining whether an item will fit in a given space.

<u>Convert element to `block`</u>

- You can convert any element to a `block` element with the `display: block` CSS property. It's common to render links (`a`) and images (`img`) as `block` elements.

### `inline`

- [Inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements) provide a small bit of semantic meaning to content; browsers use this to alter the way they display small sections of text, which, in turn, helps the reader spot specific items with ease. 
  - For instance, if you want to use bolded text for definitions, you can use the `b` element to render definitions in boldface. The reader can see at a glance where the definitions are in the document. By default, `b` is an `inline` element.

- The following elements are `inline` by default.

  - `span`

  - `b`, `i`, `u`, `strong`, `em`

  - `a`

  - `sub` and `sup`

  - `img`: It's a common misbelief that images (`img`) are `inline-block` elements; in fact, they are `inline` elements.
  - See [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements) for a complete list. Four elements from this list, `button`, `input`, `select`, and `textarea` may, in fact, default to `inline-block` instead of `inline`, but this depends on the browser. See the section on `inline-block` elements below.


<u>Vertical Alignment</u>

- Browsers perform vertical alignment for adjacent  `inline` elements. 

<u>Flow</u>

- `inline` elements flow from one line to the next, which lets you place `inline-block` elements side by side with other `inline` or `inline-block` elements.
- The main idea is that the left/right factors affect the **flow**, while the top and bottom do not.

![Box layout at 800 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-1.png)

*Figure 1*: Element flow at 800 pixels

![Box layout at 700 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-2.png)

*Figure 2*: Element flow at 700 pixels

<u>`inline` elements and dimension properties</u>

- `inline` elements handle the dimension properties (`width`, `height`, `padding`, `border`, and `margin`) differently from the way `block` elements treat them. This difference is where the box model starts to get messy.

- Browsers handle *left* and *right* margins and padding for `inline` elements in the same way as for `block` elements, but they process other box model properties differently. For `inline` elements, browsers:

  - *ignore* the `width` and `height` properties (except with the `img` element), but instead use values computed from the element content.

  - *ignore* top and bottom margins.

  - *don't ignore* borders, but the results may look odd (see the next section).

  - *don't ignore* top and bottom padding, but you won't notice this unless you have a border or background.


<u>Convert element to `inline` element</u>

- You can convert any element to an `inline` element with the `display: inline` CSS property. The most common reason to do so is to override a prior declaration.

#### Borders, Padding, Margins, and Inline Elements

Consider the following HTML and CSS and the associated output:

```html
<p>
  Deserunt ad eu dolor in nostrud eu. Aliqua ad veniam magna et nostrud. Non ea
  sunt. <em>Magna aliqua nostrud et laboris fugiat.</em> Ea nostrud non laboris.
  Quis sunt dolore esse pariatur velit minim cillum ipsum.
</p>
```

```css
p {
  background-color: #d4f0f8;
  border: 1px solid #2db7e1;
  box-sizing: border-box;
  font-size: 1.5rem;
  padding: 0.5em;
  width: 780px;
}

em {
  background-color: rgba(255, 255, 0, .5);
  border: 30px solid rgba(255, 0, 64, .5);
  margin: 40px;
  padding: 30px;
}
```



![Inline borders, padding, and margins](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/the-visual-formatting-model-01.png)

This example demonstrates how browsers handle borders, padding, and margins with `inline` elements. 

- The border for `<em>` is in orange. The padding is yellow. The margin is transparent, but you can see that it plainly affects the text to the left and right of the `em` element.
- The presence of the orange and yellow areas shows that the `em` element has padding and a border on all four sides, but the text above and below the element ignores them. 
  - In fact, through the magic of CSS opacity (transparency), we can see the `em` border and padding overlay the text above it, while the content below it overlays the border and padding.

Top & bottom borders extend beyond boundaries

- One more item to note here is that the top and bottom borders extend beyond the boundaries of the `p` element. The padding would do that as well if we increased it by a few more pixels.

- You need to understand this behavior more as something to avoid than to make use of it. You can waste a lot of time trying to use borders, padding, and margins with inline elements when you're not expecting this behavior. 

- The main idea is that the left/right factors affect the **flow**, while the top and bottom do not.

### `inline-block`

> Legacy Model
>
> - The `inline-block` visual display model is a *legacy* model. It is equivalent to a new model called `inline flow-root`. 
> - However, despite its legacy status, `inline-block` is probably not going to go away anytime soon; there are too many websites that still use it. 
> - We will use `inline-block` throughout this course; it will probably be several years before `inline flow-root` and other new display models gain traction.

- `inline-block` elements are a mixture of both previous types. They act like `block` elements, except for one significant detail: `inline-block` elements do not take up an entire row when the `width` property is less than the available width. 

<u>Flow</u>

- Similar to `inline` elements : flow in the same way that text and `inline` elements flow from one line to the next (see Figures 1 and 2 on the previous page), which lets you place `inline-block` elements side by side with other `inline` or `inline-block` elements.

<u>`inline-block` with dimension properties</u>

- Similar to  block elements but different from `inline` elements :   `inline-block` elements observe the `width` and `height` properties. 
- Similar to block elements: The padding, borders, and margin are used to determine the size of the element. 

<u>Vertical Alignment</u>

- Browsers perform vertical alignment for adjacent `inline-block` elements as well as ordinary `inline` elements. 

The next three examples illustrate three of the available alignments; all three use the same HTML and CSS except for the `vertical-align` property.

```html
<div>
  <p>
    Occaecat sunt nulla esse. Est cupidatat fugiat sit mollit.  Sunt in velit
    mollit deserunt veniam.
  </p>
  <p>
    Aliquip dolor aliqua consequat ullamco exercitation anim.  Dolor voluptate
    irure eiusmod cillum consectetur enim excepteur mollit mollit. Do proident
    ipsum dolore. Et aliqua veniam ex laborum aliquip cupidatat excepteur.
  </p>
</div>
```

```css
div {
  background-color: #c0ffc0;
  border: 1px solid green;
  padding: 10px;
}

p {
  background-color: white;
  border: 1px solid blue;
  display: inline-block;
  margin: 0 2%;
  padding: 10px;
  vertical-align: bottom;
  width: 40%;
}
```

![Bottom alignment](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/the-visual-formatting-model-02.png)

```css
p {
  vertical-align: middle;
}
```

![Middle alignment](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/the-visual-formatting-model-03.png)

```css
p {
  vertical-align: top;
}
```

![Top alignment](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/the-visual-formatting-model-04.png)

<u>Browser chooses the visual display model</u>

- The browser has some choice between using `inline` or `inline-block` as the default `display` property for an element type. In most cases, all browsers agree, but there are exceptions. 
- For instance, Chrome and Safari treat `input` and `textarea` elements as `inline-block`, while Firefox treats them as `inline` elements. This inconsistency typically isn't a problem. When it is, you can explicitly set the `display` property:

```css
input, textarea {
  display: inline-block;
}
```

- It's a common misbelief that images (`img`) are `inline-block` elements; in fact, they are `inline` elements.

<u>Convert element to `inline-block`</u>

- You can convert any element to an `inline-block` element with the `display: inline-block` CSS property. 
- A useful application for this is to arrange the contents of a list horizontally instead of vertically; horizontal navigation bars often use list elements defined as `inline-block`.

## Nesting Elements and the Visual Display Model

- HTML lets you nest elements inside other elements; it's built-in to the syntax of the language. However, such nesting is not uncontrolled. 
  - For instance, you can't nest `block` and `inline-block` elements within `inline` elements.
  - Thus, you can put an `em` (inline) inside a `blockquote` (block), but you can't put a `blockquote` in an `em`.

- There is one exception to this rule: you can nest `block` and `inline-block` elements inside an `a` tag provided the block does not include interactive elements like `input`, `button`, `select`, `textarea`, or another `a` tag. In practice, you will probably not use this feature.

- Your browser may render improperly nested elements the way you want them to appear, but you should not rely on that behavior; other browsers or browser versions may not. If W3C complains about nesting, you should correct it in most cases. (Late in this course we will see one situation in which we will ignore W3C's advice on this matter.)

- Beware of invalid nesting as well. Most browsers will render both of these snippets the way the developer intended:

```html
<strong><em>This is strong emphasized text</em></strong>
```

```html
<strong><em>This is strong emphasized text</strong></em>
```

However, the second will fail W3C validation; one pair of open/close tags should nest entirely inside the other. You should never ignore a warning about this type of mis-nesting.

## Other Visual Display Models

- As mentioned earlier, there are around two dozen visual display models. Some show up in routine development. 
  - For instance, list items default to a `list-item` display model, while table cells have a `table-cell` display model. 
  - You won't use these models a lot in practice, so don't bother trying to memorize them. However, some of the variants are sometimes useful. Let an expert tell you when.

- Two newer `display` properties have seen widespread growth in recent years (as of 2022): `flex` and `grid`. 
  - These properties solve a lot of design problems that plague front-end developers today. As of late 2022, `flex` is available for over 99% of all browsers, while `grid` lags a bit at 96%.
  - We'll introduce both in a later lesson, but consider learning more on your own.

# Box Sizing Model

- Understand the `content-box` and `border-box` sizing models.
- How and when can you change the box-sizing model for an element?

------

### `content-box`

### `border-box`

# Dimensions

- Know the differences between `px`, `em`, `rem`, `%`, and `auto`.
- Understand why we need to talk about CSS reference pixels and physical pixels. Don't try to memorize the details, but understand the topic well enough that you won't be too surprised the first time you encounter the differences in the wild.
- Use `auto` margins to center block elements horizontally.

------

## absolute units

## relative units

## Other terms

#### container

#### physical pixels

#### CSS reference pixels

# CSS Properties

Become comfortable with the CSS `display`, `box-sizing`, `width`, `height`, `padding`, `border`, and `margin` properties. Memorize this list of properties so you can look up the details when needed.

------

- `display`

- ``box-sizing`

-  `width`

-  `height`

- `padding`

- `border`

- and `margin` 