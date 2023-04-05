# Lesson 6 : Advanced Layout

# Introduction

Thus far, we've stuck to the CSS Box Model and used it to get a little control over the page flow. We haven't worried much, though, about where the browser places content, other than using the `display` property to control whether two adjacent elements will appear on the same line. The material flows down the page naturally, left-to-right and top-to-bottom, with line breaks inserted where needed. This simple "mental model" of how browsers work is useful as you're starting out, but, sooner or later you will run into more complicated layouts.

At the simplest level, most web pages have a typical layout: a header, footer, navigation bar, and the content. Your HTML file should reflect this structure with each area defined in sequence. You can build hundreds of pages following this pattern, and control them all with a single CSS file.

What happens when your boss wants you to move the ad bar from above the header to a position below it? Your HTML files probably look something like this:

```html
<body>
  <!-- Yes, `aside` is appropriate semantic markup for ads -->
  <aside id="ad-banner">content</aside>
  <header>content</header>
  <main>content</main>
  <footer>content</footer>
</body>
```

Do you want to go through hundreds of pages making the same edit to move the ad banner below the header? Of course not. Instead, you'll look for a way to edit the single CSS file. As it happens, it's not that hard to change the layout as needed using CSS.

This same need for ignoring the location of elements in the HTML file and positioning them elsewhere occurs when you need to make your website look different on cell phones, tablets, and desktop computers. Again, you can use CSS to reposition content elsewhere on the page when the display size reaches a certain point.

In this lesson, we'll explore the different ways you can position and lay out items on a web page. That is, you'll learn how to tell the browser where to place each element. Sounds simple, right? In principle, it is. In practice, layout and positioning may be the hardest CSS topics you will encounter.

Don't let that last paragraph scare you. Both concepts are learnable. Once learned, you will be able to give your web pages a professional touch that you can't achieve any other way.

## What to Focus On

In this lesson, we'll take a whirlwind tour of some layout-related features of CSS: floats, positioning, flex, grid, CSS frameworks, and responsive design. None of these topics are easy; in fact, unlike most of our material here at Launch School, **we don't expect you to master them in this lesson**. Instead, familiarize yourself with the concepts and what you can do with them, then use Google and MDN when you need to use them. Master the material we discussed in the previous lessons, but leave advanced layout until you're ready to use it. Don't struggle. When you've had more experience, you will get a better handle on the subject.

For now, you should know how to use the following in simple projects and problem sets:

- floated elements, including how to clear floats
- positioning with `position: absolute`
- basic media queries
- liquid and fluid layouts

### Study From The Summary

Spend time with the Summary at the end of this lesson. It reviews the topics and terminology you should master before moving on.

# Floats

Thus far, when we've wanted to place elements side by side, we've used `inline` or `inline-block` display types. There are some cases where that is not the best solution, e.g., when you need to collapse the whitespace between two side-by-side `inline-block` elements. As we've seen elsewhere, you need some ugly hacks to avoid that whitespace. Floats sometimes come in handy in these situations; a floated element tells the browser to move it as far to the left or right as possible but to leave the remaining space available for additional content.

Elements float within their immediate container, which puts a limit on how far the browser can move the floated element. If you float two elements in a row in the same direction, their vertical edges (counting their margins) will touch, providing they fit in the same row. Any whitespace (other than margins and padding) that would otherwise appear between the elements will collapse.

```html
<div class="outer">
  <div class="primary">
    <p>Main Content</p>
  </div>

  <div class="secondary">
    <p>Sidebar 1</p>
  </div>
</div>
```

```css
html {
  font-size: 16px;
}

* {
  margin: 0;
  padding: 0;
}

body {
  padding: 0.5rem;
}

p {
  color: black;
  font-family: serif;
  font-size: 1.5rem;
  font-weight: bold;
}

.outer {
  border: 1px solid gray;
  overflow: hidden;
  width: 100%;
}

.primary, .secondary {
  border: 1px solid black;
  box-sizing: border-box;
  text-align: center;
}

.primary {
  background-color: moccasin;
  float: left;
  height: 100px;
  line-height: 100px;
  width: 65%;
}

.secondary {
  background-color: coral;
  float: left;
  height: 75px;
  line-height: 75px;
  width: 30%;
}
```



![Floating Left](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/floats-01.png)



If we want to add some space between the two boxes, we can add a right margin to the primary column or a left margin to the secondary. We can also change our secondary column to float right and leave the space between the elements empty; we don't have to calculate the margins now.

```css
.secondary {
  float: right;
}
```



![Floating Left and Right](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/floats-02.png)



Our designer is looking over our shoulder and thinks the page will look better if we swap the primary and secondary columns. We can readily reverse the order that they appear in the HTML and change the floats to match, but suppose this page is one of several hundred that all use the same CSS and layout. It would be easier to update the CSS if we can. As it happens, we can change the `float` values, and our columns will switch places.

```css
.primary {
  float: right;
}

.secondary {
  float: left;
}
```



![Floating Right and Left](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/floats-03.png)



Let's see what happens when the floated elements won't all fit:

```html
<div class="outer">
  <div class="primary">
    <p>Main Content</p>
  </div>

  <div class="secondary">
    <p>Sidebar 1</p>
  </div>

  <div class="secondary">
    <p>Sidebar 2</p>
  </div>

  <div class="secondary">
    <p>Sidebar 3</p>
  </div>

  <div class="tertiary">
    <p>Another Sidebar</p>
  </div>

  <div class="secondary">
    <p>Sidebar 4</p>
  </div>

  <div class="tertiary">
    <p>Another Sidebar 2</p>
  </div>

  <div class="secondary">
    <p>Sidebar 5</p>
  </div>

  <div class="secondary">
    <p>Sidebar 6</p>
  </div>

  <div class="secondary">
    <p>Sidebar 7</p>
  </div>

  <div class="secondary">
    <p>Sidebar 8</p>
  </div>
</div>
```

```css
.primary, .secondary, .tertiary {
  border: 1px solid black;
  box-sizing: border-box;
  text-align: center;
}

.tertiary {
  background-color: powderblue;
  float: left;
  height: 200px;
  line-height: 200px;
  width: 40%;
}
```

As you might expect, the extra floats wrap around to the next available spot. What's surprising here is that the items that wrapped did so in odd ways.



![Crazy floats 1](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/floats-04.png)



That looks crazy! Look how Sidebar 2 ended up under Sidebar 1, but Sidebars 5, 6, and 7 stacked up on the right side, and Sidebars 4 and 8 didn't slide under Sidebar 2 like you may have expected. There are rules to this craziness, but you don't have to know them. Most developers try to keep their use simple when it comes to floats: make sure all floats in a group have the same height and direction (left or right), and they will wrap logically. You can also mix left and right floats with predictable results if you're careful, again provided the heights are consistent. Better yet, use Flex, Grid, or a Frameworks package as discussed later in this lesson.

# Containing Floats

When we use floats for layout, we often run into the "containing floats" problem. Let's look at an example:

```html
<div id="columns">
  <div id="primary">
    <h1>Main Content</h1>
  </div>

  <div id="secondary">
    <h3>Sidebar Content</h3>
  </div>
</div>
```

Copy Code

```css
#columns {
  background-color: #e0e0e0;
  box-sizing: border-box;
  margin: 0 auto;
  padding: 20px;
  width: 780px;
}

#primary, #secondary {
  background-color: yellow;
}

#primary {
  float: left;
  width: 500px;
}

#secondary {
  float: right;
  width: 200px;
}
```



![Uncontained floats](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/containing-floats-01.png)



What's going on with our columns? They look like they're outside of the gray columns container. Well, the boxes are partly inside and partly outside of the container. What's happening is a typical float issue: The browser removes floats from the normal document flow, and that means the container no longer contains the floated items. Hence, the browser cannot determine the container's height, so it can't render the container correctly.

Floated elements and absolute or fixed position elements (we'll discuss those soon) typically don't affect the dimensions of their parents. Since the browser removes the content from the flow, the rendering engine no longer cares about them. The floated or positioned elements can overwrite other content. To fix this problem, we must add an `overflow` option to the floated element's container or wrap it in a **clearfix**.

`overflow: hidden` (or `overflow: auto`) is the simplest way to clear a floated element. Apply the property to the container element and watch it expand to wrap your floated elements.

```css
#columns {
  overflow: hidden;
}
```



![Floats contained with overflow](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/containing-floats-02.png)



The `overflow` ensures that the parent container properly envelops the two columns.

While `overflow` works in most cases, there are two edge cases you should know about:

- `overflow: hidden` can cut off (clip) content that exceeds the allocated space for the text if the container has a set height or width
- `overflow: auto` can add unwanted scrollbars, which is a browser specific behavior.

If you experience either problem, you can use the clearfix approach described below.

Why does `overflow` work? According to the existing W3C standards documentation, `overflow` creates a **block formatting context** which contains everything inside the element to which it applies, and that includes floats. For now, that's all you need to know. If you want to learn more, google "block formatting context" and "floats."

Instead of `overflow`, you can add a **clearfix** to the container. A clearfix is a standard pattern that developers use to ensure a container doesn't lose its floated children. It employs an invisible block element as the last child element of the container and the `clear` property. Let's update our code to show the clearfix in operation:

```css
#columns {
  /* overflow: hidden; */
}

#columns::after { /* This rule is the clearfix */
  clear: both;
  content: "";
  display: block;
}
```



![Floats contained with clearfix](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/containing-floats-03.png)



As with `overflow`, the clearfix ensures that the parent container wraps the two floated columns. Let's examine it.

The `::after` pseudo-element creates a child element at the end of the selected element(s); here, we put it at the end of our container. We define this child as a block element, which means it must be on a line by itself. The `content: ""` property sets the content of the child element: an empty string. Thus, the clearfix child is invisible. Lastly, we use `clear: both` to "clear" the floats inside the container, which forces the invisible child directly below the floated content. The final result is similar to that of using `overflow`: the container can see the clearfix, so all it needs to do is stretch itself to enclose the clearfix and the floated content as well.

`clear` takes values of `right`, `left`, or `both`. `right` and `left` refer to the type of floated element it will clear, while `both` clears any floated element that it finds. You can use any of these values with `clear`, but you should use `clear: both` unless you find that you need `clear: left` or `clear: right` for some reason.

To help clarify our explanation of `::after`, let's look at the following example that also uses the companion `::before` pseudo-element:

```html
<p>Hello</p>
```

```css
html {
  font-size: 48px;
}

p {
  margin: 0;
  padding: 0;
}

p::before {
  content: "+- ";
  color: red;
}

p::after {
  content: " -+";
  color: blue;
}
```



![before and after](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/before-and-after.png)



Use double colons with pseudo-elements. The standard lets you get away with a single colon, but this flexibility may not endure.

CSS presently supports around a dozen pseudo-elements, and nearly half of those are experimental. `::after` and `::before` are the most useful. See the MDN page on [Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) for more information.

# Practice Problems: Floats (1)

For these problems, you'll work with two columns of different sizes. You can grab some content for both over at [lipsum.com](http://www.lipsum.com/); generate several paragraphs of copy for both columns. For the best results, the two columns should have differing amounts of text.

After most problem descriptions, you'll see a screenshot of how your page should look. The background colors help show where each element begins and ends; choose any colors you want.

1. Create a `section` element with a fixed width of 750px, and horizontally center it on the page using CSS margins. Create two columns inside it, a 500px-wide `article` and a 250px-wide `aside`, positioned side by side with CSS floats. The left column should contain the `article`. Each column should have `1rem` of whitespace between the text and edges of the container. Add some background colors to the `body`, `section`, `article`, and `aside` so you can see the boundaries of each element.

   

   ![Fixed width floated columns](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/f1.png)

   

   Solution

   ```html
<section>
     <article>
       <p><!-- lipsum content #1 --></p>
       <p><!-- lipsum content #2 --></p>
         <!-- more content -->
     </article>
     <aside>
       <p><!-- lipsum content #3 --></p>
       <p><!-- lipsum content #4 --></p>
         <!-- more content -->
     </aside>
   </section>
   ```
   
   

   ```css
body, section, article, aside {
     margin: 0;
     padding: 0;
   }
   
   body {
     background-color: #ccc;
   }
   
   section {
     background-color: white;
     margin: 0 auto;
     width: 750px;
   }
   
   article, aside {
     box-sizing: border-box;
     float: left;
     padding: 1rem;
   }
   
   article {
     background-color: #ffc;
     width: 500px;
   }
   
   aside {
     background-color: #cfc;
     width: 250px;
   }
   ```
   
   You can also float the `aside` to the `right` since the total of the column widths matches that of the container.

   Note that we need padding to provide the whitespace between the text and the edges of the container. Since we're mixing `padding` with `width`, we should also use `border-box` box-sizing to simplify our calculations.

2. If necessary, add some more text to the `article` to ensure it is noticeably taller than the `aside`. Can you see the background color you set on the section element? Why not? What can you add to your CSS to fix it?

   

   ![Fixed width floated columns with padding](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/f2.png)

   

   Solution

   Since the browser removes floats from the normal flow, the parent element doesn't contain them properly. Thus, the background color doesn't paint to the bottom of the taller column. You need to tell the container (the `section`) to expand itself enough to cover the area used by the taller column. Use `overflow` or a clearfix as desired.

   ```css
   /* Using overflow */
   section {
     overflow: hidden;  /* beware of clipping */
   }
   ```
   
   or:

   ```css
   /* Using clearfix */
   section::after {
     clear: both;
     content: "";
     display: block;
   }
   ```
   
   You should now see some white background beneath the shorter of the two columns.
   
3. Remove the fixed width of 750px from the `section` and set a maximum width of 1000px instead. Modify the right column to take up the remainder of the space without floating the column or giving it a specific width.

   Solution

   Adding `overflow: hidden` to the last floated element in a row and removing the `float` and `width` properties cause it to take up the remaining space within the row. This technique is useful when your last element should take up the leftover space in a variable width layout.

   ```css
section {
     max-width: 1000px;
     /* width: 750px; */
   }
   
   aside {
     float: none;
     overflow: hidden;
     /* width: 250px; DELETE */
   }
   ```
   
   Modify the CSS as shown and watch what happens as you adjust your browser's width. Be sure to narrow your browser down to the point where there is no more room for the `aside` and observe the behavior as go past that point.

4. Change the left column from a fixed width to a variable width of 70% of the parent's width.

   Solution

   If you haven't already done so, use the `box-sizing` property to ensure that your `article` takes up precisely 70% of the row width, rather than 70% plus the padding.

   ```css
   article {
     box-sizing: border-box;
     width: 70%;
   }
   ```
   
5. Add a `footer` below the two columns.

   

   ![Clearing columns](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/f3.png)

   

   Solution

   If you used a clearfix in problem 2, you can remove it and clear the floats with the `footer` element and `clear: both`.

   ```html
   <section>
     <article>
       content
     </article>
     <aside>
       content
     </aside>
     <footer>
       <p><!-- lipsum content #7 --></p>
     </footer>
   </section>
   ```
   
   ```css
   section {
     /* overflow: hidden; */
   }
   
   /*
   section::after {
     clear: both;
     content: "";
     display: block;
   }
   */
   
   footer {
     background-color: #ebecff;
     clear: both;
     padding: 1rem;
   }
   ```

# Practice Problems: Floats (2)

For this problem set, use the Inspector to add CSS properties to the working page and see immediate results. If you need a review of the Inspector, see [the documentation](https://developers.google.com/web/tools/chrome-devtools/inspect-styles/). You must know how to inspect and edit pages and styles for this assignment; you don't need any other developer tools.

1. [Open this page](https://d3jtzah944tvom.cloudfront.net/lesson_4/exercises_floating_positioning/float1.html) then open the Inspector and find the div with the "floated" ID. Select it, then make the `div` float left by updating the styles tab.

   Solution

   The page should now look something like this.

   

   ![Floating a short column](https://d3jtzah944tvom.cloudfront.net/lesson_4/exercises_floating_positioning/float1.jpg)

   

2. Can you determine why the blue paragraph hangs out beneath the right edge of the orange `div`? Add a CSS property to force the blue box beneath the orange; don't worry about the widths - the blue box will be wider than the orange.

   Solution

   ```css
   /* A selector of `#floated + p` will also work */
   main > p {
     clear: both;
   }
   ```
   
3. Why is the orange container now narrower than the blue? How can you keep the orange box floated but take on the same width as the blue?

   Solution

   When you float an element, it uses as much space as it needs to display its content, which is less than that required by the `main` element. To use all available width, add `width: 100%`.

   ```css
   #floated {
     width: 100%;
   }
   ```
   
4. Change the floated element's width to 20%, then remove the `clear` from the `p` below it. Try setting a left margin on the blue paragraph equal to the width of the floated element.

   Solution

   This code works to produce a two-column layout here.

   ```css
#floated {
     width: 20%;
   }
   
   main > p {
     /* clear: both; */
     margin-left: 20%;
   }
   ```
   
   This code works, but it isn't robust. For instance, if you add a fixed height to the blue paragraph that isn't enough to fully contain the text, the text will overflow. If you add `overflow: hidden` to the blue box, the overflowing text will get clipped. If you add `overflow: auto` instead, you will be able to scroll the blue box.

   Can you find other ways to demonstrate the lack of robustness?

5. Remove the left margin on the blue paragraph, and have it float right instead. What do you think will happen? Will the orange and blue elements sit side by side?

   Solution

   The blue element ends up too large to fit within the remaining space. Remember that floated elements take up as much space as they need for the content, within the bounds of any space constraints.

6. Ideally, you want both boxes side by side. In an attempt to do that, you add a width of 80% to the blue paragraph. What happens? How can you fix this problem without changing the width setting?

   Solution

   Since the paragraph has 1em of padding on all sides, we need to account for that when we set the width. In fact, as is, the blue box is 80% of the container width plus an additional 2rem. To fix this issue, set the box-sizing mode to `border-box`.

# Positioning

When you need to fine-tune the placement of elements within their containers or need to overlay them atop others, CSS positioning comes into play. Some people find positioning hard to understand; the rules are a bit complicated. We'll look at some of the basics in this assignment to get you heading in the right direction, but someday you'll need to expand your knowledge; a google search produces plenty of tutorials and discussions that will help.

## Offset Properties

Before we talk about the `position` property, we need to discuss the **offset properties**: `top`, `right`, `bottom`, and `left`. They work in conjunction with `position` to determine what direction you want to move an element and how far. Each offset measures the *inward* distance from the side of the container named by the offset property. For instance, `bottom: 50px` indicates a position 50px inward from (above) the bottom edge of the container. If you memorize one fact from this page, remember that *the offset is always inward* when working with positive offset values.

Negative offsets shift elements in the opposite direction. That is, they cause the browser to push the edges outward from the container.

## The `position` Property

The `position` property tells the browser how to position the selected elements.

### `position: static`

Static positioning is the default. While floated, grid, flex, as well as elements with absolute and fixed positioning get removed from the page flow, statically positioned items are part of the page flow. They appear in the same order they appear in the markup. The offset properties do not affect static elements.

### `position: relative`

Relative positioning moves an element to a new position relative to where the browser would otherwise put it. For instance, if you include `left: 50px` and `bottom: 100px` with `position: relative`, the browser will shift the element 50px inward from the left edge and 100px upward from the bottom edge from where the browser would place it otherwise.

When using relative positioning, you should typically provide at most one vertical offset (`top` or `bottom`) and at most one horizontal offset (`left` or `right`). However, the CSS standard does permit using both vertical or both horizontal offsets at the same time:

- `left` overrides `right` for left-to-right languages.
- `right` overrides `left` for right-to-left languages.
- `top` overrides `bottom` at all times.

Relative positioning *does not* remove an item from the document flow. The browser positions the next element as though the previous one still occupied its pre-offset location. You can see this behavior in the examples below.

```html
<section>
  <aside class="normal">normal</aside>
  <aside class="shifted pos">top</aside>
  <aside class="shifted neg">-top</aside>
  <aside class="normal">normal</aside>
</section>
```

```css
section {
  border: 1px solid gray;
  padding: 70px 10px;
}

aside {
  border: 1px solid black;
  display: inline-block;
  height: 100px;
  line-height: 100px;
  margin: 0;
  padding: 0;
  text-align: center;
  width: 100px;
}

.normal {
  background-color: yellow;
}

.shifted {
  position: relative;
}

.pos {
  background-color: cyan;
  top: 60px;
}

.neg {
  background-color: lightgreen;
  top: -60px;
}
```



![Relative positioning, top](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-01.png)



Above, we see top positioning. Notice how each box respects the area that the previous one would occupy in the absence of positioning offsets.

```html
<section>
  <aside class="normal">normal</aside>
  <aside class="shifted pos">bottom</aside>
  <aside class="shifted neg">-bottom</aside>
  <aside class="normal">normal</aside>
</section>
```

```css
.pos {
  /* top: 60px; */.
  bottom: 60px;
}

.neg {
  /* top: -60px; */.
  bottom: -60px;
}
```



![Relative positioning, bottom](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-02.png)



The above example depicts bottom positioning. Again, each box respects the area that the previous one would occupy in the absence of positioning offsets.

```html
<section>
  <aside class="normal">normal</aside>
  <aside class="shifted pos">right</aside>
  <aside class="shifted neg">-right</aside>
  <aside class="normal">normal</aside>
</section>
```

```css
section {
  padding: 10px;
}

.pos {
  /* bottom: 60px; */.
  right: 60px;
}

.neg {
  /* bottom: -60px; */.
  right: -60px;
}
```



![Relative positioning, right](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-03.png)



With this example, we see right positioning: once more, each box respects the area that the previous one would occupy in the absence of positioning offsets.

```html
<section>
  <aside class="normal">normal</aside>
  <aside class="shifted pos">left</aside>
  <aside class="shifted neg">-left</aside>
  <aside class="normal">normal</aside>
</section>
```

```css
.pos {
  /* right: 50px; */.
  left: 50px;
}

.neg {
  /* right: -50px; */.
  left: -50px;
}
```



![Relative positioning, left](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-04.png)



With left positioning, each box still respects the area that the previous one would occupy in the absence of positioning offsets. Since we shifted the green and cyan boxes toward each other, the green box now overlays most of the cyan box.

### `position: absolute`

Absolute positioning causes the browser to move the element to a new position within a container element. By default, the container is *the nearest ancestor element that has a fixed, relative, absolute, or sticky `position`*. (We don't discuss sticky positioning in this course.) If no such ancestor is present, the browser uses the initial containing block (the body); that is, the browser positions the element at an absolute position on the page.

```html
<section>
  <aside class="relative">
    <div class="absolute-1"></div>
  </aside>
  <aside class="relative">
    <div class="absolute-2"></div>
  </aside>
  <aside class="relative">
    <div class="absolute-3"></div>
  </aside>
</section>
```

```css
section {
  border: 1px solid gray;
  padding: 10px 10px 60px;
  width: 780px;
}

aside {
  border: 1px solid black;
  display: inline-block;
}

.relative {
  background-color: yellow;
  height: 200px;
  left: 0;
  margin: 0 25px;
  position: relative;
  top: 0;
  width: 200px;
}

.absolute-1 {
  background-color: lightgreen;
  bottom: 33%;
  left: 33%;
  position: absolute;
  right: 33%;
  top: 33%;
}

.absolute-2 {
  background-color: cyan;
  bottom: 150px;
  left: 0;
  position: absolute;
  right: 20px;
  top: 0;
}

.absolute-3 {
  background-color: pink;
  bottom: -50px;
  left: 100px;
  position: absolute;
  right: -40px;
  top: 150px;
}
```



![Absolute positioning](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-05.png)



In the above example:

- The yellow boxes are our containers; they use relative positioning. Recall that absolute positioning requires an ancestor element that uses relative, absolute, or sticky positioning; otherwise, it uses the body.
- The green box demonstrates how we can use absolute positioning to center an item within its container: set all four offset properties to the same value. Note: this won't work if the green box has an explicit height or width; see the next assignment for a way to handle that situation.
- The cyan box shows a different example of absolute positioning. The critical point is that we need to specify the offset positions as distances from the four corresponding sides. Thus, the bottom of the cyan box is 150px from the bottom of the yellow container.
- The pink box reveals that you can use negative offsets, which moves part of the pink box outside of its container.

Absolute positioning removes elements from the normal document flow. No matter where you position it, the browser won't treat that space as occupied space. Let's look at an example using code that is similar to the previous example:

```html
<section>
  <aside class="relative">
    <div class="absolute-1"></div>
    <div class="absolute-2"></div>
    <div class="absolute-3"></div>
    <div class="unpositioned"></div>
  </aside>
</section>
```

```css
.unpositioned {
  background-color: black;
  height: 100px;
  width: 100px;
}
```



![Absolute positioning and the flow](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-06.png)



Here, we've put all three boxes with absolute positioning inside our container, along with an unpositioned (`static`) black box. As you can see, the positioned boxes remain in their original positions relative to the yellow container, while the black box acts as though there is nothing else present.

### `position: fixed`

Fixed positioning behaves as it sounds: it sets an element to a fixed position within the window. The element **does not move** if the user scrolls the page. You've probably seen this on some websites, with a sticky navigation bar at the top of the window while you continue to scroll down the page.

```html
<header>
  Fixed Position Demo
</header>

<section>
  <p>
    This part of the window scrolls up and down.
  </p>
  <p>
    Sint cillum tempor esse eu laborum ipsum eu. Cupidatat sint laboris
    excepteur eu enim adipisicing officia. Sunt cupidatat id ipsum reprehenderit
    et irure veniam ex. Duis cupidatat ullamco adipisicing mollit ea nulla irure
    mollit eu. Aliqua laboris aute sint consectetur aute occaecat cillum sint
    aliqua. Culpa eiusmod officia Lorem dolore.
  </p>
  <p>
    Dolor proident mollit eiusmod. Cupidatat Lorem ipsum irure culpa quis. Non
    consequat sunt non nostrud sint id quis consectetur aute. Exercitation nisi
    tempor excepteur. Magna exercitation ad amet ut commodo consequat non. Duis
    veniam culpa esse magna laborum aute sunt quis.
  </p>
  <!-- add several more paragraph here -->
</section>
```

Copy Code

```css
header {
  background-color: lightgreen;
  font-size: 4rem;
  height: 8rem;
  left: 0;
  line-height: 8rem;
  opacity: .75;
  position: fixed;
  text-align: center;
  top: 0;
  width: 100%;
}

section {
  margin: 0 auto;
  padding: 10rem 1rem 0;
  width: 600px;
}

p {
  font-size: 2rem;
  margin-bottom: 1.5rem;
}
```



![Fixed positioning](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/positioning-07.png)



We've given the fixed element some opacity so you can see how the rest of the page scrolls beneath it. You must **run the code in your browser to see it in action**, though. Reduce the browser's height if you can't scroll the window from the start.

# Practice Problems: Positioning

For these problems, create a simple HTML page with a few paragraphs of text. You should have enough content that you must scroll the browser window to read the bottommost content; you can also shorten the window height if you prefer. If you add any elements to the page, add them after the paragraph elements.

1. Starting with a new document, create an element and position it at the top right of the page. It should scroll with the rest of the window when you scroll.

   

   ![Absolute positioning](https://d3jtzah944tvom.cloudfront.net/lesson_4/exercises_floating_positioning/p1.jpg)

   

   Solution

   Copy Code

   ```html
   <section>
     <!-- text paragraphs go here -->
   </section>
   
   <div id="positioned">I'm positioned!</div>
   ```

   ```css
   body {
     margin: 0;
     padding: 0;
   }
   
   section {
     border: 8px solid #cecece;
   }
   
   #positioned {
     background-color: #ffc;
     padding: 30px 15px;
     position: absolute;
     right: 0;
     top: 0;
   }
   ```
   
2. Change the element to remain in the top right of the viewport when the window scrolls.

   

   ![Using fixed positioning](https://d3jtzah944tvom.cloudfront.net/lesson_4/exercises_floating_positioning/p2.jpg)

   

   Solution

   The viewport is the visible area within the browser. For clarification, if you are on a web page that is too long to fit within the initial window, you must scroll to the bottom of the page to see the page bottom within the viewport. The top part would be outside of the viewport.

   ```css
   #positioned {
     position: fixed;
   }
   ```
   
3. Set the element's width to 400px and center it horizontally. Centering positioned elements is tricky, so feel free to check the hints and use Google.

   

   ![Centering absolute positioned elements](https://d3jtzah944tvom.cloudfront.net/lesson_4/exercises_floating_positioning/p3.jpg)

   

   Hint 1

   How would you position the left-most edge of the element at the halfway point of the container? Consider using a percentage offset.

   Hint 2

   Once you have the element at the halfway point as described by the previous hint, you need to move it back in the opposite direction to center the element's midpoint. How can you do this? Consider using a negative left margin to pull the element to the left. If interested, you can read up on negative margins [here](https://www.smashingmagazine.com/2009/07/the-definitive-guide-to-using-negative-margins/).

   Solution

   To horizontally center a positioned element with fixed width, you can move it to the center of the container with a `left` offset of 50%, and a negative left margin that is half the width of the element. In our example, we're moving the element from the left edge to the center of the container, then reversing direction by using a negative margin.

   Copy Code

   ```css
   #positioned {
     box-sizing: border-box;
     left: 50%;
     margin-left: -200px;
     /* right: 0; */
     width: 400px;
   }
   ```

4. Place a new element between the page contents and the yellow item; by between, we mean in a 3D sense. Consider the page content to be at the bottom of a stack and the yellow at the top; place the new element between the two.

   The new element should take up the full width and height of the page. Use the CSS below to get started; note that it sets the background to a translucent color. The new element should fill the browser's entire window, and it should appear in front of the paragraphs but behind the yellow box.

   ```css
   background-color: rgba(0, 0, 0, .6);
   ```
   
   

   ![Adding a translucent overlay](https://d3jtzah944tvom.cloudfront.net/lesson_4/exercises_floating_positioning/p4.jpg)

   

   Hint 1

   Read about the `z-index` property.

   Solution

   To take up the entirety of the window, we can use a width and height of `100%`. We can use z-index values for both elements to position one on top of the other.

   ```html
   <div id="fixed"></div>
   ```

   ```css
   #positioned {
     /* z-index must be greater than that of the elements you want overlay */
     z-index: 2; /* 2 must be > 1 */
   }
   
   #fixed {
     background-color: rgba(0, 0, 0, .6);
     height: 100%;
     left: 0;
     position: fixed;
     top: 0;
     width: 100%;
     z-index: 1; /* 1 must be < 2 */
   }
   ```
   
5. Create a new element inside the `#positioned` container. Starting with the CSS below, move the new item partially outside the parent's boundaries by 10px to the left and top. To ensure you can see everything, move the parent element down from the top of the page.

   ```css
   ... {
     /* code omitted */
     background-color: pink;
     height: 20px;
     width: 20px;
   }
   ```
   
   

   ![Positioning outside containers](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/translucent.png)

   

   Solution

   ```html
   <div id="positioned">
     <span></span>
     I'm positioned!
   </div>
   ```
   
   ```css
   #positioned {
     top: 20px;
   }
   
   #positioned span {
     background-color: pink;
     height: 20px;
     left: -10px;
     position: absolute;
     top: -10px;
     width: 20px;
   }
   ```

# On Your Own: Floats and Positioning

We've put together a summary of CSS box models, floats and positioning rules with examples and made a page for it. [See it here](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/box_model_v2/main.html).

Reproduce this page with HTML and CSS on your own. You can grab the raw text here:

Raw Text

```plaintext
Inline Elements

Inline elements occupy the space required by the content, and nothing more. They do not take width and height values.

Example

Anchor tags are inline elements: they take up the width required by their content and not the entire width of the page.

  Home
  Portfolio
  Contact

What happens when we set a margin on an inline-level element?

Inline elements ignore top and bottom margins but observe the left and right margins.

  Home
  Portfolio
  Contact

In the above example, we requested a margin of 30px on all sides. However, the browser ignored the top and bottom margins.

What about padding?

  Home
  Portfolio
  Contact

Inline elements accept padding on all sides.

Floating Inline Elements

  Home
  Portfolio
  Contact

Floating an inline element changes its display value to block, which makes it subject to all block-level characteristics. Thus, floated inline elements can take margins, padding, heights, and widths.

Block Elements

Block-level elements require the entire width of the page and always start a new line. They can have margins and padding. When you omit the width, block elements expand to fill their parent container's natural width; when you omit the height, they expand to fit the content.

Example

`div` elements are block-level.

This div has no explicit width or height.

Without an explicit width or height, the box fills the entire width and uses as much height as it needs to fit the content.

This div has no explicit width but a height of 60px; it also has both padding and margins of 20px on all sides.

With an explicit height of 60px plus margins and padding, the box still fills the entire width (including the padding and margins), but now requires the requested height.

This div has a width of 90px and no explicit height.

With an explicit width of 90px, the box collapses down to 90px width but expands the height to ensure the text still fits.

This div has a width of 180px and a height of 120px; it also has both padding and margins of 20px on all sides.

With an explicit width of 180px and height of 120px, the box takes on the requested dimensions. However, the content can overflow the box as it does here.

Floating Block Elements

Floating block elements with no width or height

Box - 1 - Floated Left
Box - 2 - Floated Right

Floated block-level elements that don't have a width collapse down to the width required by the content. Thus, multiple floated blocks can fit on the same line as shown above where we float one item left and the other right.

Floating block elements with width and height set.

Box - 1 - Floated Left
Box - 2 - Floated Right

When you specify the widths on floated block-level elements, the browser will observe the widths. In the above example, our blocks have widths of 40% and 50%.

Can we change an inline element into a block element?

Let's use the anchor tag as an example.

  Home
  About
  Contact

Yes, we can change a block element to an inline and vice versa. You can change the display property regardless of the previous value.

Inline-Block Elements

Inline-block elements are inline elements that take on most block element properties, such as width and height.

Example

Let's use `inline-block` to create a navigation bar:

  Home
  Portfolio
  About
  Contact

We achieved similar results when we floated the anchor elements. It's as though you get two elements in one: you have the flow properties of inline elements combined with most properties of block elements.

Floats and Positioning Elements

Floats

The browser removes floated elements from the normal flow. Floated elements automatically become block-level elements: two or more floated elements can fit on the same line.

Example

  Box 1
  Box-2
  Box-3

Elements that follow a floated element wrap around it. However, we don't want this behavior above, so we applied clear:both` property to the third `div`. There are two other values for `clear`, `left` and `right`, but we typically want `both.

There are other ways to clear floats. One technique is the clearfix method:

  elementName::after {
    content: " ";
    display:block;
    clear: both;
  }

Here we append the ::after pseudo-element to the parent element's selector.

Positioning

We sometimes want to position elements at specific locations on the page. The normal page flow and floats can't do this with the precision we often want. We can use CSS positioning in this case. There are four positioning types:

  Static
  Fixed
  Relative
  Absolute

Static Positioning

The element renders at its normal position on the page. That is, the browser uses the standard page flow. All elements default to static positioning.

Fixed Positioning

Lets you place an element at a fixed position in the browser window; it will remain in place even when you scroll the page. You need the top`, `bottom`, `right`, and `left properties to position the element.

The browser removes elements with fixed positioning from the page flow. It does not leave a gap in the location where the browser would have positioned it otherwise.

The blue box on the bottom-left corner of the page is a fixed position element.

I use fixed positioning.

Relative Positioning

Relative positioning positions an element at a location relative to its normal position. Unlike fixed positioning, relative positioning does not remove an element from the page flow; in fact, you can observe a gap in the flow indicating the original position.

I use relative positioning.

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non cumque repellat sapiente vitae nihil debitis accusamus, odit, tempore id reiciendis consequatur necessitatibus veritatis, distinctio vel, cum repellendus numquam blanditiis perferendis?

Absolute Positioning

Absolute positioning removes an element from the normal page flow and positions it at an absolute position relative to its parent element. If the parent element is the `<body>`, the position is absolute relative to the complete page.

The green box shows absolute positioning.

I use absolute positioning.
```

This project may be challenging. If you get stuck, don't be afraid to look at the example HTML and CSS below:

Example HTML

```html
<!DOCTYPE html>
<html lang="en-US">
<head>
  <title>Positioning</title>
  <meta charset="utf-8">
  <link href="main.css" rel="stylesheet">
</head>

<body>
  <div class="container">

    <section>
      <h1>Inline Elements</h1>

      <p>
        Inline elements occupy the space required by the content, and nothing more. They do not take width and height values.
      </p>

      <h2>Example</h2>

      <p>
        Anchor tags are inline elements: they take up the width required by their content and not the entire width of the page.
      </p>

      <div class="border">
        <a href="#">Home</a>
        <a href="#">Portfolio</a>
        <a href="#">Contact</a>
      </div>

      <h2>What happens when we set a margin on an inline-level element?</h2>

      <p>Inline elements ignore top and bottom margins but observe the left and right margins.</p>

      <div class="border inline-margin">
        <a href="#">Home</a>
        <a href="#">Portfolio</a>
        <a href="#">Contact</a>
      </div>

      <p>
        In the above example, we requested a margin of 30px on all sides. However, the browser ignored the top and bottom margins.
      </p>

      <h2>What about padding?</h2>

      <div class="border inline-padding">
        <a href="#">Home</a>
        <a href="#">Portfolio</a>
        <a href="#">Contact</a>
      </div>

      <p>Inline elements accept padding on all sides.</p>

      <h2>Floating Inline Elements</h2>

      <div class="border inline-float cf">
        <a href="#">Home</a>
        <a href="#">Portfolio</a>
        <a href="#">Contact</a>
      </div>

      <p>
        Floating an inline element changes its display value to block, which makes it subject to all block-level characteristics. Thus, floated inline elements can take margins, padding, heights, and widths.
      </p>
    </section>

    <section class="block">
      <h1>Block Elements</h1>

      <p>
        Block-level elements require the entire width of the page and always start a new line. They can have margins and padding. When you omit the width, block elements expand to fill their parent container's natural width; when you omit the height, they expand to fit the content.
      </p>

      <h2>Example</h2>

      <p><code>div</code> elements are block-level.</p>

      <div class="wrapper">
        <div class="box-1">
          This <code>div</code> has no explicit width or height.
        </div>

        <p>
          Without an explicit width or height, the box fills the entire width and uses as much height as it needs to fit the content.
        </p>

        <div class="box-2">
          This <code>div</code> has no explicit width but a height of 60px; it also has both padding and margins of 20px on all sides.
        </div>

        <p>
          With an explicit height of 60px plus margins and padding, the box still fills the entire width (including the padding and margins), but now requires the requested height.
        </p>

        <div class="box-3">
          This <code>div</code> has a width of 90px and no explicit height.
        </div>

        <p>
          With an explicit width of 90px, the box collapses down to 90px width but expands the height to ensure the text still fits.
        </p>

        <div class="box-4">
          This <code>div</code> has a width of 180px and a height of 120px; it also has both padding and margins of 20px on all sides.
        </div>

        <p>
          With an explicit width of 180px and height of 120px, the box takes on the requested dimensions. However, the content can overflow the box as it does here.
        </p>
      </div>

      <h2>Floating Block Elements</h2>

      <h3>Floating block elements with no width or height</h3>

      <div class="wrapper cf">
        <div class="fl-1">Box - 1 - Floated Left</div>
        <div class="fl-2">Box - 2 - Floated Right</div>
      </div>

      <p>
        Floated block-level elements that don't have a width collapse down to the width required by the content. Thus, multiple floated blocks can fit on the same line as shown above where we float one item left and the other right.
      </p>

      <h3>Floating block elements with width and height set.</h3>

      <div class="wrapper cf">
        <div class="fl-3">Box - 1 - Floated Left</div>
        <div class="fl-4">Box - 2 - Floated Right</div>
      </div>

      <p>
        When you specify the widths on floated block-level elements, the browser will observe the widths. In the above example, our blocks have widths of 40% and 50%.
      </p>

      <h3>Can we change an inline element into a block element?</h3>

      <p>Let's use the anchor tag as an example.</p>

      <div class="wrapper">
        <a href="#" class="bl-a">Home</a>
        <a href="#" class="bl-a">About</a>
        <a href="#" class="bl-a">Contact</a>
      </div>

      <p>
        Yes, we can change a block element to an inline and vice versa. You can change the <code>display</code> property regardless of the previous value.
      </p>
    </section>

    <section class="in-bl">
      <h1>Inline-Block Elements</h1>

      <p>
        Inline-block elements are inline elements that take on most block element properties, such as width and height.
      </p>

      <h2>Example</h2>

      <p>Let's use <code>inline-block</code> to create a navigation bar:</p>

      <div class="nav">
        <a href="#">Home</a>
        <a href="#">Portfolio</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
      </div>

      <p>
        We achieved similar results when we floated the anchor elements. It's as though you get two elements in one: you have the flow properties of inline elements combined with most properties of block elements.
      </p>
    </section>

    <section class="pos-fl">
      <h1>Floats and Positioning Elements</h1>

      <h2>Floats</h2>

      <p>
        The browser removes floated elements from the normal flow. Floated elements automatically become block-level elements: two or more floated elements can fit on the same line.
      </p>

      <h2>Example</h2>

      <div class="wrapper">
        <div class="flbx-1">Box 1</div>
        <div class="flbx-2">Box-2</div>
        <div class="flbx-3">Box-3</div>
      </div>

      <p>
        Elements that follow a floated element wrap around it. However, we don't want this behavior above, so we applied <code>clear:both</code> property to the third <code>div</code>. There are two other values for <code>clear</code>, <code>left</code> and <code>right</code>, but we typically want <code>both</code>.
      </p>

      <p>
        There are other ways to clear floats. One technique is the <strong>clearfix</strong> method:
      </p>

      <pre>
        <code>
          elementName::after {
            content: &quot; &quot;;
            display:block;
            clear: both;
          }
        </code>
      </pre>

      <p>
        Here we append the <code>::after</code> pseudo-element to the parent element's selector.
      </p>
    </section>

    <section class="pos">
      <h1>Positioning</h1>

      <p>
        We sometimes want to position elements at specific locations on the page. The normal page flow and floats can't do this with the precision we often want. We can use CSS positioning in this case. There are four positioning types:
      </p>

      <ul>
        <li>Static</li>
        <li>Fixed</li>
        <li>Relative</li>
        <li>Absolute</li>
      </ul>

      <section class="pos-static">
        <h2>Static Positioning</h2>

        <p>
          The element renders at its normal position on the page. That is, the browser uses the standard page flow. All elements default to static positioning.
        </p>
      </section>

      <section class="pos-fixed">
        <h2>Fixed Positioning</h2>

        <p>
          Lets you place an element at a fixed position in the browser window; it will remain in place even when you scroll the page. You need the <code>top</code>, <code>bottom</code>, <code>right</code>, and <code>left</code> properties to position the element.
        </p>

        <p>
          The browser removes elements with fixed positioning from the page flow. It does not leave a gap in the location where the browser would have positioned it otherwise.
        </p>

        <p>
          The blue box on the bottom-left corner of the page is a fixed position element.
        </p>

        <div class="fixed">I use fixed positioning.</div>
      </section>

      <section class="pos-relative">
        <h2>Relative Positioning</h2>

        <p>
          Relative positioning positions an element at a location relative to its normal position. Unlike fixed positioning, relative positioning does not remove an element from the page flow; in fact, you can observe a gap in the flow indicating the original position.
        </p>

        <div class="wrapper">
          <div class="rel-box">I use relative positioning.</div>

          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non cumque repellat sapiente vitae nihil debitis accusamus, odit, tempore id reiciendis consequatur necessitatibus veritatis, distinctio vel, cum repellendus numquam blanditiis perferendis?
          </p>
        </div>
      </section>

      <section class="pos-absolute">
        <h2>Absolute Positioning</h2>

        <p>
          Absolute positioning removes an element from the normal page flow and positions it at an absolute position relative to its parent element. If the parent element is the <code>&lt;body&gt;</code>, the position is absolute relative to the complete page.
        </p>

        <p>The green box shows absolute positioning.</p>

        <div class="wrap">
          <div class="abs-box1">I use absolute positioning.</div>
        </div>
      </section>
    </section>
  </div>
</body>
</html>
```

Example CSS

```css
* {
  box-sizing: border-box;
}

.cf::before,
.cf::after {
  content: "";
  display: block;
}

.cf::after {
  clear: both;
}

body {
  background-color: white;
  color: #545459;
  font: normal 16px Helvetica, Arial, sans-serif;
}

.container {
  border: 2px solid #999;
  margin: 0 auto;
  padding: 20px;
  width: 1000px;
}

section h1 {
  font-size: 24px;
}

section h2 {
  font-size: 20px;
}

section h3 {
  font-size: 16px;
}

section h1,
section h2,
section h3 {
  background-color: inherit; /* white */
  color: #ce4a4a;
  font-weight: bold;
  margin: 20px 0;
}

section p {
  line-height: 35px;
  margin-bottom: 25px;
}

section .border {
  border: 2px dashed #555;
  margin: 45px;
  padding: 30px;
  width: 650px;
}

section .bold {
  font-weight: bold;
}

section a {
  background-color: inherit; /* white */
  color: #333;
  text-decoration: none;
}

section .inline-margin a {
  margin: 30px;
}

section .inline-padding a {
  background-color: green;
  color: white;
  padding: 30px;
}

section .inline-float a {
  background-color: green;
  border: 3px solid darkgreen;
  color: white;
  float: left;
  margin: 15px;
  padding: 25px;
  text-align: center;
  width: 120px;
}

/**** BLOCK ****/
.block .wrapper {
  margin-bottom: 35px;
}

.block .box-1 {
  background-color: dodgerblue;
  color: white;
}

.block .box-2 {
  background-color: green;
  color: white;
  height: 60px;
  margin: 20px;
  padding: 20px;
}

.block .box-3 {
  background-color: tomato;
  color: white;
  width: 90px;
}

.block .box-4 {
  background-color: pink;
  color: white;
  height: 120px;
  margin: 20px;
  padding: 20px;
  width: 180px;
}

.block .fl-1 {
  background-color: dodgerblue;
  border: 1px solid red;
  color: white;
  float: left;
}

.block .fl-2 {
  background-color: tomato;
  border: 1px solid red;
  color: white;
  float: right;
}

.block .fl-3 {
  background-color: tomato;
  color: white;
  float: left;
  height: 70px;
  line-height: 70px;
  text-align: center;
  width: 40%;
}

.block .fl-4 {
  background-color: dodgerblue;
  color: white;
  float: right;
  height: 70px;
  line-height: 70px;
  text-align: center;
  width: 50%;
}

.block .bl-a {
  background-color: dodgerblue;
  color: white;
  display: block;
  margin: 10px;
  padding: 10px;
  text-align: center;
}

.in-bl::after {
  border-bottom: 2px dashed #545459;
  content: "";
  display: block;
  padding-top: 30px;
  width: 100%;
}

.in-bl .nav {
  text-align: center;
}

.in-bl .nav a {
  background-color: dodgerblue;
  border: 1px solid #1b95e0;
  color: white;
  display: inline-block;
  margin: 20px 8px 25px;
  padding: 20px 30px;
  width: 180px;
}

.pos-fl h1 {
  margin: 30px 0 25px;
  text-align: center;
}

.pos-fl .flbx-1 {
  background-color: tomato;
  color: white;
  float: left;
  font-weight: bold;
  height: 100px;
  line-height: 100px;
  text-align: center;
  width: 450px;
}

.pos-fl .flbx-2 {
  background-color: dodgerblue;
  color: white;
  float: left;
  font-weight: bold;
  height: 100px;
  line-height: 100px;
  text-align: center;
  width: 505px;
}

.pos-fl .flbx-3 {
  background-color: seagreen;
  clear: both;
  color: white;
  font-weight: bold;
  height: 50px;
  line-height: 50px;
  margin-bottom: 35px;
  text-align: center;
  width: 955px;
}

.pos ul {
  list-style-type: disc;
  margin: 0 0 45px 40px;
}

.pos ul li {
  font-style: italic;
  margin-bottom: 10px;
}

.pos-fixed div {
  background-color: dodgerblue;
  border-radius: 10px;
  bottom: 50px;
  color: white;
  left: 35px;
  padding: 25px 35px;
  position: fixed;
  text-align: center;
  width: 225px;
}

.pos-relative .rel-box {
  background-color: tomato;
  border-radius: 10px;
  bottom: -45px;
  color: white;
  margin-bottom: 30px;
  padding: 25px 35px;
  position: relative;
  right: 90px;
  text-align: center;
  width: 325px;
}

.pos-absolute {
  position: relative;
}

.pos-absolute .abs-box1 {
  background-color: green;
  border-radius: 10px;
  color: white;
  left: 230px;
  margin-bottom: 30px;
  padding: 25px 35px;
  position: absolute;
  text-align: center;
  top: -30px;
  width: 200px;
}
```

# Flex and Grid

Thus far, we've talked about using floats and positioning to control CSS layouts. These features work well; they have endured for years, but both can be hard to use for some formats. As we saw in the previous assignment, even a simple operation like centering an element inside a positioned container is more complicated than it seems. Furthermore, with both floats and positioning, you must deal with the effects of removing items from the flow.

## Flex

As of 2018, a new `display` property seems poised for widespread growth: `flex`. Flex (or Flexbox) solves a lot of design problems that plague front-end developers. Support is strong across contemporary browsers, with nearly universal availability to users. We recommend trying to use Flex in your projects, including Launch School projects.

Flex is a one-dimensional layout tool; you can lay out a single row or column with a single flexbox. You can create two-dimensional formats by using multiple flexboxes, but Grid works better for two-dimensional work.

## Grid

Another `display` property, `grid`, has exploded on the Web and become a useful companion for Flex. Widespread use is now here with over 96% of browsers now supporting Grid. The specification is complete, so feel free to use it in your projects, including here at Launch School.

Grid is a two-dimensional layout tool; you can place elements in a grid (rows and columns) format at the same time. It's also possible to do a single row or a single column, but that's merely a degenerate form of a grid; Flex is often better for such cases.

## Further Study

Please spend some time watching the videos linked below. If you want additional information, read the non-video links.

- **Flex**
  - **Video:** One of our students gave a [15-minute talk on Flex](https://launchschool.com/posts/b401d522).
  - **Video:** [Flexbox Tutorial (CSS): Real Layout Examples](https://www.youtube.com/watch?v=k32voqQhODc)
  - [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
  - [Using CSS Flexible Boxes](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes)
- **Grid**
  - **Video:** [CSS Grid Changes Everything](https://www.youtube.com/watch?v=7kVeCqQCxlk)
  - [A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
  - [CSS Grid Layout](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
  - [Grid by Example](https://gridbyexample.com/)
- **Flex** and Grid
  - [codepip: Learn to Code With Games](https://codepip.com/)
  - [Flexbox and Grids, your layout’s best friends](https://aerolab.co/blog/flexbox-grids)

We don't expect you to learn all there is to know about Flex and Grid right now, but you should know enough to sit down with MDN and Google and figure out how to produce some simple layouts. We'll do that in the next two assignments.

# Guided Project: Flex

In this project, you'll use Flex to lay out a partially completed web page. It will give you a general idea of how to use Flex.

To get started, download the [initial project files](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/flex.zip) and unzip them. You can view the completed project [here](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/flex/final/flex.html)

Make all your modifications to the CSS file; don't make any changes to the HTML. Do not use any `float`, `position`, or `grid` properties, and don't convert any elements to `inline-block`. Use Flex features instead.

Flex and Grid naturally work in concert. This contrived project intentionally restricts the use of Grid to force you to use Flex.

This project may be hard if you have no prior exposure to Flex. Don't waste a lot of time struggling with it; check the solutions if you get stuck. We don't expect you to learn Flex in this course, merely see it in action.

This project probably has a variety of solutions. Don't worry if your CSS looks different, as long as it meets the requirements.

1. Load the completed project and your in-progress project from the downloaded file in your browser. Study the differences, and try to decide what general actions you must take to convert your project to one that matches the completed project. Think about the tasks you need to accomplish, not the CSS you need to code.

   Our Initial Notes

2. Start by providing any global settings you think you will need. You can update this later.

   Solution

3. Give the header a blue background; the `h1` heading has a blue background, but not the `header`.

   Solution

4. Convert the navigation links into a horizontal navigation bar:

   Solution

5. Create three columns of text - an `article` and two `aside`s - as the main body of the page. The `article` should consume half the page width, while the `aside`s should each consume one-quarter (that is, the `article` is twice the width of each `aside`). Each column should be the same height, no matter how much text it contains.

   Solution

   flex.css

   Copy Code

   ```css
   main {
     display: flex;
   }
   
   article {
     flex: 2;
   }
   
   aside {
     flex: 1;
   }
   ```

   You can do the same thing with floats and positioning, but it isn't easy.

6. Create a two-column `footer` with the copyright notice on the left, and the 200px high image on the right.

   Solution

   flex.css

   Copy Code

   ```css
   footer {
     background-color: yellow;
     display: flex;
     justify-content: space-between;
   }
   
   img {
     display: block;
     height: 200px;
   }
   ```

   Using `display: flex` in the `footer` selector puts both the copyright notice and the image on the same line, while `justify-content: space-between` forces the image to the right side of the line. You must convert the image to use `display: block` or you will see a narrow orange band below the image; see [The strange  gap in HTML](https://dev.to/christiankaindl/the-strange-img-gap-in-html) for more information. One of our students also wrote an [article on this topic](https://medium.com/launch-school/mind-the-gap-mind-the-gap-28496470991).

7. Swap the positions of the copyright notice and image to place the image on the left and the copyright notice on the right.

   Solution

   flex.css

   ```css
footer {
     background-color: yellow;
     display: flex;
     flex-flow: row-reverse;
     justify-content: space-between;
   }
   ```
   
   The `flex-flow` property sets the direction for a flex-box; you can orient it by row or column, and in forward or reverse order.

8. Center the copyright notice vertically.

   Solution

   flex.css

   ```css
   footer {
     align-items: center;
     background-color: yellow;
     display: flex;
     flex-flow: row-reverse;
     justify-content: space-between;
   }
   ```
   
   We use `align-items` or `align-content` when working with Flex, not `vertical-align`. `vertical-align` works with `inline` elements, not `flex`.

You can view the completed CSS file [here](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/flex/final/flex.css).

# Guided Project: Grid

In this project, you'll use Grid to build a layout similar to the one we created in the previous assignment. The videos you watched earlier should give you an idea on how to proceed.

To get started, download the [initial project files](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/grid.zip) and unzip them. You can view the completed project [here](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/grid/final/grid.html).

Make all your modifications to the CSS file; don't make any changes to the HTML. Do not use any `float`, `position`, or `flex` properties, and don't convert any elements to `inline-block`. Use Grid features instead.

Flex and Grid naturally work in concert. This contrived project intentionally restricts the use of Flex to force you to use Grid.

This project may be hard if you have no prior exposure to Grid. Don't waste a lot of time struggling with it; check the solutions if you get stuck. We don't expect you to learn Grid in this course, merely see it in action.

As usual, there are different ways to complete this project. Don't worry if your CSS looks different, as long as it meets the requirements.

1. Load the completed project and your in-progress project from the downloaded file in your browser. Study the differences, and try to decide what general actions you must take to convert your project to one that matches the completed project. Think about the tasks you need to accomplish, not the CSS you need to code.

   Our Initial Notes

   1. Zero out margins and padding
   2. Set primary font and color info.
   3. Convert navigation menu to horizontal
   4. Create a 5-line, 3-column grid format for the page
   5. Position elements in the grid
   6. Create a 1-line, 2-column grid in the footer.
   7. Move the image and copyright to the footer grid.
   8. Shrink image.
   9. Center copyright notice vertically and right justify it.

2. Start by providing any global settings you think you will need. You can update this later.

   Solution

   flex.css

   Copy Code

   ```css
   * {
     margin: 0;
     padding: 0;
   }
   
   html {
     background-color: white;
     color: black;
     font: normal 24px Helvetica, Arial, sans-serif;
   }
   ```

   It's a good idea to start out by getting rid of all margins and padding at the global level to decrease the cross-browser differences. We can use the `*` selector in this project; you would typically use a CSS reset (discussed later) for this.

   From step 1, we can observe that most of our text should be black and that white is a good starting choice for the background color; we apply both of those via the `html` selector.

3. Convert the navigation links into a horizontal navigation bar:

   Solution

   grid.css

   Copy Code

   ```css
   ul {
     display: grid;
     grid-template-columns: repeat(5, 1fr);
     list-style-type: none;
   }
   ```

   This code converts the list of navigation links to a single line grid in which each item is part of a `1fr`-width cell. Assigning each cell the same `1fr` width divides the cells up evenly, with each cell taking up 1/5th of the page width.

   Without Grid, you would have to convert the `li` elements to `inline-block` then deal with the spaces between the `inline-block` elements. Grid takes care of both those needs.

4. Organize the entire page as a grid of three columns and five lines, with named grid areas. The first and last column should each take up 1/4 of the page width, while the central column should take up 1/2 the page width. Use fractions, not percentages, to designate these measurements. The `header` should be on the top line, followed by the navigation bar. The content area consists of two lines. The first has two `aside` elements and an `article`, with the `article` in the larger center column. The next line consists of an `article` and an `aside`. Lastly, the `footer` should appear at the bottom of the grid.

   Solution

5. Divide the footer area into a sub-grid that will show the logo on the left and the copyright notice on the right.

   Solution

   grid.css

   ```css
footer {
     background-color: yellow;
     display: grid;
     grid-area: footer;
     grid-template-areas: "logo copyright";
   }
   
   #copyright {
     grid-area: copyright;
     margin: 0 1rem;
   }
   
   #logo {
     background-color: orange;
     grid-area: logo;
   }
   ```
   
   This solution is similar to that used in the previous step: we define a grid template area, then assign the grid-area names to the appropriate selectors.

   If you make the window narrow enough, the space allocated for the image may begin to shrink due to the space required for the copyright message.

6. Reduce the size of the image to the same size as the first column of the content area.

   Solution

   grid.css

   ```css
footer {
     background-color: yellow;
     display: grid;
     grid-area: footer;
     grid-template-areas: "logo copyright";
     grid-template-columns: 1fr 3fr;
   }
   
   img {
     display: block;
     object-fit: cover;
     width: 100%;
   }
   ```
   
   This solution is similar to that used in the Flex project: we set the display type to `block` and set the width, though this time we want the width to be 100% of the cell width. We also need to supply `object-fit` to control the technique used to resize the image.

   If you make the window narrow enough, the space allocated for the image may begin to shrink due to the space required for the copyright message.

7. Right-align and vertically center the copyright message in the yellow box.

   Solution

   grid.css

   ```css
   #copyright {
     align-self: center;
     grid-area: copyright;
     margin: 0 1rem;
     justify-self: end;
   }
   ```
   
   You can think of `justify-self` as a [more Grid-like way to align content](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout/Box_Alignment_in_CSS_Grid_Layout). If you're using an older browser, you can replace `justify-self: end` with `text-align: right`. The result is identical, but the `justify-self` approach is more Grid-like.

You can view the completed CSS file [here](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/grid/final/grid.css).

# CSS Frameworks

If you've sought out material on CSS organization and current technologies you've probably come across a CSS framework or two. As of this writing, the most common ones you'll find used in a project are Twitter Bootstrap and Foundation. Both have advantages, and both have extra baggage that you may never need. The most beneficial aspects of these frameworks are their handling of media queries for tablet and mobile views as well as a grid system that's already defined for you by way of generic classes.

With the new Flex and Grid systems, it may seem that CSS frameworks are less useful than they once were. However, they work with browsers that don't support Flex or Grid, which will continue to keep them viable for several years yet. In the long run, the developers of CSS frameworks should also enhance their products to keep them useful in an age when Flex and Grid provide most functionality.

Students often ask us about which CSS frameworks we teach at Launch School. The answer is surprising: none. Launch School's focus is on teaching the fundamentals; frameworks are not a fundamental skill since most have a short or dynamic lifespan. By the time you feel you've mastered one, it's time to start learning the next. With a strong background in CSS fundamentals, you can learn any frameworks package with comparative ease. Thus, we won't discuss any specific products here; we'll talk in generalities instead.

A frameworks package has a grid system implemented with a combination of HTML, CSS, and JavaScript at its heart. This grid has nothing to do with CSS Grid, though it's possible that frameworks may soon incorporate Grid.

Column containers almost always use a relative width measurement as well, i.e., percentages or rems, so you can nest columns within others and have them behave the same way no matter the parent container's width.

As an example, consider a 4-column grid layout. We want four equal-sized containers per row and want that behavior no matter the browser's current width. We can create a class called `one-fourth` and have it set to 25% of the parent container's width.

Copy Code

```css
ul {
  padding: 0;
}

.one-fourth {
  display: inline-block;
  outline: 1px solid gray;
  vertical-align: top;
  width: 25%;
}
```

Now we can create an unordered list of products for a site that fits four items per row, adjusting for browser width.

```html
<ul class="row">
  <li class="one-fourth">8 GB SD card</li>
  <li class="one-fourth">16 GB SD card</li>
  <li class="one-fourth">32 GB SD card</li>
  <li class="one-fourth">64 GB SD card</li>
</ul>
```

As you may recall, the whitespace character between each list item causes the row to exceed the container's width, making the fourth list item drop down to a new row. One method we can use to work around this problem uses a combination of `float` and a `block` container that self-clears. In fact, Twitter Bootstrap employs this technique:

```css
.row::after {
  clear: both;
  content: "";
  display: block;
  line-height: 0;
}

.one-fourth {
  display: inline-block;
  float: left;
  outline: 1px solid gray;
  vertical-align: top;
  width: 25%;
}
```

The result looks like this:



![Simple 4-Column Layout](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/frameworks-01.png)



We now have four list items in a row, changing the width to match 25% of the browser's width. We can use the same approach for two, three, six, and more columns as well as mix and match them to make uneven columns:

```html
<ul class="row">
  <li class="one-half">1 of 2</li>
  <li class="one-half">2 of 2</li>
</ul>

<ul class="row">
  <li class="one-third">1 of 3</li>
  <li class="one-third">2 of 3</li>
  <li class="one-third">3 of 3</li>
</ul>

<ul class="row">
  <li class="one-fourth">1 of 4</li>
  <li class="one-fourth">2 of 4</li>
  <li class="one-fourth">3 of 4</li>
  <li class="one-fourth">4 of 4</li>
</ul>

<ul class="row">
  <li class="one-sixth">1 of 6</li>
  <li class="one-sixth">2 of 6</li>
  <li class="one-sixth">3 of 6</li>
  <li class="one-sixth">4 of 6</li>
  <li class="one-sixth">5 of 6</li>
  <li class="one-sixth">6 of 6</li>
</ul>
```

Copy Code

```css
ul {
  padding: 0;
}

.row::after {
  clear: both;
  content: "";
  display: block;
  line-height: 0;
}

.one-sixth, .one-fourth, .one-third, .one-half {
  display: inline-block;
  float: left;
  outline: 1px solid black;
  text-align: center;
  vertical-align: top;
}

.one-sixth {
  width: 16.6667%;
}

.one-fourth {
  width: 25%;
}

.one-third {
  width: 33.3333%;
}

.one-half {
  width: 50%;
}
```



![Mixed Layout](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_6/frameworks-02.png)



Even nested columns work well using these same classes.

That's the basic idea behind CSS frameworks: they create a grid system using classes, and your HTML uses those classes to handle the layout part of your site. Beyond that, they also provide "responsive design" capabilities to your site, which lets your site work well on all devices from the smallest to the largest.

For now, that's all you need to know about frameworks. When you're ready to start learning one, you'll find it comparably easy to do so since you already have a good foundation with CSS and HTML.

# Responsive Design

Most websites must look good and provide identical functionality regardless of whether the user is using a smartphone or a desktop with a massive display, or anything in between. However, what looks great on a desktop, for example, is sometimes a poor user experience on a smartphone. The same holds in the other direction: a site that looks great on your cell phone will look sparse and empty on your 34-inch display.

Dealing with these differences is not hard, but it requires the ability to write CSS that changes with different output devices. That's the role of **CSS media queries**.

## Media Queries

Media queries typically define styles that change based on the current size of the browser window, which lets us customize the look for phones, tablets, small laptops, and large desktop displays. Here's a simple media query that changes the link color on small devices (cell phones frequently have screens less than 480px wide):

```css
a {
  color: #f00;
}

@media (max-width: 480px) {
  a {
    color: #06c;
  }
}
```

Any styles you put inside the media query block will apply when the screen width is 480px or less, as specified by the `(max-width: 480px)` query.

You can also use the words `not` and `and` in media queries, and choose different media types such as `screen`, `print`, or `speech`. Most common is a combination of `screen` media type and a `min-width` or `max-width`, like this:

Copy Code

```css
@media screen and (max-width: 1600px) {
  /* CSS for 1600px (or smaller) screens (no printers!) */
}
```

Be sure to take a few minutes to read over the [media query documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) at MDN to acquaint yourself with other capabilities.

### Mobile-First and Desktop-First

One key decision you must make when developing a website is to choose whether you want to use mobile devices or desktops as your primary device: the device your CSS expects when no media query is active. For instance, most developers start out by styling the mobile site first (the so-called "mobile-first approach"), and then use several media queries to handle progressively larger devices:

Copy Code

```css
/* CSS for all cell phones and shared cross-browser CSS */

@media screen and (min-width: 481px) {
  /* CSS for tablets and larger */
}

@media screen and (min-width: 961px) {
  /* CSS for small desktop and laptop screens and larger */
}

@media screen and (min-width: 1501px) {
  /* CSS for large laptop and desktop displays */
}

@media print {
  /* CSS for printers */
}
```

Development starts in the section with no media query. It provides the CSS you need for the smallest devices you intend to support, as well as any CSS that is common to all or most of the media queries you will supply. For instance, colors don't often change on different devices, so it's common for colors to appear in the top-most section. Since the first media query specifies a minimum screen size of 481px, any CSS intended solely for use on smaller devices (phones) should appear in the top-most section as well.

You can use the remaining `screen` queries to provide CSS intended for larger mobile devices, small laptops and desktops, and large laptops and desktops respectively. Lastly, there's a media query for printing (perhaps you don't want to waste the colored inks).

Conversely, the desktop-first approach to site design starts with the full-scale large desktop design first, and then progressively provides media queries for the smaller displays.

The mobile-first approach frequently results in faster downloads on mobile devices, while the desktop-first approach results in slower downloads. Most developers consider the mobile-first approach to be best-practice.

### Breakpoints

We show a variety of sizes, or **breakpoints**, for the media queries above. We also use some comments to classify each breakpoint as a tablet, laptop, etc. In practice, such classification systems don't work well. Contemporary mobile devices now cover a continuum of different screen sizes, and its hard to differentiate between a large cell phone and a small tablet.

Instead of asking whether you're working on a cell phone or desktop, it's more natural and useful to ask what layout works best over a particular range of screen sizes, then build each of those layouts with the appropriate media query.

### Emulating Devices in Google Chrome

Do you need to support a specific mobile device but don't have a physical device to test? For most popular devices, this isn't a problem. Chrome's developer tools now include most popular devices as emulations that you can use. To view a web page as it appears on an iPhone 8, for example:

- Open the inspector.
- Click the emulation icon in the top bar (it looks like a smartphone resting atop a tablet in Chrome v64 - other versions may differ).
- Several drop-downs will appear above the web page.
- Select iPhone 8 from the "Responsive" drop-down.
- Refresh the page to ensure the page loads everything it needs.

You'll now see your page as iPhone 8 users will see it. You can even simulate a slower connection by choosing mid-tier mobile or low-tier mobile to test performance at emulated network speeds.

You can edit the list of devices supported with the Edit option.

Other browsers often provide similar capabilities.

### Using Your Page on Multiple Devices

If you design your application with responsiveness in mind, you must put the following `<meta>` element in the `<head>` part of the `<html>`. It tells mobile devices how to handle that page; without it, those devices often display a miniaturized version of the page instead of showing the desired mobile device page described by your media queries and CSS.

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

[Don't use this tag](http://blog.javierusobiaga.com/stop-using-the-viewport-tag-until-you-know-ho) if your app has no responsiveness traits.

Search for "meta viewport" on MDN for more information on what `<meta name="viewport">` does and how to use it.

## Fluid and Liquid Layouts

Fluid, liquid, responsive, elastic, hybrid: how's a front-end developer supposed to know which to use? As you'll see, these layouts are nearly identical; the differences are minor. You'll also hear people use one and mean another, so it's good to know what techniques you can use to achieve a given layout type.

Since we've already covered responsive design with media query breakpoints to change the content to fit screen widths, we'll focus on liquid and fluid layouts. Liquid layouts often employ percentage values for widths to maintain the same width ratios for content areas as the browser width changes.

Let's create a simple example of a liquid layout:

```html
<main>
  <article class="content">
    Enim Lorem aliqua anim nulla labore nulla ullamco. Deserunt fugiat duis ex
    dolor. Ex laboris ad officia minim quis.  Incididunt eu reprehenderit
    ullamco eiusmod dolor pariatur mollit qui. Officia aliqua velit deserunt
    adipisicing duis minim minim tempor.
  </article>

  <aside class="sidebar">
    Proident cillum ad cillum minim magna. Duis nulla est est non sunt. Est
    culpa laborum velit dolor.
  </aside>
</main>
```

```css
html {
  font-size: 16px;
}

body, article, p {
  margin: 0;
  padding: 0;
}

body {
  margin: 0;
  padding: 0.5rem;
}

main {
  clear: both;
  overflow: hidden;
  padding-bottom: 1.5rem;
}

.content,
.sidebar {
  box-sizing: border-box;
  float: left;
  padding: 20px 30px;
}

.content {
  background-color: pink;
  width: 70%;
}

.sidebar {
  background-color: cyan;
  width: 30%;
}
```

![image-20230314182925838](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314182925838.png)



No matter how we adjust the browser window's width, the two columns maintain their width ratios. Such synchronized behavior is the foundation of both liquid and fluid layouts. As the browser width changes, so do the content areas.

### Liquid Layouts

If we want to resize the content `article` in the above example, we must resize the sidebar as well. For instance, if we set the `article` to 60%, we must set the sidebar to 40%.

There's an alternative: we can use the `overflow` property with any value except `visible` on the sidebar element. To use this technique, we must remove the `float` and `width` properties from the sidebar:

```css
.content,
.sidebar {
  /* delete: float: left; */
}

.content {
  float: left;
  width: 60%; /* was 70% */
}

.sidebar {
  overflow: hidden;
  /* delete: width: 30%; */
}
```

![image-20230314182917340](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314182917340.png)



You can now change the width of the content without changing the width of the sidebar. The layout is liquid since it expands and contracts with the browser window's width.

We can set `overflow` on the sidebar to either `hidden` or `auto` to achieve the same effect. However, there are some differences between these two values.

- With `hidden`, the browser crops any content that doesn't fit inside the sidebar's container.
- With `auto`, the browser doesn't crop content, but it may show unwanted scrollbars on the sidebar.

### Fluid Layouts

Liquid layouts ordinarily take up the entire width of the browser window, no matter how big it gets. If you want to restrict the expansion or collapse, you need to use a fluid layout. Once the window reaches one of the limits, the element will cease expanding or collapsing and remain fixed in width as the width continues to change in the same direction. Fluid layouts expand and collapse like a liquid layout to a point, then become fixed once the browser width reaches a specific size.

Let's convert the example above to a fluid layout with a couple of simple changes. We'll set a min-width and max-width on the container to prevent the site from becoming too spacious or cramped.

```css
main {
  max-width: 1000px;
  min-width: 500px;
}

.content,
.sidebar {
  padding: 20px 30px;
}

.content {
  box-sizing: border-box;
  float: left;
  width: 70%;
}

.sidebar {
  overflow: hidden;
}
```

![image-20230314182903655](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314182903655.png)



When we resize the browser now, we'll see our layout change until we reach the minimum and maximum dimensions on the `main` element.

# On Your Own: Fluid Photo Gallery

In this project, your job is to replicate the photo gallery shown below. It shows a single photo at the full width of the column, followed by four smaller thumbnail images in a single row below it. All of these should adjust their widths to take up the same percentage width no matter what the main gallery width is.



![Photo gallery](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/photo_gallery_with_fluid_layout/example.png)



The box that encloses the entire gallery should have a minimum and maximum width of 500px and 1000px, respectively. Use your best judgment to determine other size and color measurements.

If you don't have photos to use, you can generate some placeholders using the `https://via.placeholder.com/1200x900`, where 1200 is the width, and 900 is the height. Use these same dimensions for the images you create. If these placeholders don't work, you can try using `https://fpoimg.com/1200x900` instead - this site works the same way as `via.placeholder.com`, though the images may look just a bit different.

You should wrap the central photo in a figure element and use a `figcaption` tag for the caption below it. You'll have to remove the default styles applied to the figure element by the browser to make it take up the entire column width.

Use any technique you want to arrange the thumbnail elements. You can use something traditional like `inline-block` or `float`, or something newer and more interesting like Flex and Grid.

### Solution

You can view our completed example of this assignment if you're stuck:

Completed Solution

example.html

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>Example Liquid Photo Gallery</title>
    <meta charset="utf-8">
    <link rel="stylesheet" href="gallery.css">
  </head>
  <body>
    <main>
      <h1>My Photo Gallery</h1>
      <figure>
        <img src="https://via.placeholder.com/1200x900" alt="">
        <figcaption>Example photo</figcaption>
      </figure>
      <ul>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 1">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 2">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 3">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 4">
        </li>
      </ul>
    </main>
  </body>
</html>
```

gallery.css

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  background-color: #151515;
  color: #f0f0f0;
  font: normal 16px Helvetica, Arial, sans-serif;
}

main {
  background-color: #333;
  color: inherit; /* #f0f0f0 */
  box-sizing: border-box;
  display: block;
  margin: 0 auto;
  max-width: 1000px;
  min-width: 500px;
  padding: 25px 20px 20px;
}

h1 {
  margin: 1.33rem 0;
  text-align: center;
}

img {
  box-sizing: border-box;
  display: block;
  height: auto;
  width: 100%;
}

figure {
  margin: 0;
  padding: 0 0 30px;
}

figure img {
  border: 15px solid white;
}

figcaption {
  display: block;
  padding: 10px 0 0;
}

ul {
  font-size: 0;
  margin: 0 -15px;
  padding: 0;
}

li {
  box-sizing: border-box;
  display: inline-block;
  margin-bottom: 30px;
  padding: 0 15px;
  vertical-align: top;
  width: 25%;
}

li img {
  border: 3px solid white;
}
```

Note that we used `inline-block` in our solution, but we designed this project before Flex and Grid were widely available.

We also have a video that walks you through creating this project. The instructor uses a Photoshop design file in the video to measure component sizes and colors. We'll discuss design files a bit in the next lesson, but since Photoshop no longer has a reasonable trial period, we no longer go into using Photoshop design files for building projects.

The instructor also uses a negative margin at one point; if interested, you can read up on negative margins [here](https://www.smashingmagazine.com/2009/07/the-definitive-guide-to-using-negative-margins/).

Remember: the video may differ from the written instructions and the completed example. The written instructions take precedence.

<video id="video_c1903ef8b45f_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/fluid_gallery_2d7b41_s1015/fluid_gallery_2d7b41_s1015.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 886.659px; height: 498.739px;"></video>

Play Video

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/fluid_gallery_2d7b41_s1015/fluid_gallery_2d7b41_s1015.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/fluid_gallery_2d7b41_s1015/fluid_gallery_2d7b41_s1015.sbv)

# Guided Project: Photo Gallery With Media Queries

In this project, you will add some media queries to the photo gallery project from the previous assignment to adjust the design for both smaller and larger screens. In the original project, we used a fluid layout with a minimum width of 500 pixels and a maximum width of 1000. In this project, we'll do away with the minimum width; instead, we'll reduce the number of thumbnails shown at the bottom as the screen width shrinks.

The final project displays four thumbnails per line when the window is at least 900 pixels wide. It displays three per line when the window is between 600 and 899 pixels, and two per line when the window is narrower than 600 pixels. As a challenge, we'll add an extra layout that kicks in when the window width is 1280px or more.

You can start this project with the completed example from the previous project or your own completed version.

1. Add a meta tag that tells the browser that this page is a responsive design.

   Solution

   Copy Code

   ```html
   <head>
     <title>Example Liquid Photo Gallery</title>
     <meta charset="utf-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <link rel="stylesheet" href="gallery.css">
   </head>
   ```

2. Remove the minimum width from the project.

   Solution

   Copy Code

   ```css
   main {
     /*min-width: 500px;*/
   }
   ```

3. Add several additional thumbnail images to the HTML to help make your changes stand out as the number of thumbnails per line shrinks. Add some margin between each row of thumbnails.

   Solution

   gallery.html

   Copy Code

   ```html
   <li>
     <img src="https://via.placeholder.com/1200x900" alt="Photo 5">
   </li>
   
   <li>
     <img src="https://via.placeholder.com/1200x900" alt="Photo 6">
   </li>
   
   <li>
     <img src="https://via.placeholder.com/1200x900" alt="Photo 7">
   </li>
   ```

   gallery.css

   Copy Code

   ```css
   li {
     margin-bottom: 15px;
   }
   ```

4. Add a media query with the CSS you need to limit the number of thumbnails per line to three when the window width is less than 900px.

   Solution

   gallery.css

   Copy Code

   ```css
   @media screen and (max-width: 899px) {
     li {
       width: 33.3333%;
     }
   }
   ```

5. Add a media query with the CSS you need to limit the number of thumbnails per line to two when the window width is less than 600px.

   Solution

   gallery.css

   Copy Code

   ```css
   @media screen and (max-width: 599px) {
     li {
       width: 50%;
     }
   }
   ```

6. **Challenge** Add a media query and the necessary CSS to move the thumbnails to the right side of the primary photo when the browser's width is 1280 pixels or more. Arrange the thumbnails as a single column. Allow the thumbnails to continue expanding as you increase the window width, but limit the central photo to 950px. If your display can't handle 1280 pixels, choose a smaller value, and make any necessary adjustments. See the [completed project](https://d3jtzah944tvom.cloudfront.net/202/projects/lesson_6/photo_gallery_with_fluid_layout/example2.html) for the expected appearance.

   Hint

   When the browser window is at least 1280 pixels wide, expand the `main` element to allow it to fill the window's entire width.

   Solution

   gallery.css

   Copy Code

   ```css
   @media screen and (min-width: 1280px) {
     main {
       max-width: 100%;
     }
   
     figure {
       display: inline-block;
       float: left;
       margin-right: 50px;
       vertical-align: top;
       width: 950px;
     }
   
     ul {
       overflow: hidden;
     }
   
     li {
       width: 100%;
     }
   }
   ```

Completed Project

example.html

Copy Code

```html
<!DOCTYPE html>
<html lang="en-US">
  <head>
    <title>Example Liquid Photo Gallery</title>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="gallery.css">
  </head>
  <body>
    <main>
      <h1>My Photo Gallery</h1>
      <figure>
        <img src="https://via.placeholder.com/1200x900" alt="">
        <figcaption>Example photo</figcaption>
      </figure>
      <ul>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 1">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 2">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 3">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 4">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 5">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 6">
        </li>
        <li>
          <img src="https://via.placeholder.com/1200x900" alt="Photo 7">
        </li>
      </ul>
    </main>
  </body>
</html>
```

Copy Code

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  background-color: #151515;
  color: #f0f0f0;
  font: normal 16px Helvetica, Arial, sans-serif;
}

main {
  background-color: #333;
  color: inherit; /* #f0f0f0 */
  box-sizing: border-box;
  display: block;
  margin: 0 auto;
  max-width: 1000px;
  padding: 25px 20px 20px;
}

h1 {
  margin: 1.33rem 0;
  text-align: center;
}

img {
  box-sizing: border-box;
  display: block;
  height: auto;
  width: 100%;
}

figure {
  margin: 0;
  padding: 0 0 30px;
}

figure img {
  border: 15px solid white;
}

figcaption {
  display: block;
  padding: 10px 0 0;
}

ul {
  font-size: 0;
  margin: 0 -15px;
  padding: 0;
}

li {
  box-sizing: border-box;
  display: inline-block;
  margin-bottom: 30px;
  padding: 0 15px;
  vertical-align: top;
  width: 25%;
}

li img {
  border: 3px solid white;
}

@media screen and (min-width: 1280px) {
  main {
    max-width: 100%;
  }

  figure {
    display: inline-block;
    float: left;
    margin-right: 50px;
    vertical-align: top;
    width: 950px;
  }

  ul {
    overflow: hidden;
  }

  li {
    width: 100%;
  }
}

@media screen and (max-width: 999px) {
  li {
    width: 25%;
  }
}

@media screen and (max-width: 899px) {
  li {
    width: 33.3333%;
  }
}

@media screen and (max-width: 599px) {
  li {
    width: 50%;
  }
}
```

# Summary

This lesson covered one of the hardest topics you'll come upon in your work with CSS: layouts. In particular, we looked at floats, positioning, Flex, Grid, and CSS frameworks. We also looked at responsive design using media queries as well as liquid and fluid layouts. We didn't go into great depth on any of these subjects, in part because employers don't expect junior software engineers to know it in depth, but also because of the complexity involved in mastering these topics - we could make two or three complete courses to cover these subjects. For now, you're better off learning this material on your own when you need it.

That said, you're still expected to take away some information from this lesson. In particular, you should be able to use:

- floated elements
- simple positioning
- liquid and fluid layouts
- media queries.

You should also know how and why you need to clear floats.

The next lesson introduces the concept of design files and gives you the opportunity to work on a couple of significant projects that will help solidify the concepts from this course.