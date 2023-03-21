# Lesson 2: The Box Model

# Introduction

In this lesson, we'll discuss some fundamental CSS concepts, namely the different types of display objects, dimensions and spacing, and, most importantly, the Box Model. Without a solid understanding of these concepts, CSS may seem like a game of [Whac-A-Mole](https://en.wikipedia.org/wiki/Whac-A-Mole):



![Whac-A-Mole](http://i.imgur.com/uxipJQU.gif)



If you don't want to play Whac-A-Mole, you must master the fundamentals of CSS and understand why and how it works.

## Testing and Validation

In this lesson, we will stop telling you to display or validate your pages. Testing and validation should be a habit; don't wait for us to ask.

1. Update your code.
2. Test the results in your browser.
3. Validate your HTML.
4. Validate your CSS.
5. **Check your page on other browsers.**
6. Go back to step 1.

Step 5 is new: different browsers and browser versions use different defaults for CSS styles and sometimes process HTML differently, which can lead to discrepancies when you view a site in another browser. CSS resets (discussed later) and using the W3C validators help avoid these issues, but they don't prevent them. As a rule, you should periodically check your pages in different browsers depending on which browsers your site intends to support. Checking for cross-browser issues is crucial if your app must work on phones, tablets, and older browsers. Check for cross-browser problems often; it can be hard to pin down the cause of a problem if you wait until the end of the project.

## What to Focus On

This lesson focuses on the CSS box model, which describes the mechanism that browsers use to construct a web page from the seemingly unrelated HTML and CSS code. The box model is probably the most crucial concept a web developer needs to understand; without it, you'll soon find yourself playing Whac-A-Mole. Learn what to expect from the browser when it processes your HTML and CSS, and how that changes depending on the visual display model, box-sizing model, and the box properties. Don't skim this lesson: read it several times until you're sure you understand the concepts.

Use the guidelines below to focus your study and practice as you move through this lesson.

### Vocabulary

As usual with most development topics, there are some new words and concepts you need to know and understand. You should be able to use the following terms properly when discussing the box model and how it works.

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

# Everything is a Box

Word processing software ordinarily outputs one character at a time, moving from left-to-right or right-to-left as required by the document's language (we will ignore languages that use vertical text). As each line fills with words, the word processor automatically wraps down to the next line and starts adding characters to the beginning of a new line.

Your browser works in much the same way to render HTML pages: it displays "words" one at a time horizontally until it encounters a "word" that doesn't fit. At this point, the browser starts a new **line** -- one or more "words" at the same horizontal level in the current container element.

We put "words" in quotes since a browser must deal with more than words: web pages have images, media players, containers (which we'll discuss later), and other kinds of objects. For simplicity and clarity, we'll call these objects **elements** instead of words.

As the browser renders a document, it processes one element at a time. The browser determines how much horizontal and vertical space -- a rectangle or **box** -- it needs to draw the item. It uses the browser defaults and your CSS to calculate the required dimensions. If there's enough horizontal space remaining on the current line, the browser places the element there; otherwise, it starts a new line. Each line uses enough vertical space to contain all its rectangles. This process repeats for every box on the page.

Our description simplifies the rendering process considerably, but this mental model works well enough to help understand the process. The most important takeaways from this description are:

- Every element requires a box-shaped segment of the page.
- Every character of text content also needs a boxed portion of the page.
- The browser calculates the dimensions of that box by using the browser defaults and CSS.

That's a lot of calculating, but computers do that well. Still, even something simple, like determining the size of a box, has more subtlety to it than you might think. How hard can it be to measure the height and width of an element? Well, it's not difficult, but there's more than one way to determine the size. We use the term **CSS box model** or **box model** to describe how the browser calculates the box size for any given element. We will spend most of this lesson learning about the box model; it may be the most fundamental concept in HTML and CSS, so be sure you grasp it.

## Widths and Heights

To begin, let's assume that the box model treats elements as having a height and width and no other characteristics. Assume we have five elements with the following dimensions:

| Width in pixels | Height in pixels |
| :-------------: | :--------------: |
|       300       |       125        |
|       400       |       200        |
|       100       |       100        |
|       500       |        80        |
|       250       |        60        |

We also assume that our elements have a `display` property of `inline-block`, which we'll discuss later. For now, you should know that the browser lays out `inline-block` elements side by side up to the page width. If one doesn't fit, the browser starts a new line.

Figure 1 illustrates how this process works when the browser viewport (the part of the window where the browser displays content) is 800 pixels wide. Figure 2 shows the same information when the viewport is 700 pixels wide.

![Box layout at 800 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-1.png)

*Figure 1*: Element flow at 800 pixels

![Box layout at 700 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-2.png)

*Figure 2*: Element flow at 700 pixels

The vertical positioning of side-by-side boxes varies. Figures 1 and 2 show them aligned at the top, but the actual alignment varies based on the content and the CSS settings for each rectangle.

## Box Properties

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

# The Visual Formatting Model

In the previous section, we introduced the CSS Box Model and discussed how the browser uses it to lay out HTML elements and text in your browser's window. If this was all there was to the story, front-end development would be a simple affair, though nobody would be happy with the result. As it happens, there's more to the CSS Box Model. In this section, we'll learn about the **visual formatting model**.

When we discussed how the browser lays out elements, our stated assumption was that all boxes have a `display` property of `inline-block`. We chose that property value since it's easy to understand, and best demonstrates how page layout works in a browser. In truth, `display` has more than two dozen values, but most CSS uses the values `block`, `inline`, and `inline-block`. We call this property the visual formatting model.

## Block Elements

[Block elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) appear on almost all web pages: headings, paragraphs, sections, tables, forms, lists, and more are `block` elements.

Most `block` elements group one or more elements - some of which may themselves be `block`s - into areas of the page. For instance, `header` elements group together elements into a page header. We often call such `block` elements **containers**. The master container (the outermost) is the `body`; every other element belongs to a container.

> We sometimes use the term **parent** to refer to a container, and use **child** to describe an element contained within a container. These relationship terms also let us talk about grandparents, ancestors, descendants, siblings, cousins, etc..

By default, a `block` element occupies all horizontal space available within its container, with nothing to the left or right of the `block`. If your page contains 3 `block` elements directly inside the `body` element and nothing else, then all three elements will display one above the other like a stack of blocks. This behavior makes `block` elements predictable and easy to use.

`block` elements use the box properties (`width`, `height`, `padding`, `border`, `margin`) to determine the size of the element. The browser reserves a box of the right size on the page, and this is where it draws the content. If you want an element that is 928 pixels wide, 168 pixels high, with 20 pixels of left and right padding, 10 pixels of padding at the top and bottom, a 1-pixel border, and a 28-pixel bottom margin, all those properties will play a part in the overall dimensions of the element. Thus, the overall dimensions will be 970 x 218 pixels. (As we'll see later, it's possible to change the way the browser calculates the dimensions. This example assumes that you're using the browser defaults)

> As we'll see later, the `width` and `height` of an element may include the `padding` and `border` in addition to the content area. By default, `width` and `height` exclude the `padding` and `border` from the measured content area. We'll learn more about this fact in the next assignment when we learn about box sizing.

Another item of note is that the height and width values never include the margins. Technically, margins provide spacing between elements but are not part of them. However, you do need to account for the margins when determining whether an item will fit in a given space.

Though a `block` element takes up an entire row in a container, this does not alter the width of the element. The browser renders the `block` element on a line by itself, but the element has the specified (or computed) width. For example, if you have a 500-pixel wide `blockquote` in a 900-pixel wide `section`, the `blockquote` element uses 500 pixels, but the browser will leave the remaining 400 pixels of the `section` empty.

Most elements are `block` elements by default. Here are some of the most common:

- `section`, `article`, `aside`, `header`, `footer`
- `p`
- `h1` through `h6`
- `blockquote`
- `ul`, `ol`, `dl`
- `figure` and `figcaption`
- `form` and `fieldset`

> See [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements) for a complete list of block elements.

You can convert any element to a `block` element with the `display: block` CSS property. It's common to render links (`a`) and images (`img`) as `block` elements.

## Inline Elements

[Inline elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements) provide a small bit of semantic meaning to content; browsers use this to alter the way they display small sections of text, which, in turn, helps the reader spot specific items with ease. For instance, if you want to use bolded text for definitions, you can use the `b` element to render definitions in boldface. The reader can see at a glance where the definitions are in the document. By default, `b` is an `inline` element.

The following elements are `inline` by default.

- `span`
- `b`, `i`, `u`, `strong`, `em`
- `a`
- `sub` and `sup`
- `img`

> See [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements) for a complete list. Four elements from this list, `button`, `input`, `select`, and `textarea` may, in fact, default to `inline-block` instead of `inline`, but this depends on the browser. See the section on `inline-block` elements below.

`inline` elements handle the dimension properties (`width`, `height`, `padding`, `border`, and `margin`) differently from the way `block` elements treat them. This difference is where the box model starts to get messy. Browsers handle *left* and *right* margins and padding for `inline` elements in the same way as for `block` elements, but they process other box model properties differently. For `inline` elements, browsers:

- *ignore* the `width` and `height` properties (except with the `img` element), but instead use values computed from the element content.
- *ignore* top and bottom margins.
- *don't ignore* borders, but the results may look odd (see the next section).
- *don't ignore* top and bottom padding, but you won't notice this unless you have a border or background.

You can convert any element to an `inline` element with the `display: inline` CSS property. The most common reason to do so is to override a prior declaration.

### Borders, Padding, Margins, and Inline Elements

Consider the following HTML and CSS and the associated output:

```html
<p>
  Deserunt ad eu dolor in nostrud eu. Aliqua ad veniam magna et nostrud. Non ea
  sunt. <em>Magna aliqua nostrud et laboris fugiat.</em> Ea nostrud non laboris.
  Quis sunt dolore esse pariatur velit minim cillum ipsum.
</p>
```

Copy Code

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



This example demonstrates how browsers handle borders, padding, and margins with `inline` elements. Here, the border for the `<em>` is orange and the padding yellow. You can't see the margin since it's transparent, but it plainly affects the text to the left and right of the `em` element. The presence of the orange and yellow areas shows that the `em` element has padding and a border on all four sides, but the text above and below the element ignores them. In fact, through the magic of CSS opacity (transparency), we can see the `em` border and padding overlay the text above it, while the content below it overlays the border and padding.

One more item to note here is that the top and bottom borders extend beyond the boundaries of the `p` element. The padding would do that as well if we increased it by a few more pixels.

You need to understand this behavior more as something to avoid than to make use of it. You can waste a lot of time trying to use borders, padding, and margins with inline elements when you're not expecting this behavior. The main idea is that the left/right factors affect the flow, while the top and bottom do not.

## Inline-Block Elements

> The `inline-block` visual display model is a *legacy* model. It is equivalent to a new model called `inline flow-root`. However, despite its legacy status, `inline-block` is probably not going to go away anytime soon; there are too many websites that still use it. We will use `inline-block` throughout this course; it will probably be several years before `inline flow-root` and other new display models gain traction.

`inline-block` elements are a mixture of both previous types. They act like `block` elements, except for one significant detail: `inline-block` elements do not take up an entire row when the `width` property is less than the available width. Instead, they flow in the same way that text and `inline` elements flow from one line to the next (see Figures 1 and 2 on the previous page), which lets you place `inline-block` elements side by side with other `inline` or `inline-block` elements.

`inline-block` elements also differ from `inline` in that `inline-block` elements observe the `width` and `height` properties. The padding, borders, and margin all work like they do with `block` elements.

Browsers perform vertical alignment for adjacent `inline-block` elements as well as ordinary `inline` elements. The next three examples illustrate three of the available alignments; all three use the same HTML and CSS except for the `vertical-align` property.

Copy Code

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

Copy Code

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



Copy Code

```css
p {
  vertical-align: middle;
}
```



![Middle alignment](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/the-visual-formatting-model-03.png)



Copy Code

```css
p {
  vertical-align: top;
}
```



![Top alignment](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/the-visual-formatting-model-04.png)



The browser has some choice between using `inline` or `inline-block` as the default `display` property for an element type. In most cases, all browsers agree, but there are exceptions. For instance, Chrome and Safari treat `input` and `textarea` elements as `inline-block`, while Firefox treats them as `inline` elements. This inconsistency typically isn't a problem. When it is, you can explicitly set the `display` property:

Copy Code

```css
input, textarea {
  display: inline-block;
}
```

It's a common misbelief that images (`img`) are `inline-block` elements; in fact, they are `inline` elements.

You can convert any element to an `inline-block` element with the `display: inline-block` CSS property. A useful application for this is to arrange the contents of a list horizontally instead of vertically; horizontal navigation bars often use list elements defined as `inline-block`.

## Nesting Elements and the Visual Display Model

HTML lets you nest elements inside other elements; it's built-in to the syntax of the language. However, such nesting is not uncontrolled. For instance, you can't nest `block` and `inline-block` elements within `inline` elements. Thus, you can put an `em` (inline) inside a `blockquote` (block), but you can't put a `blockquote` in an `em`.

There is one exception to this rule: you can nest `block` and `inline-block` elements inside an `a` tag provided the block does not include interactive elements like `input`, `button`, `select`, `textarea`, or another `a` tag. In practice, you will probably not use this feature.

Your browser may render improperly nested elements the way you want them to appear, but you should not rely on that behavior; other browsers or browser versions may not. If W3C complains about nesting, you should correct it in most cases. (Late in this course we will see one situation in which we will ignore W3C's advice on this matter.)

Beware of invalid nesting as well. Most browsers will render both of these snippets the way the developer intended:

Copy Code

```html
<strong><em>This is strong emphasized text</em></strong>
```

Copy Code

```html
<strong><em>This is strong emphasized text</strong></em>
```

However, the second will fail W3C validation; one pair of open/close tags should nest entirely inside the other. You should never ignore a warning about this type of mis-nesting.

## Other Visual Display Models

As mentioned earlier, there are around two dozen visual display models. Some show up in routine development. For instance, list items default to a `list-item` display model, while table cells have a `table-cell` display model. You won't use these models a lot in practice, so don't bother trying to memorize them. However, some of the variants are sometimes useful. Let an expert tell you when.

Two newer `display` properties have seen widespread growth in recent years (as of 2022): `flex` and `grid`. These properties solve a lot of design problems that plague front-end developers today. As of late 2022, `flex` is available for over 99% of all browsers, while `grid` lags a bit at 96%. We'll introduce both in a later lesson, but consider learning more on your own.

# Box Sizing

Take a few minutes now to read this article on [Box Sizing](https://css-tricks.com/box-sizing/).

The linked article talks about Microsoft's Quirks mode. What it doesn't mention, except through yet another link, is that before Quirks mode, Microsoft Internet Explorer ran full-time in what became Quirks mode, and later still became the border-box box-sizing mode.

Officially, Microsoft's original implementation was a bug. It caused compatibility problems with other browsers, enough so that a lot of sites sported "Made for Microsoft Internet Explorer!" or "Best with Netscape Navigator!" logos because it was impossible to get a consistent appearance between Internet Explorer and the rest of the browsers. When Microsoft fixed the bug, it left the old mode available as a way to maintain backward compatibility and called it Quirks mode.

After all that, Microsoft got the last laugh, though. While content-box box-sizing remains the default, developers today often recognize the value of border-box and prefer it.

The important takeaways here are:

- The usable `box-sizing` property values are `content-box`, and `border-box`. The CSS standard deprecates the `padding-box` setting; **don't use it**.

- The `content-box` setting is the default setting for the `box-sizing` property for all elements in all modern browsers. In this model, the `width` and `height` properties specify the size of the actual content area. You need to add padding and borders to get the size of the visible box.

- The `border-box` setting causes the browser to interpret the `width` and `height` properties as the total width and height of the box excluding the margins. That is, the width and height include the content area as well as the padding and borders.

- The `border-box` setting is "best" since it simplifies the math a front-end developer must do. For example, if we have a box with a width of 50% and padding of 12px; `border-box` ensures that it's precisely 50% of the container width, not 50% plus 24 pixels.

- If you want to use border-box pretty much everywhere, you can add the following to your CSS:

  Copy Code

  ```css
  html {
    box-sizing: border-box;
  }
  
  *, *::before, *::after {
    box-sizing: inherit;
  }
  ```

  See [this article](https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice/) for an explanation of this code. Note that the article uses the old-style single colon to specify the pseudo-elements `before` and `after`; modern usage suggests a double colon.

# Practice Problems: The Box Model

This problem set will exercise your understanding of how a browser uses the box model to compute how much horizontal and vertical space it needs for each element. It focuses on the `width`, `height`, `padding`, `border`, and `margin` properties, as well as how the visual display model and the box-sizing mode interact with them.

1. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `img` element (including its margins)?

   Copy Code

   ```html
   <div>
     <img src="#" alt="test">
   </div>
   ```

   Copy Code

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: border-box;
     display: inline-block;
     margin: 0;
     padding: 0;
   }
   
   img {
     border: 4px solid red;
     box-sizing: content-box;
     display: inline-block;
     height: 300px;
     margin: 20px 19px 10px 11px;
     padding: 10px 20px;
     width: 500px;
   }
   ```

   Solution

   Since the `img` has `display: inline-block`, we can compute the dimensions directly from the CSS properties. The `div` element needs 580 pixels horizontally:

   - 500 pixels for the width
   - 8 pixels for the left and right borders
   - 40 pixels for the left and right padding
   - 11 pixels for the left margin
   - 19 pixels for the right margin
   - 2 pixels for the left and right borders of the `div`

   The `div` needs 360 pixels vertically:

   - 300 pixels for the height
   - 8 pixels for the top and bottom borders
   - 20 pixels for the top and bottom padding
   - 20 pixels for the top margin
   - 10 pixels for the bottom margin
   - 2 pixels for the top and bottom borders of the `div`

   Since the `div` uses `border-box` box-sizing, it must have a width and height of at least 580px and 360px, respectively.

   While we don't typically count margins in determining an element's height and width, we need to include them here when calculating how much space we need in the `div`.

2. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `section` element (including its margins)? How does this differ from the result of the previous practice problem?

   Copy Code

   ```html
   <div>
     <section>content</section>
   </div>
   ```

   Copy Code

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: border-box;
     display: inline-block;
     margin: 0;
     padding: 0;
   }
   
   section {
     border: 4px solid red;
     box-sizing: content-box;
     display: block;
     height: 300px;
     margin: 20px 19px 10px 11px;
     padding: 10px 20px;
     width: 500px;
   }
   ```

   Solution

   Since the `section` element is a `block` element, we can compute the dimensions directly from the CSS properties. The `div` element needs 580 pixels horizontally:

   - 500 pixels for the width
   - 8 pixels for the left and right borders
   - 40 pixels for the left and right padding
   - 11 pixels for the left margin
   - 19 pixels for the right margin
   - 2 pixels for the left and right borders of the `div`

   The `div` needs 360 pixels vertically:

   - 300 pixels for the height
   - 8 pixels for the top and bottom borders
   - 20 pixels for the top and bottom padding
   - 20 pixels for the top margin
   - 10 pixels for the bottom margin
   - 2 pixels for the top and bottom borders of the `div`

   Since the `div` uses `border-box` box-sizing, it must have a width and height of at least 580px and 360px, respectively. These values are identical to the answer from the previous practice problem. The chief difference is that other elements may appear adjacent to the `img` in problem 1, while the `section` in this problem will always be on a line by itself within the `div` no matter its width.

3. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `em` element (including its margins)?

   Copy Code

   ```html
   <div>
     <em>content</em>
   </div>
   ```

   Copy Code

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: border-box;
     display: inline-block;
     margin: 0;
     padding: 0;
   }
   
   em {
     border: 4px solid red;
     box-sizing: content-box;
     display: inline;
     height: 300px;
     margin: 20px 19px 10px 11px;
     padding: 10px 20px;
     width: 500px;
   }
   ```

   Solution

   This code is a bit tricky. Since the `em` element is `inline`, the browser will ignore the width, height, and top and bottom margins specified in the CSS. For this reason, we cannot calculate the amount of space that any given `em` will take unless we know the actual width and height of the content.

   If we assume that the `em` requires a 50px width, then the `div` element needs 130 pixels horizontally:

   - 50 pixels for the assumed width
   - 8 pixels for the left and right borders
   - 40 pixels for the left and right padding
   - 11 pixels for the left margin
   - 19 pixels for the right margin
   - 2 pixels for the left and right borders of the `div`

   If we assume that the `em` requires a 20px height, then the `div` needs 50 pixels vertically:

   - 20 pixels for the assumed height
   - 8 pixels for the top and bottom borders
   - 20 pixels for the top and bottom padding
   - 0 pixels for the top and bottom margins
   - 2 pixels for the top and bottom borders of the `div`

   Since the `div` uses `box-sizing`, it must have a `width` of at least 130px and a height of at least 50px.

   Keep in mind that the top and bottom padding and borders may intersect with content above and below the `em` element.

4. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to be to entirely contain the `article` element (including its margins)?

   Copy Code

   ```html
   <div>
     <article>content</article>
   </div>
   ```

   Copy Code

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: border-box;
     display: inline-block;
     margin: 0;
     padding: 0;
   }
   
   article {
     border: 4px solid red;
     box-sizing: border-box;
     display: inline-block;
     height: 300px;
     margin: 20px 19px 10px 11px;
     padding: 10px 20px;
     width: 500px;
   }
   ```

   Solution

   Since the `article` is `inline-block`, we can compute the dimensions directly from the CSS properties. Since we also set the `box-sizing` property to `border-box`, we must ignore the padding and border to calculate the actual dimensions. The `div` element needs 532 pixels horizontally:

   - 500 pixels for the width
   - 0 pixels for the left and right borders
   - 0 pixels for the left and right padding
   - 11 pixels for the left margin
   - 19 pixels for the right margin
   - 2 pixels for the left and right borders of the `div`

   The `div` needs 332 pixels vertically:

   - 300 pixels for the height
   - 0 pixels for the top and bottom borders
   - 0 pixels for the top and bottom padding
   - 20 pixels for the top margin
   - 10 pixels for the bottom margin
   - 2 pixels for the top and bottom borders of the `div`

   Since the `div` uses `box-sizing`, it must have a `width` of at least 532px and a height of at least 332px.

5. Given the code below:

   Copy Code

   ```html
   <div>
     <tag1>content</tag1><tag2>content</tag2>
   </div>
   ```

   Copy Code

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: content-box;
     display: inline-block;
     margin: 0;
     padding: 0;
     width: 720px;
   }
   
   tag1, tag2 {
     box-sizing: border-box;
     height: 240px;
     margin: 0;
     padding: 0;
     width: 360px;
   }
   
   tag1 {
     background-color: yellow;
   }
   
   tag2 {
     background-color: lime;
   }
   ```

   Which of the following element pairs will display side by side in the `<div>`? Select all that apply:

   1. Both elements are `block` elements.
   2. Both elements are `inline` elements.
   3. Both elements are `inline-block` elements.
   4. One element is a `block` element, and one is an `inline` element.
   5. One element is a `block` element, and one is an `inline-block` element.
   6. One element is an `inline` element, and one is an `inline-block` element.

   You may assume that any `inline` element has a **content width** of no more than 360 pixels. Remember, the `width` property doesn't affect `inline` elements, so this "content width" is the actual width of the content area as determined by your browser.

   Solution

   Combinations (2), (3), and (6) will all appear side by side. The other three combinations have `block` elements which never appear side by side with anything.

6. Will the following code display the two article boxes side by side? If not, why not? How would you fix it so that it places the boxes side by side?

   Copy Code

   ```html
   <section>
     <article>content</article><article>more content</article>
   </section>
   ```

   Copy Code

   ```css
   section {
     background-color: yellow;
     border: 1px solid red;
     box-sizing: content-box;
     display: inline-block;
     height: 400px;
     margin: 0;
     padding: 20px;
     width: 900px;
   }
   
   article {
     background-color: lime;
     border: 1px solid blue;
     height: 100%;
     margin: 0;
     padding: 10px;
     width: 50%;
   }
   ```

   Hide

   The browser won't display the article boxes side by side since they are `block` elements. Even if we could place the `block` elements side by side, they won't fit inside the section because the total width of each article is 50% of the width plus 22 pixels for its padding and border.

   The first change we must make is to add `display: inline-block;` to the CSS `article` selector, which lets us position two or more articles side by side, provided there is room. To make them fit, we must set the actual width (including padding and the border) to 50% of the available space, so we also add `box-sizing: border-box;` to the `article` selector.

   Copy Code

   ```css
   article {
     background-color: lime;
     border: 1px solid blue;
     box-sizing: border-box;
     display: inline-block;
     height: 100%;
     margin: 0;
     padding: 10px;
     width: 50%;
   }
   ```

   Now both article boxes appear inside the section box, side by side.

7. **Challenge.** Given our solution to the previous question, what will happen if we put the `article` tags on separate lines?

   Copy Code

   ```html
   <section>
     <article>content</article>
     <article>more content</article>
   </section>
   ```

   Try to figure out the answer without peeking. Why do you think this is?

   Solution

   When you put the `article` elements on separate lines in the HTML, the browser sees the whitespace (a newline and several spaces in this case) between the two articles. It then collapses that whitespace into a single space character and uses the result as content between the elements. Thus, the two articles require 900 pixels total plus a few more pixels to account for the space character. Since that exceeds the 900-pixel width of the `section`, the two `article`s no longer fit on the same line.

   This kind of problem often occurs when one of the elements is an inline-block; the rest of the time, the extra space typically doesn't matter. Aside from placing the two tags up against each other to eliminate the whitespace, there are several other techniques you will see later that let you remove the space or make it invisible.

# Padding and Margins

Beginners often get confused by padding and margins. After all, both provide whitespace that surrounds an element. In this assignment, we'll learn the differences and how and when you should use each.

## What is the Difference Between Padding and Margins?

Both padding and margins surround elements with whitespace. Padding lies inside the border, while margins lie outside it. What if you don't have one? You do - it has zero-width, so it's an invisible border, but the browser knows it's there and uses it in the box model.

Margins are typically transparent, while the padding is opaque.

Put another way, padding is part of the visible and clickable bounds of an element, while a margin is spacing between adjacent elements. It's easy to see this with clickable elements. If you click on the content area or anywhere in the padding or border, the browser will process the click. If you click on the margin, nothing happens. Consider this example:

Copy Code

```html
<!--
Don't worry about contents of this <script> tag: it is JavaScript. We need it to
implement the color toggle, but you don't need to understand it right now.
You'll learn all about JavaScript in future courses.
-->
<script>
  var article = {
    toggleColor: function() {
      document.querySelector('article').classList.toggle('toggled');
    }
  };
</script>

<!--
The onclick attribute on the article tag causes the browser to run the
JavaScript above when the user clicks the <article> element. Don't bother
memorizing this right now.
-->
<section>
  <article onclick="article.toggleColor();">
    Click here
  </article>
</section>
```

Copy Code

```css
section {
  background-color: #ffc0c0;
  border: 1px solid black;
  height: 300px;
  margin: 0;
  padding: 0;
  width: 300px;
}

article {
  background-color: #c0c0ff;
  border: 30px solid blue;
  box-sizing: border-box;
  cursor: pointer;
  height: 200px;
  margin: 40px;
  padding: 50px;
  width: 200px;
}

/* The JavaScript code above turns this class on and off in the <article> */
.toggled {
  background-color: #c0ffc0;
  border: 30px solid green;
}
```

Click here



If you click anywhere inside the inner (blue) box, the box turns green; click again, and it becomes blue once again. Click elsewhere on the page (including on the light red area of the outer box -- the margin of the inner box), and nothing happens. This behavior shows that the padding is part of the element, but the margin is not. (If you click on the blue or green border directly, you'll see that it's also clickable.)

### Margins, Padding, and Backgrounds

The background of an element appears in the padding area, while that of a container shows through the contained element's margins. Thus, the interior of the inner box is light blue or green (the inner box's background color). However, the surrounding area is pale red (the outer box's background).

### Top and Bottom Margins and Padding on Inline Elements

As we learned earlier, the browser doesn't use the top and bottom margins and padding for `inline` elements for spacing. New developers often forget this, which leads to headaches as they try to figure out why the margins or padding aren't working the way they expect. No matter how big the top and bottom margins are on an `inline` element, they do not affect the placement of the element's content nor the content surrounding it. See the example under *Borders, Padding, and Inline Elements* in *The Visual Formatting Model* assignment.

### Margin Collapse

An even bigger difference between margins and padding is that top and bottom margins "collapse" between `block` elements. If you position two adjacent `block`'s one above the other, the margin between them isn't the sum of the bottom margin of the first and the top margin of the second. Instead, the margin collapses to the larger of the two margins in question. For instance, assume that we have the following HTML:

Copy Code

```html
<p>This is the first sentence</p>
<p>This is the second sentence</p>
```

We also have the following CSS:

Copy Code

```css
p {
  margin-bottom: 15px;
  margin-top: 32px;
}
```

The spacing between the two paragraphs won't be 47 pixels - it'll be 32 pixels.

Margin collapse occurs with top and bottom margins, not with left and right margins. Padding does not collapse.

## Should I Use Padding or Margins?

There's no firm answer to this question, but one useful strategy is to use margins for spacing between elements, and padding to affect the visible or clickable area of one. Within a container, use padding for horizontal separation between its edges and content, and margins for the vertical distance.

This approach works well but sometimes leaves you wondering about the correct choice. Another technique is to use margins everywhere except when you need padding. You probably need to use padding when:

- You want to change the height or width of a border.
- You want to adjust how much background is visible around an element.
- You want to alter the amount of clickable area.
- You want to avoid margin collapse.
- You want some horizontal spacing to the left or right of an `inline` element.
- As before, use padding to separate the left and right sides of a container from its content. Use margins for the vertical gap.

This approach is a simple mechanical process: ask yourself whether any of the above options apply to the element. If any do, use padding to provide those features. Otherwise, use margins. This strategy doesn't guarantee that you will make the correct choice between padding and margins in every situation. However, it should help you choose the right property most of the time.

As you go through this course, you will see code that doesn't follow the padding vs. margins guidelines above. That's fine; they help you decide which to use, but they are not absolute laws. Not all developers must follow the same rules.

# Dimensions

Some CSS properties require lengths as property values to provide the size of some detail on the page. For instance, we've used the `width`, `height`, `margin`, `padding`, and `border` properties to specify the characteristics of element boxes and their attributes. We've also seen a few instances of using `font-size` to specify the text size. Each of these properties includes a length specification, such as `12px`, `3rem`, or `50%`; we call these values **measurements** or **dimensions**. We also call `px`, `rem`, `%`, etc. **measurement units** or **units**.

Before we begin, take some time to read the pages on [lengths](https://developer.mozilla.org/en-US/docs/Web/CSS/length) and [percentages](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage) at MDN. Don't try to memorize all the different dimensions (notably those marked as experimental), but get a feel for what is available. In this course, we will chiefly use `px`, `rem`, `em`, and `%`.

## Absolute vs. Relative Units

We measure everything using either **absolute** or **relative** units. In the real world, most of us know and use both.

Real world absolute units include inches, feet, meters, millimeters, furlongs, etc. We base these units on a standard system of measures that nearly everybody agrees on: a meter in Japan is the same as a meter in Madagascar which is the same as a meter in the USA (if the USA used meters, that is). Absolute measures don't change depending on circumstances.

Relative units are scarce in the modern world, but they were common in days-gone-by. For instance, a *hand* was once defined as the width of a person's hand measured across his fingers. Not everybody's hands were the same size, and some people included his thumb while others excluded it, so measurements involving hands were relative. A more modern unit is the *story* or *floor* used to give the height of buildings: they are not all the same height.

### Absolute Units

CSS has one absolute unit of significance: the **pixel**. Most people think of the pixel as a single spot of light on your computer's display, and with good reason - we use the term pixel to describe them. In CSS, pixels are similar, but the actual term implies a lot more meaning; we'll discuss that below. To use pixels in your CSS dimensions, append the letters `px` to the value:

Copy Code

```css
article {
  width: 500px;    /* 500 pixels */
}
```

#### Physical vs. Reference Pixels

This section dives into some technical territory that you don't need to know in detail but should recognize.

There's a problem with using pixels as an absolute unit: a pixel on a desktop computer and a pixel on a cell phone aren't the same size. Worse yet, the pixel density of displays causes variations in size as well: a pixel on a high-resolution screen (such as Apple's Retina displays) is much smaller than a pixel on a standard- or low-resolution display. That doesn't sound much like an absolute unit, and it isn't.

To get around the pixel size problem, CSS distinguishes between a **physical pixel** (also **device pixel** or **display pixel**) and what we call the **CSS reference pixel** (or **CSS pixel** or **reference pixel**). The size of a reference pixel is the size of a pixel on a display that has 96 pixels per inch. However, if you're working on a high-resolution display, you might have 192 pixels per inch. To account for this, CSS will use a total of four physical pixels on that high-resolution display for each CSS pixel. (Remember that pixels are 2-dimensional, so we need four high-resolution pixels to equal one low-resolution pixel.) Without this trick, images that look okay on a low-resolution screen appear much smaller when viewed on a high-resolution display of the same physical size. Instead, browsers use CSS pixels, so the image seems to be about the same size on both low- and high-resolution screens.

Even so, this isn't a complete solution to the problem of absolute pixel units. If you place a 27-inch desktop display and a 5-inch phone side by side and view the same 200-pixel by 200-pixel images on both devices, the images will not appear to be the same size. To account for this, CSS defines the reference pixel based on the **angular** diameter of a CSS pixel **as viewed from the typical viewing distance (TVD) for the display**. The TVD for a phone (around 14 inches) is less than the TVD for a 27-inch desktop display (about 33 inches), so if we place both screens at the appropriate TVD, that 200x200 pixel image appears to be the same size (or close to it, anyway).

In the end, this means that CSS pixels are as close to an absolute unit as you can get with CSS, provided you take the TVD into account.

The difference between CSS reference pixels and physical pixels can pose a problem when using a design document to build a web page. If you have a high-resolution screen (like Apple's Retina displays) and view an image in Photoshop at 100% of its size, then look at it in your browser, the Photoshop version may appear smaller. If you're aware of this, you can account for the differences.

#### Other Absolute Units

CSS supports other absolute units, including inches and millimeters, but you won't use these units often. In theory, a CSS inch should appear to be 1 inch on a screen at the TVD since a CSS inch is 96 CSS pixels. If you measure the length of that inch with a ruler, though, it may be larger or smaller than an actual inch. This difference leads most developers to stay away from inches and millimeters unless they need something that appears close to "life-size."

### Relative Units

CSS provides a handful of relative units of interest: the **em**, the **rem**, percentages, as well as a few we won't discuss.

#### Ems and Rems

Ems and rems are proportional to the **calculated** and **root** font sizes, respectively. The calculated font size is the height of the current font in pixels. The root font size is the height of the base font for the document: the font size designated for the `html` element. If the calculated font size is 20 pixels and the root font size is 16 pixels, then `1.5em` is `30px` (20 * 1.5), while `1.5rem` is `24px` (16 * 1.5).

In most cases, you should use pixels to specify the root font size. Some developers use ems or rems to give the user some control over the font, but this can result in odd behavior as your precisely positioned items start to overflow, overlap each other, or rearrange themselves on the page.

Bugs in some older browsers make it a good idea to set the root font size in both the `html` and `body` elements. Always use pixels when you do so.

You may find it easier to work with rems instead of ems since rems are consistent. Once you've set the root font size for a document, `1.5rem` means the same thing everywhere in that document. This relationship isn't true for ems; they compound. For example:

Copy Code

```html
<h1>Using `em` Units</h1>
<div class="a-em">
  1em == 1 * 24px == 24px
  <div class="b-em">
    1.5em == 1.5 * 24px == 36px
    <div class="c-em">
      2em == 2 * 36px == 72px
      <div class="a-em">
        1em == 1 * 72px == 72px
      </div>
    </div>
  </div>
</div>

<hr>

<h1>Using `rem` Units</h1>
<div class="a-rem">
  1rem == 1 * 24px == 24px
  <div class="b-rem">
    1.5rem == 1.5 * 24px == 36px
    <div class="c-rem">
      2rem == 2 * 24px == 48px
      <div class="a-rem">
        1rem == 1 * 24px == 24px
      </div>
    </div>
  </div>
</div>
```

Copy Code

```css
html, body { font-size: 24px; }

.a-em { font-size: 1em; }
.b-em { font-size: 1.5em; }
.c-em { font-size: 2em; }

.a-rem { font-size: 1rem; }
.b-rem { font-size: 1.5rem; }
.c-rem { font-size: 2rem; }
```



![Ems and Rems](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/measurement-units-01.png)



Pay attention to the difference between the 1em and 1rem lines at the final level. You can't go back to the original font size by specifying `1em`, but `1rem` takes you back directly to the original font size. You may also notice that the `1.5em` and `1.5rem` items use the same font size in this instance, but the `2em` line is noticeably larger than the `2rem` line since the calculated font size is larger than the root.

This compounding makes ems hard to use and maintain. Some older browsers, though, don't recognize rems; if you must support such browsers, use a **fallback** unit:

Copy Code

```css
p {
  font-size: 20px; font-size: 1.25rem;
}
```

This CSS tells the browser to use `1.25rem` as the font size. If the browser doesn't recognize rems, it falls back to `20px`. Placing both values on the same line makes the presence of a fallback easier to see, but it isn't required.

We chose `20px` as the fallback value since most (not all) browsers default to `16px`, which makes `1.25rem` equivalent to `20px`. If you must use fallbacks, assuming a `16px` default font-size is your best bet.

#### Percentages

Technically, CSS doesn't consider percentages as a length value, but this distinction doesn't matter much at this stage. You can use them to define dimensions as a fraction of the container's width or height. If you place a `block` or `inline-block` element in a container and set it to `width: 50%;`, the element's width is 50% of the width of the container. Likewise, if you need a height of one-quarter of the container's height, use `height: 25%`.

Remember: `width` and `height` have no effect on `inline` elements.

#### Auto

The `auto` specifier also isn't a length value, but you can use it when you want to let the browser determine a width or height for you. Its specific role depends on where you use it, but its most common uses are:

- As a `width` or `height`, it tells the browser to try to fit the entire element (including its margins) in its container.
- As a left or right `margin` value on a block element, it tells the browser to push the element all the way right or left (note the reversal!) inside its container. You can center a block element by setting both left and right margins to `auto`. See below.
- As a top or bottom `margin` value, `auto` is equivalent to `0`.
- Padding does not accept `auto` values.

New developers sometimes assume that `auto` and `100%` are the same, but they are not. For example, if you use `width: auto`, the browser tries to put the entire element, including its margins, border, and padding within the container. If you use `width: 100%` instead, the browser won't consider the margins when it calculates the required element size. Thus, the element may extend beyond the bounds of the container. Furthermore, if you use the `content-box` box-sizing model, the browser won't consider the border and padding when determining the required size. For example:

Copy Code

```html
<div id="auto-width">
  <div id="auto-width-auto">width: auto</div>
  <div id="auto-width-100-border">width: 100%; box-sizing: border-box;</div>
  <div id="auto-width-100-content">width: 100%; box-sizing: content-box;</div>
</div>
```

Copy Code

```css
#auto-width {
  background-color: cyan;
  border: 1px solid gray;
  font-family: monospace;
  text-align: center;
  width: 730px;
}

#auto-width div {
  background-color: #ffe0e0;
  border: 10px solid red;
  margin: 10px;
  padding: 10px;
  text-align: left;
}

#auto-width-auto {
  width: auto;
}

#auto-width-100-border {
  box-sizing: border-box;
  width: 100%;
}

#auto-width-100-content {
  box-sizing: content-box;
  width: 100%;
}
```



![width: auto vs width: 100%](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/measurement-units-02.png)



In the above code, using `width: auto` is not strictly necessary. By default, not specifying a `width` (or a `height`) is the same as specifying `width: auto` or `height: auto`. So, in most cases, you don't need to provide an `auto` setting for the `width` or `height`.

However, there are some situations where the `auto` value is needed. In particular, if there's another selector in your CSS that sets the `width` or `height` to some other value, there's a chance that the CSS cascade will cause that value to be used unexpectedly. For this reason, specifying `width: auto` and/or `height: auto` is a good idea (but check your team's coding standards first).

For instance, consider the following code:

Copy Code

```html
<html lang="en-US">
  <head>
    <style>
      div {
        width: 250px;
        height: 250px;
        background-color: yellow;
        border: 1px solid black;
      }

      div.full {
        width: auto;
        background-color: lime;
      }

      div.should-be-full {
        background-color: cyan;
      }

    </style>
  </head>

  <body>
    <div></div>
    <div class="full"></div>
    <div class="should-be-full"></div>
  </body>
</html>
```

If you load this code in your browser, you should see that only the `div` with a class of `full` stretches across the entire window. The one with a class of `should-be-full` does not stretch across the window because it is using the `width` property specified by the `div` selector.

Let's now look at using `auto` with margins to center and right align a (non-inline) element inside its container without also altering the element's content as `text-align` would:

Copy Code

```html
<div id="center-margin-auto">
  <div id="center-margin-auto-center">centered</div>
  <div id="center-margin-auto-right">right</div>
</div>
```

Copy Code

```css
#center-margin-auto {
  background-color: cyan;
  border: 1px solid gray;
  width: 780px;
}

#center-margin-auto div {
  background-color: #ffe0e0;
  border: 10px solid red;
  padding: 10px;
  width: 50%;
}

#center-margin-auto-center {
  margin: 10px auto;
}

#center-margin-auto-right {
  margin: 10px 10px 10px auto;
}
```



![width: auto](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/measurement-units-03.png)



### Zero Lengths

Standard CSS style omits the units when providing a length of 0 units. For example, if you want no margins on `blockquote` elements, you can add the following to your CSS:

Copy Code

```css
blockquote {
  margin: 0;
}
```

We omit the units here since 0 is the same in all units.

### Mixing Units

You can freely mix units anywhere you want on a page: you can use pixels for some elements, rems for others, `%`, and `auto` even within a single element's styling:

Copy Code

```css
p {
  border: 1rem solid red;
  height: auto;
  margin: 10px;
  padding: 0.5em 10vw 0.5in 18pt;
  width: 80%;
}
```

Be careful, though: mixing and matching units can lead to problems when you need to determine the "right" length to make something come out correct. Consider:

Copy Code

```html
<div class="a">
  <div class="b"></div>
  <div class="c"></div>
</div>
```

Copy Code

```css
div {
  border: 1px solid black;
  height: 50px;
}

.a {
  width: 500px;
}

.b {
  display: inline-block;
  margin: 0 50px;
  width: 25%;
}

.c {
  display: inline-block;
  margin: 0 1rem;
  width: ???;
}
```

What `width` should you provide to the `.c` selector to ensure that the outer box is precisely large enough to contain both the `b` and `c` boxes? The best you can do here is estimate a value, but no size you specify will be precise for all page widths.

Using `box-sizing: border-box` can help in situations like this, provided you aren't also using left or right margins on the inner boxes.

### When to Use the Different Units

Trying to decide which dimensional units you should use is sometimes difficult. Here are some general guidelines - none of these are absolute, and you will almost certainly find developers that disagree:

- Use absolute units sparingly, and stick with pixels. Pixels work well for:
  - the root font size
  - image widths and heights
  - top and bottom margins and padding, sometimes useful with left and right margins and padding
  - width or height of fixed-width/fixed-height containers such as navigation sidebars
  - border widths
- Use relative units liberally:
  - Use rems for fonts, possibly with a fallback to ems or pixels. The root font should use pixels.
  - If you must use ems instead of rems, try to avoid compounding font sizes.
  - Use rems, ems, or pixels for left and right margins and padding.
  - Use `%` for measurements that are proportional to the container element's width or height. Percentages work best for container dimensions and come in handy when you want certain areas of the page to grow and shrink as the width of the browser window changes.
  - Use `auto` with `width` and `height` to let the browser calculate an appropriate value.
  - Use `auto` with left and right margins to left, center, or right justify a block element within its container.

You can ignore or break any of these rules when appropriate. We violate them often in this course.

# Practice Problems: Spacing and Dimensions

In these practice problems, we'll work with heights, widths, padding, margins, and a variety of dimensional units.

Some of these problems use [this image](https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_dimension_and_spacing/Hôtel_des_Invalides_-_20150801_16h09_(10630).jpg). You may use it in your HTML like this:

Copy Code

```html
<img src="https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_dimension_and_spacing/H%C3%B4tel_des_Invalides_-_20150801_16h09_%2810630%29.jpg"
    alt="Demonstration of image sizing">
```

We'll discuss images and the `img` tag in a later lesson.

1. Use CSS to set a fixed width on the image of 800 pixels, and center it in the window horizontally.

   Hint

   The easiest way to center an image is to use an `auto` margin. However, you must also change the visual display model.

   Solution

   `auto` margins work for `block` elements, but not `inline` or `inline-block`, so you must also set the `display` style when trying to center an `img`.

   Copy Code

   ```css
   img {
     display: block;
     margin: 0 auto; /* 0: top and bottom margin, auto: left and right */
     width: 800px;
   }
   ```

   `margin: XXX auto;` is a common way to center block content; learn it and use it, where `XXX` is the size of the top and bottom margins, while `auto` applies to the left and right margins. An XXX value of 0 means no top and bottom margins.

2. Using the code from the previous problem, change the `width` property for `img` to `100%`, and set the `max-width` property to `800px`. The image should expand to fit any container width up to 800 pixels. Resize your browser width and watch how that affects the photograph.

   Solution

   Copy Code

   ```css
   img {
     display: block;
     margin: 0 auto;
     max-width: 800px;
     width: 100%;
   }
   ```

3. Using the code from the previous problem, set a fixed height on the image of 533 pixels. Resize the browser window and watch how the image dimensions change.

   Solution

   Copy Code

   ```css
   img {
     display: block;
     height: 533px;
     margin: 0 auto;
     max-width: 800px;
     width: 100%;
   }
   ```

4. As you can see, having a variable size for one dimension and fixed for the other makes for a container with strange behavior: this one stretches horizontally but remains fixed vertically. Remove the height and update the CSS to ensure the width does not get smaller than 500 pixels.

   Solution

   Copy Code

   ```css
   img {
     /*DELETED height: 533px;*/
     min-width: 500px;
   }
   ```

5. Create a new HTML page with two consecutive `div` elements. Make each a fixed width and height of 300 pixels. Set the background color on the first `div` to `"#fcc"` (red) and the second to `"#ccf"` (blue).

   Solution

   Copy Code

   ```html
   <div class="red"></div>
   <div class="blue"></div>
   ```

   Copy Code

   ```css
   div {
     height: 300px;
     width: 300px;
   }
   
   .red {
     background-color: #fcc;
   }
   
   .blue {
     background-color: #ccf;
   }
   ```

6. Add a 5-pixel solid black border to the blue `div`. Compare the widths of the two boxes. Why is the blue box a different size?

   Solution

   Copy Code

   ```css
   .blue {
     background-color: #ccf;
     border: 5px solid black;
   }
   ```

   By default, the CSS box model uses a value of `content-box` on all elements which means the browser doesn't include the padding or border in the `width` and `height`. Instead, it adds the padding and border sizes to calculate the dimensions of the element.

7. Add 20 pixels padding to all four sides of the red `div`. Notice the different widths again. Add a CSS property to both elements to ensure the total width for each is `300px` rather than `300px` and then some.

   Solution

   Copy Code

   ```css
   div {
     box-sizing: border-box;
     height: 300px;
     width: 300px;
   }
   
   .red {
     background-color: #fcc;
     padding: 20px;
   }
   ```

   Use the `box-sizing` property to change how the box model treats padding and borders. When set to `border-box`, the browser includes both padding and borders as part of the total dimensions.

8. Change both boxes to place them side by side instead of stacked vertically. If necessary, increase the width of your browser window.

   Solution

   Copy Code

   ```css
   div {
     display: inline-block;
     box-sizing: border-box;
     height: 300px;
     width: 300px;
   }
   ```

9. Add 20px of space between the red and blue boxes.

   Solution

   Copy Code

   ```css
   .red {
     background-color: #fcc;
     margin-right: 20px;
     padding: 20px;
   }
   ```

10. Create a new HTML file with the following CSS and HTML:

    Copy Code

    ```html
    <body>
      <ul>
        <li>Item 1</li><!--
        --><li>Item 2</li><!--
        --><li>Item 3</li><!--
        --><li>Item 4</li>
      </ul>
    </body>
    ```

    Copy Code

    ```css
     body {
      margin: 50px;
    }
    
    ul {
      background-color: #a7ceff;
      border: 10px solid blue;
      list-style: none;
      padding: 0;
    }
    
    li {
      background-color: #ffc;
      border: 10px solid red;
      box-sizing: border-box;
      line-height: 120px;
      min-height: 120px;
      text-align: center;
    }
    ```

    Don't overlook the oddly-formatted comments between the list items above! They're a necessary part of this problem.

    Add the CSS needed to list all four items side by side in one row. Each list item should use the same amount of space as the other elements, and together they should hide the blue background entirely (but not the blue border).

    Solution

    Copy Code

    ```css
    li {
      background-color: #ffc;
      border: 10px solid red;
      box-sizing: border-box;
      display: inline-block;
      line-height: 120px;
      min-height: 120px;
      text-align: center;
      width: 25%;
    }
    ```

    To understand the comments, review the challenge exercise at the end of the practice problems for the box model. In that example, we ensured that there was no space between consecutive items by making their tags adjacent. The comments here are a variation on this theme: the browser ignores them entirely, so we end up with adjacent elements.

    Annoying, right? Yes, but a necessary evil you must learn to manage. Breaking this behavior would cause other problems, so we're stuck with it for now. Try removing the comments from the above code temporarily to see for yourself how that extra whitespace makes a difference.

    Read [this article](https://css-tricks.com/fighting-the-space-between-inline-block-elements/) for more information on why this problem occurs and to learn some other techniques for dealing with it.

11. Using the code from the previous problem solution, set the left and right margin on each `li` element to 1%, but do not let the inner boxes wrap around - they must all continue to fit on the same line with no change in the outer box's size.

    Solution

    Copy Code

    ```css
    li {
      background-color: #ffc;
      border: 10px solid red;
      box-sizing: border-box;
      display: inline-block;
      line-height: 120px;
      margin: 0 1%;
      min-height: 120px;
      text-align: center;
      width: 23%;
    }
    ```

    We need to remove 2% from each element's width to account for the 1% margin. (`100% - 4 * ( 1% + 1% ) ==> 92%, 92% / 4 => 23%`)

# Summary

This lesson discussed the fundamental concepts of CSS: the box model, spacing, and dimensional measurements. All these are crucial to a proper understanding of front-end development.

We learned how browsers treat everything on a page as a box. These boxes have properties including `width`, `height`, `padding`, `border`, and `margin` that control the size and spacing of each box. Our discussion explored how the browser flows elements onto the page. We also covered the top three `display` properties that influence this behavior: `block`, `inline`, and `inline-block`. Lastly, we talked about the `box-sizing` property, specifically the `content-box` and `border-box` sizing models. Together, these topics comprise the concept of the HTML box model.

From there we examined the sometimes confusing concepts of padding and margins in more detail and talked about when you should use margins and when you should use padding.

We ended our lesson with a look at the essential dimensional units used in CSS, including both absolute and relative units, and talked briefly about when to use them.

In the next lesson, we will take a look at one of the most ubiquitous components of web pages: images. They're everywhere, and now they're coming to a web page near you.

