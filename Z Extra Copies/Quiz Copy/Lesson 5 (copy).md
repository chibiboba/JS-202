# 1

![image-20230314193636943](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193636943.png)

### Discussion

Most forms need an `action` and `method` attribute. Note, though, that the HTML5 standards require neither: you can also provide the action and method with the `formaction` and `formmethod` attributes on one or more of the input widgets (typically, a button). Thus, choices **B** and **C** are correct.

**A** is incorrect since most forms don't need a `class` attribute. **D** is incorrect since `formaction` is not valid for the `<form>` tag.)

### Discussion

Most forms need an `action` and `method` attribute. Note, though, that the HTML5 standards require neither: you can also provide the action and method with the `formaction` and `formmethod` attributes on one or more of the input widgets (typically, a button). Thus, choices **B** and **C** are correct.

**A** is incorrect since most forms don't need a `class` attribute. **D** is incorrect since `formaction` is not valid for the `<form>` tag.)

![image-20230314193651503](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193651503.png)

# 2

![image-20230314193708601](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193708601.png)

### Discussion

Although the HTTP protocol defines a variety of different request methods, the HTML `<form>` tag limits you to the `GET` and `POST` methods. Thus, choices **B** and **E** are correct (note that case is unimportant when providing the method via the `method` attribute).

![image-20230314193745187](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193745187.png)

# 3

![image-20230314193800578](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193800578.png)

### Discussion

You should use the `POST` method for any request that updates the server-side database in any significant way. Searches seldom update the database, and most log entries are insignificant, so choices **C** and **E** are incorrect.

![image-20230314193812097](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193812097.png)

# 4

![image-20230314193819287](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193819287.png)

### Discussion

Both **B** and **D** are correct: they each create a button that submits the form when clicked. Choice **B** labels the button as `Send`, while choice **D** labels it as `Submit`.

Choice **A** is incorrect: it displays a button labeled as `Submit`, but the button won't submit the form by default. You must attach an "event handler" (which we'll discuss in a later course) to the button that tells the browser what should happen when the user clicks it.

Choice **C** is incorrect since it displays a text input field.

![image-20230314193832334](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193832334.png)

# 5

![image-20230314193840675](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193840675.png)

![image-20230314193849198](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193849198.png)

![image-20230314193854552](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193854552.png)

### Discussion

Choice **A** displays a set of 3 checkboxes from which the user can choose 0, 1, 2, or 3 items. Choice **C** uses a drop-down list with the `multiple` attribute to accomplish the same thing. Thus, both **A** and **C** are correct.

Choices **B** and **D** are incorrect since both radio buttons and drop-down lists without the `multiple` attribute limit the user to 0 or 1 selection.

# 6

Which of the following HTML snippets requires the user to choose a single color? The form data sent to the server should include the user's selection in lowercase (`red`, `green`, `blue`). The user should be able to choose a color by clicking on the control or its label. Select all that apply.

![image-20230314193925511](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193925511.png)

![image-20230314193933658](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314193933658.png)

### Discussion

Correct : B and D

Choice **A** is incorrect since it uses a `checkbox` control. Checkboxes let the user choose more than one item, and even let them choose none. Choice **B** is closer since it uses `radio` controls, but the `<input>` tags are missing the `id` attributes required to match them with their labels. Choice **C** is almost correct, but since it doesn't use the `value` attribute, the browser sends `color=on` to the server regardless of which button the user clicks.

Choice **D** is correct. It uses `radio` buttons to limit the user to one color. Each `<input>` has an appropriate `value` attribute, and each has an `id` attribute that associates it with its corresponding `<label>` tag.

# 7

![image-20230314194018809](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194018809.png)

![image-20230314194027599](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194027599.png)

### Discussion

Choice **C** is the correct choice. The `<textarea>` element lets a user enter multiple lines of text.

Choice **A** limits input to a single line of text. Choice **B** is invalid HTML: `<input>` is invalid inside a `<select>` element. Choice **D** uses a `multiple` attribute, which isn't defined for `<input>`.

# 8

![image-20230314194046289](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194046289.png)

![image-20230314194051451](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194051451.png)

### Discussion

Choice **B** is the correct choice: the password input control typically masks the input with a series of `*` characters, thus hiding it from the view of shoulder surfers and screen sharers.

Choice **A** is incorrect since it displays the typed text. Choices **C** and **D** both hide the control from view which prevents the user from doing anything with it, so they are also incorrect.

# 9

![image-20230314194108538](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194108538.png)

### Discussion

Choice **A** is incorrect; by default, most browsers don't do a good job laying out forms. Most browsers use an `inline` or `inline-block` visual display model for the labels and most controls which means that the elements flow like text. Typically, that's not what you want.

Choice **D** is incorrect: an unordered list limits the amount of positioning and alignment you can do. Instead, use definition lists for optimum flexibility.

Choices **B** and **C** will both prove helpful in laying out your forms.

![image-20230314194119275](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230314194119275.png)
