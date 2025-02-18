#CSS Interview

---

### 1) Difference Between Class Selectors and ID Selectors in CSS

### Class Selectors (`.`):
- Used to select elements that belong to a specific class.
- You can apply the same class to multiple elements.

#### Example:
```css
.button {
  background-color: blue;
  color: white;
}
```

### ID Selectors (`#`):
- Used to select an element with a specific ID.
- The ID should be unique within the page, meaning no two elements should have the same ID.

#### Example:
```css
#header {
  font-size: 24px;
}
```
---
### 2) What are CSS Properties?
CSS properties define the style or appearance of elements on a webpage. They control aspects like layout, colors, fonts, spacing, etc.

---

### 3) What is the CSS Box Model?

The CSS Box Model is describes how elements are structured and spaced on a webpage. Every HTML element is treated as a rectangular box with the following four components:

- **Margin** – The space between the element and other elements.
 - **Border** – The edge surrounding the padding (or content if no padding is applied).
- **Padding** – The space between the content and the border.
- **Content** – The actual text or image inside the element.
---
### 4)  Difference Between Inline, Block, and Inline-Block Elements in CSS

### ✅ Inline Elements (`display: inline;`)
- Do not start on a new line.
- Only take up as much width as needed (cannot set width and height).
- **Examples:** `<span>`, `<a>`, `<b>`, `<i>`, `<img>`

### Block Elements (`display: block;`)
- Always start on a new line.
- Takes up full width available (by default).
- You can set width and height.
- **Examples:** `<div>`, `<p>`, `<h1>`, `<section>`, `<article>`

### Inline-Block Elements (`display: inline-block;`)
- Stays in the same line like inline.
- Respects width and height, unlike inline.
- **Examples:** `<button>`, `<input>`, `<img>`
---
### 5)  How to Apply an External CSS Stylesheet to an HTML Page
You can link an external CSS file to an HTML page using the `<link>` tag inside the `<head>` section. Inside link tag we specifies that the linked file is a CSS stylesheet and provides its file location.

#### Example:
```html
<head>
    <link rel="stylesheet" href="style.css">
</head>
```

---
### 6)  What is the `z-index` Property in CSS?
✅ `z-index` is a CSS property that controls the vertical stacking order of elements on a webpage.

- It only works on positioned elements (`position: relative;`, `absolute;`, `fixed;`, or `sticky;`).
- --
### 7)  What is the `z-index` Property in CSS?
✅ `z-index` is a CSS property that controls the vertical stacking order of elements on a webpage.

- It only works on positioned elements (`position: relative;`, `absolute;`, `fixed;`, or `sticky;`).

### Different Position Values in CSS
The `position` property in CSS controls how an element is placed in the document. There are five main position values:

### ✅ 1. `static` (Default Position)
- This is the default position for all elements.
- The element follows the normal document flow (does not move).
- `top`, `left`, `right`, and `bottom` do not work with static.

#### Example:
```css
div {
  position: static; /* Default behavior */
}
```

### 2. `relative` (Positioned Relative to Itself)
- The element is positioned relative to its normal position.
- You can move it using `top`, `left`, `right`, or `bottom`.
- Other elements do not take its original space when moved.

#### Example:
```css
.box {
  position: relative;
  top: 20px;  /* Moves 20px down */
  left: 30px; /* Moves 30px right */
}
```
📌 The element moves but still occupies its original space.

### 3. `absolute` (Positioned Relative to the Nearest Positioned Ancestor)
- The element is removed from the normal document flow.
- It is positioned relative to the nearest positioned (non-static) ancestor.
- If no ancestor has `position: relative;`, it will be positioned relative to the `<html>` (document body).

#### Example:
```css
.parent {
  position: relative; /* Parent container */
  width: 300px;
  height: 300px;
  background-color: lightblue;
}

.child {
  position: absolute;
  top: 50px; /* 50px from the parent's top */
  left: 50px; /* 50px from the parent's left */
  width: 100px;
  height: 100px;
  background-color: red;
}
```
📌 If `.parent` is `relative`, `.child` will be positioned inside it.

### 4. `fixed` (Fixed to the Viewport)
- The element is always fixed in the same position, even when the page is scrolled.
- It is positioned relative to the browser window (viewport).
- Commonly used for sticky headers, floating buttons, or navigation bars.

#### Example:
```css
.fixed-box {
  position: fixed;
  top: 0;
  right: 0;
  width: 200px;
  height: 50px;
  background-color: black;
  color: white;
}
```
📌 The `.fixed-box` will stay at the top-right corner even when scrolling.

### ✅ 5. `sticky` (Sticky Until a Scroll Threshold)
- The element behaves like `relative` until the page is scrolled to a certain point, then it sticks like `fixed`.
- It is `relative` by default but becomes `fixed` when scrolling past a threshold.
- Commonly used for sticky navigation bars or headings.

#### Example:
```css
.sticky-box {
  position: sticky;
  top: 10px; /* Sticks when scrolling down */
  background-color: yellow;
  padding: 10px;
}
```
📌 The element stays in place once scrolled past `top: 10px;`.

 
---
### 6)  Centering Elements in CSS
#### Using Flexbox (Recommended Method)
```css
.parent {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background-color: lightgray;
}

.child {
    width: 200px;
    height: 100px;
    background-color: blue;
    color: white;
    text-align: center;
    line-height: 100px;
}
```

### Using Grid (Another Modern Approach)
```css
.parent {
    display: grid;
    place-items: center;
    height: 100vh;
}
```

### Using `position: absolute;` and `transform`
```css
.parent {
    position: relative;
    height: 100vh;
}

.child {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: red;
    padding: 20px;
}
```
---
### 7) Difference Between Flexbox and Grid 

### **Flexbox (Flexible Box Layout)**

Flexbox is a **one-dimensional layout system** that arranges elements in either a row (horizontal) or a column (vertical). It is best suited for aligning items within a container when the focus is on **either row-wise or column-wise placement**.


### **CSS Grid Layout**

Grid is a **two-dimensional layout system**, meaning it can handle both rows **and** columns simultaneously. It is best for designing **complex layouts** like website structures with headers, sidebars, and content sections.

---

### 8)  Pseudo-Classes vs. Pseudo-Elements in CSS

### ✅ Pseudo-Classes
A pseudo-class is used to select elements based on their state, position, or interaction with the user.

#### Example Pseudo-Classes:
- `:hover` → Applies styles when the user hovers over an element.
- `:focus` → Styles an element when it is focused (like in an input field).
- `:nth-child(n)` → Targets elements based on their position in a parent.
- `:first-child`, `:last-child` → Styles the first or last child element.
- `:checked` → Styles checkboxes or radio buttons when they are checked.

### ✅ Pseudo-Elements
A pseudo-element is used to style a specific part of an element or insert content before/after it.

#### Example Pseudo-Elements:
- `::before` → Inserts content before an element.
- `::after` → Inserts content after an element.
- `::first-letter` → Styles only the first letter of a text block.
- `::first-line` → Styles only the first line of a text block.
- `::selection` → Styles the text when selected (highlighted).
