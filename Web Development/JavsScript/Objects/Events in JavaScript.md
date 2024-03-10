- Events are things that happen in the system.
- The system fires some kind of signal when an event occurs and provides a mechanism for taking automatic action.
For eg. 
	- a user selects, clicks or hovers over a certain element.
	- the user presses some key on the keyboard.
	- the user resizes or closes the browser window.
	- a web page finishes loading.
	- a form is submitted.
	- a video is played, paused or ends.
	- an error occurs.

- To react to an event, you attach an **event handler** to it.
- An event handler is a block of code that executes when an event occurs. Writing such a block of code is known as **registering an event handler**.
- They are also sometimes caller **event listeners**.
- Listener listens for the event and the handler is the code that is run in response to that event.

> Web events are not a part of the core JS language. They are defined as part of the APIs built into the browser.

#### Example: handling a click event.
```html
<button>Change color</button>
```

```js
const btn = document.querySelector('button');
```

	dafdsf