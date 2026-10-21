# Web Application & HTML Basics

> **Study notes:** Introduction to web applications, client--server
> communication, HTTP requests and responses, and basic HTML.

## Table of Contents

1.  [Web Applications](#1-web-applications)
2.  [How a Web Application Works](#2-how-a-web-application-works)
3.  [Web Application Development](#3-web-application-development)
4.  [Client and Server: Request and
    Response](#4-client-and-server-request-and-response)
5.  [Technical Aspects of Requests and
    Responses](#5-technical-aspects-of-requests-and-responses)
6.  [HTML: Introduction](#6-html-introduction)
7.  [Basic HTML Structure](#7-basic-html-structure)
8.  [HTML Tags and Elements](#8-html-tags-and-elements)
9.  [Paragraphs, Spans, and Headings](#9-paragraphs-spans-and-headings)
10. [HTML Attributes](#10-html-attributes)
11. [Displaying Images](#11-displaying-images)
12. [Creating Links](#12-creating-links)
13. [HTML Lists](#13-html-lists)
14. [The `iframe` Tag](#14-the-iframe-tag)
15. [Technical Clarifications](#15-technical-clarifications)

------------------------------------------------------------------------

## 1. Web Applications

### Types of Applications

-   **Desktop apps:** Directly installed on the system.
-   **Web apps:** Need a browser and internet.

**Examples:** - [youtube.com](https://www.youtube.com) -
[flipkart.com](https://www.flipkart.com) -
[amazon.in](https://www.amazon.in)

------------------------------------------------------------------------

## 2. How a Web Application Works

### Client

The **client** is usually a web browser.

### Server

A server is used:

1.  To make our web app accessible to everyone.
2.  Because it is not practically possible to store and process large
    amounts of data locally.

The server will contain the entire app and data, including the database.
The server will execute all the operations on that application.

### Basic flow

1.  The client (a web browser) sends a request to the server.
2.  The server accepts the request.
3.  The server processes the request.
4.  The server sends a response to the client.

------------------------------------------------------------------------

## 3. Web Application Development

Web application development can be divided into two main parts.

### 3.1 Frontend

The **frontend** is the UI (user interface) screen.

  -----------------------------------------------------------------------
  Technology                          Use
  ----------------------------------- -----------------------------------
  **HTML** --- HyperText Markup       Used to create the skeleton or
  Language                            structure. Whatever is visible on
                                      the browser is created using HTML.

  **CSS** --- Cascading Style Sheets  Used to style a web page.

  **JavaScript**                      Used to perform operations on the
                                      browser/client side.

  **React.js**                        Frontend library

  **Tailwind CSS**                    CSS framework

  **Angular**                         Frontend framework
  -----------------------------------------------------------------------

### 3.2 Backend

The **backend** is the processing part. It runs on the server and
includes:

-   **Application logic:** JavaScript
-   **Database:** MySQL, MongoDB

------------------------------------------------------------------------

## 4. Client and Server: Request and Response

The client and server communicate through requests and responses.

1.  The client sends a request to the server.
2.  The server accepts the request and processes it.
3.  The server sends a response to the client.

------------------------------------------------------------------------

## 5. Technical Aspects of Requests and Responses

### 5.1 Request

A request has important details, including:

#### 1. Server address / URL

To send a request, we need the address or URL of a server.

Examples:

-   IP address: `192.168.1.2`
-   `www.flipkart.com`
-   `www.amazon.in`

#### 2. Request method

The request method describes the purpose or type of request.

Common methods:

-   `GET`
-   `POST`
-   `PUT`
-   `DELETE`
-   `PATCH`
-   `OPTIONS`

### 5.2 Response

A response contains:

1.  **Data**
2.  **Status:** The status helps the client understand what happened to
    the request on the server side. The server sends a status along with
    the response data.

#### Status code ranges

  Status code range   General meaning
  ------------------- ----------------------
  `200–299`           Successful responses
  `300–399`           Redirection
  `400–499`           Client-side errors
  `500–599`           Server-side errors

#### Common status codes

  Status code   Message
  ------------- -----------------------
  `200`         OK
  `400`         Bad Request
  `401`         Unauthorized
  `500`         Internal Server Error

A status consists of a **code** and a corresponding **message**.

------------------------------------------------------------------------

## 6. HTML: Introduction

**HTML** stands for **HyperText Markup Language**.

HTML is used to:

-   Create the skeleton or structure of a web page.
-   Display data on a web page.

HTML files use the `.html` extension.

HTML code uses tags to structure and display content on a web page. HTML
has predefined tags.

### Case sensitivity

HTML tag names are case-insensitive. For example, these tag names are
treated the same in HTML:

``` html
<form>
<FORM>
<fOrM>
```

> Original note: "HTML is error free."

See [Technical Clarifications](#15-technical-clarifications) for an
important clarification about this statement.

------------------------------------------------------------------------

## 7. Basic HTML Structure

``` html
<html>
    <head>
        <title>My first page</title>
    </head>
    <body>
        <p>hello world</p>
    </body>
</html>
```

### Main parts

-   `<html>` --- Root element of the HTML document.
-   `<head>` --- Contains document information, such as the title.
-   `<title>` --- Sets the page title shown in the browser tab.
-   `<body>` --- Contains the page content.
-   `<p>` --- Defines a paragraph.

------------------------------------------------------------------------

## 8. HTML Tags and Elements

With the help of tags, we can display and structure things on a web
page.

### 8.1 Container tags

Container tags have both an opening tag and a closing tag.

Examples:

``` html
<form></form>
<body></body>
```

### 8.2 Empty tags

Empty tags do not have a separate closing tag or content between opening
and closing tags.

Examples:

``` html
<br>
<img>
```

------------------------------------------------------------------------

## 9. Paragraphs, Spans, and Headings

### Paragraph: `<p>`

Every `<p>` element starts on a new line in normal browser rendering.

``` html
<p>This is the first paragraph.</p>
<p>This is the second paragraph.</p>
```

### Span: `<span>`

A `<span>` element can sit on the same line as surrounding text.

``` html
<p>This is <span>inline text</span> inside a paragraph.</p>
```

### Six heading tags

HTML provides six heading levels:

`<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, and `<h6>`.

Example:

``` html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
```

------------------------------------------------------------------------

## 10. HTML Attributes

Every tag can have its own set of attributes or properties, which can be
used to customize it.

### Example: `align`

``` html
<p align="left">Left aligned text</p>
<p align="right">Right aligned text</p>
<p align="center">Center aligned text</p>
```

The original shorthand form was:

``` html
<p align="left|right|center"></p>
```

------------------------------------------------------------------------

## 11. Displaying Images

Use the `<img>` tag to display an image.

### Case 1: Image and HTML file are in the same folder

``` html
<img src="filename.png" width="" height="">
```

Example: the original notes mention resizing an image from `1900 × 1080`
to `500 × 300`.

``` html
<img src="photo.png" width="500" height="300">
```

### Case 2: Image is inside another folder

If the image is in an `images` folder:

``` html
<img src="images/photo.png" width="500" height="300">
```

### Case 3: Move up one folder level

`../` means going out one level from the current folder.

``` html
<img src="../images/photo.png" width="500" height="300">
```

------------------------------------------------------------------------

## 12. Creating Links

Use the **anchor tag** (`<a>`) to display a link.

``` html
<a href="https://www.flipkart.com">Visit flipkart</a>
```

-   `<a>` --- Anchor tag.
-   `href` --- Specifies the destination URL.
-   `Visit flipkart` --- The clickable link text.

------------------------------------------------------------------------

## 13. HTML Lists

HTML has two common types of lists: ordered lists and unordered lists.

### 13.1 Ordered list: `<ol>`

An ordered list displays a series of items with a sequence of numeric or
alphabetic values.

Example sequence:

a.  Mumbai\
b.  Pune\
c.  Indore

#### List type values

The `type` attribute can use:

-   `1` --- Numbers
-   `a` --- Lowercase letters
-   `A` --- Uppercase letters
-   `I` --- Uppercase Roman numerals
-   `i` --- Lowercase Roman numerals

#### Basic ordered list

``` html
<ol>
    <li>Mumbai</li>
    <li>Pune</li>
    <li>Nagpur</li>
    <li>Chennai</li>
</ol>
```

#### Ordered list with `type` and `start`

``` html
<ol type="a" start="3">
    <li>Mumbai</li>
    <li>Pune</li>
    <li>Nagpur</li>
    <li>Chennai</li>
</ol>
```

Here, `type="a"` uses lowercase letters, and `start="3"` starts the
sequence at the third letter (`c`).

### 13.2 Unordered list: `<ul>`

An unordered list displays items using bullet markers.

``` html
<ul type="square">
    <li>Mumbai</li>
    <li>Pune</li>
    <li>Nagpur</li>
    <li>Chennai</li>
</ul>
```

The original example uses `type="square"` to show square bullets.

------------------------------------------------------------------------

## 14. The `iframe` Tag

The original notes introduce the `iframe` tag here; no explanation or
example was included in the supplied material.

------------------------------------------------------------------------

## 15. Technical Clarifications

These notes preserve the supplied material. The following clarifications
are listed separately so the original content is not silently changed.

1.  **Web apps and internet:** Web apps run in a browser, but not every
    web app requires an internet connection. Some can work locally or
    offline after being loaded.
2.  **What is on the server:** A server does not necessarily contain the
    entire application or all data. Modern apps may split work between
    the browser, application servers, APIs, databases, and cloud
    storage.
3.  **Frontend technologies:** HTML structures content, CSS styles it,
    and JavaScript adds behavior. React.js and Angular are used to build
    user interfaces; Tailwind CSS is a utility-first CSS framework.
4.  **Backend and databases:** JavaScript can be used for backend logic,
    for example with Node.js. MySQL and MongoDB are database systems.
5.  **Requests and responses:** HTTP requests usually include a method
    and a URL, along with headers and sometimes a body. HTTP responses
    include a status code, headers, and sometimes a body.
6.  **Status codes:** The ranges shown are broadly correct. `200–299`
    means success, `300–399` redirection, `400–499` client errors, and
    `500–599` server errors. A `401 Unauthorized` response generally
    means authentication is required or has failed.
7.  **HTML validity:** HTML has defined rules, but invalid or malformed
    HTML can still be written. Browsers often try to recover and render
    a page rather than rejecting it completely.
8.  **Empty tags:** `<br>` and `<img>` are void elements in HTML; they
    do not have closing tags.
9.  **Paragraphs and spans:** `<p>` is a block-level element in normal
    browser styling, while `<span>` is inline by default. CSS can change
    their display behavior.
10. **The `align` attribute:** It appears in older examples but is
    obsolete in modern HTML. CSS is preferred for alignment, for example
    `text-align: center;`.
11. **Image dimensions:** Setting both `width` and `height` to fixed
    values can distort an image if those dimensions do not match its
    aspect ratio. CSS such as `max-width: 100%; height: auto;` is often
    preferable.
12. **List styling:** The `type` attribute on `<ul>` is obsolete in
    modern HTML. CSS `list-style-type` is the preferred way to style
    unordered-list markers.
