
## Semantic Markups

Semantics is the use of HTML tags for their meaning rather than their aesthetics. It’s also useful for making sure that your web page is easily understood by both search engine machines and people browsing without stylesheets, such as the viably impaired.

**Easy way to make sure that your markup has proper structure is to write it without a stylesheet.**


### Benefits

- more accessibility
- good for search engine optimization.
- easier to style if it is marked up correctly.

---

### Main
> `<main>` represents the main content of the `body` of a document. Helpful when you design a single-page web.

### Article

> `<article>`  
> element represents a **self-contained composition** in a document, page, application, or site. Examples include: a forum post, a magazine or newspaper article, or a blog entry.


### Section

> `<section>` represents a standalone section - which doesn’t have a more specific semantic element to represent it. Such as chapters, or just areas that are broken up visually.


### Aside
> Content related to the main content but in an area like a sidebar. (side navigation should use the `<nav>`



---

### examples


```html
<section> | <article>
  <h1>Heading</h1>
  <p>Bunch of awesome content</p>
</section> | </article>
```


```html
<section>
  <h1>Harry Potter</h1>
   <section>
		  <h2>Meet Harry</h2>
		  <p>Bunch of awesome content</p>
	 </section>

	 <section>
		 <h2>Meet Ron</h2>
		 <p>Bunch of awesome content</p>
	 </section>
</section>
```



> Elements are meant to be meaningful but also flexible in their usage. They don’t have any inherent styles of their own and can be used in any combination that makes sense to you.
> >
> from [thoughtbot : Writing Semantic Markup](https://robots.thoughtbot.com/writing-semantic-markup)




