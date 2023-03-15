# 1

![image-20230314192447673](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192447673.png)

### Discussion

Choice **A** is incorrect since two `block` elements always use the entire width of the container, so cannot be side by side if they have the same parent. Choice **C** is incorrect since browsers do use the left and right margins of `block` elements.

Choice **B** is correct since the parent elements may be `inline-block` or `inline`, which lets the browser render them side by side. With the proper dimensions, margins, padding, and alignment, it's possible to arrange the child `block` elements side by side as well.

Choice **D** is correct. In fact, you can change any element's visual display model to any other visual display model.

![image-20230314192459445](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192459445.png)

# 2

![image-20230314192511950](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192511950.png)

### Discussion

While browsers ignore the `width` property for most `inline` elements and calculate the width based on the content, the `img` element is an exception. Thus, choice **A** is incorrect. Choice **B** is incorrect since browsers don't ignore the left and right margins for inline elements; they do, however, ignore the top and bottom margins, so choice **C** is correct. Choice **D** is incorrect since browsers use padding for `inline` elements.

![image-20230314192522156](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192522156.png)

# 3

![image-20230314192530187](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192530187.png)

### Discussion

Some developers believe that images are `inline-block` elements by default; in fact, they are `inline` elements. Thus, choice **A** is incorrect.

Choice **B** is incorrect. Two consecutive `inline-block` elements with a total width of `100%` may render side by side, but not necessarily. To render side by side, you must account for any whitespace between the two elements, and must also account for their borders and padding; the left/right margins must be 0 in any case.

The browser collapses any whitespace between adjacent `inline-block` elements to a single space. Thus, choice **C** is incorrect.

![image-20230314192542171](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192542171.png)

# 4

![image-20230314192554003](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192554003.png)

What size font will browsers use to display the words `Red`, `Green` and `Blue`?

Try to answer this question without using your browser.

![image-20230314192809159](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192809159.png)

### Discussion

The CSS defines the font size of the `<li>` elements as `1.2rem`. Rem measurements use the root font size (as determined by the `<html>` element) to calculate the desired size. In this case, we have a root font size of `20px`, so we can determine the size of the `<li>` elements as `20px * 1.2`, or `24px`. Thus, choice **B** is correct.

![image-20230314192612011](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192612011.png)

# 5

![image-20230314192624673](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192624673.png)

![image-20230314192632034](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192632034.png)

![image-20230314192756308](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192756308.png)

### Discussion

The CSS defines the font size of the `<li>` elements as `1.2em`. Em measurements use the font size for the parent element to calculate the desired size. In this case, the `<ul>` parent inherits a font size of `1.25rem` from the `<section>` header. `1.25rem` is `25px` based on the root font, so the final size of the `<li>` elements is `25px * 1.2`, or `30px`. Thus, choice **D** is correct.

![image-20230314192645312](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192645312.png)

# 6

Consider the following code:

```HTML
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

Try to answer this question without using your browser.

![image-20230314192740123](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192740123.png)

### Discussion

Percentage widths use the content width of the parent element and must also take into account the `box-sizing` property. In this problem, the content width for the `<body>` element is 880px: 1000px for the `width` property, less 120px for the padding and border on the sides since we have a `border-box` sizing model. The `<section>`'s width is 660px (880px * 0.75), and that leads to a width of 528px (660px * 0.80) for the `<img>`. Thus, choice **A** is correct. Note that the actual width of the image does not factor into the computation.

![image-20230314192725695](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314192725695.png)