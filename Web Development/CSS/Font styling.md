```css
p {
color: red;
font-family: Arial;

}
```
- Sets the foreground color of the element.
- Sets the font.

## Web safe fonts

Fonts that are generally available in all systems.

[cssfontstack.com](cssfontstack.com) webiste maintains list of websafe fonts.

Eg.
- `Arial - Sans Serif
- `Courier New - Monospace
- `Gerogia - Serif
- `Times New Roman - Serif
- `Verdana - Sans Serif

## Default fonts
CSS provides 5 generic fonts -
- `serif
- `sans-serif 
- `monospace
- `cursive
- `fantasy

> These are very generic and the exact font from these generic names can vary between each browser and operating system.


## Font stack
```css
p {
  font-family: "Trebuchet MS", Verdana, sans-serif;
}
```
Since font availability is always guaranteed, its best to provide multiple options with a generic font in last. 

## Font size 
- **`px`** - (pixels) *absolute unit* , meaning it will have the same size on all devices. 
- **`em`** -  `1em` is equal to the font size of the parent element. Using em across the whole web page make maintenance easy. 
- **`rem`** - (`root em`)  `1rem` is equal to the size set on the root element i.e. `<html>`. It makes doing math for size of other elements easy.


> It is best to use `rem` where you can to keep things simple, and avoid setting the `font-size` of container elements where possible.

## Font style, Font weight, text transform, and text decoration.


CSS provides 4 common properties to alter the visual weight/emphasis for text: 

- **`font-style`**:  used to turn italic text on/off.
    - `normal`: Set text to normal font. (Turns existing italics off)
    - `italic`: uses italic version of the font.
    - `oblique`: uses simulated version of italic font, created by slanting the normal version. 
- **`font-weight`**: sets how bold the text is. Values available are `light`, `normal`, `bold`, `extrabold`, `black`, etc. 
    - `normal`, `bold`
    - `lighter`, `bolder`
    - `100`-`900`
- **`text-transform`**: 
    - `none`
    - `uppercase`
    - `lowercase`
    - `capitalize`
    - `full-width`: transforms all letters to be written inside a fixed-width square
- **`text-decoration`**: 
    - `none`
    - `underline`
    - `overline`
    - `line-through`

> `text-decoration` can accept multiple values at once
```css
text-decoration: underline overline;
```

> `text-decoration` is a shorthand property for `text-decoration-line`, `text-decoration-style`, and `text-decoration-color`
```css
text-decoration: line-through red wavy;
```
