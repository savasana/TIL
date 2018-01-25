# form

> Form is a component of a Web page that has form controls (text fields, buttons, checkboxes, range controls, or color pickers)

- Any form starts with a `<form>` element, inside which are placed the contols.
- Most controls are represented by the `<input>` element
- `<label>` element is used to label a control
- To group a batch of controls together, you can use the `<fieldset>`element
- Title of a group is given by the `<legend>` element


```html
<form>
  <div><label>Customer name: <input type=text>firstname lastname</label></div>
</form>
```

---


### `<form>` element

> The `<form>` element represents a collection of form-associated elements(button, fieldset, input, label, ..)

 
`<form action="" method="get|post|action">`




### `<label>` element

> a caption in a user interface. The caption can be associated with a specific form contorl, known as the label element's labeled control, eighter using the `for` attribute, or by putting the form control inside the `<label>` element itself


```html
<label for="name"></label>
<input type="text" id="name">
```

```html
<label>
	<input type="text">
</label>

```

---

### `<input>`
create interactive controls for web-based forms

#### input types
- type = text
- type = number
- type = color
- type = checkbox
- type = radio
- type = date
- type = file
- type = month
- type = password
- type = range
- type = time
- type = email
- type = image
- type = range
- type = reset
- type = search
- type = submit
- type = tel



#### input attributes

`<input type="text" autocomplete="off">`

- type
- autocomplete : off | on | name | email | username 
- maxlength | minlength
- placeholder
- autofocus
- checked
- disabled
- required

---

### `<select>`

```html
<!-- automatically select value1-->
<select name = "text">
	<option value="value1" selected>value1</option>
	<option value="value2">value1</option>
	<option value="value3">value1</option>
</select>

```


### `<option>`
define an item contained in a `<select>`, `<optgroup>` or <datalist>
`<option>` can represent menu items in popups and other lists of items in an html document.

---

### `<datalist>`
contains a set of `<option>` elements that represent the values available for other controls.

```html
<label>choose a browser list:
<input list="browsers" name="myBrowser" />
</label>
<datalist id="browsers">
	<option value="Chrome">
	<option value="FireFox">
	<option value="Safari">
	<option value="Opera">
</datalist>

```

---

### `<button>`

> represents a clickable button, which can be used in forms, or anywhere in a document that needs simple, standard button functionality. 


By default, HTML buttons are typically presented in a style similar to that of the host platform the user agent is running on, but you can change the appearance of the button using CSS.



#### types of `<button>`

- submit : submits the form data to the server
- reset : resets all the controls to their initial values
- button : has no default behavior. client-side scripts associated with the element’s events.



---

There is no particular significance to the way some of the attributes have their **values quoted and others don’t.** The HTML syntax allows a variety of equally valid ways to specify attributes.

---

### links

[W3C 4.10. Forms](https://www.w3.org/TR/2017/REC-html52-20171214/sec-forms.html#sec-forms)
[<input> | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
[<button> | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)