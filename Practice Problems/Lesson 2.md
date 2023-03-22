# Practice Problems: The Box Model

1. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `img` element (including its margins)?

```html
<div>
  <img src="#" alt="test">
</div>
```

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
```

Answer 

- Since `img` has `display: inline-block` meaning that is an `inline-block` element, we can compute dimensions directly from CSS properties. Since `img` uses `content-box` sizing, we calculate the total dimensions (the visible area) by `width`, `height`, `margin`, `padding`, and `border`. 

- Since `div` uses `border-box` sizing, we include the dimensions of `img` as well as `div`'s borders, padding, and margin. Though we don't typically count margins in determining an element's width and height, we need to include them here when calculating how much space we need in the `div`. 

- Horizontally, the `div` element needs 580 pixels.
  - border: 4 pixels left, 4 pixels right
  - margin: 19 pixels right, 11 pixels left
  - padding: 20 pixels right, 20 pixels left
  - width: 500 px 
  - 2 pixels for the left and right borders of `div`
- Veritically, the `div` element needs 380 pixels.
  - border: 4 px top, 4x bottom
  - margin: 20 px top, 10 px bottom
  - padding: 10 px top 10 px bottom
  - height: 300 px
  - 2 pixels for the top and bottom borders of `div`. 

2. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `section` element (including its margins)? How does this differ from the result of the previous practice problem?

```html
<div>
  <section>content</section>
</div>
```

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

- The difference here is that `section` is a block element, so it will always appear on a line by itself within it's container `div` no matter its width. And because it is a block element, the browser will use all the CSS properties to compute the dimensions  for `section` including : `width` `height` `margin` `border` and `padding`. Since `section` is uses `content-box` sizing, we include the border and padding in calculating the total dimension of `section`. 
- Since `div` uses `border-box` sizing, the padding, border, and margin of `div` are included in calculating the total space needed. Although margins are typically not included in `box sizing`, we will need to include it our calculations for how much space `div` needs to contain `section`.  
- The width and height will be 580 pixels horizontally and 360 pixels vertically. 

3. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `em` element (including its margins)?

```html
<div>
  <em>content</em>
</div>
```

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

- Since `em` element is `inline` element, the browser ignores the width, height, top and bottom margins specified in the CSS. For this reason, we can't calculate the amount of space that any given `em` would take unless we know the actual width and height of the content. 

- Just as an example, if we assume that `em` requires 50px width, then the `div` element would need 130 pixels horizontally. 

  - 50 pixels for assumed width

  - 4 px left border 4 px right border

  - 19 px right margin 11 px left margin

  - 2 pixels for left and right borders of the `div`. 

- If we assume that the `em` requires a 20px height, then the `div` needs 50 pixels vertically.
  - 20 pixels for assumed height.
  - 4 px top border 4 px bottom border
  - 10 px top padding 10 px bottom padding
  - 0 pixels for top and bottom margins (because it's `em` is `inline`)
  - 1 px for top 1 px bottom borders of `div`.

- Since `div` uses `border-box sizing`,  minimum width and height `div` needs to contain `em` is 130px width and 50 px height. This includes the dimensions of `em` including the assumed width and height & margins, as well as any borders, padding, or margins of `div`. 
- We need to keep in mind that the top and bottom padding and borders of `em` may intersect with content above and below the `em` element. 
  - This is because `em` has an assumed fixed height of 20 pixels and `div` height has a minimum height of 50 pixels, so any content above or below the `em` element may overlap with the padding and border of `em`. 

4. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to be to entirely contain the `article` element (including its margins)?

```html
<div>
  <article>content</article>
</div>
```

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

First we calculate the dimensions of `article`. `article` is `inline-block` so we can use CSS dimensions to calculate it. But because `article ` uses `border-box` sizing, we must ignore the padding and border to calculate the actual dimensions. Aside from margins, the actual dimensions of `article` is determined in its width and height already. 

Because `div` use `box-sizing` `border-box`, we include its margins, padding, and border of `div` too. 

- Horizontally - total is 532 pixels.
  - width: 500 px
  - padding: 0 pixels for left and right. 
  - margin: 19 px right 11 px left
  - border: 0 px for left and right. 
  - border of `div` : 2 px for left and right
- Vertically - total is 332 pixels.
  - 300 px height
  - padding: 0 pixels top and bottom
  - margin: 20 px top 10 px bottom
  - border: 0 pixels top and bottom
  - Border of `div` : 2 px for top and bottom

5. Given the code below:

```html
<div>
  <tag1>content</tag1><tag2>content</tag2>
</div>
```

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

2, 3, 6 will all appear side by side. The other three combinations have `block` elements which never appear side by side with anything. 

Solution

6. Will the following code display the two article boxes side by side? If not, why not? How would you fix it so that it places the boxes side by side?

```html
<section>
  <article>content</article><article>more content</article>
</section>
```

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

Show

No because `article` is a block element so it always appears on its own line and takes up the whole width of its container element. 

We can convert the `article` elements into an `inline-block` element by adding this code `display: inline-block` in the CSS selector. We need to set the actual width (including padding and border) to 50% of the container's space, and also add `box-sizing: border-box` to the `article` CSS selector.

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

7. **Challenge.** Given our solution to the previous question, what will happen if we put the `article` tags on separate lines?

```html
<section>
  <article>content</article>
  <article>more content</article>
</section>
```

Try to figure out the answer without peeking. Why do you think this is?

Solution

Because `article` is now an `inline-block` element, the browser sees the spaces between the two `article ` elements will collapse them into one whitespace character and uses the result as content between the two `article` elements. Since the total width of the container is only 900 pixels and now the white space takes a few pixels to account for the single space character, the two `article`s no longer fit in the same line.  

This kind of problem often occurs when one of the elements is an inline-block; the rest of the time, the extra space typically doesn't matter. Aside from placing the two tags up against each other to eliminate the whitespace, there are several other techniques you will see later that let you remove the space or make it invisible.

# Practice Problems: Spacing and Dimensions

In these practice problems, we'll work with heights, widths, padding, margins, and a variety of dimensional units.

Some of these problems use [this image](https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_dimension_and_spacing/Hôtel_des_Invalides_-_20150801_16h09_(10630).jpg). You may use it in your HTML like this:

```html
<img src="https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_dimension_and_spacing/H%C3%B4tel_des_Invalides_-_20150801_16h09_%2810630%29.jpg"
    alt="Demonstration of image sizing">
```

We'll discuss images and the `img` tag in a later lesson.

1. Use CSS to set a fixed width on the image of 800 pixels, and center it in the window horizontally.

   Hint

   Solution

   ```css
   img {
     display: block;
     margin: 0 auto; /* 0: top and bottom margin, auto: left and right */
     width: 800px;
   }
   ```

2. Using the code from the previous problem, change the `width` property for `img` to `100%`, and set the `max-width` property to `800px`. The image should expand to fit any container width up to 800 pixels. Resize your browser width and watch how that affects the photograph.

   Solution

3. Using the code from the previous problem, set a fixed height on the image of 533 pixels. Resize the browser window and watch how the image dimensions change.

   Solution

4. As you can see, having a variable size for one dimension and fixed for the other makes for a container with strange behavior: this one stretches horizontally but remains fixed vertically. Remove the height and update the CSS to ensure the width does not get smaller than 500 pixels.

   Solution

5. Create a new HTML page with two consecutive `div` elements. Make each a fixed width and height of 300 pixels. Set the background color on the first `div` to `"#fcc"` (red) and the second to `"#ccf"` (blue).

   Solution

6. Add a 5-pixel solid black border to the blue `div`. Compare the widths of the two boxes. Why is the blue box a different size?

   Solution

7. Add 20 pixels padding to all four sides of the red `div`. Notice the different widths again. Add a CSS property to both elements to ensure the total width for each is `300px` rather than `300px` and then some.

   Solution

8. Change both boxes to place them side by side instead of stacked vertically. If necessary, increase the width of your browser window.

   Solution

9. Add 20px of space between the red and blue boxes.

   Solution

10. Create a new HTML file with the following CSS and HTML:

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

11. Using the code from the previous problem solution, set the left and right margin on each `li` element to 1%, but do not let the inner boxes wrap around - they must all continue to fit on the same line with no change in the outer box's size.

    Solution