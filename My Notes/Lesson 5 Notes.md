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
- We use the terms **control**, **widget**, and **input** informally to refer to any of those elements as a group. 
  - If we need to be more specific, we'll talk about an input tag or input element or use `input` with inline-code styling.
  - In the real world, there is no single term like **control** or **input** that has the same connotation -- **widget** probably comes closest.

### The `method` Attribute

- The `method` attribute tells the browser whether it should use the HTTP GET or HTTP POST method when sending the data to the server. 
  - Use `method="get"` when requesting information from the server.
  - Use `method="post"` when updating data on the server.

- HTTP supports several other methods, but HTML limits you to `GET` and `POST`. You must use JavaScript or a backend application to use the other methods.

### The `action` and `formaction` Attributes

- `action` provides the URL to which the browser sends requests.
- You can use `action="#"` instead of `action=""`if you want your code to pass W3C validation.
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

#### `id` attribute

- The `for` attribute of a `label` element must be equal to the `id` attribute of the related label/input element pair  to be associated together.

![download (15)](C:\Users\jenny\Downloads\download (15).png)

## The `label` element

- The `label` tag provides a way to associate some identifying text with an input field. 

#### `for` attribute `id` attribute

- Here we associate the label `Phone` with the field named `phone_number`. The browser uses the `for` attribute in the `label` tag and the `id` attribute in the `input` tag to associate the two items. 

```html
<label for="phone">Phone</label>
<input type="text" id="phone" name="phone_number">
```

- The `for` attribute of a `label` element must be equal to the `id` attribute of the related label/input element pair  to be associated together.

![download (15)](C:\Users\jenny\Downloads\download (15).png)

- One advantage of this association is that the user can click on the label to make the cursor jump to the desired field.

#### Container syntax

- You can also use `label` tags as containers:

  - The "container" syntax eliminates the need for the `for` and `id` attributes, so it's easier to use. 

  - However, styling can be more difficult with the container syntax, and there are times when you must use a `for` attribute, so learn both variants.

    ```html
    <label>
      Phone
      <input type="text" name="phone">
    </label>
    ```

  - This syntax allows for the label to be on the right side of the input. For example

  ```html
  <label>
    <input type="checkbox" name="favorite" id="toggle" value="toggle">
     Add to my favorites
  </label>
  ```

  ![image-20230328130735726](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230328130735726.png)

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

# Input Element

- The **`<input>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element is used to create interactive controls for web-based forms in order to accept data from the user; a wide variety of types of input data and control widgets are available, depending on the device and [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent). The `<input>` element is one of the most powerful and complex in all of HTML due to the sheer number of combinations of input types and attributes.
- The most versatile and widely used form widget is the `input` element. 
  - Most controls are `input` elements. 
  - Some look identical in most browsers, such as the `text`, `email`, and `tel` types, but some look radically different: a `text` input looks nothing like a `submit` button or a `checkbox`.

- The example `input` elements shown on this page use Launch School's styling. If you copy the HTML to your browser, you will see results that use your browser's default styling instead.

## `Type` attribute

- How an `<input>` works varies considerably depending on the value of its [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#type) attribute, hence the different types are covered in their own separate reference pages. If this attribute is not specified, the default type adopted is `text`.

- Start with the `type` attribute when creating an `input` element. With the development of HTML5, the number of types available almost tripled. Not all see widespread use, but they all serve a purpose.

- The most common input types are as follows:

- [MDN Documentation on Input types](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)

### Type `text`

- The `text` type creates a simple text entry field. The user can enter any text desired in this control, though the developer should almost always validate the data. 
- `text`-type inputs ignore carriage returns, newlines, and other whitespace characters.
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
- Use the `value` attribute to give the value the form sends to the server when the user selects that checkbox. (optional)
  - `value="search"`
- Use the Boolean `checked` attribute to pre-select checkboxes. 
  - The Boolean `checked` attribute marks a checkbox as selected when supplied in the `input` tag. 
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

### Type `search`

- Notice the method is `get` because searches customarily don't update the server, so a GET request is more appropriate than a POST request.

```html
<form action="#" method="get">
  <fieldset>
    <label>
      Search for
      <input type="search" name="query" id="query">
    </label>
  </fieldset>
</form>
```

### Type `number`

- `input` elements of type `number` are used to let the user enter a number. They include build-in validation to reject non-numerical entries.
- offer suggested values in a list
  - You can provide a list of default options from which the user can select by specifying the [`list`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#list) attribute, which contains as its value the [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#id) of a `datalist` which in turn contains one `option` element per suggested value. Each `option`'s `value` is the corresponding suggested value for the number entry box.
- You can use the [`min`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#min) and [`max`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#max) attributes to constrain valid values to lower and upper bounds.

![image-20230328132447337](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230328132447337.png)

### Type `range` (slider)

- To create a slider in HTML, you can use the `<input>` element with the `type="range"` attribute. 
- The video uses an `<input type="range">` tag to implement the rating as a slider. However, browser support for sliders is feeble as of early 2018. Only Chrome supports ticks, and no widely-used browsers support labels. If you want these features, you must implement them some other way, probably with JavaScript or some messy HTML and CSS.

### Other Input Types

- There are other form controls, some of which we may ask you to use later in this lesson. 
- To see the complete list, see the [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) for the `<input>` tag. Study the list, but don't try to memorize them all - you can look them up as needed.

## Input's other Attributes

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

  - The `<br>` HTML element produces a line break in text (carriage-return). 


  ```html
  <form action="#" method="post">
    <fieldset>
      <label>
        <input type="radio" name="color" value="red">
        Red
      </label>
      <br> /*line break element*/
  
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

  

  - Technically, `radio` input types don't require the `value` attribute. If you omit the `value` attribute, the browser will send `NAME=on` to the server, where `NAME` is the value of the `name` property. We recommend always using the `value` attribute and use `name` to group related radio buttons together. If several radio buttons belong together, they should all have the same `name` attribute value.

  - Note that we added a `checked` attribute to the blue button to make that button the initial selection. If we want to leave all of the radio buttons unselected, but still require a selection, we can add a `required` attribute to each button.

- Button types, such as `submit`, `reset`, and the `button` type use the `value` attribute for the label that appears on the button:

  - Note that `type="button"` is out of favor; consider using the `<button>` element instead.

  ```html
  <form action="#" method="post">
    <fieldset>
      <input type="submit" value="Save">
    </fieldset>
  </form>
  ```

  

  ![value attribute with buttons](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-03.png)

  


### The `size` and `maxlength` Attributes

- These attributes apply to most text-based input types.

- The `size` attribute lets you control the size of an `input` element in characters. 
- `size` is an *approximation* for the width of the input box. The HTML5 standard requires that "the user agent should ensure that at least that many characters are visible"; in practice, you may see both more and fewer characters displayed.
- You can also specify the width with the CSS `width` property, but it does not support character measurements. 
  - The CSS `width` overrides the `size` attribute in CSS-enabled browsers.
  - `maxlength` is similar, but it limits the maximum length of input values; this value can be more or less than the `size` value.
  - HTML5 also supports a `minlength` attribute, but support for this attribute is inadequate at the time of this writing.

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

### The `placeholder` Attribute

- The `placeholder` attribute lets you display some text when a field is empty to help describe the expected input; it applies to most of the text-based `input` types. 
- Most browsers display `placeholder` text using a grayed-out format, and they erase the placeholder text as soon as you start typing:

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



- Don't use placeholders as substitute for labels.
  - You may see sites that use placeholders as a substitute for labels. Don't do this yourself, though, since it breaks screen readers. Labels and placeholders have different purposes, so use them appropriately. 
  - If you're forced to use placeholders, include the labels too, but hide them using CSS. This hack works well since most screen readers can read the hidden text.

### The `disabled` Attribute

- The `disabled` attribute lets you disable `input` elements; the browser renders disabled elements but won't let the user interact with them. The rendering looks different from enabled attributes, often by using a gray or lighter color. 
- `disabled` also turns on the `:disabled` CSS pseudo-class. (Non-disabled elements set the `:enabled` pseudo-class.)

- Most web applications handle the `disabled` attribute programmatically, either at the time the application generates the HTML or dynamically with JavaScript. You still need to know that `disabled` exists, though; you may have to write some HTML for a program that expects disabled inputs on the original form.

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

- The `required` attribute marks an `input` as required; the browser won't let you submit the form until the user completes all required fields. 
- `required` also turns on the `:required` CSS pseudo-class.

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

```css
input:required { /*selecting the required pseudoclass */
  background-color: yellow;
}
```



![reuqired attribute](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/input-attributes-07.png)



### The `autocomplete` Attribute

- You can use `autocomplete` on most `input` text-box elements. 
- The HTML attribute `autocomplete` is used to control whether a browser should automatically complete a form field with previously entered values. When the autocomplete attribute is used, the browser will suggest possible values that match the characters entered in the input field.
- Setting the attribute to `off` prevents the browser from storing data for later reuse by the browser's `autocomplete` features. 
- Autocomplete is common on smartphones and tablets but can be a nuisance. You can use the values `on` and `off` to explicitly turn `autocomplete` on or off on any given field.

```html
<input type="tel" value="123-456-7890" name="phone" autocomplete="off">
```

- The `autocomplete` option does not affect the `password` input type.

### The `autocapitalize` Attribute

- The `autocapitalize` attribute is used to control autocapitalization for the first letter of words or sentences. 
- Browsers that recognize this attribute default to the `sentences` value if not otherwise specified. 
- Use `autocapitalize="none"` when expecting input that you don't want to capitalize. You can also specify `autocapitalize="words"` or `autocapitalize="characters"`.

```html
<input type="text" name="full-name" autocapitalize="words">
```

- `autocapitalize` is not part of the HTML standard, but an attribute provided by some *mobile* browsers, such as iOS Safari and Google Chrome. It does not affect desktop and laptop systems. 
- The W3C HTML validator presently complains about `autocapitalize` since it is non-standard. If you want to use this attribute, you'll have to suffer that complaint.

### The `autocorrect` Attribute

- Some browsers support an `autocorrect` attribute that turns automatic spelling correction on and off. 
- You can disable this feature with `autocorrect="off"`; you should usually disable it with names, addresses, and other information where autocorrection would be a bother.

```html
<input type="text" name="full-name" autocorrect="off">
```

- `autocorrect` is non-standard HTML, but an attribute presently provided by iOS Mobile Safari. Since it is non-standard, the W3C HTML validator will complain about the `autocorrect` attribute. If you want to use this attribute, you'll need to get used to this complaint.

# Select and Textarea elements

- Now that you've got some input controls in your toolkit, the remaining inputs, `select` and `textarea`, will be quick to learn.

## The `textarea` Element

- `textarea` lets the user input multiple lines of text. 
- The **`<textarea>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a multi-line plain-text editing **control**, useful when you want to allow users to enter a sizeable amount of free-form text, for example a comment on a review or feedback form.

Unlike other input controls

- `textarea` elements retain carriage returns, newlines, and other whitespace characters, and use them to format the text into lines and paragraphs. 
- Since `textarea` preserves whitespace, its common practice to code the open and close tags on the same line unless the initial text content contains newlines.
- The value of the `textarea` doesn't use the `value` attribute to provide a value for the element. Instead, you need to contain the text between the opening and closing tags.

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

![image-20230327112945221](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327112945221.png)

### Rows and Cols attributes

- `textarea` uses the `rows` and `cols` attributes to control the height and width of the text box; `rows` is the height in lines, while `cols` is the width in characters. 
- As with the `size` attribute on some `input` tags, neither measurement is precise - the browser may choose to display more or fewer lines or columns than requested. 
  - The CSS `height` and `width` properties will also override these attributes. 
  - Furthermore, the `rows` value is not a maximum for the number of lines of input allowed; instead, it's the number of visible lines. The text box enables vertical scrolling when the content exceeds the `rows` count.

- Most browsers today let the user resize the `textarea` box by dragging and dropping a small triangle that appears in the lower-right corner of the text box.
  - You can disable this feature with the CSS `resize` property.

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

![image-20230327113000816](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113000816.png)

## The `select` Element

- The **`<select>`** [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element represents a **control** that provides a menu of options.
- `select` creates a drop-down list of options from which the user can select zero or more options. It has two possible child elements, the `option` and `optgroup` elements (we won't discuss `optgroup` in this course). 
- `select` uses the `name` attribute like other form elements, but it uses the `option` elements within it to describe the values shown to the user and sent to the server (which may be different).

### The `option` Element

- An `option` defines one of the choices a user can make in a `select` tag. A `select` element is useless without its `option` elements. 
  - The text contained inside the `<option>` element is what the user sees in the dropdown list.
  - Each `option` represents a possible value for the select, and they use the `value` attribute as the value sent to the server with the `select` element's name. 
  - If an `option` does not have a `value` attribute, the browser uses the text contained by the `option` element instead.

- `<select>` elements often have a placeholder `option` that says something like "Choose One" and has a `value` of an empty string, as well as a `disabled` and `selected` attribute. 
  - In HTML, the `disabled` and `selected` attributes are used with the `<select>` element to specify whether a particular option within a dropdown list should be disabled or preselected.
- By default, `select` lets the user choose precisely one option or leave the option unselected if it contains a `disabled selected` option as shown below.
- This option works something like the placeholder attribute on text boxes: the user can see some helpful text, but she cannot select that text.

![image-20230327113026532](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113026532.png)

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

- Show multiple options at once

  - If you add the `multiple` attribute, the user can select more than one option. On most browsers, a `select` with `multiple` appears as a (possibly scrolling) rectangle that displays several options. 
  - The user then Ctrl-clicks (Windows) or Cmd-clicks (Mac) to select the options she wants. You can also supply the size attribute to control the height of the selection box.

  ![image-20230327113053866](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113053866.png)

```html
<form action="#" method="post">
  <fieldset>
    <label>
      Choose Your Favorite Movies
      <select name="favorites" size="4" multiple >
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

# Other elements

## `button` tag

- `name` attribute: The name of the button, submitted as a pair with the button's `value` as part of the form data, when that button is used to submit the form.

```html
<button name="search">Search</button>
```

# Form Layouts

Nearly all websites or applications use forms in some capacity to collect information from the user. Knowing some of the standard styling techniques will help you create attractive and usable apps. You will see numerous different forms, but nearly all combine label and input control pairs that are horizontally or vertically oriented.

The following video walkthrough shows you how to work with both orientations, with emphasis on the easier-to-style top-to-bottom arrangement. It also demonstrates a practical use of the description list approach for form layout.

There are some minor discrepancies between the video and the rest of this page, but they are not significant. The most obvious change is that we use `fieldset` to draw a gray box around each example below, but the CSS also differs a bit.

## Video Notes

<video id="video_9c8825bd2f97_html5_api" class="vjs-tech" poster="https://launchschool.com/assets/tealeaf_markup/video_poster.jpg" preload="none" src="https://d3jtzah944tvom.cloudfront.net/videos/output/form_layout_47a8d7_s1712/form_layout_47a8d7_s1712.mp4" style="box-sizing: inherit; display: inline-block; top: 0px; left: 0px; width: 818.944px; height: 460.647px;"></video>

Play Video.

Download: [HD](https://d3jtzah944tvom.cloudfront.net/videos/output/form_layout_47a8d7_s1712/form_layout_47a8d7_s1712.mp4)|[Transcript](https://d3jtzah944tvom.cloudfront.net/videos/transcripts/form_layout_47a8d7_s1712/form_layout_47a8d7_s1712.sbv)

Duration: **28:32**

- `border-radius` for round edges.
- Whenever you modify border, you get a different style than browser default style.
- Designs usually make labels a fixed  take up the remaining width.
- Use definition list instead of div. 
  - As we get into more complicated form layouts such as form that captures form, name,address, inputs are styled to be different widths than rest of inputs. 
  - For example address, city state zip code side by side in one row.
- You can declare multiple classes for one element.
- [which browsers supports vender prefix](https://caniuse.com/)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Form Layouts</title>
  <style>
    body {
      font: normal 14 px Helvetica, Arial, Sans-serif;
    }
    dl {
      margin: 0;
      padding-bottom: 20px;
    }
    dt {
      display: inline-block;
      width: 10%;
      padding-right: 20px;
      vertical-align: middle;
      box-sizing: border-box;
    }
    dd {
      display: inline-block;
      width: 90%;
      margin: 0;
      padding-bottom: 20px;
    }
    input[type="text"]{
      width: 100%;
      height: 40px;
      padding: 0 8px;
      font: normal 14px Helvetica, Arial, sans-serif;
      border: 1px solid #cecece;
      border-radius: 4px;
      box-sizing: border-box;
    }
    input[type="text"] + input[type="text"] { /*adjacent sibling selector*/
      margin-top: 10px;
    }
    /* style select box */
    /* Make it look like the rest of the text input boxes */
    select {
      box-sizing: border-box;
      width: 100%;
      height: 40px;
      padding: 0 8px;
      -webkit-appearance: none;
      -moz-appearance: none;
      appearance: none; /* css default*/
      background: white;
      border: 1px solid #cecece;

    }
    dl.partial {
      display: inline-block;
      padding-right: 20px;
      box-sizing: border-box;
    }
    dl.city {
      width: 50%;
    }
    dl.state {
      width: 25%;
    }
    dl.zipcode {
      width: 25%;
      padding-right: 0;
    }

  </style>
</head>
<body>
  <form action="" method="post">
    <dl>
      <dt>
        <label for="name">Your Name</label>
      </dt><!--
      --><dd>
        <input type="text" name="name" id="name"/>
      </dd>
    </dl><!--
    --><dl>
      <dt>
        <label for="address">Address</label>
      </dt>
      <dd>
        <input type="text" name="address1" id="address1"/>
        <input type="text" name="address2" id="address2"/>
      </dd>
    </dl><!--
    --><dl class="city partial">
      <dt>
        <label for="city">City</label>
      </dt>
      <dd>
        <input type="text" name="city" id="city"/>
      </dd>
    </dl><!--
    --><dl class="state partial">
      <dt>
        <label for="state">State</label>
      </dt>
      <dd>
        <select id="state partial" name="state">
          <option>AK</option>
          <option>AL</option>
        </select>
      </dd>
    </dl><!--
    --><dl class="zip partial">
      <dt>
        <label for="zipcode">Zipcode</label>
      </dt>
      <dd>
        <input type="text" name="zipcode" id="zipcode" />
      </dd>
    </dl>
  </form>
</body>
</html>
```

## start with 2 field form

We'll start with a two-field form using the default side-by-side positioning for the label and input. Our purpose here isn't to show you how to position these items side by side, but to show the overall styling we'll use throughout this walkthrough. Starting from this CSS, we can focus first on the general styling, then worry about how to position the label and inputs.

```html
<form action="#" class="styled-form">
  <fieldset>
    <label for="text_field">Input Field</label>
    <input type="text" name="text_field" id="text_field"
           placeholder="this is the input area">

    <br> /*creates a line break */

    <label for="select_field">Select Field</label>
    <select name="select_field" id="select_field">
      <option>Choice 1</option>
      <option>Choice 2</option>
      <option>Choice 3</option>
    </select>
  </fieldset>
</form>
```

```css
/* Eliminate margins and padding on everything */
.styled-form * {
  margin: 0;
  padding: 0;
}

/* Grey box and default font for fieldsets */
.styled-form fieldset {
  background-color: #ececec;
  border: 2px solid #999;
  box-sizing: border-box;
  color: #4d4d4d;
  font-family:
    myriad-pro, "Helvetica Neue", Helvetica, Roboto,
    Arial, sans-serif;
  padding: 1rem;
}

/* Custom appearance for labels */
.styled-form label {
  font-weight: bold;
  line-height: 1.5rem;
}

/* Custom appearance for input and select fields */
.styled-form input[type="text"],
.styled-form select {
  border: 1px solid #06c;
  border-radius: 4px;
  box-sizing: border-box;
  font: normal 1rem Helvetica, Arial, sans-serif;
  height: 40px;
  padding: 5px 8px;
}

/* More customization for select lists */
.styled-form select {
  -moz-appearance: none;
  -webkit-appearance: none;
  appearance: none; /*turn off browser specific default apperance*/
  background-image:
    url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZlcnNpb249IjEuMSIgeD0iMTJweCIgeT0iMHB4IiB3aWR0aD0iMjRweCIgaGVpZ2h0PSIzcHgiIHZpZXdCb3g9IjAgMCA2IDMiIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDYgMyIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSI+PHBvbHlnb24gcG9pbnRzPSI1Ljk5MiwwIDIuOTkyLDMgLTAuMDA4LDAgIi8+PC9zdmc+");
  background-position: 100% center;
  background-repeat: no-repeat;
  padding-right: 1.5rem;
}
```

![image-20230327113220356](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113220356.png)

Take a few minutes to study these initial settings, comparing them against the example output. Most of this CSS should be familiar. However, there's some new material here:

## Basic css for forms

- The three `background-*` properties combine to provide the custom look for the `select` control.
- The `url("data:rest-of-url")` value on `background-image` loads an "**inline image**" that shows the tiny drop-down arrow in the select box rather than downloading it separately. 
  - You don't need to know how to make these inline images, but you should know how to use them. 
  - you will typically be given the `data:` URL that you can plug directly into the `url()` value.

- The `border-radius` property lets you apply rounded corners to any element with a border. 
  - You should be aware of this property; you'll need it again.

- The `appearance` property lets you turn off the browser-specific default appearance of a widget (the `select` in this case). 
  - You should know how to remove browser-specific styling from input controls; you'll need it again.


If you want, you can take a few minutes to look these up at MDN.

- At the time of this writing at the start of 2018, `appearance` is **experimental**. However, most browsers in current use support it with the `none` value provided that you use the vendor-specific names `-webkit-appearance` and `-moz-appearance`, e.g.:

```css
select {
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
}
```

- [Can I Use](https://caniuse.com/#feat=css-appearance) shows acceptance of the `none` value by around 95% of browsers now in use. Given the acceptance rate, this feature is unlikely to go away, but it remains experimental, so use it with caution.

Now that we've got the basic styling out of the way let's move on to styles that specifically apply to top-and-bottom and side-by-side positioning of the labels and inputs.

## top-and-bottom label/input

- Of the two orientations, top-and-bottom is easier to work with and typically more flexible. 
- Our first example shows how to use top-and-bottom label/input pairs:
- All we have to do is convert the label and input items to block elements. The `width` property makes them both take up all available room, though the label field doesn't show this visibly.

```html
<form action="#" class="styled-form top-to-bottom">
  <fieldset>
    <label for="text_field">Input Field</label>
    <input type="text" name="text_field" id="text_field"
           placeholder="this is the input area">
  <!--
    Delete this code
    <br>
    <label for="select_field">Select Field</label>
    <select name="select_field" id="select_field">
      <option>Choice 1</option>
      <option>Choice 2</option>
      <option>Choice 3</option>
    </select>
  -->
  </fieldset>
</form>
```

CSS for top-to-bottom 

```css
/* Add to end of file */
.top-to-bottom label,
.top-to-bottom input[type="text"] {
  display: block;
  width: 100%;
}
```

![image-20230327113250830](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113250830.png)

## side-by-side label/input

- In the next example, we'll place the labels and controls side by side:

```html
<form action="#" class="styled-form side-by-side">
  <fieldset>
    <label for="text_field">Input Field</label>
    <input type="text" name="text_field" id="text_field"
           placeholder="this is the input area">
  </fieldset>
</form>
```

Css for side-by-side

```css
/* Add to end of file */
.side-by-side label,
.side-by-side input[type="text"] {
  display: inline-block;
}

.side-by-side label {
  margin-right: 1rem;
  vertical-align: middle;
}

.side-by-side input[type="text"] {
  vertical-align: middle;
  width: 35%;
}
```

![image-20230327113311600](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113311600.png)

- Putting the label and input side by side is slightly harder, but not too hard. First, convert each element to `inline-block` to allow a side-by-side arrangement while providing widths and heights. If you use the default `inline` setting, the browser will ignore those dimensions. 
- Next, set the `width` of the `input` element, and vertically align the label/input pair.

What happens when we add another label/input pair to the form with this layout? Since types are `inline-block`, we may end up with multiple labels all in one row.

```html
<form action="#" class="styled-form side-by-side">
  <fieldset>
    <label for="text_field">Input Field</label>
    <input type="text" name="text_field" id="text_field"
           placeholder="this is the input area">

    <label for="another_field">Another Field</label>
    <input type="text" name="another_field" id="another_field"
            placeholder="this is another input area">
  </fieldset>
</form>
```

![image-20230327113329697](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113329697.png)

#### Issue: element wrapping

- If your browser window is too narrow, the elements may wrap, leaving the label on the right side of one line and the input on the left side of the next. To see this behavior in action, expand your browser window so that everything fits on one line, then gradually reduce the width as far as it will go. The resulting arrangement is ugly. 

#### Use `div` for blocks and vertical alignment

- Solution: Developers wrap the label and input pairs in a `block` element, such as a new `div`. The new element ensures that each pair remains together. However it introduces a new problem. 

```html
<form action="#" class="styled-form side-by-side">
  <fieldset>
    <div class="keep-together">
      <label for="text_field">Input Field</label>
      <input type="text" name="text_field" id="text_field"
             placeholder="this is the input area">
    </div>

    <div class="keep-together">
      <label for="another_field">Another Field</label>
      <input type="text" name="another_field" id="another_field"
             placeholder="this is another input area">
    </div>
  </fieldset>
</form>
```

![image-20230327113348321](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113348321.png)

#### Issue: inputs don't align veritically

- We could style the `div`s to provide some spacing between them, but we already see another issue: the labels have different widths, so the inputs don't align vertically. We could rearrange the HTML to put the `label` elements in one column and the controls in another, but that leads to other problems with readability, maintainability, and alignment.

#### Description list for vertical alignment

- Solution: What we can do instead is use a description list to mark up our forms, which may seem strange. 
  - However, think about the semantic meaning behind a description list: the terms are your labels, and they, in turn, identify controls for the user. Thus, you can wrap form controls in description list elements. 
  - They also provide additional tags that you can style without changing your HTML:

```html
<form action="#" class="styled-form side-by-side">
  <fieldset>
    <dl>
      <dt><label for="text_field">Input Field</label></dt>
      <dd><input type="text" id="text_field" name="text_field"></dd>

      <dt><label for="another_field">Another Field</label></dt>
      <dd><input type="text" id="another_field" name="another_field"></dd>
    </dl>
  </fieldset>
</form>
```

```css
.side-by-side input[type="text"] {
  width: 100%; /* Replaces 35% */
}

/* Add to end of file */
.side-by-side dl {
  font-size: 0;
}

.side-by-side dt,
.side-by-side dd {
  box-sizing: border-box;
  display: inline-block;
  font-size: 1rem;
  vertical-align: middle;
}

.side-by-side dt {
  padding-right: 1rem;
  width: 25%;
}

.side-by-side dd {
  width: 75%;
}
```

![image-20230327113403548](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113403548.png)

## Divide label/input pairs into separate lists

You get even more flexibility if you divide the label/input pairs into separate lists so that each belongs to a different container. You can also style several related pairs together on one horizontal line, such as a city, state, and Zip Code. All you have to do is add appropriate classes to the `dl` elements and then style them.

```html
<form action="#" class="styled-form top-to-bottom">
  <fieldset>
    <dl>
      <dt><label for="name">Name</label></dt>
      <dd><input type="text" id="name"></dd>
    </dl>

    <dl class="address">
      <dt><label for="address1">Address</label></dt>
      <dd>
        <input type="text" id="address1">
        <input type="text" id="address2">
      </dd>
    </dl>

    <dl class="city partial">
      <dt><label for="city">City</label></dt>
      <dd><input type="text" id="city"></dd>
    </dl>

    <dl class="state partial">
      <dt><label for="state">State</label></dt>
      <dd>
        <select id="state">
          <option>AK</option>
          <option>AL</option>
          <!-- You can download the complete list of states at -->
          <!-- https://launchschool.com/gists/2424a869 -->
        </select>
      </dd>
    </dl>

    <dl class="zipcode partial">
      <dt><label for="zipcode">Zip</label></dt>
      <dd><input type="text" id="zipcode"></dd>
    </dl>

  </fieldset>
</form>
```

```css
/* Add to end of file */
.styled-form label {
  padding-top: 0.3333rem;
}

.top-to-bottom dl.partial {
  box-sizing: border-box;
  display: inline-block;
  padding-right: 1rem;
  vertical-align: top;
}

.top-to-bottom dl.address {
  width: 100%;
}

.top-to-bottom dl.city {
  width: 50%;
}

.top-to-bottom dl.state {
  width: 25%;
}

.top-to-bottom dl.zipcode {
  padding-right: 0;
  width: 25%;
}

.top-to-bottom dl dd {
  width: auto;
}

.top-to-bottom fieldset,
.top-to-bottom dl,
.top-to-bottom dl dd,
.top-to-bottom dl dt {
  font-size: 0;
}

.top-to-bottom dl label,
.top-to-bottom dl input[type="text"] {
  font-size: 1rem;
}

.top-to-bottom select {
  width: 100%;
}
```

![image-20230327113426271](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230327113426271.png)

- Our code here uses one `dl` per label/input pair. This simple change lets us treat each `dl` separately. However, this variation makes it harder to produce a horizontal layout where each label is the same size.

- The `partial` class provides our `dl` with the basic `inline-block` styles, and the class name for each input type provides the width and any other overriding properties like the padding on the zip code `dl`.

- One last note on this code: typing that list of states would be tedious. Instead, you can search the Web for someone else's HTML and copy it (be sure it is complete and correct, though), or you can use [ours](https://launchschool.com/gists/2424a869). Feel free to download it and add it to your code.

- State abbreviations

```html
<select name="state">
  <option>AK</option>
  <option>AL</option>
  <option>AR</option>
  <option>AZ</option>
  <option>CA</option>
  <option>CO</option>
  <option>CT</option>
  <option>DC</option>
  <option>DE</option>
  <option>FL</option>
  <option>GA</option>
  <option>HI</option>
  <option>IA</option>
  <option>ID</option>
  <option>IL</option>
  <option>IN</option>
  <option>KS</option>
  <option>KY</option>
  <option>LA</option>
  <option>MA</option>
  <option>MD</option>
  <option>ME</option>
  <option>MI</option>
  <option>MN</option>
  <option>MO</option>
  <option>MS</option>
  <option>MT</option>
  <option>NC</option>
  <option>ND</option>
  <option>NE</option>
  <option>NH</option>
  <option>NJ</option>
  <option>NM</option>
  <option>NV</option>
  <option>NY</option>
  <option>OH</option>
  <option>OK</option>
  <option>OR</option>
  <option>PA</option>
  <option>RI</option>
  <option>SC</option>
  <option>SD</option>
  <option>TN</option>
  <option>TX</option>
  <option>UT</option>
  <option>VA</option>
  <option>VT</option>
  <option>WA</option>
  <option>WI</option>
  <option>WV</option>
  <option>WY</option>
</select>
```

- Keeping track of bits of code that you will probably reuse, such as the list of states, is a good habit. Good developers are lazy developers. Doing the work once and then reusing your work will pay off in speed and efficiency.

- Now that you understand how to create form layouts, it's time to put them into practice.

# practice problem examples

## 1-6

![image-20230328134051414](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230328134051414.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Practice Problem 1-6</title>
</head>
<body>
  <form action="#" method="post">
    <fieldset>
      <dl>
        <!--user's first name-->
        <dt><label for="firstname">First Name</label></dt>
        <dd>
          <input type="text" id="firstname" name="firstname" required>
        </dd>

        <!--user's last name-->
        <dt><label for="lastname">Last Name</label></dt>
        <dd><input type="text" id="lastname" name="lastname" required></dd>

        <!--email address-->
        <dt><label for="email">Email Address</label></dt>
        <dd><input type="text" id="email" name="email" autocomplete="off" 
          autocorrect="off" autocapitalize="none" required>
        </dd>
        
        <!-- user's phone number-->
        <dt><label for="phone"> Phone Number</label></dt>
        <dd><input type="tel" id="phone" name="phone" 
          placeholder="###=###-####" required>
        </dd>

        <!--Select box for phone type-->
        <dt><label for="phonetype">Phone Type</label></dt>
        <dd>
          <select name="phonetype" id="phonetype">
            <option value="phonetype" disabled>Choose one</option>
            <option value="home" selected>Home</option>
            <option value="business">Business</option>
            <option value="mobile">Mobile</option>
          </select>
        </dd>

        <!-- message box-->
        <dt><label for="messagebox">Message</label></dt>
        <dd><textarea name="messagebox" rows="6" cols="80"
          placeholder="Type your message here"></textarea>
        </dd>
      </dl>
      <input type="submit" value="send">
    </fieldset>
  </form>
</body>
</html>
```

## 7

![image-20230328134227350](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230328134227350.png)

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Practice Problems 7</title>
  <style>
    fieldset {
      display: inline-block;
    }
  </style>
</head>
<body>
  <form action="#" method="get">
    <fieldset>
      <label for="search">Search for</label>
      <input type="search" name="query" id="query">

      <input type="radio" name="filter" value="TV" required>
      <label for="TV">TV</label>

      <input type="radio" name="filter" value="movies" required>
      <label for="movies">Movies</label>

      <input type="radio" name="filter" value="music" required>
      <label for="Music">Music</label>

      <input type="submit" value="Rate movie">
    </fieldset>
  </form>
</body>
</html>
```



## 8

<img src="C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230328134130055.png" alt="image-20230328134130055" style="zoom:50%;" />

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Practice Problem 8</title>
</head>
<body>
  <form action="#" method="post">
    <fieldset>
      <dl>
        <dt><label for="movie">Movie</label></dt>
        <dd>
          <select name="movie" multiple size="4">
            <option value="Looper">Looper</option>
            <option value="Frozen">Frozen</option>
            <option value="Tommy Boy">Tommy Boy</option>
            <option value="Alien" selected>Alien</option>
          </select>
        </dd>
        <dt><label for="rating">Rating</label></dt>
        <dd>
          <input type="number" name="rating" id="rating" min="1" max="5">
        </dd>
      </dl>
      <div>
        <label>
          <input type="checkbox" name="favorite" checked>
          Add to my favorites
        </label>
      </div>
      <button name="submit">Rate movie</button>
    </fieldset>
  </form>
</body>
</html>
```

# 12

![image-20230328142407258](C:\Users\jenny\AppData\Roaming\Typora\typora-user-images\image-20230328142407258.png)

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>11</title>
  <style>
    ul {
      list-style: none;
    }
  </style>
</head>

<body>
  <!--form that filters news articles by a single category and any number of selected tag words-->
  <form action="#" method="get"> <!--get method allows user to save and share filtered URL-->
    <h1>Categories</h1>
    <fieldset>
      <!--radio buttons for news category-->
      <!--Categories: Core, Plugins and Libraries, Conventions, Reviews, Opinion, People-->
      <dl>
        <dt><label for="category">News Category</label></dt>
        <dd>
          <select name="category" id="category">
            <option value="core">Core</option>
            <option value="plugs-libraries">Plugs and Libraries</option>
            <option value="conventions">Conventions</option>
            <option value="reviews">Reviews</option>
            <option value="opinion">Opinion</option>
            <option value="people">People</option>
          </select>
        </dd>
      </dl>

      <h1>Tags</h1>
      <dl>
        <dt><label for="tags">Tags</label></dt>
        <dd>
          <select name="tags" id="tags" size="7" multiple>
            <option value="HTML">HTML</option>
            <option value="CSS">CSS</option>
            <option value="Javascript">Javascript</option>
            <option value="Ruby">Ruby</option>
            <option value="Rails">Rails</option>
            <option value="Python">Python</option>
            <option value="Django">Django</option>
          </select>
        </dd>
      </dl>
  
      <input type="submit" value="Filter">
      <input type="reset">
    </fieldset>
  </form>
</body>
</html>
```

# Practice Problems: Forms

Remember: the videos may differ from the written instructions and the completed example. The written instructions take precedence.

The videos that accompany this problem set show the `action` attribute defined with an empty string, e.g., `action=""`. You can use `action="#"` instead if you want your code to pass W3C validation.

1. Create a contact form that collects the user's first name, last name, email address, and phone number. Be sure to require all inputs and to use appropriate input types and labels. Prevent Chrome and iOS Safari from doing any auto-actions (e.g., autocomplete and autocorrect) on the email input.

   For this problem, don't use a definition list to organize your form. We'll do that in the next question.

   Solution

2. Convert the HTML from the previous problem to use a single description list to pair each label and input control.

   Solution

   Walkthrough

3. Add a `select` box to your solution from the previous problem that lets the user select a phone type given the options "home," "business," and "mobile." Make sure you pre-select the "home" option.

   Solution

   Walkthrough

4. Add a message box to your solution from the previous problem that lets the user enter an optional multi-line message. The message box should allow around six lines of text of up to about 80-characters each.

   Solution

5. Add some placeholder text to the phone number input that shows the format you expect to see. (For instance, `###-###-####`.)

   Solution

6. Add some placeholder text to the message box, e.g., `Type your message here.`.

   Solution

7. Create a search form with three items:

   - a field for the search term,
   - a group of three controls to select precisely one from the list "TV," "Movies," and "Music,"
   - a Search button (use the `button` tag, not the obsolete `<input type="button">` tag).

   The form doesn't have to do anything when submitted. Don't use a description list for this problem.

   

   ![Search form](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/f2.jpg)

   

   Solution

   Walkthrough

8. Create a review form with a single control that lets the user select from the movies "Looper," "Frozen," and "Tommy Boy," then add a numeric rating field that the user can set to any integer from 1-5. Next, add a toggle control to add the movie to your favorites list. Enable the toggle control by default. Lastly, add a submit button.

   

   ![Movie review form](https://d3jtzah944tvom.cloudfront.net/202/images/lesson_5/form-range-01.png)

   

   Solution

   Walkthrough

9. Add the movie "Alien" to the end of the drop-down list and make it the initial selection when displaying the form.

   Solution

10. Update your solution to show all four possible choices at once.

    Solution

11. Create a form that filters news articles by a single category and any number of selected tag words. Use radio buttons for the news category and checkboxes for the tags. Make sure you use the `get` method to allow the user to save and share the filtered URL.

    - **Categories**: Core, Plugins and Libraries, Conventions, Reviews, Opinion, People
    - **Tags**: HTML, CSS, Javascript, Ruby, Rails, Python, Django

    For this problem, use the container-style `label` tag (without the `for` attribute). Use an unordered list instead of a description list for both the categories and tags.

    Solution

    Walkthrough

12. Convert the radios and checkboxes in the filter form to `select` lists. Let the user select any number of tags, and ensure the selection box is large enough that she can see several choices at once. Use description lists to organize the form elements.

    Solution

    Walkthrough

13. Provide the user with a way to reset the filter form.

    Solution