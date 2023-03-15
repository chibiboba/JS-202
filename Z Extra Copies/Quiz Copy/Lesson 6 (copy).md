# 1

Consider the following code:

```html
<main>
  <section class="right">Right</section>
  <section class="left">Left</section>
</main>
```

```html
html {
  font-size: 32px;
}

main {
  border: 1px solid blue;
  padding: 10px;
}

section {
  border: 1px solid red;
  padding: 10px;
}

.right {
  float: right;
}

.left {
  float: left;
}
```

![image-20230314194212330](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194212330.png)

![image-20230314194223925](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194223925.png)

![image-20230314194230526](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194230526.png)

### Discussion

Browsers remove floated elements from the view of all container elements. In this case, they remove the two `section` elements from the `main` element, so `main` fails to expand enough to enclose both `section`s. To account for the floated content, you must apply `overflow: hidden;` or `overflow: auto;` to the container or add an element to the end of the container that uses the `clear` property. Here, we use an `::after` pseudo-element to add the correct element to the end of the `main` container. Choices **B** and **C** are incorrect since neither applies the required properties to `main`. Thus, choices **A** and **D** are correct.

![image-20230314203333566](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203333566.png)

# 2

[Question 2](https://launchschool.com/quizzes/cba810f6)

Consider the following code:

```html
<main>
  <section>Box 1</section>
  <section>Box 2</section>
  <section>Box 3</section>
</main>
```

```html
html {
  font-size: 32px;
}

main {
  border: 1px solid blue;
  overflow: hidden;
  padding: 10px;
}

section {
  border: 1px solid red;
  float: right;
  margin: 0;
  padding: 20px;
}
```

Pick the image that most nearly shows how browsers will render this code. You may assume that the browser window is wide enough to fit all three `section` elements on the same line. Try to solve this problem without trying the code in your browser:

![image-20230314203411928](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203411928.png)

![image-20230314203422381](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203422381.png)

### Discussion

Answer is C

Browsers will float items as they encounter them in the HTML, so Box 1 will float all the way to the right, Box 2 next, and Box 3 will appear first in line. Thus, we can eliminate choices **A** and **D**. We can also eliminate choice **E** since floated items don't wrap to the next line unless there isn't enough room for the item. Lastly, we can eliminate choice **B** since it shows non-zero margins between each box. Thus, choice **C** is correct.

# 3

Consider the following code:

```html
<header>
  <h1>
    This is My Heading
  </h1>
</header>
```

```css
header {
  color: red;
  font-size: 32px;
}

h1 {
  color: green;
  display: inline-block;
}

header::after {
  content: "*";
}

h1::before {
  content: "+";
}
```

Which of the following statements are true? Try to solve this problem without copying the code to your browser:

![image-20230314203525629](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203525629.png)

# ![image-20230314203530880](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203530880.png)

### Discussion

The `::after` and `::before` pseudo-element selectors add child text elements to the indicated container. Thus, `header::after` adds an `*` to the end of the `header` element that inherits the `color: red` property from the `header` selector. Likewise, `h1::before` adds a `+` to the beginning of the `h1` element and inherits the green color from the `h1` selector. Thus, choice **D** is the sole valid answer.

# 4

![image-20230314203545130](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203545130.png)

### Discussion

Choice **A** is incorrect since the browser does not remove `position: static` elements from the page flow unless some other characteristic (such as the `float` property) removes it from the flow. Choice **D** is incorrect: you can put a `position: static` element inside any container regardless of that container's `position` property.

![image-20230314203550867](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203550867.png)

# 5

![image-20230314203605894](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203605894.png)

### Discussion

Choice **A** is incorrect since browsers don't remove `position: relative` content from the page flow. In fact, they place the next element as though the relative content had static positioning. Thus, choice **D** is correct.

When an element includes both `left` and `right` properties, the browser will choose one depending on the language direction. However, the browser will use either value if the element omits one, regardless of language direction. Thus, choice **B** is wrong.

Choice **C** is correct since browsers will use `top` when the element includes both `top` and `bottom` values.

![image-20230314203614620](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203614620.png)

# 6

![image-20230314203630352](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203630352.png)

### Discussion

The browser positions `position: absolute` elements at a fixed position in the nearest ancestor element that has a `relative`, `absolute`, or `sticky` `position` property. If no such element exists, it uses the `body` element as the container. Thus, choices **C** and **D** are false.

Choices **A** and **B** are correct: `position: absolute` removes elements from the page flow, and browsers use all the offset properties supplied but does not require any of them.

![image-20230314203645911](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203645911.png)

# 7

![image-20230314203653236](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203653236.png)

### Discussion

Choice **C** is incorrect: the browser places `position: fixed` at a fixed position in the browser window, not inside a parent or container element. Thus, choice **D** is also wrong.

Choices **A** and **B** are both correct.

![image-20230314203706868](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203706868.png)

# 8

![image-20230314203715509](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203715509.png)

### Discussion

Choice **B** is correct: you define a Flex column or row by using `display: flex` on the container element for the row or column. Thus, choice **A** is incorrect. Choice **C** and choice **D** are incorrect since Flex does work with both rows and columns.

![image-20230314203726134](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203726134.png)

# 9

![image-20230314203735221](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203735221.png)

### Discussion

Choice **B** is false: Grid and Flex have different use cases but work well together. Choice **C** is also incorrect since Grid works best for grids of data: multiple rows and multiple columns. You can use it for individual rows and columns, but Flex provides a better alternative.

Choice **A** and choice **D** are both valid ways to use Grid.

![image-20230314203745571](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203745571.png)

# 10

![image-20230314203758821](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203758821.png)

![image-20230314203805524](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203805524.png)

### Discussion

With a mobile-first approach, the developer begins by writing the CSS needed to make the site work on the smallest displays, then uses media queries to add more CSS for progressively larger screens. Here, choice **C** best fits the idea that the developer used a mobile-first approach. The first block of CSS works with small phone-level devices, the second with larger devices (481px through 1000px in width), and then everything else.

![image-20230314203813007](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314203813007.png)
