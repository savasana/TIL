# form

> Form is a component of a Web page that has form controls (text fields, buttons, checkboxes, range controls, or color pickers)


```html
<form>
	<fieldset>
		<legend>login</legend>
		<label>
			<input type="submit">
		</label>
	</fieldset>
</form>
```

`<fieldset>` group several controls as well as labels.
`<legend>` is like title of the fieldset
`<label>`  represents a caption for an item 



### `<form></form>`

`<form action="test" method="get|post|action">`



### `<legend></legend>`

caption for the content of its parent `<fieldset>`



### `<label></label>`

`for = "id-name"`으로 연결 하거나 감싸서 연결

```html
<label for="user-id"></label>
<input type="text" id="user-id">
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
- text
- number
- color
- checkbox
- radio
- date
- file
- month
- password
- range
- time
- email
- image
- range
- reset
- search
- submit
- tel



#### input attributes

`<input type="text" autocomplete="off">`

- type
- autocomplete : off | on | name | email | username 
- maxlength | minlength
- placeholder
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
represents a clickable button, which can be used in forms, or anywhere in a document that needs simple, standard button functionality. By default, HTML buttons are typically presented in a style similar to that of the host platform the user agent is running on, but you can change the appearance of the button using CSS.

#### types of `<button>`
- submit : submits the form data to the server
- reset : resets all the controls to their initial values
- button : has no default behavior. client-side scripts associated with the element’s events.


---
### links

[W3C 4.10. Forms](https://www.w3.org/TR/2017/REC-html52-20171214/sec-forms.html#sec-forms)
[<input> | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
[<button> | MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)