## how to make "skip to content"

### what is a skip links?
These are invisible links that let you skip a group of navigation items and go straight to the main content area.(for screenreader and tab keyboard)


### Don't use `display:none`
sreenreader wil ignore the element if you set the display to none.


### how to use it?
create skip-to-content link element and make it invisible? but accessible.
```html
<div class="skip-nav">
 <a href="#content" class="a11y">skip to content</a>
</div>
```

```css
.skip-nav:not(:focus) {
  /* Workaround for falsely pronounced, smushed text */
  white-space: nowrap;
  /* Set it to the smallest posscible size (some screen readers ignore elements with zero height and width) */
  width: 1px;
  height: 1px;
  /* Hide overflowing content after resizing */
  overflow: hidden;
  /* Reset any property that may change the elements size */
  border: 0;
  padding: 0;
  /* Clipping defines what part of an element should be displayed. */
  /* Deprecated clip property for older browsers */
  clip: rect(0 0 0 0);
  /* clip-path for newer browsers. inset(50%) defines an inset rectangle that makes the content disappear. */
  clip-path: inset(50%); 
  /* It seems like at the moment nobody is quite sure why margin: -1px is there. On top of that it seems to cause issues (see: https://github.com/h5bp/html5-boilerplate/issues/1985). */
  margin: -1px;
}

```

There's also other way to implement it.
[a11ymatters:skip link](http://www.a11ymatters.com/pattern/skip-link/)




