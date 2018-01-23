## reset


[meyer's reset](http://meyerweb.com/eric/tools/css/reset/)
[normalize.css](https://github.com/necolas/normalize.css/)
Normalize.css focuses not on using a hard reset for all common elements, but instead on setting common styles for these elements. It requires a stronger understanding of CSS, as well as awareness of what you’d like your styles to be.


- Correct the line height in all browsers.
- Prevent adjustments of font size after orientation changes in IE on Windows Phone and in iOS.
- Remove the margin in all browsers (opinionated).

mayer's reset

```css 

 html, body, div, span, applet, object, iframe,
 h1, h2, h3, h4, h5, h6, p, blockquote, pre,
 a, abbr, acronym, address, big, cite, code,
 del, dfn, em, img, ins, kbd, q, s, samp,
 small, strike, strong, sub, sup, tt, var,
 b, u, i, center,
 dl, dt, dd, ol, ul, li,
 fieldset, form, label, legend,
 table, caption, tbody, tfoot, thead, tr, th, td,
 article, aside, canvas, details, embed, 
 figure, figcaption, footer, header, hgroup, 
 menu, nav, output, ruby, section, summary,
 time, mark, audio, video {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
 }
 /* HTML5 display-role reset for older browsers */
 article, aside, details, figcaption, figure, 
 footer, header, hgroup, menu, nav, section {
  display: block;
 }
 body {
  line-height: 1;
 }
 ol, ul {
  list-style: none;
 }
 blockquote, q {
  quotes: none;
 }
 blockquote:before, blockquote:after,
 q:before, q:after {
  content: '';
  content: none;
 }
 table {
  border-collapse: collapse;
  border-spacing: 0;
 }

```
---

