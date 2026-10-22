# HTML Tables, Forms and CSS

## 1. HTML Tables

A **table** is used to represent data in the form of **rows and columns**.

- **Rows and columns → Table**
- A table consists of:
  - **Rows**
  - **Columns**
  - **Cells**

### Basic Table Structure

```html
<table>
    <tr>
        <td>id</td>
        <td>Name</td>
        <td>Phone</td>
    </tr>

    <tr>
        <td>1</td>
        <td>Nitin</td>
        <td>78888111</td>
    </tr>

    <tr>
        <td>2</td>
        <td>Suresh</td>
        <td>8999911</td>
    </tr>
</table>
```

### Important Table Tags

- `<table>` → Defines the table.
- `<tr>` → Defines a **table row**.
- `<td>` → Defines a **table data cell**.

### Table Border

By default, the table border is set to **0**, so the border is not visible.

```html
<table border="1" cellpadding="10" cellspacing="0">
```

### `cellpadding`

`cellpadding` defines the **space inside the cell**, between the cell content and its border.

### `cellspacing`

`cellspacing` defines the **space outside/between the cells**.

Example:

```html
<table border="1" cellpadding="10" cellspacing="0">
```

Here:

- `border="1"` → Displays the table border.
- `cellpadding="10"` → Adds 10 units of space inside each cell.
- `cellspacing="0"` → Removes the space between cells.

---

## 2. Table Heading

The `<th>` tag is used to define a **table heading**.

```html
<table border="1" cellpadding="10" cellspacing="0">
    <tr>
        <th>id</th>
        <th>Name</th>
        <th>Phone</th>
    </tr>

    <tr>
        <td>1</td>
        <td>Nitin</td>
        <td>78888111</td>
    </tr>

    <tr>
        <td>2</td>
        <td>Suresh</td>
        <td>8999911</td>
    </tr>
</table>
```

### `<th>` vs `<td>`

- `<th>` → Table heading.
- `<td>` → Table data.

---

## 3. Semantic Tags

**Semantic tags** are tags that may perform the same basic function but provide **better code readability and meaning**.

For tables, `<thead>` and `<tbody>` can be used to clearly separate the table heading from the table data.

```html
<table border="1" cellpadding="10" cellspacing="0">

    <thead>
        <tr>
            <th>id</th>
            <th>Name</th>
            <th>Phone</th>
        </tr>
    </thead>

    <tbody>
        <tr>
            <td>1</td>
            <td>Nitin</td>
            <td>78888111</td>
        </tr>

        <tr>
            <td>2</td>
            <td>Suresh</td>
            <td>8999911</td>
        </tr>
    </tbody>

</table>
```

### Important Semantic Table Tags

- `<thead>` → Contains the table heading/header rows.
- `<tbody>` → Contains the main table data.

---

# 4. HTML Forms

The `<form>` tag is **not used to display the form input fields itself**.

The `<form>` tag is used to **collect the entire form data and submit it to the server**.

### Basic Form Structure

```html
<form action="https://www.mydataserver.com" method="POST">

</form>
```

### `action`

The `action` attribute contains the **URL of the server where the form data has to be submitted**.

Example:

```html
<form action="https://www.mydataserver.com">
```

### `method`

The `method` attribute specifies the **request method** used to submit the form data.

Example:

```html
<form method="POST">
```

If no request method is specified, the **GET method is considered by default**.

---

# 5. Types of Buttons

There are **3 types of buttons**:

## 5.1 Plain Button

A plain button does not have any predefined functionality.

The **developer has to define its functionality**.

```html
<input type="button" value="Click me">
```

---

## 5.2 Submit Button

The submit button has predefined functionality.

It is used to **submit the form**.

```html
<input type="submit">
```

---

## 5.3 Reset Button

The reset button is used to **reset the form fields** to their initial values.

---

# 6. CSS

**CSS** stands for **Cascading Style Sheet**.

CSS is used to define the **style and appearance of HTML elements**.

---

## 7. CSS Syntax

The basic syntax of CSS is:

```css
selector {
    property: value;
    property: value;
    property: value;
    .
    .
    .
}
```

### Components of CSS Syntax

- **Selector** → Selects the HTML element to which the style should be applied.
- **Property** → Specifies what aspect of the element we want to change.
- **Value** → Specifies the value for that property.

---

## 8. CSS Example

CSS can be written inside the `<style>` tag.

```html
<style>
h1 {
    color: green;
}
</style>
```

The CSS above changes the color of the `<h1>` element to green.

HTML:

```html
<h1>Hello World</h1>
```

### Complete Example

```html
<html>
    <head>
        <style>
            h1 {
                color: green;
            }
        </style>
    </head>

    <body>
        <h1>Hello World</h1>
    </body>
</html>
```
