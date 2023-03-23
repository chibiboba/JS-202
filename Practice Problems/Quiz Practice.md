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