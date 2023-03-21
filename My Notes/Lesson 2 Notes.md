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

------

### Summary

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

### padding

- The **padding** is an area that surrounds the content area of the box and separates the content from its border. It is typically opaque and hides anything that it overlays.

Syntax

- When **one** value is specified, it applies the same padding to **all four sides**.
- When **two** values are specified, the first padding applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first padding applies to the **top**, the second to the **right and left**, the third to the **bottom**.
- When **four** values are specified, the paddings apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### margins

- The **margin** is a transparent area that lies outside the border and supplies separation between elements.

Syntax

- When **one** value is specified, it applies the same margin to **all four sides**.
- When **two** values are specified, the first margin applies to the **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first margin applies to the **top**, the second to the **right and left**, the third to the **bottom**.
- When **four** values are specified, the margins apply to the **top**, **right**, **bottom**, and **left** in that order (clockwise).

### borders

- The **border** is a boundary that surrounds the padding.

Values

- ```
  <line-width>
  ```

  Sets the thickness of the border. Defaults to `medium` if absent. See [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width).

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

- A **`block` element** takes up the full width available and starts on a new line, regardless of the width of the content inside it. 
  - Examples of block-level elements include `<div>`, `<p>`, and `<h1>`.
- [Block elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) appear on almost all web pages: headings, paragraphs, sections, tables, forms, lists, and more are `block` elements.

- Most `block` elements group one or more elements - some of which may themselves be `block`s - into areas of the page. 

  - For instance, `header` elements group together elements into a page header. 
  - **Containers** are `block` elements such as a `header` that contain one ore more elements. The master container (the outermost) is the `body`; every other element belongs to a container.

  - We sometimes use the term **parent** to refer to a container, and use **child** to describe an element contained within a container. These relationship terms also let us talk about grandparents, ancestors, descendants, siblings, cousins, etc..

<u>Common Block Elements</u>

- [Block elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements) appear on almost all web pages: headings, paragraphs, sections, tables, forms, lists, and more are `block` elements.

- Most elements are `block` elements by default. Here are some of the most common:

  - `section`, `article`, `aside`, `header`, `footer`

  - `p`

  - `h1` through `h6`
  - `<div>`

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

####  `block` layout properties

- With `block elements` we can compute dimensions directly from CSS properties. 

- `block` elements use the **box properties** (`width`, `height`, `padding`, `border`, `margin`) to determine the size of the element. The browser reserves a box of the right size on the page, and this is where it draws the content. 
- A block element will always appear on a line by itself within it's container `div` no matter its width. 
- Though a `block` element takes up an entire row in a container, this does not alter the width of the element. The browser renders the `block` element on a line by itself, but the element has the specified (or computed) width. 
  - For example, if you have a 500-pixel wide `blockquote` in a 900-pixel wide `section`, the `blockquote` element uses 500 pixels, but the browser will leave the remaining 400 pixels of the `section` empty.
- Example
  - If you want an element that is 928 pixels wide, 168 pixels high, with 20 pixels of left and right padding, 10 pixels of padding at the top and bottom, a 1-pixel border, and a 28-pixel bottom margin, all those properties will play a part in the overall dimensions of the element. 
  - Thus, the overall dimensions will be 970 x 218 pixels. (As we'll see later, it's possible to change the way the browser calculates the dimensions. This example assumes that you're using the browser defaults)

<u>Width and height may include padding and border</u>

- As we'll see later, the `width` and `height` of an element may include the `padding` and `border` in addition to the content area. By default, `width` and `height` exclude the `padding` and `border` from the measured content area. We'll learn more about this fact in the next assignment when we learn about box sizing.

<u>Width and height always excludes margins</u>

- Another item of note is that the height and width values never include the margins. Technically, margins provide spacing between elements but are not part of them. However, you do need to account for the margins when determining whether an item will fit in a given space.

<u>Convert element to `block`</u>

- You can convert any element to a `block` element with the `display: block` CSS property. It's common to render links (`a`) and images (`img`) as `block` elements.

### `inline`

- **An `inline` element** only takes up as much width as its content requires and does not start on a new line. 
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

<u>Flow</u>

- `inline` elements flow from one line to the next, which lets you place `inline-block` elements side by side with other `inline` or `inline-block` elements.
- The main idea is that the left/right factors affect the **flow**, while the top and bottom do not.

![Box layout at 800 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-1.png)

*Figure 1*: Element flow at 800 pixels

![Box layout at 700 pixels width](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_2/everything-a-box-2.png)

*Figure 2*: Element flow at 700 pixels

#### `inline` Layout properties

- inline is tricky.

<u>Which dimension properties not ignored by browser for `inline elements`</u>

- Left and right `margins`
- `border`s: but the results may look odd (see the next section).
  - Top and bottom borders may extend beyond the boundaries of the content area. 
- Top and bottom `padding`:  but you won't notice this unless you have a border or background.
  - Padding may also extend beyond boundaries of content area. 

<u>dimensions properties ignored by browser</u>

- *ignore* the `width` and `height` properties (except with the `img` element), but instead use values computed from the element content.

- *ignore* top and bottom margins. 

<u>`inline` elements vs `block` elements</u>

- `inline` elements handle the dimension properties (`width`, `height`, `padding`, `border`, and `margin`) differently from the way `block` elements treat them. This difference is where the box model starts to get messy.

- Browsers handle *left* and *right* margins and padding for `inline` elements in the same way as for `block` elements, but they process other box model properties differently. 

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

- An **`inline-block` element** behaves like an inline element in terms of not starting on a new line, but like block element, it allows you to set a width and height, as well as margins and padding. 
  - This makes it useful for creating horizontal lists or for aligning elements next to each other. 
  - Examples of inline-block elements include `<button>`, `<input>`, and `<label>`.

> Legacy Model
>
> - The `inline-block` visual display model is a *legacy* model. It is equivalent to a new model called `inline flow-root`. 
> - However, despite its legacy status, `inline-block` is probably not going to go away anytime soon; there are too many websites that still use it. 
> - We will use `inline-block` throughout this course; it will probably be several years before `inline flow-root` and other new display models gain traction.

- `inline-block` elements are a mixture of both previous types. They act like `block` elements, except for one significant detail: `inline-block` elements do not take up an entire row when the `width` property is less than the available width. 

<u>Flow</u>

- Inline-block elements can have a set width and height, but they still flow inline, making them useful for creating more complex layouts.

- Similar to `inline` elements : flow in the same way that text and `inline` elements flow from one line to the next (see Figures 1 and 2 on the previous page), which lets you place `inline-block` elements side by side with other `inline` or `inline-block` elements.

#### `inline-block` layout properties

- `display: inline-block` meaning that is an `inline-block` element, we can compute dimensions directly from CSS properties. 

- Similar to block elements but different from `inline` elements: 
  - `inline-block` elements set `width` and `height` properties. 
  - The padding, borders, and margin are used to determine the size of the element. 

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

Main Takeaway

- The usable `box-sizing` property values are `content-box`, and `border-box`. The CSS standard deprecates the `padding-box` setting; **don't use it**.

## `content-box`

- The `content-box` setting is the default setting for the `box-sizing` property for all elements in all modern browsers. 
- In this model, the `width` and `height` properties specify the size of the **actual content area**. You need to add padding and borders to get the size of the **visible box**.
  - `width` x `height` = **actual content area**
  - `width` x `height` + padding + borders = **visible box**. 
  - Margin not included in content-box.

![image-20230320185240802](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230320185240802.png)

Top represents content-box, bottom represents border-box. 

## `border-box`

- The `border-box` setting causes the browser to interpret the `width` and `height` properties as the total width and height of the box excluding the margins. 
- The width and height include the **content area** as well as the padding and borders.
  - `width` x `height` = **visible box** 
  - Visible box = content area + padding + borders. 
  - Margin not included in content-box

<u>Why border-box is best</u>

- The `border-box` setting is "best" since it simplifies the math a front-end developer must do. 
- For example, if we have a box with a width of 50% and padding of 12px; `border-box` ensures that it's precisely 50% of the container width, not 50% plus 24 pixels.

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