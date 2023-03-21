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

- Since `img` has `display: inline-block` meaning that is an `inline-block` element, we can compute dmensions directly from CSS properties. 

- Since `div` uses `border-box` sizing, it must include have a width and height of at least 580 px and 360 pixels. Though we don't typically count margins in determining an element's width and height, we need to include them here when calculating how much space we need in the `div`. 

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

- The difference here is that `section` is a block element, so it will always appear on a line by itself within it's container `div` no matter its width. And because it is a block element, the browser will use all the CSS propeties to compute the dimensions  for `section` including : `width` `height` `margin` `border` and `padding`. 
- Since `div` uses `border-box` sizing, the padding and borders are included in calculating the space needed. Although margins are typically not included in `box sizing`, we will need to include it our calculations for how much space `div` needs to contain `section`.  The width and height will be 580 pixels horizontally and 360 pixels vertically. 

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

Since `em` element is `inline` element, the browser ignores the width, height, top and bottom margins specified in the CSS.  The minimum width and height `div` needs to contain `em` is 

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

7. **Challenge.** Given our solution to the previous question, what will happen if we put the `article` tags on separate lines?

```html
<section>
  <article>content</article>
  <article>more content</article>
</section>
```

Try to figure out the answer without peeking. Why do you think this is?

Solution