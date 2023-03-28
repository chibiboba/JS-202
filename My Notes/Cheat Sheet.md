# References

[HTML5 Element FLowchart](..\..\..\..\Downloads\h5d-sectioning-flowchart.pdf) 

[HTML Validator](https://validator.w3.org/#validate_by_input)

[CSS Validator](https://jigsaw.w3.org/css-validator/)

[HTML Standard](https://html.spec.whatwg.org/multipage/)

[Dom Standard](https://dom.spec.whatwg.org/)

[Web-safe fonts](http://web.mit.edu/jmorzins/www/fonts.html) 

Pexels.com for pictures

# Further Study

- If you want to know more, here are some suggested topics for further research:

  - The technical aspects of images: color depth, image size, compression, etc.

  - Background images: positioning and sizing, gradients

- [Web-safe fonts](http://web.mit.edu/jmorzins/www/fonts.html) 

- Selectors

- https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes

# HTML

# CSS

[CSS Cheat Sheet](https://javaconceptoftheday.com/css-cheat-sheet/)

![](C:\Users\jenny\Downloads\CSS_Cheat_Sheet.webp)

# How to adjust image 

### Aspect ratio automatic adjustment

- If you specify a fixed dimension for one side and don't specify for another side, then the other side will adjust automatically to maintain the same aspect ratio. 

### Interaction with mixing units

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

### **zeroing a reset**

- Zero out the margins and paddings for all elements to ensure that the appearance remains similar in different browsers.

```css
body, main, figure, figcaption, img {
  margin: 0;
  padding: 0;
}
```

- Use`outline` to outline the border of an element. 

  - `outline` is a line outside the element's border. It doesn't interact with the box mode and doesn't take up space, so it doesn't change the page layout.
  - This makes `outline` useful during development and debugging.


### An image may extend beyond the right side of the outline. (from photo gallery project)

- If an image doesn't have the `width` property or deprecated `width` attribute, then the web browser will use original width of the image as the default displayed width. That means the image may be wider than the container its placed in, resulting in the image being hidden or overflowing outside the container.
- In this case, the container element is a `figure` element. The default width for `figure` is `100%`, which in this case represents 100% of the browser window (minus the margins). If the width exceeds the width of the `figure`, the image will extend beyond the right side of the outline.

### Size of containers & child element

- The `body` master container is usually 100% of the browser window (minus the margins).
- `main` is the master container which inherits from `body`. 
- Whatever inherits from `main` may be more wide than `main`, so adjust the `max-width` to 100%. 
- If you want the child element to fit fully in container, adjust `width` to 100%. 

### How to make two block elements fit side by side in browser.

- Convert block element to `inline-block`
- Change width of element to percentage like 50%. 
- Change box-sizing to `border-box`. 
- Make left and right margin 0. 
- If you want left and right margin then use `padding` instead because `padding` is included in the content for `border-box`. 
- Remove Whitespace: Adjust code to remove whitespace by placing closing tag next to next `inline-block`element's opening tag.

```css
figure {
	display: inline-block;
  box-sizing: border-box;
  margin: 50px 0;
  padding: 0 50px;
  outline: 1px solid red;
 	width: 50%;
}
```

- Use `text-align:center` to center an element's `inline` content within the width the `block` element.

- Add `background-image` and stretch the picture using `background-size: cover`

- Use the "View Source" feature in your browser to see the final HTML and CSS.

### Width and padding

- Padding extends beyond width of 100% if not using `border-box`. Assign a background color to container element to see this happen.

### `0 auto`

- centers something within its container.
