# References

- [MDN HTML Forms Guide](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms).
- [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) for the `<input>` tag.

# Introduction

Forms are the principal way that users interact with Web applications. HTML5 provides more than a dozen different form-related tags and more than two dozen different input types. That's a lot of material to cover, but you don't need to memorize it all -- you can use forms effectively with about a half dozen tags and around a dozen data types. We'll briefly discuss (and use) the most common in this lesson; you can learn more by reading the [MDN HTML Forms Guide](https://developer.mozilla.org/en-US/docs/Learn/HTML/Forms).

## What to Focus On

- Use the `form` tag.

- Know the differences between checkboxes, radio buttons, and selection lists.

- Use `input` and `textarea` text tags.

- Understand the `type` attribute on `input` tags.

  - `checkbox`, `radio`
  - `text`, `email`, `tel`, `password`
  - `submit`, `reset`
  - `hidden`

  

- Construct `select` lists

- Use labels in a form with both container and `for` formats.

- Use description lists to help format forms.

### Study From The Summary

Spend time with the Summary at the end of this lesson. It reviews the topics and terminology you should master before moving on.

# Forms Overview

- HTML forms let you gather information from users. The vast range of data types requires that you have a large number of form controls at your disposal, each of which has different attributes to describe the characteristics of each item.

- Forms are the point where front-end and back-end concerns come together. It's crucial to understand how forms and their controls work. 
  - A form displays information to the user, solicits updates, performs some optional rudimentary validation, and then sends the form data to the server.

- However, that's all that forms do; they don't, for instance, update information on the server. 
  - For that, the application needs back-end software, such as a Ruby program, that accepts the data from the browser and does something with it. 
  - Most web applications also use JavaScript to pre-validate forms before sending the results to the server. We'll learn about JavaScript in future courses.

## The `form` Element

- The `form` element is the parent for all form-related elements. It tells the browser where and how to send the data. The most important attributes are `action` and `method`.

- A form should contain at least one `input`, `textarea`, or `select` element; without one, the form is useless. 
  - We use the terms **control**, **widget**, and **input** informally to refer to any of these elements as a group. 
  - If we need to be more specific, we'll talk about an input tag or input element or use `input` with inline-code styling.
  - In the real world, there is no single term like **control** or **input** that has the same connotation -- **widget** probably comes closest.

### The `method` Attribute

- The `method` attribute tells the browser whether it should use the HTTP GET or HTTP POST method when sending the data to the server. 
  - Use `method="get"` when requesting information from the server.
  - Use `method="post"` when updating data on the server.

- HTTP supports several other methods, but HTML limits you to `GET` and `POST`. You must use JavaScript or a backend application to use the other methods.

### The `action` and `formaction` Attributes

- `action` provides the URL to which the browser sends requests.
- Individual action items (`button` and `input type="submit"` elements) in a form can override the form's `action` value by using the `formaction` attribute.
  - The `formaction` lets us use the same form to perform different actions. 
  - If you click either button containing `formaction` instead of the `Log In` button, the browser sends the form information to the address given by `formaction`. Otherwise, it sends it to the address given by `action` in the `form` tag.

## The `fieldset` element

- `fieldset` is an optional tag that groups together form content as a set of related data; most browsers draw a border around the content. 
- While it's common to remove that border with CSS, `fieldset` still provides useful semantic data to the browser, and developers can reference it in their CSS for layout and styling purposes.

- Forms can have multiple `fieldset` tags.

```html
<form action="/login" method="post">
  <fieldset>
    <input type="text" name="username">
    <input type="password" name="password">
  </fieldset>
  <fieldset>
    <input type="submit" value="Save">
    <input type="submit" value="Forgot Password" formaction="/forgot">
  </fieldset>
</form>
```

## The `input` element

- The `input` tag describes a control or widget; which is a mechanism that lets the user supply information or a request to the application on the server.
  - `input` is a self-closing tag.

<img src="C:\Users\jenny\Downloads\download (16).png" alt="download (16)" style="zoom: 50%;" />

#### `type` attribute

- Each `input` requires a `type` attribute, which has a large number of valid values, most of which are new in HTML5; each value indicates the type of widget required. 
- For instance 
  - `type="text"` provides space for the user to enter some text. 
  - `type="submit"` provides a button that submits the form to the server.

<img src="C:\Users\jenny\Downloads\inputtype.png" alt="inputtype" style="zoom: 50%;" />

#### `name` attribute

- The `name` attribute specifies the name of an `<input>` element.
  - Most `input` controls require a `name` attribute to specify the name of each item.
- The browser uses these names to identify each data item in the form, while the back-end application looks for that name to find the appropriate value.

```html
<input type="text" name="city">
<input type="password" name="password">
<input type="submit" value="Save">
```

For now, we won't go into much detail about the `input` tag. We'll study it in the next assignment.

## The `label` element

- The `label` tag provides a way to associate some identifying text with an input field. 

#### `for` attribute `id` attribute

- Here we associate the label `Phone` with the field named `phone_number`. The browser uses the `for` attribute in the `label` tag and the `id` attribute in the `input` tag to associate the two items. 

```html
<label for="phone">Phone</label>
<input type="text" id="phone" name="phone_number">
```

- The `for` attribute of a `label` element must be equal to the `id` attribute of the related element to be associated together.

![download (15)](C:\Users\jenny\Downloads\download (15).png)

- One advantage of this association is that the user can click on the label to make the cursor jump to the desired field.

- You can also use `label` tags as containers:
  - The "container" syntax eliminates the need for the `for` and `id` attributes, so it's easier to use. 
  - However, styling can be more difficult with the container syntax, and there are times when you must use a `for` attribute, so learn both variants.

```html
<label>
  Phone
  <input type="text" name="phone">
</label>
```

## A Complete form Example

This form has two input fields, `username` and `password`, each with a label, and four buttons.

```html
<form action="#" method="post">
  <fieldset>
    <h1>Log In</h1>
    <label for="username">Username</label>
    <input type="text" name="username" id="username">

    <label for="password">Password</label>
    <input type="password" name="password" id="password">

    <input type="submit" value="Log In">
    <input type="submit" value="Delete account"
           formaction="/account/delete">
    <input type="submit" value="Forgot password"
           formaction="/account/password">
    <input type="reset" value="Reset">
  </fieldset>
</form>
```



![Log in](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/forms-overview-01.png)



- The `formaction` on the `Delete account` and `Forgot password` buttons lets us use the same form to perform three different actions. If you click either button instead of the `Log In` button, the browser sends the form information to the address given by `formaction`. Otherwise, it sends it to the address given by `action` in the `form` tag.

- Hmm, that last form looks strange with all the inputs together on one line. Let's use a few `fieldset` tags to arrange them more attractively.

```html
<form action="#" method="post">
  <fieldset>
    <h1>Log In</h1>
    <fieldset>
      <label for="username">Username</label>
      <input type="text" name="username" id="username">
    </fieldset>

    <fieldset>
      <label for="password">Password</label>
      <input type="password" name="password" id="password">
    </fieldset>

    <fieldset>
      <input type="submit" value="Log In">
      <input type="submit" value="Delete account"
             formaction="/account/delete">
      <input type="submit" value="Forgot password"
             formaction="/account/password">
      <input type="reset" value="Reset">
    </fieldset>
  </fieldset>
</form>
```

```css
fieldset {
  border: none;
}
```

- Note that we disabled the `fieldset` border that most browsers draw by default.

![Pretty Log in](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/forms-overview-02.png)

<img src="C:\Users\jenny\Downloads\download (16).png" alt="download (16)" style="zoom: 50%;" />

# Input Types

- The most versatile and widely used form widget is the `input` element. 
  - Most controls are `input` elements. 
  - Some look identical in most browsers, such as the `text`, `email`, and `tel` types, but some look radically different: a `text` input looks nothing like a `submit` button or a `checkbox`.

- The example `input` elements shown on this page use Launch School's styling. If you copy the HTML to your browser, you will see results that use your browser's default styling instead.

## `Type` attribute

- Start with the `type` attribute when creating an `input` element. With the development of HTML5, the number of types available almost tripled. Not all see widespread use, but they all serve a purpose.

- The most common input types are as follows:

### Type `text`

- The `text` type creates a simple text entry field. The user can enter any text desired in this control, though the developer should almost always validate the data. 
- Use the `maxlength` attribute to specify the input's maximum length.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      First Name
      <input type="text" name="first_name" value="Tom">
    </label>
  </fieldset>
</form>
```

![image-20230326191750036](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230326191750036.png)

### Type `password`

- The `password` type creates a single-line text field with an obscured value, often used for passwords and other sensitive information. 
- Use the `maxlength` attribute to specify the input's maximum length.
- The `value` attribute in this example is illustrative. In most cases, you should not set a value for the `password` input type.

```html
<form action="#" method="post">
  <fieldset>
    <label for="password">Password</label>
    <input type="password" name="password" id="password"
           value="Not-good-password" size="35">
  </fieldset>
</form>
```

![image-20230326191759433](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230326191759433.png)

### Type `email`

- The `email` type allows entry of an email address in the form `username@domain`. Browsers that implement this type try to prevent incorrectly formatted email addresses. 
- However, the developer should almost always validate the data too.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Email
      <input type="email" name="email" placeholder="username@domain">
    </label>
  </fieldset>
</form>
```

![image-20230326191812256](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230326191812256.png)

### Type `tel`

- The `tel` type allows entry of a telephone number. 
- Browsers that implement this type don't validate the input since phone numbers vary so much worldwide.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" placeholder="(###) ###-####">
    </label>
  </fieldset>
</form>
```

![image-20230326191824366](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230326191824366.png)

### Type `checkbox`

- The `checkbox` type lets the user choose one or more items from a series of yes/no-type options. 
- Use the `value` attribute to give the value the form sends to the server when the user selects that checkbox. 
  - `value="search"`
- Use the boolean `checked` attribute to pre-select checkboxes. 
  - The boolean `checked` attribute marks a checkbox as selected when supplied in the `input` tag. 
  - In the above below, we've selected the 2nd and 3rd elements.
  - You can select checked elements in CSS with the `:checked` pseudo-class, which lets you change the appearance of checked radio buttons and checkboxes. Note that this pseudo-class doesn't look for the actual `checked` attribute; instead, it selects based on the current state of the checkbox.
- Use the `name` attribute to name a set of related checkboxes. The user can select zero or more items in each set of checkboxes. 
  - `name="choice"`
  - You can also use the `name` attribute without a `value` attribute.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="checkbox" name="choice" value="search">
      Sort search results
    </label>

    <label>
      <input type="checkbox" name="choice" value="google" checked>
      Search on Google
    </label>

    <label>
      <input type="checkbox" name="choice" value="recent" checked>
      Recent results (within last year)
    </label>
  </fieldset>
</form>
```

![image-20230326191836068](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230326191836068.png)

- With these three checkboxes, a user can run up to 8 different searches by turning the various checkboxes on and off. 
  - All the checkboxes have the same `name`, but different `value`s. The browser sends a `name=value` pair for each selected checkbox and no value for the unselected ones. 
  - In this case, the browser will send `choice=google` and `choice=recent` to the server.

- You can also use the `name` attribute without a `value` attribute like this:
  - Here, the browser will send `google=on` and `recent=on` to the server. 
  - Use the format that your server-side code expects. In most cases, it's easiest to use separate `name` values.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="checkbox" name="search">
      Sort search results
    </label>

    <label>
      <input type="checkbox" name="google" checked>
      Search on Google
    </label>

    <label>
      <input type="checkbox" name="recent" checked>
      Recent results (within last year)
    </label>
  </fieldset>
</form>
```

### Type `radio`

- The `radio` type lets the user choose **zero or one item** from a list of options. 
- Use the `value` attribute to define the value submitted by this item. 
- Use the `checked` attribute to mark the default radio button. 
  - If there is no default button, use the `required` attribute on all of the buttons in a group to enforce selecting a button. 
- Use the `name` attribute to name a set of related radio buttons. The user can select precisely one radio button from each group.

```html
<form action="#" method="post">
  <fieldset>
    <label>
      <input type="radio" name="color" value="red">
      Red
    </label>

    <label>
      <input type="radio" name="color" value="green" checked>
      Green
    </label>

    <label>
      <input type="radio" name="color" value="blue">
      Blue
    </label>
  </fieldset>
</form>
```

![image-20230326191917211](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230326191917211.png)

- With these three buttons, a user can choose which of three colors he wants to use in the output, but not more than one. All the buttons have the same `name` attribute of color, but a different `value` attribute of different colors.

- The boolean `checked` attribute works as it does with checkboxes by pre-selecting an item. In the above example, we've pre-selected the 2nd element. As with checkboxes, you can also use the `:checked` pseudo-class in your CSS.
- The user does not have to select a radio button if you don't pre-select one with the `checked` attribute and none of the buttons have a `required` attribute. On the other hand, if you pre-select any, you must choose precisely one, and the user must either accept that choice or choose another

- Typically, radio buttons work best with short lists. At a certain point, often around 5-8 items, they become unwieldy, both for the developer and the user. You may want to consider using the `select` list control when you have more than a handful of options from which to choose.

### Type `submit`

- The `submit` type creates a button that the user can click to submit the contents of a form to the server. 
- The `action` attribute on the `form` tag specifies the URL of the server that will receive the form data when the user submits it, but you can override that by using the `formaction` attribute. 

```html
<form action="#" method="post">
  <fieldset>
    <input type="submit" value="Save">
  </fieldset>
</form>
```

![image-20230326191929894](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230326191929894.png)

### Type `reset`

- The `reset` type creates a button that the user can click to reset the contents of a form to its default values. 
- Clicking a `reset` button does not send a request to the server.

```html
<form action="#" method="post">
  <fieldset>
    <input type="reset" value="Clear Form">
  </fieldset>
</form>
```

![image-20230326192004456](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230326192004456.png)

### Other Input Types

- There are other form controls, some of which we may ask you to use later in this lesson. 
- To see the complete list, see the [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) for the `<input>` tag. Study the list, but don't try to memorize them all - you can look them up as needed.

# Input's other Attributes

The `input` tag supports a variety of attributes -- some work with most input types, and some with just one. We describe the features worth memorizing in this assignment.

### The `value` Attribute

Most input controls can use the `value` attribute, but the meaning varies with the `type`.

- For text-based types such as `text`, `email`, and `number`, the `value` assigns a default value for the control. If you don't supply a default value, the browser uses an empty string.

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        Phone
        <input type="tel" name="phone" value="503-555-1212">
      </label>
    </fieldset>
  </form>
  ```

  

  ![value attribute with type=text](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-01.png)

  

  You should use `value` when you already have a value, either loaded from a database or provided by the user during the session.

- `checkbox` and `radio` types use the `value` attribute to set the value that the form submits for the indicated checkbox or radio group element.

  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        <input type="radio" name="color" value="red">
        Red
      </label>
      <br>
  
      <label>
        <input type="radio" name="color" value="blue" checked>
        Blue
      </label>
      <br>
  
      <label>
        <input type="radio" name="color" value="green">
        Green
      </label>
    </fieldset>
  </form>
  ```

  

  ![value attribute with type=radio and type=checkbox](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-02.png)

  

  Technically, `radio` input types don't require the `value` attribute. If you omit the `value` attribute, the browser will send `NAME=on` to the server, where `NAME` is the value of the `name` property. We recommend always using the `value` attribute and use `name` to group related radio buttons together. If several radio buttons belong together, they should all have the same `name` attribute value.

  Note that we added a `checked` attribute to the blue button to make that button the initial selection. If we want to leave all of the radio buttons unselected, but still require a selection, we can add a `required` attribute to each button.

- Button types, such as `submit`, `reset`, and the `button` type use the `value` attribute for the label that appears on the button:

  ```html
  <form action="#" method="post">
    <fieldset>
      <input type="submit" value="Save">
    </fieldset>
  </form>
  ```

  

  ![value attribute with buttons](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-03.png)

  

  Note that `type="button"` is out of favor; consider using the `<button>` element instead.

### The `size` and `maxlength` Attributes

These attributes apply to most text-based input types.

The `size` attribute lets you control the size of an `input` element in characters. You can also specify the width with the CSS `width` property, but it does not support character measurements. `maxlength` is similar, but it limits the maximum length of input values; this value can be more or less than the `size` value.

Copy Code

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" size="10" maxlength="16">
    </label>
    <br>
    <label>
      Cell Phone
      <input type="tel" name="cell-phone" size="20" maxlength="40">
    </label>
  </fieldset>
</form>
```



![size and maxlength attributes](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-04.png)



`size` is an *approximation* for the width of the input box. The HTML5 standard requires that "the user agent should ensure that at least that many characters are visible"; in practice, you may see both more and fewer characters displayed. The CSS `width` overrides the `size` attribute in CSS-enabled browsers.

HTML5 also supports a `minlength` attribute, but support for this attribute is inadequate at the time of this writing.

### The `placeholder` Attribute

The `placeholder` attribute lets you display some text when a field is empty to help describe the expected input; it applies to most of the text-based `input` types. Most browsers display `placeholder` text using a grayed-out format, and they erase the placeholder text as soon as you start typing:

Copy Code

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Phone
      <input type="tel" name="phone" placeholder="###-###-####">
    </label>
  </fieldset>
</form>
```



![placeholder attribute](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-05.png)



You may see sites that use placeholders as a substitute for labels. Don't do this yourself, though, since it breaks screen readers. Labels and placeholders have different purposes, so use them appropriately. If you're forced to use placeholders, include the labels too, but hide them using CSS. This hack works well since most screen readers can read the hidden text.

### The `disabled` Attribute

The `disabled` attribute lets you disable `input` elements; the browser renders disabled elements but won't let the user interact with them. The rendering looks different from enabled attributes, often by using a gray or lighter color. `disabled` also turns on the `:disabled` CSS pseudo-class. (Non-disabled elements set the `:enabled` pseudo-class.)

Most web applications handle the `disabled` attribute programmatically, either at the time the application generates the HTML or dynamically with JavaScript. You still need to know that `disabled` exists, though; you may have to write some HTML for a program that expects disabled inputs on the original form.

Copy Code

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Email
      <input type="email" name="email" value="xyz@example.com" disabled>
    </label>
    <br>
    <input type="submit" value="Save" disabled>
  </fieldset>
</form>
```



![disabled attribute](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-06.png)



### The `required` Attribute

The `required` attribute marks an `input` as required; the browser won't let you submit the form until the user completes all required fields. `required` also turns on the `:required` CSS pseudo-class.

Copy Code

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Home Phone
      <input type="text" name="home_phone" required>
    </label>
    <br>
    <label>
      Business Phone
      <input type="text" name="business_phone">
    </label>
    <br>
    <input type="submit" value="Save">
  </fieldset>
</form>
```

Copy Code

```css
input:required {
  background-color: yellow;
}
```



![reuqired attribute](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-07.png)



### The `autocomplete` Attribute

You can use `autocomplete` on most `input` text-box elements. This attribute prevents the browser from storing data for later reuse by the browser's `autocomplete` features. Autocomplete is common on smartphones and tablets but can be a nuisance. You can use the values `on` and `off` to explicitly turn `autocomplete` on or off on any given field.

Copy Code

```html
<input type="tel" value="123-456-7890" name="phone" autocomplete="off">
```

The `autocomplete` option does not affect the `password` input type.

### The `autocapitalize` Attribute

Some browsers recognize an `autocapitalize` attribute to turn autocapitalization on and off for the first letter of words or sentences. Browsers that recognize this attribute default to `sentences`. Use `autocapitalize="none"` when expecting input that you don't want to capitalize. You can also specify `autocapitalize="words"` or `autocapitalize="characters"`.

Copy Code

```html
<input type="text" name="full-name" autocapitalize="words">
```

`autocapitalize` is not part of the HTML standard, but an attribute provided by some *mobile* browsers, such as iOS Safari and Google Chrome. It does not affect desktop and laptop systems. The W3C HTML validator presently complains about `autocapitalize` since it is non-standard. If you want to use this attribute, you'll have to suffer that complaint.

### The `autocorrect` Attribute

Some browsers support an `autocorrect` attribute that turns automatic spelling correction on and off. You can disable this feature with `autocorrect="off"`; you should usually disable it with names, addresses, and other information where autocorrection would be a bother.

```html
<input type="text" name="full-name" autocorrect="off">
```

`autocorrect` is non-standard HTML, but an attribute presently provided by iOS Mobile Safari. Since it is non-standard, the W3C HTML validator will complain about the `autocorrect` attribute. If you want to use this attribute, you'll need to get used to this complaint.

# Select and Textarea

Now that you've got some input controls in your toolkit, the remaining inputs, `select` and `textarea`, will be quick to learn.

## The `textarea` Element

`textarea` lets the user input multiple lines of text. Unlike `text`-type inputs, which ignore carriage returns, newlines, and other whitespace characters, `textarea` elements retain them and use them to format the text into lines and paragraphs. Unlike other controls, though, the value of the `textarea` doesn't use the `value` attribute to provide a value for the element. Instead, you need to contain the text between the opening and closing tags.

Copy Code

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Comment
      <textarea name="tweet">I got 20% off my first purchase at joesburgers.com! You can too!</textarea>
    </label>
  </fieldset>
</form>
```

Comment

Since `textarea` preserves whitespace, its common practice to code the open and close tags on the same line unless the initial text content contains newlines.

### Rows and Cols

`textarea` uses the `rows` and `cols` attributes to control the height and width of the text box; `rows` is the height in lines, while `cols` is the width in characters. As with the `size` attribute on some `input` tags, neither measurement is precise - the browser may choose to display more or fewer lines or columns than requested. The CSS `height` and `width` properties will also override these attributes. Furthermore, the `rows` value is not a maximum for the number of lines of input allowed; instead, it's the number of visible lines. The text box enables vertical scrolling when the content exceeds the `rows` count.

Most browsers today let the user resize the `textarea` box by dragging and dropping a small triangle that appears in the lower-right corner of the text box.

Copy Code

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Comment
      <textarea name="tweet" rows="5" cols="40">I got 20% off my first purchase at joesburgers.com! You can too!</textarea>
    </label>
  </fieldset>
</form>
```

Comment

You can disable this feature with the CSS `resize` property.

## The `select` Element

`select` creates a drop-down list of options from which the user can select zero or more options. It has two possible child elements, the `option` and `optgroup` elements (we won't discuss `optgroup` in this course). `select` uses the `name` attribute like other form elements, but it uses the `option` elements within it to describe the values shown to the user and sent to the server (which may be different).

### The `option` Element

An `option` defines one of the choices a user can make in a `select` tag. A `select` element is useless without its `option` elements. Each `option` represents a possible value for the select, and they use the `value` attribute as the value sent to the server with the `select` element's name. If an `option` does not have a `value` attribute, the browser uses the text contained by the `option` element instead.

`select` elements often have a placeholder `option` that says something like `Choose one` and has a `value` of an empty string, as well as a `disabled` and `selected` attribute. This option works something like the placeholder attribute on text boxes: the user can see some helpful text, but she cannot select that text.

Copy Code

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Colors
      <select name="color">
        <option value="" disabled selected>Choose one</option>
        <option value="#f00">Red</option>
        <option value="#0f0">Green</option>
        <option value="#00f">Blue</option>
      </select>
    </label>
  </fieldset>
</form>
```

Colors       Choose one      Red      Green      Blue     

By default, `select` lets the user choose precisely one option or leave the option unselected if it contains a `disabled selected` option as shown above. If you add the `multiple` attribute, the user can select more than one option. On most browsers, a `select` with `multiple` appears as a (possibly scrolling) rectangle that displays several options. The user then Ctrl-clicks (Windows) or Cmd-clicks (Mac) to select the options she wants. You can also supply the size attribute to control the height of the selection box.

Copy Code

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Choose Your Favorite Movies
      <select name="favorites" multiple size="4">
        <option value="" disabled selected>Select One or More</option>
        <option>2001: A Space Odyssey</option>
        <option>Arrival</option>
        <option>Close Encounters of the Third Kind</option>
        <option>District 9</option>
        <option>Guardians of the Galaxy</option>
        <option>Interstellar</option>
        <option>Serenity</option>
        <option>Silent Running</option>
      </select>
    </label>
  </fieldset>
</form>
```

Choose Your Favorite Movies       Select One or More      2001: A Space Odyssey      Arrival      Close Encounters of the Third Kind      District 9      Guardians of the Galaxy      Interstellar      Serenity      Silent Running     