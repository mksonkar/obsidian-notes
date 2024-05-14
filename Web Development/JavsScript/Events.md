- Events are things that happen in the system.
- The system fires a signal of some kind when an event occurs, and provides a mechanism to automatically take some action when the event occurs.

Examples of events:
- the user selects, clicks or hovers over an element.
- the user presses a key on keyboard.
- the user resizes or closes a browser window.
- a web page finishes loading.
- a form is submitted.
- a video is played, paused, or ends.
- an error occurs.

### Event handler
To react to an event, you attach a **event handler** to it.

**Registering an event handler** is adding an event handling code to an event.

Event handlers are sometimes called as **event listeners**.
they can be used interchangeably but strictly speaking, event listener listens for the event happening and event handler is the code that runs in response to the event.

### Example: handling a click event
```html
<button>Change color</button>
```

```js
const btn = document.querySelector("button");

function random(number) {
	return Math.floor(Math.random() * (number + 1));
}

btn.addEventListener("click", () => {
	const rndCol = `rgb(${random(255)} ${random(255)} ${random(255)})`;
	document.body.style.backgroundColor = rndCol;
});
```

Besides `click` some other commonly used events are:
- `dbclick`
- `mouseover` and `mouseout`
- `keydown`
- `focus` and `blur`
- `play` 

Instead of using arrow function, you can keep the function separate and call the event listener as such:
```js
btn.addEventListener('mouseover', changeBgColor);
```
> ***Remember***: here we only write function name and don't call it. 
> If you call the function, then it will execute once immediately and the listener won't work.

### Remove listeners
```js
btn.removeEventListener('click', changeBgColor);
```

**Event handlers can also be removed by passing an `AbortSignal` to `addEventListener()` and then later calling `abort()` on the controller owning the `AbortSignal`.**
```js
const controller = new AbortController();

btn.addEventListener('click', 
	() => {
	  const rndCol = `rgb(${random(255)} rgb(${random(255)} rgb(${random(255)}`;
	  document.body.style.backgroundColor = rndCol;

	},
	{ signal: controller.signal } // pass an abort signal to this handler (3rd arg of listener function)				
);
```
The event handler created by the above code and be removed anytime by calling the abort() function.
```js
controller.abort();
```

Now one question may arise.
>Why would you need to clear an event handler?

- For small programs, cleaning up old, unused event handlers isn't necessary, but for larger, complex programs, it can improve efficiency.

- Also, with the ability to remove event handlers, you can have the same button performing different actions in different circumstances.

### Event handler properties
Objects such as buttons that can fire events, also have properties such as `onclick` and others starting with `on_` 
```js
btn = document.querySelector("button");

btn.onclick = () => {
	...
}
```
> **Imp info**: You can only add one event handler property to an element. 
> Adding more than one will overwrite the previous ones.

>But with `addEventListener()` you can add multiple event handlers on the same element. 
This will work, 
```js
element.addEventListener("click", function1);
element.addEventListener("click", function2);
```
only 2nd onclick will work as it replaces the first.
```js
element.onclick = function1;
element.onclick = function2;
```

#### Inline event handlers (Don't use them)
```html
<button onclick="bgChange()">Press me</button>
```
```js
function bgChange() {
  const rndCol = `rgb(${random(255)} ${random(255)} ${random(255)})`;
  document.body.style.backgroundColor = rndCol;
}
```
This is the earliest method of adding event handlers as HTML attributes.

You shouldn't use them anymore as:
- mixing up HTML and JS code makes it hard to read and maintain.
- keeping JS as a separate file helps in debugging and maintaining the code.

> Never use HTML event handler attributes - they are outdated, and using them is a bad practice.

### Adding event listeners to multiple elements at once
```js
const buttons = document.querySelectorAll("button");

for (const button of buttons) {
	button.addEventListener('click', () => bgChange);
}
```

### Event Objects
You can pass an event object inside an event handler function.
It is usually named as `e/evt/event`.
```js
btn.addEventListener('click', (e) => {
	e.target.style.backgroundColor = rndCol;
	console.log(e);
})
```
`e.target` **the target property of an event object** 
***always* refers to the element on which the event occurs.**

Here in the above example it refers to the button so it will change the button's background color.

```js
textBox.addEventListener("keydown", (event) => {
	output.textContent = `You pressed "${event.key}".`;
});
```
`keydown` event has an event object `KeyboardEvent` which has a standard set of methods and properties like `event.key` which returns the key pressed.

### Preventing default behaviour e.preventDefault()
There are some situations when you want to prevent the default behaviour of an event.
for eg. prevent form submitting if user hasn't filled all data.
```html 
<form>
  <div>
    <label for="fname">First name: </label>
    <input id="fname" type="text" />
  </div>
  <div>
    <label for="lname">Last name: </label>
    <input id="lname" type="text" />
  </div>
  <div>
    <input id="submit" type="submit" />
  </div>
</form>
<p></p>
```
```js
const form = document.querySelector("form");
const fname = document.getElementById("fname");
const lname = document.getElementById("lname");
const para = document.querySelector("p");

form.addEventListener("submit", (e) => {
  if (fname.value === "" || lname.value === "") {
    e.preventDefault();
    para.textContent = "You need to fill in both names!";
  }
});
```

### Event bubbling
```html
<body>
  <div id="container">
    <button>Click me!</button>
  </div>
  <pre id="output"></pre>
</body>
```
```js
const output = document.querySelector("#output");
function handleClick(e) {
  output.textContent += `You clicked on a ${e.currentTarget.tagName} element\n`;
}

const container = document.querySelector("#container");
const button = document.querySelector("button");

document.body.addEventListener("click", handleClick);
container.addEventListener("click", handleClick);
button.addEventListener("click", handleClick);
```

here we added click event listener to the button, its parent div and the body.
When the button is clicked, all three events are triggered, starting from the button, to its parent div, and then the body.

This is called event bubbling.
event **bubbles up** from the innermost element that was clicked.

This behaviour can be useful but sometimes can cause unexpected problems.

for ex.
- When user clicks display video button, it shows a box containing a video.
- when user clicks on video, it starts playing.
- when user clicks anywhere on the box, outside the video, the box disappears.

```html
<button>Display video</button>

<div class="hidden">
  <video>
    <source
      src="https://interactive-examples.mdn.mozilla.net/media/cc0-videos/flower.webm"
      type="video/webm" />
  </video>
</div>
```
```js
const btn = document.querySelector("button");
const box = document.querySelector("div");
const video = document.querySelector("video");

btn.addEventListener("click", () => box.classList.remove("hidden"));
video.addEventListener("click", () => video.play());
box.addEventListener("click", () => box.classList.add("hidden"));
```

what happens is as soon as the user clicks on the video to play, the click is also registered by the parent box div because of event bubbling, and the box disappears.

#### Preventing bubbling with stopPropagation()
to prevent this, we can use `stopPropagation()`
```js
const btn = document.querySelector("button");
const box = document.querySelector("div");
const video = document.querySelector("video");

btn.addEventListener("click", () => box.classList.remove("hidden"));

video.addEventListener("click", (event) => {
  event.stopPropagation(); // here bubbling will not occur
  video.play();
});

box.addEventListener("click", () => box.classList.add("hidden"));
```

#### Event capture
It is an alternative form of event propagation.
**It is like event bubbling with order reversed.**
so it fires first on the least nested element, then moves inward.

> Event capture is disabled by default, it can be enabled by passing `capture` option in `addEventListener()`

```js
document.body.addEventListener("click", handleClick, { capture: true });
container.addEventListener("click", handleClick, { capture: true });
button.addEventListener("click", handleClick);
```
here, body's click will be triggered first, followed by container and then button.

> In old days, netscape used event capture by default while internet explorer used event bubbling.
> When W3C standardized the behaviour, bubbling became the default.

### Event Delegation
Bubbling can be used to one's advantage as it enables event delegation.

suppose the page is divided into 16 tiles, we want to set each tile to a random color. 
```html
<div id="container">
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
  <div class="tile"></div>
</div>
```
Now instead of adding a listener to all the divs, we can rely on event bubbling and add an event listener only to the parent div.
```js
function random(number) {
  return Math.floor(Math.random() * number);
}

function bgChange() {
  const rndCol = `rgb(${random(255)} ${random(255)} ${random(255)})`;
  return rndCol;
}

const container = document.querySelector("#container");

container.addEventListener("click", (event) => {
  event.target.style.backgroundColor = bgChange(); //using event.target allows it to execute on each tile.
});
```

> Events are not unique to JavaScript -
> Most programming languages have some kind of event handling available, and they differ from JS's event model.

> In fact, **JS's event model differs in other environment**, such as **Node.js.**
> The Node.js event model has ***listeners*** to listen for events and ***emitters*** to emit events periodically. The code for it is quite different from JavaScript. Node.js uses functions like `on()` to register an event listener and `once()` to register a single run event listener that unregisters after single run.