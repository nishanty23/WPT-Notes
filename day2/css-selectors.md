# CSS Selectors and Styling

## 1. Basic CSS Syntax

The basic syntax of CSS is:

```css
selector {
    property: value;
}
```

- **Selector** → Selects the HTML element(s) to which the CSS will be applied.
- **Property** → Specifies what aspect of the element you want to change.
- **Value** → Specifies the value of that property.

---

## 2. Types of CSS Selectors

There are different types of CSS selectors:

### 2.1 Tag Selector

A **tag selector** uses the name of the HTML tag.

It selects **all matching tags** on the page.

```css
p {
    color: red;
}
```

The above selector will apply the CSS to **all `<p>` elements**.

---

### 2.2 ID Selector

An **ID selector** is used to identify an element **uniquely**.

The ID selector is written using the `#` symbol followed by the ID name.

```css
#head-1 {
    color: red;
}
```

The corresponding HTML element is:

```html
<h1 id="head-1">Hello</h1>
```

### Example

```html
<html>
    <head>
        <title>CSS Demo</title>

        <style>
            #head-1 {
                color: red;
            }

            #head-2 {
                color: green;
            }

            #head-3 {
                color: blue;
            }
        </style>
    </head>

    <body>
        <h1 id="head-1">Hello</h1>
        <h1 id="head-2">Heading 2</h1>
        <h1 id="head-3">Heading 3</h1>
    </body>
</html>
```

Here:

- `head-1` → Red
- `head-2` → Green
- `head-3` → Blue

---

### 2.3 Class Selector

A **class selector** is used when **multiple elements need to be identified commonly**.

The class selector is written using the `.` symbol followed by the class name.

```css
.blue-font {
    color: blue;
}
```

### Example

```html
<html>
    <head>
        <title>CSS Demo</title>

        <style>
            .blue-font {
                color: blue;
            }
        </style>
    </head>

    <body>
        <h1>Hello</h1>
        <h1 class="blue-font">Heading 2</h1>
        <h1>Heading 3</h1>

        <p class="blue-font">para 1</p>
        <p>para 2</p>

        <span>span 1</span>
        <span>span 2</span>
        <span class="blue-font">span 3</span>

        <!-- 2nd h1, 1st p, 3rd span blue -->
    </body>
</html>
```

Here, the same `blue-font` class is applied to multiple elements:

- 2nd `<h1>`
- 1st `<p>`
- 3rd `<span>`

All of these elements will have **blue text**.

---

### 2.4 Universal Selector

The **universal selector** is represented using `*`.

It selects **all elements** on the page.

```css
* {
    
}
```

---

## 3. CSS Selector Priority

The priority of the selectors is:

```text
id > class > tag selector > *
```

That means an **ID selector** has higher priority than a **class selector**, a **class selector** has higher priority than a **tag selector**, and a **tag selector** has higher priority than the **universal selector**.

---

# 4. Practical CSS Selector Combination Examples

CSS selectors can also be **combined** to select elements more precisely.

---

## 4.1 Group Selector

A **group selector** is used when the same CSS needs to be applied to multiple different selectors.

Instead of writing:

```css
h1 {
    color: blue;
}

p {
    color: blue;
}

span {
    color: blue;
}
```

We can combine them:

```css
h1, p, span {
    color: blue;
}
```

### Example

```html
<h1>Heading</h1>
<p>This is a paragraph.</p>
<span>This is a span.</span>
```

All three elements will have **blue text**.

---

## 4.2 Descendant Selector

A **descendant selector** selects an element that is present **inside another element**.

Syntax:

```css
parent child {
    property: value;
}
```

### Example

```css
div p {
    color: red;
}
```

This selects all `<p>` elements that are inside a `<div>`.

```html
<div>
    <p>This paragraph will be red.</p>
</div>

<p>This paragraph will not be red.</p>
```

Only the `<p>` inside the `<div>` will be affected.

---

## 4.3 Child Selector

A **child selector** selects only the elements that are **direct children** of another element.

The `>` symbol is used.

Syntax:

```css
parent > child {
    property: value;
}
```

### Example

```css
div > p {
    color: red;
}
```

```html
<div>
    <p>This will be red.</p>

    <section>
        <p>This will NOT be red.</p>
    </section>
</div>
```

The first `<p>` is a **direct child** of `<div>`.

The second `<p>` is inside `<section>`, so it is **not a direct child** of `<div>`.

---

## 4.4 Element + Class Selector

We can combine a **tag selector** and a **class selector**.

```css
p.blue-font {
    color: blue;
}
```

This means:

> Select only `<p>` elements that have the `blue-font` class.

### Example

```html
<p class="blue-font">Paragraph 1</p>

<h1 class="blue-font">Heading 1</h1>

<p>Paragraph 2</p>
```

Only the first `<p>` will become blue.

The `<h1>` will not be affected because the selector specifically targets `<p>` elements.

---

## 4.5 Element + ID Selector

We can also combine a **tag selector** with an **ID selector**.

```css
h1#main-heading {
    color: red;
}
```

This selects an `<h1>` element whose ID is `main-heading`.

### Example

```html
<h1 id="main-heading">Main Heading</h1>

<p id="main-heading">Paragraph</p>
```

Only the `<h1>` matches:

```css
h1#main-heading {
    color: red;
}
```

---

## 4.6 Class + Class Selector

Multiple classes can be combined.

```css
.blue-font.bold {
    color: blue;
    font-weight: bold;
}
```

This selects an element that has **both** `blue-font` and `bold` classes.

### Example

```html
<p class="blue-font bold">
    This text will be blue and bold.
</p>

<p class="blue-font">
    This text will only be blue.
</p>

<p class="bold">
    This text will only be bold.
</p>
```

Only the first paragraph has **both classes**, so only it will receive both properties.

---

## 4.7 ID + Class Selector

We can combine an ID and a class selector.

```css
#heading.blue-font {
    color: blue;
}
```

This selects the element that has:

- ID → `heading`
- Class → `blue-font`

### Example

```html
<h1 id="heading" class="blue-font">
    Hello
</h1>
```

The selector matches this element because it has both the specified ID and class.

---

## 4.8 Multiple Classes on an Element

An HTML element can have **multiple classes**.

```html
<p class="blue-font large-text bold">
    This is a paragraph.
</p>
```

CSS:

```css
.blue-font {
    color: blue;
}

.large-text {
    font-size: 30px;
}

.bold {
    font-weight: bold;
}
```

The paragraph will have:

- Blue text
- Large font
- Bold text

---

## 4.9 Combining Parent and Class Selectors

We can select a class only when it appears inside a particular element.

```css
div .blue-font {
    color: blue;
}
```

### Example

```html
<div>
    <p class="blue-font">This will be blue.</p>
</div>

<p class="blue-font">This will not be blue.</p>
```

The selector:

```css
div .blue-font
```

means:

> Select any element having the `blue-font` class that is inside a `<div>`.

---

## 4.10 Combining Parent, Child and Class Selectors

We can make the selector even more specific.

```css
div > p.blue-font {
    color: blue;
}
```

This means:

> Select a `<p>` element with the `blue-font` class that is a direct child of `<div>`.

### Example

```html
<div>
    <p class="blue-font">This will be blue.</p>

    <section>
        <p class="blue-font">This will NOT be blue.</p>
    </section>
</div>
```

The first paragraph is a direct child of `<div>`.

The second paragraph is not a direct child because it is inside `<section>`.

---

## 5. CSS Priority

The priority of these types of CSS is:

```text
inline > internal > external
```

This means **inline CSS has higher priority than internal CSS**, and **internal CSS has higher priority than external CSS**, when the rules have the same specificity and otherwise applicable conditions.

---

# 6. Font Properties

CSS provides different properties to change the appearance of text.

Example:

```css
p {
    font-size: 24px;
    font-family: 'Segoe UI Light';
    font-weight: 900;
    /* font-style: italic; */
    /* font-variant: small-caps; */
    text-transform: capitalize;
    text-decoration: line-through;
}
```

### Important Font Properties

- `font-size` → Sets the size of the text.

```css
font-size: 24px;
```

- `font-family` → Specifies the font used for the text.

```css
font-family: 'Segoe UI Light';
```

- `font-weight` → Specifies the thickness of the text.

```css
font-weight: 900;
```

- `font-style` → Specifies the style of the text, such as italic.

```css
font-style: italic;
```

- `font-variant` → Specifies variations such as small caps.

```css
font-variant: small-caps;
```

- `text-transform` → Controls the capitalization of text.

```css
text-transform: capitalize;
```

- `text-decoration` → Adds decoration to the text.

```css
text-decoration: line-through;
```

---

# 7. `<div>` Element

The `<div>` element is used to create a **division or section on a web page**.

Example:

```html
<html>

<head>
    <title>CSS Demo</title>

    <style>
        div {
            width: 300px;
            height: 300px;
            background-color: green;
            color: white;
            border-width: 10px;
            border-color: black;
            border-style: solid;
            border-radius: 20px;
        }
    </style>
</head>

<body>

    <div>
        <h3>This is heading</h3>
        <p>this is dummy para</p>
    </div>

</body>

</html>
```

### Important Properties Used

- `width` → Sets the width of the `<div>`.

```css
width: 300px;
```

- `height` → Sets the height of the `<div>`.

```css
height: 300px;
```

- `background-color` → Sets the background color.

```css
background-color: green;
```

- `color` → Sets the text color.

```css
color: white;
```

- `border-width` → Sets the width of the border.

```css
border-width: 10px;
```

- `border-color` → Sets the color of the border.

```css
border-color: black;
```

- `border-style` → Sets the style of the border.

```css
border-style: solid;
```

- `border-radius` → Makes the corners rounded.

```css
border-radius: 20px;
```

---

# 8. Padding and Margin

There are two types of spaces around an element:

1. **Internal space → Padding**
2. **External space → Margin**

---

## 8.1 Padding

**Padding** is the space between the **content and the border** of an element.

The following properties can be used:

```css
padding-left
padding-top
padding-right
padding-bottom
padding
```

Example:

```css
div {
    padding: 20px;
}
```

---

## 8.2 Margin

**Margin** is the space **outside the element**, between the element and other elements.

The following properties can be used:

```css
margin-left
margin-right
margin-bottom
margin-top
margin
```

Example:

```css
div {
    margin: 20px;
}
```

---

# 9. Different Ways of Applying Colors

There are different ways to specify colors in CSS.

### 9.1 Color Name

We can directly use the **name of the color**.

```css
color: red;
```

---

### 9.2 Hexadecimal Value

We can specify colors using a **hexadecimal value**.

Examples:

```css
color: #3b5998;
color: #671t43;
```

A hexadecimal color value generally starts with `#`.

---

### 9.3 RGB Function

We can also specify colors using the `rgb()` function.

The RGB values range from **0 to 255** for each color component.

```css
color: rgb(0, 255, 0);
```

The syntax is:

```css
rgb(red, green, blue)
```

where:

```text
red   → 0-255
green → 0-255
blue  → 0-255
```
