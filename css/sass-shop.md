# Sass

### Start Sass with node

```
//Set the location folders
$ node-sass src/sass --output css/css
```

<br>

```
//comepile sass
$ node-sass --output-style compact src --output css/
```
> output style types - compact | nested | expanded | compressed 

<br>

```
//let sass watch the changes and update automatically
$ node-sass --watch src/ --output css/
```

---

### Start Sass with Ruby

```
//running sass
$ sass source_dir output_dir

//update
$ sass --update source.scss:output.css

//watching 
$ sass --watch src_dir/sass:public_dir/stylesheets

```



---

### Repetition



#### Color

```scss

$oledWhite : #fefefe;
$logoPurple: #531946;

.header {
	background-color: $oledWhite;
}

.header a {
	color: $logoPurple;
}
```


#### Border Radius + Padding

`@mixin some-name` declare certain style setting <br>
`@include some-name` add this style setting


```scss
@mixin rounded-box {
  border-radius: 5px;
  padding: 5px 20px;
}

.header {
  @include rounded-box;
  // ...
}

.footer {
  @include rounded-box;
  // ...
}

```


#### Nesting

**General Recommendation: no more than 3 levels deep**

`&:` parent selector

```scss
.header {
	a {
	//something something

		&:hover { // ...}
	}
}

```

<br>

Can follow other selectors. This will override the parent element’s styles when it exists within the preceding selector.

```scss
a {
	.footer & {
		text-decoration: none;
		span {
			opacity: .5;
			// css : .footer a span //
		}
	}
	span {
		.navigation & {
			display: block;
			// css : .navigation a span //
		}
	}
}

```

<br>

`&` selector can be combined with strings. perfect for BEM, child elements, states, and modifications.

```scss
.module {
	&__child {
		margin-bottom: 1em;
		// css : .module__child
	}
	&--modifier {
		display: flex;
		//css :  .module--modifier
	}
}

```


<br>

nesting properties

```scss
a {
	border: {
		color: blue;	//css : border-color: blue;
		style: solid;	//css : border-style: solid;
		width: 2px;		// css : border-width: 2px;
	}
}
```


---

### links

[Getting Sassy with CSS ~ Julie Cameron](http://www.sassshop.com/#/3/1)

