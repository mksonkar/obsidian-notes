**event.target:** the element which triggered the 
**event.currentTarget:**
**event.relatedTarget:** 

Event propagation refers to the way events travel (or propagate) through the DOM tree.
### Event propagation occurs in 3 phases:
1. **Capture Phase:** The event moves from the window down the DOM tree to the target element, checking each ancestor along the way. 
		In this phase, event set to listen during the capture phase are triggered.
1. **Target Phase:** The event reaches the target element, and event listeners attached to target element are triggered.
2. **Bubble Phase:** After reaching the target, the event "bubbles up", from the target element back to the window, triggering event listeners on each ancestor element in the bubble phase.

By default, events are handled in bubble phase, unless specified to fire on capture phase.