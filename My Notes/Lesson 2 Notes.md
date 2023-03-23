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

# The HTML Box Model

- Every element requires a box-shaped segment of the page. Every character of text content also needs a boxed portion of the page. **Box model** is how the the browser calculates the dimensions of that box by using the browser defaults and CSS.
- Boxes have properties such as including `width`, `height`, `padding`, `border`, and `margin` that control the size and spacing of each box. 
- **Visual display model** and **Box sizing model** are two concepts that significantly impact the box model. 
- The visual display model refers to how an element flows and is displayed on a web page and interacts with other elements. 
  - There are many different display types in CSS, including`block` ,`inline-block` ,`inline`. 
  - The different `display` types have different properties. 
- The box sizing model determines how an element's total size is calculated which affects the overall layout of the page. 
  - `content-box` is the default `box-sizing` value which only includes the content of an element in its width and height and does not include padding border, or margin in the width and height of an element. 
  - `border-box` model includes padding and border (not margin) in the width and height of an element.
-  Together, these topics comprise the concept of the HTML box model.

--

- new line
  - Word processing software ordinarily outputs one character at a time, moving from left-to-right or right-to-left as required by the document's language (we will ignore languages that use vertical text). As each line fills with words, the word processor automatically wraps down to the next line and starts adding characters to the beginning of a new line.
  - Your browser works in much the same way to render HTML pages: it displays "words" one at a time horizontally until it encounters a "word" that doesn't fit. At this point, the browser starts a new **line** -- one or more "words" at the same horizontal level in the current container element.
- Elements
  - **Elements** are objects that the web browser has to deal with and display. Web pages have images, media players, containers (which we'll discuss later), and other kinds of objects.
  - There may be more than one way to determine 

- Box model:
  -  **CSS box model** or **box model** describes how the browser calculates the box size for any given element using browser defaults and css.
  -  The **box size** is how much horizontal and vertical space -- a rectangle or **box** -- it needs to draw the item. There's more than one way to determine this size.
  -  Details: As the browser renders a document, it processes one element at a time. The browser determines the box size it needs to draw the item. It uses the browser defaults and your CSS to calculate the required dimensions. If there's enough horizontal space remaining on the current line, the browser places the element there; otherwise, it starts a new line. Each line uses enough vertical space to contain all its rectangles. This process repeats for every box on the page.
- Summary
  - Every element requires a box-shaped segment of the page.
  - Every character of text content also needs a boxed portion of the page.
  - **Box model**: The browser calculates the dimensions of that box by using the browser defaults and CSS.

# Box Properties

- Every box has a width, height, padding, border, and margins; know the differences.
- Padding, borders, and margins have separate properties to set the left, right, top, and bottom of each element. You can use shortcut properties to specify all four sides at once.
- How does the visual display model interact with margins, borders, and padding?

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

------

## width and height

- The **width** and **height** define how much horizontal and vertical space it needs for the *content area* of the box, which may or may not include the padding and borders. In most cases, the browser can determine the width and height automatically.

Width values

- `<length>` : Defines the width as an absolute value.
- `<percentage>` : Defines the width as a percentage of the containing block's width.
- `auto` : The browser will calculate and select a width for the specified element.
- `max-content` : The intrinsic preferred width.
- `min-content`: The intrinsic minimum width.
- `fit-content(<length-percentage>)` : Uses the fit-content formula with the available space replaced by the specified argument, i.e. `min(max-content, max(min-content, <length-percentage>))`.

##### Example

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

## padding

- The **padding** is an area that surrounds the content area of the box and separates the content from its border. 
  - It is typically opaque and hides anything that it overlays.
  - Put another way, padding is part of the visible and clickable bounds of an element.
  - Background-color shows here.
  - Padding does not collapse.
- Two ways to use padding:
  - Strategy 1 : Use margins for spacing between elements, and padding for the visible or clickable area of one. Within a container, use padding for horizontal separation between its edges and content, and margins for the vertical distance.
  - Strategy 2 Use margins everywhere except when you need padding.


Syntax

- When **one** value is specified, it applies the same padding to **all four sides**.

- When **two** values are specified, the first padding applies to the **top and bottom**, the second to the **left and right**.

- When **three** values are specified, the first padding applies to the **top**, the second to the **right and left**, the third to the **bottom**.

- When **four** values are specified, the paddings apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

## borders

- The **border** is a boundary that surrounds the padding.

Syntax

```css
/* style */
border: solid;

/* width | style */
border: 2px dotted;

/* style | color */
border: outset #f33;

/* width | style | color */
border: medium dashed green;

/* Global values */
border: inherit;
border: initial;
border: revert;
border: revert-layer;
border: unset;

```

Values

- ```
  <line-width>
  ```

  Sets the thickness of the border. Defaults to `medium` if absent. See [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width).

## margins

- The **margin** is a typically transparent area that lies outside the border and supplies spacing between adjacent elements.

  It is not "clickable".
- Margin collapse: In adjacent elements, margin collapses to the larger of the two margins in question.
- Background color interaction: 

  - Background color of container element shows in the transparent margin of the contained element.

- How to use margins

  - Use margins for spacing between elements, and padding for the visible or clickable area of one. 
  - Within a container, use padding for horizontal separation between its edges and content, and margins for the vertical distance.


Constituent properties

- [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top)
- [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right)
- [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom)
- [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left)

Syntax

```css
/* Apply to all four sides */
margin: 1em;
margin: -3px;

/* top and bottom | left and right */
margin: 5% auto;

/* top | left and right | bottom */
margin: 1em auto 2em;

/* top | right | bottom | left */
margin: 2px 1em 0 auto;

/* Global values */
margin: inherit;
margin: initial;
margin: revert;
margin: revert-layer;
margin: unset;

```

`<length>` Values for `margin`. 

- When **one** value is specified, it applies the same margin to **all four sides**.
- When **two** values are specified, the first margin applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first margin applies to the **top**, the second to the **right and left**, the third to the **bottom**.
- When **four** values are specified, the margins apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

# Padding and Margins

Beginners often get confused by padding and margins. After all, both provide whitespace that surrounds an element. In this assignment, we'll learn the differences and how and when you should use each.

## What is the Difference Between Padding and Margins?

- Border separates the margin and padding.
  - Both padding and margins surround elements with whitespace. Padding lies inside the border, while margins lie outside it. What if you don't have a border? You do - it has zero-width, so it's an invisible border, but the browser knows it's there and uses it in the box model.

- Margins are typically transparent, while the padding is opaque.
- Put another way, padding is part of the visible and clickable bounds of an element, while a margin is spacing between adjacent elements. 
  - It's easy to see this with clickable elements. If you click on the content area or anywhere in the padding or border, the browser will process the click. If you click on the margin, nothing happens. Consider this example:

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

### Background color interaction

- The `background-color` of a contained element appears in the padding area, while the `background-color` of the container shows through the contained element's margins. 
  - Note: the `background-color` of the container will only show through the contained element's margins if the margins are transparent. 
  - Note: If the contained element has a background color that is opaque, it will completely cover any background color or image of the container element beneath it, regardless of whether the margins are transparent or not. 
- The inner box's background color: interior of the inner box is light blue or green. 
- The outer box's background: the surrounding area is pale red.

![](C:\Users\jenny\Downloads\download (11).png)

### Top and Bottom Margins and Padding on Inline Elements

- As we learned earlier, the browser doesn't use the top and bottom margins and padding for `inline` elements for spacing. New developers often forget this, which leads to headaches as they try to figure out why the margins or padding aren't working the way they expect. 
- No matter how big the top and bottom margins are on an `inline` element, they do not affect the placement of the element's content nor the content surrounding it. 
- See the example under *Borders, Padding, and Inline Elements* in *The Visual Formatting Model* assignment.

### Margin Collapse

- An even bigger difference between margins and padding is that top and bottom margins "collapse" between `block` elements. 
- If you position two adjacent `block`'s one above the other, the margin between them isn't the sum of the bottom margin of the first and the top margin of the second. Instead, the margin collapses to the larger of the two margins in question. For instance, assume that we have the following HTML:

```html
<p>This is the first sentence</p>
<p>This is the second sentence</p>
```

We also have the following CSS:

```css
p {
  margin-bottom: 15px;
  margin-top: 32px;
}
```

The spacing between the two paragraphs won't be 47 pixels - it'll be 32 pixels.

- Margin collapse occurs with top and bottom margins, not with left and right margins. 
- Padding does not collapse.

## Should I Use Padding or Margins?

Strategy 1

- Use margins for spacing between elements, and padding for the visible or clickable area of one. 

- Within a container, use padding for horizontal separation between its edges and content, and margins for the vertical distance.

This approach works well but sometimes leaves you wondering about the correct choice. 

Strategy 2

- Another technique is to use margins everywhere except when you need padding.

- This approach is a simple mechanical process: ask yourself whether any of the below options apply to the element. If any do, use padding to provide those features. Otherwise, use margins. 

- You probably need to use padding when:

  - You want to change the height or width of a border.

  - You want to adjust how much background is visible around an element.

  - You want to alter the amount of clickable area.

  - You want to avoid margin collapse.

  - You want some horizontal spacing to the left or right of an `inline` element.

  - As before, use padding to separate the left and right sides of a container from its content. Use margins for the vertical gap.

- This strategy doesn't guarantee that you will make the correct choice between padding and margins in every situation. However, it should help you choose the right property most of the time. 

As you go through this course, you will see code that doesn't follow the padding vs. margins guidelines above. That's fine; they help you decide which to use, but they are not absolute laws. Not all developers must follow the same rules.

# Visual Display Models

- Understand the differences between `inline`, `block`, and `inline-block`.
- Containers are almost always `block` elements, while non-containers are `inline`. When in doubt, check MDN.
- Don't try to memorize which HTML elements are `block` or `inline`.
- How and when can you change an element's visual display model?

------

## **Visual formatting model** (`display` style)

- How a browser lays out its elements is determined by the `display` property. The `display` property has more than two dozen values, but most CSS uses the values `block`, `inline`, and `inline-block`. We call this property the visual formatting model.
- Assumption: When we discussed how the browser lays out elements, our stated assumption was that all boxes have a `display` property of `inline-block`. We chose that property value since it's easy to understand, and best demonstrates how page layout works in a browser. 
- **Flow**: How browser flows elements onto the page. 

## Block

<u>Definition</u>

- A **`block` element** always takes up the entire width of *its container element* and starts on a new line, regardless of its actual content width.
- Note: Two `block` elements that ***DON'T*** have the same parent element may appear side by side on a page. 
  - How this happens is if the parent element is `inline-block` or `inline` which lets the browser render them side by side. 
  - With the proper dimensions, margins, padding, and alignment, it's possible to arrange the child `block` elements side by side as well.
- [Block elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) appear on almost all web pages: headings, paragraphs, sections, tables, forms, lists, and more are `block` elements.

- Most `block` elements group one or more elements - some of which may themselves be `block`s - into areas of the page. 

  - For instance, `header` elements group together elements into a page header. 

<u>Common Block Elements</u>

- [Block elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) appear on almost all web pages: headings, paragraphs, sections, tables, forms, lists, and more are `block` elements.
- Most elements are `block` elements by default. Here are some of the most common:
- `<div>`
  - `section`, `article`, `aside`, `header`, `footer`
- `p`
  - `h1` through `h6`
- `blockquote`
  - `ul`, `ol`, `dl`
  - `figure` and `figcaption`
- `form` and `fieldset`
  - See [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements) for a complete list of block elements.

#### containers

- **Containers** are `block` elements such as a `header` that contain one or more elements. The master container (the outermost) is the `body`; every other element belongs to a container.

- We sometimes use the term **parent** to refer to a container, and use **child** to describe an element contained within a container. These relationship terms also let us talk about grandparents, ancestors, descendants, siblings, cousins, etc..

#### Spacing / Flow

- A **`block` element** takes up the full width of *its container element* and starts on a new line, regardless of its actual content width.

- Note: Two `block` elements that ***DON'T*** have the same parent element may appear side by side on a page. 

  - How this happens is if the parent element is `inline-block` or `inline` which lets the browser render them side by side. 
  - With the proper dimensions, margins, padding, and alignment, it's possible to arrange the child `block` elements side by side as well.

- By default, a `block` element occupies all horizontal space available within its container, with nothing to the left or right of the `block`. 
  - If your page contains 3 `block` elements directly inside the `body` element and nothing else, then all three elements will display one above the other like a stack of blocks. 
  - This behavior makes `block` elements predictable and easy to use.

- Though a `block` element takes up an entire row in a container, this does not alter the width of the element. The browser renders the `block` element on a line by itself, but the element has the specified (or computed) width. 

  - For example, if you have a 500-pixel wide `blockquote` in a 900-pixel wide `section`, the `blockquote` element uses 500 pixels, but the browser will leave the remaining 400 pixels of the `section` empty.

- A block element will always appear on a line by itself within it's container `div` no matter its width. 

  Example

  - If you want an element that is 928 pixels wide, 168 pixels high, with 20 pixels of left and right padding, 10 pixels of padding at the top and bottom, a 1-pixel border, and a 28-pixel bottom margin, all those properties will play a part in the overall dimensions of the element. 
  - Thus, the overall dimensions will be 970 x 218 pixels. (As we'll see later, it's possible to change the way the browser calculates the dimensions. This example assumes that you're using the browser defaults)

####  layout properties

- With `block elements` we can compute dimensions directly from CSS properties. 
- `block` elements use the **box properties** (`width`, `height`, `padding`, `border`, `margin`) to determine the size of the element. The browser reserves a box of the right size on the page, and this is where it draws the content. 

#### Other notes about `block` elements

<u>Width and height may include padding and border</u>

- As we'll see later, the `width` and `height` of an element may include the `padding` and `border` in addition to the content area. By default, `width` and `height` exclude the `padding` and `border` from the measured content area. We'll learn more about this fact in the next assignment when we learn about box sizing.

<u>Width and height always excludes margins</u>

- Another item of note is that the height and width values never include the margins. Technically, margins provide spacing between elements but are not part of them. However, you do need to account for the margins when determining whether an item will fit in a given space.

<u>Margin Collapse</u>

- Top and bottom margins "collapse" between `block` elements. 
- If you position two adjacent `block`'s one above the other, the margin between them isn't the sum of the bottom margin of the first and the top margin of the second. Instead, the margin collapses to the larger of the two margins in question. 

#### Convert element to `block`

- You can convert any element to a `block` element with the `display: block` CSS property. It's common to render links (`a`) and images (`img`) as `block` elements.

## Inline

- What are `inline` elements?
  - Inline elements can be nested inside other inline elements, as well as block-level elements. However, all content must ultimately be contained within the body element or a block-level element.

- **An `inline` element** only takes up as much width as its **content** requires and does not start on a new line. 
  - Examples of inline elements include `<span>`, `<a>`, and `<img>`.
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

#### Flow

- **Flow**: `inline` elements flow from one line to the next, which lets you place `inline`  elements side by side with other `inline` or `inline-block` elements.
  - The main idea is that the left/right factors affect the **flow**, while the top and bottom do not.

- padding, margins & borders impact on flow of content within a container
  - **Left and right overlap with container**: For `inline` elements, if contained element's left or right padding or border is wider than the container's width, then it will simply overlap with the container's content area, rather than the `inline` element going to a new line like `inline-block` elements would. 
  - **top & bottom overlap with container**: The top & bottom padding and borders may extend beyond the boundaries of the `inline` element's content area. This means that if there is content above or below the `inline` element, it will overlap with the top or bottom border / padding  of that `inline` element. This behavior should be avoided. 
  - **Margin causes adjacent `inline`** elements to overlap: If the margin is too big, inline elements would be pushed apart from each other, which may cause adjacent inline elements to overlap.

Demonstration

![Box layout at 800 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-1.png)

*Figure 1*: Element flow at 800 pixels

![Box layout at 700 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-2.png)

*Figure 2*: Element flow at 700 pixels

#### Spacing

- **Spacing**: Remember that in code, inline elements respect white spaces around the character and in between then. And the white space collapses to a single white space character. So multiple space characters would render as one space character. 

#### Layout properties

<u>dimensions properties ignored by browser</u>

- *ignore* the `width` and `height` properties (except with the `img` element), but instead use values computed from the element content. The **actual content area** is determined by the browser.
- *ignore* top and bottom `margin`s. 

<u>Which dimension properties not ignored by browser for `inline elements`</u>

- *don't ignore* left and right `margins`. 
- *don't ignore* `borders`, but the top and bottom borders may extend beyond the boundaries of the content area. 
- *don't ignore* left and right padding, handled in same way as `block` elements. 
- *don't ignore* top and bottom `padding`, but the top and bottom padding may also extend beyond boundaries of content area. 

<u>Summary of `inline` 's trickiness</u> 

- The `width` and `height` properties is ignored by the browser and does not determine the actual content area. The actual content area is determined by the browser.
- **Properties ignored by the browser** for `inline` elements: `width` and `height`, top and bottom`margins`. Since browser ignores these CSS properties, we can't calculate the space this contained element would take unless we know the actual width and height of the content. 
- **Properties not ignored by browser**: left and right `margins`, left and right `padding`, top and bottom `padding`, Borders. 
- **Overlap**: Also keep in mind how the top & bottom padding and borders may extend beyond the boundaries of the `inline` element's content area. This means that if there is content above or below the `inline` element, it will overlap with the top or bottom border / padding  of that `inline` element. This behavior should be avoided.
- Exception: While browsers ignore the `width` property for most `inline` elements and calculate the width based on the content, the `img` element is an exception. 

<u>`inline` elements vs `block` elements</u>

- `inline` elements handle the dimension properties (`width`, `height`, `padding`, `border`, and `margin`) differently from the way `block` elements treat them. This difference is where the box model starts to get messy.

- Browsers handle *left* and *right* margins and padding for `inline` elements in the same way as for `block` elements, but they process other box model properties differently. 

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

<u>Top & bottom borders and padding extend beyond boundaries</u>

- One more item to note here is that the top and bottom borders extend beyond the boundaries of the `p` element. The padding would do that as well if we increased it by a few more pixels.

- You need to understand this behavior more as something to avoid than to make use of it. You can waste a lot of time trying to use borders, padding, and margins with inline elements when you're not expecting this behavior. 

- The main idea is that the left/right factors affect the **flow**, while the top and bottom do not.

#### Convert element to `inline` element

- You can convert any element to an `inline` element with the `display: inline` CSS property. The most common reason to do so is to override a prior declaration.

#### `inline` interaction with `border-box`

- Technically, it is possible to apply `border-box` sizing to an inline element using CSS, but it may not always work as expected due to the nature of inline elements. 
- When you apply `border-box` sizing to an inline element, the element's total width and height will include its content area, padding, and border. 
- However, because inline elements are designed to flow with the text and not disrupt the layout, adding padding and border to an inline element can cause the element to "break out" of the text flow, resulting in unexpected, overlapping layout issues.
  - This means that the element may be wider and taller than its actual content, and any padding or border added to the element will be included in its dimensions.
  - To avoid this issue, avoid adding padding and border to inline elements. 

## Inline-block

- `inline-block` elements are a mixture of both previous types. They act like `block` elements by allowing you to set width, height, borders, margins padding. Except for one significant detail: `inline-block` elements do not take up an entire row when the `width` property is less than the available width, and thus flow inline rather than starting on a new line.
  - This makes it useful for creating horizontal lists or for aligning elements next to each other. 

Default `inline-block` elements

-  `<button>`
-  `<input>`
-  `<label>`.

> Legacy Model
>
> - The `inline-block` visual display model is a *legacy* model. It is equivalent to a new model called `inline flow-root`. 
> - However, despite its legacy status, `inline-block` is probably not going to go away anytime soon; there are too many websites that still use it. 
> - We will use `inline-block` throughout this course; it will probably be several years before `inline flow-root` and other new display models gain traction.

#### Flow

- **Flow:** Inline-block elements can have a set width, height, borders, margins padding but they still flow inline, making them useful for creating more complex layouts.
  - `inline-block` elements do not take up an entire row when the `width` property is less than the available width, and thus flow inline rather than starting on a new line.
  - This lets you place `inline-block` elements side by side with other `inline` or `inline-block` elements.

- Padding, margin & borders impact on flow of elements in a container
  - **Enlarging container**: For `inline-block` elements, if padding, border, or margin is wider than container's width, then the contained element it will go to a new line, making the container bigger. This is assuming the container doesn't have fixed dimensions. 
  - **Overflowing container**: If a container element has smaller dimensions than a child element, the child element will overflow the container and appear on top of the container.

- Do `inline-block` elements always appear side by side if their width properties add up to 100%?
  - Two consecutive `inline-block` elements with a total width of `100%` may render side by side, but not necessarily. 
  - To render side by side, you must account for any `whitespace` between the two elements, and must also account for their `border`s and `padding`; the left/right `margins` must be 0 in any case.
  - If `border-box` is used, then just need to account for the left/right `margins`. 

#### Spacing

- **Spacing**: Remember that in code, `inline` elements respect white spaces around characters and in between then. And the white space collapses to a single white space character. So multiple space characters would render as one space character.

#### layout properties

- `display: inline-block` meaning that is an `inline-block` element. 

- Similar to block elements but different from `inline` elements: we can compute dimensions directly from CSS properties. 
-  `width`, `height`, `padding`, `border`, `margin` are all used to determine the size of the element.

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

#### Convert element to `inline-block`

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

## `box-sizing` property

- The usable `box-sizing` property values are `content-box`, and `border-box`. The CSS standard deprecates the `padding-box` setting; **don't use it**.

- The `box-sizing` property controls how an element's total width or height is calculated. The **content** area is different for the 2 models.
  - Use the `box-sizing` property to change how the box model treats padding and borders. When set to `border-box`, the browser includes both padding and borders as part of the total dimensions.
- Note that `box-sizing` only plays a part when you specify the width and height of the element. If you don't specify a width and height, then your browser computes the width and height it needs from the elements it contains. This width and height are not affected by the `box-sizing` property of the container element. 

## `content-box`

- By default, the CSS box model uses a value of `content-box` on all elements on modern browsers, which means the browser doesn't include the padding or border in the `width` and `height`. Instead, it adds the padding and border sizes to calculate the dimensions of the element.
- **Actual content area** = space inside element where actual content is displayed. 
- In this model, the `width` and `height` properties specify the size of the **actual content area**. You need to add padding and borders to get the size of the visible box.
  - `width` x `height` = **actual content area**, not visible box.
  - `width` x `height` + padding + borders = **visible box**. 
  - Margin not included in content-box.

![image-20230320185240802](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230320185240802.png)

Top represents content-box, bottom represents border-box. 

## `border-box`

- The `border-box` setting causes the browser to interpret the `width` and `height` properties as the total width and height of the box excluding the margins. 
- The width and height include is the actual content area + padding + borders. 
  - `width` x `height` = **visible box**
  - **content width** + padding + borders = `width`
  - **content height** + padding + borders = `height`
  - Margin not included in border-box

<u>Why border-box is best</u>

- The `border-box` setting is "best" since it simplifies the math a front-end developer must do. 
- `border-box` is made for responsive design. 
- For example, if we have a box with a width of 50% and padding of 12px; `border-box` ensures that it's precisely 50% of the container width, not 50% plus 24 pixels. 
- Use `border-box` if you don't want paddings or borders to exceed a certain dimension. 

<u>Box reset: Universal Box Sizing with Inheritance</u>

- If you want to use border-box pretty much everywhere, you can add the following to your CSS: 

  ```css
  html {
    box-sizing: border-box;
  }
  
  *, *::before, *::after {
    box-sizing: inherit;
  }
  ```


- What this code means:
  - `box-sizing: border-box;` is set for the `html` element, which means that all the elements inside the `html` element will have the `box-sizing` property set to `border-box`.
  - All elements, their `::before` and `::after` pseudo-elements will inherit the `box-sizing` property value from the `html` element.
  - By setting `box-sizing` property to `inherit`, it makes sure that all the elements on the page will follow the `border-box` box model, which means that any padding and border will be included in the element's specified width and height, rather than being added to it.
- Why this reset offers flexibility
  - This reset gives you more flexibility than its predecessors — you can use `content-box` without worrying about a universal selector overriding your CSS. 
  - Any element with an explicitly set `box-sizing` property will retain its specified value, while all other elements will inherit the `border-box` value from their parent element: the `html` element. 

<u>See [this article](https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice/) for an explanation of this code.</u> 

- Note that the article uses the old-style single colon to specify the pseudo-elements `before` and `after`; modern usage suggests a double colon.
- One potential gripe with it is that `box-sizing` isn’t normally inherited, so it’s specialized behavior, not quite the same as something you’d normally put in a reset.

What the article explains

- The article highlights that if you set the `box-sizing` property to `content-box` on the component selector, it won't reset the entire component. Some parts of the component may still rely on the default `content-box` box model, and changing the `box-sizing` property of the component selector will not affect those parts.
- To address this issue, the article suggests using an inheriting snippet that sets `box-sizing: inherit` on all elements, including their pseudo-elements. This approach ensures that all elements inherit the `box-sizing` property value from their parent element, without disrupting the `box-sizing` values that might have been explicitly set on individual elements.
- By using this approach, the `box-sizing` property of the pre-designed component is preserved, and any nested elements within the component will inherit the correct `box-sizing` value, whether it's `content-box` or `border-box`.

## [Article about box-sizing](https://css-tricks.com/box-sizing/)

#### Box Model History

- Box model worked like this by default
  - width + padding + border = actual visible/rendered width of an element’s box
  - height + padding + border = actual visible/rendered height of an element’s box
- This can be a little counter-intuitive, since the width and height you set for an element both go out the window as soon as you start adding padding and borders to the element.
- Early versions of Internet Explorer (IE6) handled box model differently in quirks mode. 
  - width = actual visible/rendered width of an element's box 
  - height = actual visible/rendered height of an element's box
- The border and padding values were moved inside the element's box, cutting into the width/height of the box rather than expanding it.

![widthbox](https://i0.wp.com/css-tricks.com/wp-content/uploads/2010/09/widthbox.png?resize=367%2C604)

The box at the top shows the default box model. The box at the bottom shows what was once the “quirks mode” interpretation of the box model.

- But, in the days of fixed-width design, it wasn’t particularly complicated to work with the default box model once you understood it. You could do a bit of arithmetic to figure out how many pixels you needed to trim off of an element’s declared width or height to accommodate its padding and border. 

Responsive design 

- The problem for present-day developers is that those absolute pixel lengths don’t translate to responsive design, so the same math doesn’t apply anymore.
- As responsive design (or, as it was once known, “fluid” or “liquid” layout) started to gain popularity, developers and designers wished for an update to the box model.

Present-day box-sizing

- Those wishes were granted when the `box-sizing` property was introduced in CSS3. Though `box-sizing` has three possible values (`content-box`, `padding-box`, and `border-box`), the most popular value is `border-box`.
- Today, the current versions of all browsers use the original “width or height + padding + border = actual width or height” box model. With `box-sizing: border-box;`, we can change the box model to what was once the “quirky” way, where an element’s specified width and height aren’t affected by padding or borders. This has proven so useful in responsive design that it’s found its way into reset styles.

From bug to border-box

- Officially, Microsoft's original implementation was a bug. It caused compatibility problems with other browsers. When Microsoft fixed the bug, it left the old mode available as a way to maintain backward compatibility and called it Quirks mode.

#### Box resets

- **box reset**: a box reset refers to a set of rules applied to an HTML element in order to remove any default styling that might be applied by the browser. Box resets are used to provide a consistent starting point for styling HTML elements across different browsers and devices.

<u>The “Old” `border-box` Reset</u>

The earliest `box-sizing: border-box;` reset looked like this:

```css
* {
  box-sizing: border-box;
}
```

- This works fairly well, but it leaves out pseudo elements, which can lead to some unexpected results. A revised reset that covers pseudo elements quickly emerged:

<u>Universal Box Sizing</u>

```css
*, *:before, *:after {
  box-sizing: border-box;
}
```

- This method selected pseudo elements as well, improving the normalizing effect of `border-box`. But, the `*` selector makes it difficult for developers to use `content-box` or `padding-box` elsewhere in the CSS. Which brings us to the current frontrunner for best practice:

<u>Universal Box Sizing with Inheritance</u>

```css
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
}
```

- This reset gives you more flexibility than its predecessors — you can use `content-box` or `padding-box` (where supported) at will, without worrying about a universal selector overriding your CSS. 
- We went into more depth on this technique and the reasoning behind it in [“Inheriting `box-sizing` Probably Slightly Better Best Practice”](https://css-tricks.com/inheriting-box-sizing-probably-slightly-better-best-practice/). One potential gripe with it is that `box-sizing` isn’t normally inherited, so it’s specialized behavior, not quite the same as something you’d normally put in a reset.

#### Vendor Prefixes

- Every current browser supports `box-sizing: border-box;` unprefixed, so the need for vendor prefixes is fading. But, if you need to support older versions of Safari (< 5.1), Chrome (< 10), and Firefox (< 29), you should include the prefixes `-webkit` and `-moz`, like this:

```css
html {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*, *:before, *:after {
  -webkit-box-sizing: inherit;
  -moz-box-sizing: inherit;
  box-sizing: inherit;
  }
```

### Known Issues

- `box-sizing: border-box;` is supported in the current versions of all major browsers. The less-commonly used `padding-box` is only supported in Firefox at the moment. There’s more comprehensive information about browser support in our `box-sizing` almanac entry.

- There are a few issues with older versions of Internet Explorer (8 and older). IE 8 doesn’t recognize `border-box` on elements with `min/max-width` or `min/max-height` (this used to affect Firefox too, but it was [fixed in 2012](https://bugzilla.mozilla.org/show_bug.cgi?id=308801)). IE 7 and below do not recognize `box-sizing` at all, but there’s a [polyfill that can help](https://github.com/Schepp/box-sizing-polyfill).

- Know the differences between `px`, `em`, `rem`, `%`, and `auto`.
- Understand why we need to talk about CSS reference pixels and physical pixels. Don't try to memorize the details, but understand the topic well enough that you won't be too surprised the first time you encounter the differences in the wild.
- Use `auto` margins to center block elements horizontally.

# Dimensions

- Know the differences between `px`, `em`, `rem`, `%`, and `auto`.
- Understand why we need to talk about CSS reference pixels and physical pixels. Don't try to memorize the details, but understand the topic well enough that you won't be too surprised the first time you encounter the differences in the wild.
- Use `auto` margins to center block elements horizontally.

------

- CSS properties like `width`, `height`, `margin`, `padding`, and `border` specify the characteristics of element boxes and their attributes. We've also seen a few instances of using `font-size` to specify the text size.
- Each CSS property includes a length specification called **measurements** or **dimensions** such as `12px`, `3rem`, or `50%`. 
- `px`, `rem`, `em`, `%` are **measurement units** or **units**.
- [lengths](https://developer.mozilla.org/en-US/docs/Web/CSS/length) 
  - The **`<length>`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Types) represents a distance value. Lengths can be used in numerous CSS properties, such as [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin), [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding), [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width), [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size), and [`text-shadow`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-shadow).
  - The `<length>` units can be relative or absolute. Relative lengths represent a measurement in terms of some other distance. Depending on the unit, this distance can be the size of a specific character, the [line height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height), or the size of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport). Style sheets that use relative length units can more easily scale from one output environment to another.
- [percentages](https://developer.mozilla.org/en-US/docs/Web/CSS/percentage)
  - The **`<percentage>`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Types) represents a percentage value. It is often used to define a size as relative to an element's parent object. Numerous properties can use percentages, such as [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height), [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin), [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding), and [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size).

## Absolute Units

- **Absolute units** is based on a standard system of measures that nearly everyone agrees on. It doesn't change depending on circumstances. 
  - For example a meter in Japan is the same as a meter in the USA. 
  - Absolute units include inches, feet, meters, millimeters, etc.

### pixel (`px`)

- CSS has one absolute unit of significance: the **pixel**. 

- The actual meaning of the term pixel implies a lot more meaning than just a single spot of light on a computer's display. Check section on physical vs reference pixels.

- To use pixels in your CSS dimensions, append the letters `px` to the value:

  ```css
  article {
    width: 500px;    /* 500 pixels */
  }
  ```

### Physical vs. Reference Pixels

- A **CSS reference pixel** (or **CSS pixel** or **reference pixel**) is a theoretical pixel used in CSS visual rendering to define a baseline pixel size for devices with different pixel densities.
  - One reference pixel corresponds to a visual angle of one pixel with a pixel density of 96 dots per inch (dpi). 
  - Other pixel densities are then scaled relative to this reference dpi. 

- A **physical pixel** (also **device pixel** or **display pixel**)  is an actual, physical dot on a screen or display that is a fixed, absolute unit of measurement that represents the smallest unit of display on a device. 

  --

Problem: 

- There's a problem with using pixels as an absolute unit: a pixel on a desktop computer and a pixel on a cell phone aren't the same size.
- Worse yet, the pixel density of displays causes variations in size as well: a pixel on a high-resolution screen (such as Apple's Retina displays) is much smaller than a pixel on a standard- or low-resolution display. That doesn't sound much like an absolute unit, and it isn't.
- To get around the pixel size problem, CSS distinguishes between a **physical pixel** (also **device pixel** or **display pixel**) and what we call the **CSS reference pixel** (or **CSS pixel** or **reference pixel**). 

Problem: Images that look okay on a low-resolution screen appear much smaller when viewed on a high-resolution display of the same physical size. 

- Solution: The size of a **reference pixel** is increased for higher resolution displays, using more **physical physical** pixels per each CSS pixel. Browsers use CSS pixels so that the image seems to be about the same size on both low and high-resolution screens.

- Details: The size of a reference pixel is the size of a pixel on a display that has 96 pixels per inch. However, if you're working on a high-resolution display, you might have 192 pixels per inch. To account for this, CSS will use a total of four physical pixels on that high-resolution display for each CSS pixel. (Remember that pixels are 2-dimensional, so we need four high-resolution pixels to equal one low-resolution pixel.)

Problem:  If you place a larger display and a small display side by side and view the same 200-pixel by 200-pixel images on both devices, the image will not appear to be the same size. 

- Detail: If you place a 27-inch desktop display and a 5-inch phone side by side and view the same 200-pixel by 200-pixel images on both devices, the images will not appear to be the same size.
- Solution: To account for this, CSS defines the r**eference pixel** based on the **angular** diameter of a CSS pixel **as viewed from the typical viewing distance (TVD) for the display**. The TVD for a phone (around 14 inches) is less than the TVD for a 27-inch desktop display (about 33 inches), so if we place both screens at the appropriate TVD, that 200x200 pixel image appears to be the same size (or close to it, anyway).

In the end, this means that CSS pixels are as close to an absolute unit as you can get with CSS, provided you take the TVD into account.

The difference between CSS reference pixels and physical pixels can pose a problem when using a design document to build a web page. If you have a high-resolution screen (like Apple's Retina displays) and view an image in Photoshop at 100% of its size, then look at it in your browser, the Photoshop version may appear smaller. If you're aware of this, you can account for the differences.

### Other Absolute units

- CSS supports other absolute units, including inches and millimeters, but you won't use these units often. 
- In theory, a CSS inch should appear to be 1 inch on a screen at the TVD (typical viewing distance) since a CSS inch is 96 CSS pixels. If you measure the length of that inch with a ruler, though, it may be larger or smaller than an actual inch. This difference leads most developers to stay away from inches and millimeters unless they need something that appears close to "life-size."

## Relative Units

- **Relative units** were common in the past. 
  - For example a modern unit is the *story* or *floor* used to give the height of buildings, even though each floor or story may not be the same height. 
  - The unit is relative but useful. 

### Ems 

- **Ems** are proportional to the **calculated** font size. 
  - The font size of the parent element is used to calculate the nested element size. 
  - The parent element itself is relative to the font-size of the **root element**. 
  - Ems **compound** each time it is used. This compounding makes ems hard to use and maintain. 


##### Compounding 

- `em` units are relative to the font-size of their parent element, so they compound each time it is used in nested elements.

- Em units compound so you can't go back by specifying the original `em`. 
- The calculated, compounded font size is also be much larger than Rems.

##### Example 1

- `Em` measurements use the font size for the parent element to calculate the desired size.
- The root font size is 20 px, which is the `html` element size. The parent element is `section` and its size is 1.25rem, so the calculated font size is 1.25 x 20 = 25 px. `ul` is nested in `section` and inherits this size from `section`. `li` is nested in `ul`, so the compounded size for `li` is 1.2em which is 1.2 x 24 = 30px. 

CSS

```css
html { font-size: 20px; }
section { font-size: 1.25rem; }
li { font-size: 1.2em; }
```

HTML

```html
  <body>
    <section>
      <ul>
        <li>Red</li>
        <li>Green</li>
        <li>Blue</li>
      </ul>
    </section>
  </body>
```

##### Example 2

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

- Pay attention to the difference between the 1em and 1rem lines at the final level. You can't go back to the original font size by specifying `1em`, but `1rem` takes you back directly to the original font size. 

- You may also notice that the `1.5em` and `1.5rem` items use the same font size in this instance, but the `2em` line is noticeably larger than the `2rem` line since the calculated font size is larger than the root.

### Rems

- **Rems** are always proportional to the **root** font size.

  - The root font size is the height of the base font for the document: it is the font size designated for the `<html>` element.

  - If the root font size is 16 pixels, then `1.5rem` is `24px` (16 * 1.5).

  - ```html
    <style>
      html { font-size: 20px; } /*root font-size is 20 px*/
      li { font-size: 1.2rem; } /*font-size for li is 24 px*/
    </style>
    ```

- In most cases, you should use pixels to specify the root font size.

  - Some developers use ems or rems to give the user some control over the font, but this can result in odd behavior as your precisely positioned items start to overflow, overlap each other, or rearrange themselves on the page.

  - Bugs in some older browsers make it a good idea to set the root font size in both the `html` and `body` elements. Always use pixels when you do so.

- Compounding: Rems are more consistent and easier to work with because they don't compound.

##### fallback unit

- Some older browsers, though, don't recognize rems; if you must support such browsers, use a **fallback** unit:

```css
p {
  font-size: 20px; font-size: 1.25rem;
}
```

- This CSS tells the browser to use `1.25rem` as the font size. If the browser doesn't recognize rems, it falls back to `20px`. Placing both values on the same line makes the presence of a fallback easier to see, but it isn't required.

- We chose `20px` as the fallback value since most (not all) browsers default to `16px`, which makes `1.25rem` equivalent to `20px`. If you must use fallbacks, assuming a `16px` default font-size is your best bet.

### Percentages

- Ethnically CSS doesn't consider percentages a length value, but you can use **percentages** to define dimensions as a fraction of the container's width or height. 
- If you place a `block` or `inline-block` element in a container and set it to `width: 50%;`, the element's width is 50% of the width of the container. Likewise, if you need a height of one-quarter of the container's height, use `height: 25%`.
- IMPORTANT NOTE: Percentage widths use the **content width** of the parent element and must also take into account the `box-sizing` property.
  - If `box-sizing` property is set to `border-box`, then the **content width** is the `width` property subtract left and right padding, then subtract left and right border.  
  - content width = width - padding - border. (see quiz question 6)

- Remember: `width` and `height` have no effect on `inline` elements.
- Browser window interaction
  - When you use a percentage width for an image, the image will resize proportionally based on the size of the browser window. 
  - For example, if you set the width of an image to 50%, the image will take up 50% of the width of its containing element. If the containing element is the entire width of the browser window, then the image will take up 50% of the width of the browser window. As the size of the browser window changes, the image will resize proportionally to always take up 50% of the width of its containing element.


### Auto

- The `auto` specifier also isn't a length value, but you can use it when you want to let the browser determine a width or height for you. 

- Its specific role depends on where you use it, but its most common uses are:

  - Using `auto` for `width` or `height` tells the browser to try to fit the entire element (including its margins) in its container.

  - As a left or right `margin` value on a `block` element, it tells the browser to push the element all the way right or left (note the reversal!) inside its container. You can center a block element by setting both left and right margins to `auto`. See below.

  - As a top or bottom `margin` value, `auto` is equivalent to `0`.

  - Padding does not accept `auto` values.

- `auto` does not mean `100%`. 

  - For example, if you use `width: auto`, the browser tries to put the entire element, including its margins, border, and padding within the container. 
  - If you use `width: 100%` instead, the browser won't consider the margins when it calculates the required element size. Thus, the element may extend beyond the bounds of the container.
  - Furthermore, if you use the `content-box` box-sizing model, the browser won't consider the border and padding when determining the required size. 

- For example:

```html
<div id="auto-width">
  <div id="auto-width-auto">width: auto</div>
  <div id="auto-width-100-border">width: 100%; box-sizing: border-box;</div>
  <div id="auto-width-100-content">width: 100%; box-sizing: content-box;</div>
</div>
```

```css
#auto-width { /*container element*/
  background-color: cyan;
  border: 1px solid gray;
  font-family: monospace;
  text-align: center;
  width: 730px;
}

#auto-width div { /*applies to all 3 contained elements*/
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

##### When is `auto` needed?

- Using `width: auto` is not strictly necessary. By default, not specifying a `width` (or a `height`) is the same as specifying `width: auto` or `height: auto`. So, in most cases, you don't need to provide an `auto` setting for the `width` or `height`.

- However, there are some situations where the `auto` value is needed. In particular, if there's another selector in your CSS that sets the `width` or `height` to some other value, there's a chance that the CSS cascade will cause that value to be used unexpectedly. For this reason, specifying `width: auto` and/or `height: auto` is a good idea (but check your team's coding standards first).

- For instance, consider the following code:

  ```html
  <html lang="en-US">
    <head>
      <style>
        div {
          width: 250px; /*selector set width to 250*/
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

- If you load this code in your browser, you should see that only the `div` with a class of `full` stretches across the entire window. The one with a class of `should-be-full` does not stretch across the window because it is using the `width` property specified by the `div` selector.

##### Using `auto` with `margin`s to align an element

- Use `auto` with `margin`s to center and right align a (non-inline) element inside its container without also altering the element's content as `text-align` would. 

- `margin: XXX auto;` is a common way to center block content.  `XXX` is the size of the top and bottom margins, while `auto` applies to the left and right margins. An XXX value of 0 means no top and bottom margins.

  - ```cs
    margin: auto; /* top and bottom: 0 margin*/
    /* Box is horizontally centered */
    ```

- Remember: `auto` margins work for `block` elements, but not `inline` or `inline-block`, so you must also set the `display` style when trying to center an `img`.

```html
<div id="center-margin-auto">
  <div id="center-margin-auto-center">centered</div>
  <div id="center-margin-auto-right">right</div>
</div>
```

```css
#center-margin-auto {
  background-color: cyan;
  border: 1px solid gray;
  width: 780px;
}

#center-margin-auto div { /*descendant selector, the key selector is div, and the prequalifier is center-margin-auto*/
  background-color: #ffe0e0;
  border: 10px solid red;
  padding: 10px;
  width: 50%;
}

#center-margin-auto-center { /*center align*/
  margin: 10px auto;
}

#center-margin-auto-right { /*right align*/
  margin: 10px 10px 10px auto;
}
```



![width: auto](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/measurement-units-03.png)

## How to use Units

#### Zero Lengths

- Standard CSS style omits the units when providing a length of 0 units. For example, if you want no margins on `blockquote` elements, you can add the following to your CSS:

```css
blockquote {
  margin: 0;
}
```

- We omit the units here since 0 is the same in all units.

#### Mixing Units

You can freely mix units anywhere you want on a page: you can use pixels for some elements, rems for others, `%`, and `auto` even within a single element's styling:

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

```html
<div class="a">
  <div class="b"></div>
  <div class="c"></div>
</div>
```

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

What `width` should you provide to the `.c` selector to ensure that the outer box is precisely large enough to contain both the `b` and `c` boxes? 

- The best you can do here is estimate a value, but no size you specify will be precise for all page widths.
- Because we are using different units (`px` and `rem`) and different margin values for the `b` and `c` boxes, it is difficult to determine an exact `width` value for the `.c` selector that will work for all page widths.

Use `box-sizing` 

- One possible solution to this problem is to use the `box-sizing: border-box` property on all `div` elements. This property includes the border and padding in the `width` and `height` calculations, so it can help to ensure that the inner `div` elements fit within the outer `div` element without causing overflow.
- However using `box-sizing: border-box` can still cause problems if left or right margins are used on the inner boxes. In those cases, it may be necessary to adjust the margin values or use a different approach altogether.

#### Interaction with mixing units

- Using fixed dimension for one side and a relative variable dimension for another side will cause the image to stretch weirdly when browser is resized. 

  - For example, a fixed height and a width of 100% will cause the image to stretch horizontally but remain fixed vertically. 

    ```css
    img {
      display: block;
      height: 533px;
      margin: 0 auto;
      max-width: 800px;
      width: 100%;
    }
    ```

#### When to Use the Different Units

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

# My notes

## How to calculate minimum dimensions for container

Q: Calculate the minimum width and height that a **container element** needs to contain another element (including the container element's margins). 

1. Calculate the total dimensions of the **child** element.

- First use the `display` property to determine which properties are used by the browser and included in calculating dimensions.

  - `block` element:`width`, `height`, `padding`, `border`, `margin`

  - `inline-block` element: `width`, `height`, `padding`, `border`, `margin`

  - `inline` element: Browser ignores `width`, `height`, top and bottom `margin` specified in CSS, so we can't calculate the space this child element would take unless we know the **actual width and height** of the **content area**. The content area and the actual width and height is determined by the browser. 

    Keep in mind that top and bottom borders and padding may extend beyond the boundaries of the content area, so if there is content above or below the child element, it will overlap.

- Then use the `box-sizing` property to determine which properties are included in calculating the dimensions. 

  -  `content-box`: include `padding`, `border`, `margin` with `width` and `height` to determine dimensions. 
  -  `border-box`: Do not include `padding` and `border` to determine total horizontal or vertical dimensions, because these two properties are already included in the width and height. The `width` and `height` includes **content**, padding, and border. 

2. Calculate minimum dimension of container element and add it to the child element's dimensions.
   - ??? Note that `box-sizing` only plays a part when you specify the width and height of the element. If you don't specify a width and height, then your browser computes the width and height it needs from the elements it contains. This width and height are not affected by the `box-sizing` property of the container element. ???

- Use `box-sizing` property of container element.

  - If `border-box` is used, we must add the container padding and border with child element dimensions. This because for `border-box` sizing, the `width` and `height` includes the padding and border.

  - If `content-box` is used, we do not include the *container* element's padding or border, just the *child* element's dimensions. This is because we are calculating for the minimum dimension, so the minimum  `width` and `height` of the container is equal to the child element's width. 

## container element interactions

## What are containers

- **Containers** are `block` elements such as a `header` that contain one ore more elements. The master container (the outermost) is the `body`; every other element belongs to a container.
- We sometimes use the term **parent** to refer to a container, and use **child** to describe an element contained within a container. These relationship terms also let us talk about grandparents, ancestors, descendants, siblings, cousins, etc..
- ChatGPT: In HTML, a **container** is a type of **parent** element that has **child** elements nested within it, and is used to used to group related content together. 
  - Container elements do not have any inherent styling or layout, but are used to create a logical structure for the content and make it easier to apply styling and layout rules to the group of elements as a whole. 
- An element's `display` property and `box-sizing` can both impact the layout and flow of content within a container element. In other words, the layout and flow of content is impacted by the visual display model and box-sizing model. 

#### `display` interaction with flow 

- Depending on the element's `display` property / visual display model, the contained element flows differently within a container.
- `inline`
  - **Left and right padding/border overlap with container**: For `inline` elements, if contained element's left or right padding or border is wider than the container's width, then it will simply overlap with the container's content area, rather than the `inline` element going to a new line like `inline-block` elements would. 
  - **top & bottom padding/border overlap with container**: The top & bottom padding and borders may extend beyond the boundaries of the `inline` element's content area. This means that if there is content above or below the `inline` element, it will overlap with the top or bottom border / padding  of that `inline` element. This behavior should be avoided. 
  - **Margin causes adjacent `inline`** elements to overlap: If the margin is too big, inline elements would be pushed apart from each other, which may cause adjacent inline elements to overlap.
- `inline-block`
  - Padding, margin & borders impact on flow of elements in a container
    - Enlarging container: For `inline-block` elements, if padding, border, or margin is wider than container's width, then the contained element it will go to a new line, making the container bigger. This is assuming the container doesn't have fixed dimensions. 
    - Overflowing container: If a container element has smaller dimensions than a child element, the child element will overflow the container and appear on top of the container.
  - Do `inline-block` elements always appear side by side if their width properties add up to 100%?
    - Two consecutive `inline-block` elements with a total width of `100%` may render side by side, but not necessarily. 
    - To render side by side, you must account for any `whitespace` between the two elements, and must also account for their `border`s and `padding`; the left/right `margins` must be 0 in any case.
    - If `border-box` is used, then just need to account for the left/right `margins`. 
- `block`
  - By default, a `block` element occupies all horizontal space available within its container, with nothing to the left or right of the `block`. 
    - If your page contains 3 `block` elements directly inside the `body` element and nothing else, then all three elements will display one above the other like a stack of blocks. 
    - This behavior makes `block` elements predictable and easy to use.
  - Though a `block` element takes up an entire row in a container, this does not alter the width of the element. The browser renders the `block` element on a line by itself, but the element has the specified (or computed) width. 
    - For example, if you have a 500-pixel wide `blockquote` in a 900-pixel wide `section`, the `blockquote` element uses 500 pixels, but the browser will leave the remaining 400 pixels of the `section` empty.

#### `box-sizing` interaction with flow

- The `box-sizing` property also controls how an element's total width or height is calculated, so it affects the size of an element's box which in turn affects the flow of content within the container. 
- For `box-sizing: content box`, an element's width and height are calculated based on content within it and any paddings, borders, or margins are added to the total width and height. This can cause the element to expand beyond the size of its container if the padding, borders, or margins are large enough.
- When `box-sizing: border-box` is used, an element's width and height are calculated based on the content within it, as well as any padding and borders, but margins are still added to the total width and height. This can make it easier to control the layout of elements within a container, as the total width and height of the element will always include its borders and padding.

#### `inline` interaction with `border-box`

- Technically, it is possible to apply `border-box` sizing to an inline element using CSS, but it may not always work as expected due to the nature of inline elements. 
- When you apply `border-box` sizing to an inline element, the element's total width and height will include its content area, padding, and border. 
- However, because inline elements are designed to flow with the text and not disrupt the layout, adding padding and border to an inline element can cause the element to "break out" of the text flow, resulting in unexpected, overlapping layout issues.
  - This means that the element may be wider and taller than its actual content, and any padding or border added to the element will be included in its dimensions.
  - To avoid this issue, avoid adding padding and border to inline elements. 

## Relationship btwn visual display models & box sizing models

- Visual display models and box-sizing models are two concepts related to the layout and rendering of HTML elements on web pages.

- Visual display models define how HTML elements should be displayed on the screen, and they include inline, block, inline-block, table, and flex display modes. Each of these modes has different default rendering properties, such as how they flow with other elements and how they respond to size changes.

- Box-sizing models, on the other hand, define how the total width and height of an HTML element is calculated, including any padding, border, or margin that surrounds the content. There are two box-sizing models: content-box and border-box. In the content-box model, the total width and height of an element exclude any padding, border, or margin. In the border-box model, the total width and height of an element include any padding and border, but not margin.

How does visual display models relate to box sizing models?

- The relationship between visual display models and box-sizing models is that the default box-sizing value is different for different display modes. 
- For example, the default box-sizing for the block display mode is content-box, which means that the width and height of a block element exclude any padding, border, or margin. However, the default box-sizing for the flex display mode is border-box, which means that the width and height of a flex item include any padding and border, but not margin.

- Understanding both visual display models and box-sizing models is important for creating well-designed and responsive web pages. By setting the appropriate display mode and box-sizing value for each HTML element, you can control how it is rendered on the screen and how it interacts with other elements on the page.

## Spacing 

- Use `margin` to create spacing between adjacent elements 

- **Spacing**: Remember that in code, `inline` and `inline-block` elements respect white spaces around the character and in between then. And the white space collapses to a single white space character. So multiple space characters would render as one space character. 

- Use html comments to remove space between adjacent elements.

  - Assume here that `li` is now an `inline-block` element.

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

## Article about spacing

Read [this article](https://css-tricks.com/fighting-the-space-between-inline-block-elements/) for more information on why this problem occurs and to learn some other techniques for dealing with it.

- Problem: a series of `inline-block` elements formatted like you normally format HTML will have spaces in between them.

- In other words:

```html
<nav>
  <a href="#">One</a>
  <a href="#">Two</a>
  <a href="#">Three</a>
</nav>
nav a {
  display: inline-block;
  padding: 5px;
  background: red;
}
```

Will result in:

![spaces](https://i0.wp.com/css-tricks.com/wp-content/uploads/2012/04/spaces.png?resize=170%2C67)Often highly undesirable

- We often want the elements to butt up against each other. In the case of navigation, that means it avoids the awkward little unclickable gaps.

- This isn’t a “bug” (I don’t think). It’s just the way setting elements on a line works. You want spaces between words that you type to be spaces right? The spaces between these blocks are just like spaces between words. That’s not to say the spec couldn’t be updated to say that spaces between inline-block elements should be nothing, but I’m fairly certain that is a huge can of worms that is unlikely to ever happen.

- Here’s some ways to fight the gap and get inline-block elements sitting directly next to each other.

#### Remove the spaces

- The reason you get the spaces is because, well, you have spaces between the elements (a line break and a few tabs counts as a space, just to be clear). 

- Minimized HTML will solve this problem, or one of these tricks:

```html
<ul>
  <li>
   one</li><li>
   two</li><li>
   three</li>
</ul>
```

or

```html
<ul>
  <li>one</li
  ><li>two</li
  ><li>three</li>
</ul>
```

or with comments…

```html
<ul>
  <li>one</li><!--
  --><li>two</li><!--
  --><li>three</li>
</ul>
```

- They’re all pretty funky, but it does the trick.

#### Negative margin

- You can scoot the elements back into place with negative 4px of margin (may need to be adjusted based on font size of parent). 
- Apparently this is problematic in older IE (6 & 7), but if you don’t care about those browsers at least you can keep the code formatting clean.

```css
nav a {
  display: inline-block;
  margin-right: -4px;
}
```

#### Skip the closing tag

- HTML5 doesn’t care anyway. Although you gotta admit, it feels weird.

```html
<ul>
  <li>one
  <li>two
  <li>three
</ul>
```

#### Set the font size to zero

- A space that has zero `font-size` is… zero width.

```css
nav {
  font-size: 0;
}
nav a {
  font-size: 16px;
}
```

- Matt Stow reports that the font-size: 0; technique has some problems on Android. Quote: Pre-Jellybean does not remove the space at all, and Jellybean has a bug whereby the last element randomly has a tiny bit of space. [See research.](http://codepen.io/stowball/details/LsICH)

- Also note, if [you’re sizing fonts in ems](https://css-tricks.com/why-ems/), this zero font size thing can be an issue, since ems cascade the children would also have zero font size. Rems would be of help here, otherwise any other non-cascading `font-size` to bump it back up.

- Another weirdness! Doug Stewart showed me that if you use @font-face with this technique, the fonts will lose anti-aliasing in Safari 5.0.x. ([test case](http://jsfiddle.net/39GZd/7/)) ([screenshot](https://css-tricks.com/wp-content/uploads/2012/04/Screen-Shot-2013-06-11-at-4.23.03-PM.png)).

#### Just float them instead

- Maybe they don’t need to be inline-block at all, maybe they can just be floated one way or another. That allows you to set their width and height and padding and stuff. 
- You just can’t center them like you can by `text-align: center;` the parent of `inline-block` elements. Well… you kinda can but [it’s weird](http://codepen.io/chriscoyier/pen/blExo).

#### Just use flexbox instead

- If the [browser support](https://css-tricks.com/using-flexbox/) is acceptable to you and what you need out of inline-block is centering, you could use flexbox. They aren’t exactly interchangeable layout models or anything, but you might get what you need out of it.

# CSS Properties

Become comfortable with the CSS `display`, `box-sizing`, `width`, `height`, `padding`, `border`, and `margin` properties. Memorize this list of properties so you can look up the details when needed.

------

- `display`
- ``box-sizing`
- `width`
  - Fixed width. Image remains this fixed width even when resizing browser window.

- `height`
  - Fixed height. Image remains this fixed height even when resizing browser window. 

- `padding`
- `border`
-  `margin` 

# Other CSS properties

- The **`text-align`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the horizontal alignment of the inline-level content inside a block element or table-cell box.
  - This property alters an element's content.

- The **`max-width`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the maximum width of an element. It prevents the [used value](https://developer.mozilla.org/en-US/docs/Web/CSS/used_value) of the [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) property from becoming larger than the value specified by `max-width`.
  - `max-width` overrides [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width), but [`min-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/min-width) overrides `max-width`.
  - It does not include padding, borders, or margins.
- The **`min-width`** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the minimum width of an element. It prevents the [used value](https://developer.mozilla.org/en-US/docs/Web/CSS/used_value) of the [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) property from becoming smaller than the value specified for `min-width`.
  - It does not include padding, borders, or margins.

# Summary

This lesson discussed the fundamental concepts of CSS: the box model, spacing, and dimensional measurements. All these are crucial to a proper understanding of front-end development.

We learned how browsers treat everything on a page as a box. These boxes have properties including `width`, `height`, `padding`, `border`, and `margin` that control the size and spacing of each box. Our discussion explored how the browser flows elements onto the page. We also covered the top three `display` properties that influence this behavior: `block`, `inline`, and `inline-block`. Lastly, we talked about the `box-sizing` property, specifically the `content-box` and `border-box` sizing models. Together, these topics comprise the concept of the HTML box model.

From there we examined the sometimes confusing concepts of padding and margins in more detail and talked about when you should use margins and when you should use padding.

We ended our lesson with a look at the essential dimensional units used in CSS, including both absolute and relative units, and talked briefly about when to use them.

In the next lesson, we will take a look at one of the most ubiquitous components of web pages: images. They're everywhere, and now they're coming to a web page near you.

# Quiz Problem 6

```html
<!doctype html>
<html>
  <head>
    <title>My Picture</title>
    <meta charset="utf-8">
    <style>
      body {
        box-sizing: border-box;
        width: 1000px;
        padding: 50px;
        margin: 30px;
        border: 10px solid blue;
      }

      section {
        width: 75%;
        padding: 25px;
        margin: 15px;
      }

      img { width: 80%; }
    </style>
  </head>
  <body>
    <section>
      <img src="picture.jpg">
    </section>
  </body>
</html>
```

Determine the final width of the image, in pixels. Assume that `picture.jpg` is 800px in width.

- `body` is uses `border-box` sizing property, so the **content width** is the width subtract padding and borders. 1000 - (50 x 2) - (10 x 2) = 880. 
- `section` is using the default `boxing-size` property `content-box`, so the content width is the given width property, 75%.  75% of 880 = 660
- `img`'s width propery is 80% of `section`'s content width 660 = 528. Since `img` is also using default `boxing-size` property `content-box`, any border and padding has to be added into the final calculation. But because `img` has no borders, padding, or margin, 528px is the final width. 