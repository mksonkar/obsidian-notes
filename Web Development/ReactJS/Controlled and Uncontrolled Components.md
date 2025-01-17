These concepts define how form data is handled within a component.

If a component has some local state, it is referred to as **uncontrolled** component, 
because its parent component cannot influence it.

Whereas, a component can be called **controlled** if the important information in it is 
driven by props rather than its own local state.
This lets the parent component fully specify its behaviour.

Uncontrolled components are easier to use, as they require less configuration.
But they are less flexible when you want to coordinate them together.
Controlled components are maximally flexible, but they require their parent components to 
fully configure them with props.

In practice, controlled and uncontrolled components are strict technical terms, 
each component usually has a mix of both local state and props.
However, it is a useful way to talk about how components are designed and what
capabilities they offer.

When writing a component, think of which information in it should be controlled via props
and which information should be uncontrolled via state.
You can always change your mind and refactor later if needed.