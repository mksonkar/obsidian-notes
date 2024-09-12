- React provides a declarative way to manipulate the UI.
- Instead of manipulating the individual UI elements directly, you describe the different states your component can be in and switch between them in response to user actions.
- This is similar to how designers think about the UI.

### How declarative UI compares to imperative
How declarative UI programming differs from imperative UI programming.

When you design UI interactions, you think of how the UI changes with user actions.

eg. In a form, that's lets you submit a response, 
- When you type something in a form, the submit button **gets enabled**.
- When you press submit, the form **gets disabled** and a spinner **appears**.
- If the network request succeeds, the form gets hidden, and a **success** message appears.
- If the network request fails, an error message appears and the form gets **enabled** again.

In imperative programming, you have to write exact instructions to manipulate the UI depending on what just happened.
This is like sitting in a taxi and telling the driver where to turn at each moment. It's called imperative because you have to command each element on how to behave and when.

Manipulating the UI imperatively works well for small isolated cases,
but for larger projects its gets exponentially more difficult to manage.
For eg, adding a new element would require you to check all existing code to make sure you haven't introduced a bug.

React was built to solve this problem.

In React, you don't directly manipulate the UI, 
instead, you declare what you want to show, and React figures out how to update the UI.
For eg, Instead for telling the driver where to turn all the time, just tell the driver where you want to go, and it's the driver's job to take you there, he might even know shortcuts that you might not have considered.

## Thinking about UI declaratively

1. **Identify** your component's visual states.
2. **Determine** what triggers those state changes.
3. **Represent** the state in memory using `useState`.
4. **Remove** any non-essential states.
5. **Connect** event handlers to set the state.