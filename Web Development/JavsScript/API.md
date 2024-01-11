
## What is an API?

An API or Application Programming Interface is like a bridge that allows two different software systems to communicate with each other.

It defines a set of rules and protocols for requesting and exchanging data.

## How to Use the Fetch API for GET Requests
To make API requests in JS, you can use the fetch API, which is built into modern browsers.
It is a promise-based API that makes it easy to send HTTP requests and handle responses asynchronously.

```js
// Define the API URL
const apiURL = 'https://api.example.com/data';

// Make a GET request
fetch(apiURL)
	.then(response => {
		if (!response.ok) {
			throw new Error('Network response was not ok');
		}
		return response.json();
	})
	.then(data => {
		console.log(data);
	})
	.catch(error => {
		console.error('Error:', error);
	});
```