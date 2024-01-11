
## HTML boilerplate

Every HTML file starts with a:
`<!DOCTYPE html>` declaration, and 
`<html></html>` tags.
```html
```html 
<!DOCTYPE html> <!-- declaration -->
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta device="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <!-- Body -->
</body>
</html>
```


## Heading & paragraph

`<h1>` to `<h6>` can be used for headings.

```html
<section>
	<h1>Heading 1</h1>
	<h2>Heading 2</h2>
	<p>This is a paragraph</p>
</section>
```

- Different parts of the web page can be grouped into different `<section></section>` tags.
## Link and image

HTML Link:
```html
```<a href="src/to/page" target="_blank">
```
`target="_blank"` makes the link open in a new tab.

```html
<section>
	<a href="https://www.google.com" target="_blank">Google search</a>
	<figure>
		<img src="/link/to/image" alt="alternate text"> <!-- self closing tag-->
		<figcaption>
			<strong>Caption</strong> to the <em>image</em>
		</figcaption>
	</figure>
</section>
```
- Image content can be wrapped inside `<figure></figure>` tags.
- `<figcaption></figcaption>` tag can be used to add caption to the image.

## HTML Lists
```html
<section><!--Unordered List-->
	<ul> 
		<li>item 1</li>
		<li>item 2</li>
	</ul> 
	<ol></ol> <!--Ordered list-->
</section>
```


