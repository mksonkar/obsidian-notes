 [[Flexbox]] is a one-dimensional CSS layout
 It controls the way items are spaced out and aligned within a container.
 
### Quick summary of flexbox properties.
- `flex-direction`: [row, row-reverse, column, column-reverse]
- `align-items`: [flex-start, flex-end, center, baseline, stretch (default)]
- `justify-content`: [flex-start, flex-end, center, space-around, space-between]
- `order: [-2, -1, 0, 1, 2]
- `align-self`: accepts same values as `align-items` but applied on specific item.
- `flex-wrap`: [nowrap, wrap, wrap-reverse]
- `flex-flow`: `flex-direction` and `flex-wrap` are used together very often, so there's a shorthand property for them.  `flex-flow: row wrap`
- `align-content`: set how multiple lines are spaced apart. takes same values as `justify-content`. 
> `align-content` determines the spacing between lines, while `align-items` determines how the items as a whole are aligned within the container. When there is only one line `align-content` has no effect. 
## Using flexbox
  Give an element a `display: flex` property. 
  This will make that element a *flex container*.
  Any direct children of a flex container are called *flex items*.

Flexbox has a *main* and *cross* axis. 
The main axis is defined by the `flex-direction` property, which has 4 possible values:
- `row`: horizontal axis, flex items from left to right.
- `row-reverse`: horizontal axis, flex items from right to left.
- `column`: vertical axis, flex items from top to bottom.
- `column-reverse`: vertical axis, flex items from bottom to top.

The `flex-wrap` property determines how flex items will behave when the flex container is too small. 
`flex-wrap: wrap` will allow the items to wrap to the next row or column. 
`flex-wrap: nowrap` (default) will prevent items from wrapping and shrink them if needed.

The `justify-content` property determines how the items inside a flex container are positioned along the main axis, affecting their position and the space around them.
```css
justify-content: center;
```

The `align-items` property positions the flex content along the cross axis. 
```css
align-items: center;
```

### maintain aspect ratios of images
```css
object-fit: cover;
```

The `gap` property sets the gaps (gutters) between rows and columns. 
`gap`, `row-gap` and `column-gap` sub-properties provide this functionality for flex and grid layout. 
```css
gap: 16px;
```
## `::after` pseudo-element
It creates an element that is the last child of the selected element. 
You can use it to add an empty element after the last child. 



