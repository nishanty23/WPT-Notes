# Day 1 --- Advanced Web Application Concepts

> **Purpose:** Build a deeper understanding of web applications beyond
> the introductory notes.
>
> Each topic has two levels: **Simple Explanation** for intuition and
> **Technical View** for how the concept is used in real software
> systems.

## Table of Contents

1.  [Web Application Architecture](#1-web-application-architecture)
2.  [Client--Server Communication](#2-clientserver-communication)
3.  [What Happens When You Open a
    Website?](#3-what-happens-when-you-open-a-website)
4.  [HTTP Requests and Responses](#4-http-requests-and-responses)
5.  [Frontend, Backend, and Database](#5-frontend-backend-and-database)
6.  [Status Codes and Error
    Handling](#6-status-codes-and-error-handling)
7.  [A Practical Example](#7-a-practical-example)
8.  [Key Takeaways](#8-key-takeaways)

------------------------------------------------------------------------

## 1. Web Application Architecture

### Simple explanation

A web application is more than the page displayed in your browser.
Consider an online shopping website. You see products, but the
application must also retrieve product details, manage user accounts,
process orders, and store information.

Different parts of the system work together to provide the complete
experience.

### Technical view

A typical web application may include:

-   **Client:** The browser or app through which the user interacts.
-   **Frontend:** HTML, CSS, JavaScript, and other resources used to
    display and operate the interface.
-   **Backend:** Server-side code that implements business rules and
    processes requests.
-   **API:** An interface through which software components communicate.
-   **Database:** Stores application data, such as users, products, and
    orders.
-   **Infrastructure:** Hosting, networking, domain-name resolution,
    caching, and monitoring services.

These are logical responsibilities, not necessarily separate machines. A
small application may run on a single server, while a larger application
may use multiple services and managed cloud systems.

### Why not do everything in the browser?

The browser can perform many operations, but it is not a trusted place
for all application logic or shared data. Users can inspect and modify
client-side code. Sensitive operations---such as verifying permissions,
processing orders, or accessing private database records---should be
controlled by the backend.

The server also allows multiple users to access shared information
without each user maintaining their own separate copy.

------------------------------------------------------------------------

## 2. Client--Server Communication

### Simple explanation

The client asks for a resource or action, and the server processes the
request and returns a response.

For example, when you open a product page:

1.  The browser sends a request.
2.  The server receives and processes it.
3.  The application retrieves the necessary information.
4.  The server returns a response.
5.  The browser displays the result.

### Technical view

Client--server communication follows a protocol. Websites commonly use
**HTTP (Hypertext Transfer Protocol)**, or **HTTPS**, which protects
HTTP communication using TLS encryption.

A client may request an HTML page or call an API that returns data such
as JSON. The server might be a web server, an application process, or a
collection of services working together.

### Why this architecture is useful

-   **Shared access:** Many clients can use the same application and
    data.
-   **Centralized business rules:** Important checks can be performed on
    the server.
-   **Maintainability:** Interface code and backend logic can evolve
    separately.
-   **Scalability:** Components can be scaled according to demand.
-   **Security:** Database credentials and other secrets can remain on
    the server.

### An important distinction

The server does not always contain the entire application or perform
every operation. JavaScript can run in the browser, static files may be
delivered by a CDN, and data may live in a managed database or
object-storage service. The architecture depends on the product's
requirements.

------------------------------------------------------------------------

## 3. What Happens When You Open a Website?

### Simple explanation

When you enter a website address, the browser has to locate the
destination, connect to it, request content, and display the result.

### Technical sequence

1.  **URL parsing:** The browser interprets the URL, including its
    scheme, hostname, path, and optional query string.
2.  **DNS lookup:** The hostname is resolved to an IP address, unless a
    suitable result is already cached.
3.  **Connection setup:** The browser establishes a network connection.
    HTTPS also involves establishing a secure TLS connection.
4.  **HTTP request:** The browser requests the resource.
5.  **Server-side processing:** A web server, application server, CDN,
    or cache handles the request.
6.  **HTTP response:** The client receives a status code, headers, and
    possibly a response body.
7.  **Rendering:** The browser parses HTML, applies CSS, and executes
    JavaScript.
8.  **Additional requests:** The page may request images, fonts,
    stylesheets, scripts, or API data.

The exact sequence can vary because browsers and networks cache
resources, and modern protocols may combine or optimize some steps.

### Example URL

``` text
https://shop.example.com/products?id=42
```

  Component            Meaning
  -------------------- --------------
  `https`              Scheme
  `shop.example.com`   Hostname
  `/products`          Path
  `?id=42`             Query string

A URL identifies a resource or endpoint. The HTTP method and request
details help determine what operation the client is asking the server to
perform.

------------------------------------------------------------------------

## 4. HTTP Requests and Responses

HTTP defines how a client and server exchange messages.

### 4.1 Request

A request commonly contains a method, URL, headers, and sometimes a
body.

``` http
GET /api/products/42 HTTP/1.1
Host: shop.example.com
Accept: application/json
```

-   **Method:** `GET` indicates that the client wants to retrieve a
    resource.
-   **Path:** `/api/products/42` identifies the requested endpoint.
-   **Headers:** `Accept` indicates a response format the client can
    handle.
-   **Body:** This example has no request body.

### 4.2 Response

A response commonly contains a status code, headers, and an optional
body.

``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 42,
  "name": "Running Shoes",
  "price": 1999
}
```

The `Content-Type` header describes the format of the response body. In
this example, the server returns JSON data.

### Common HTTP methods

  Method      Typical purpose
  ----------- ---------------------------------------------
  `GET`       Retrieve a resource
  `POST`      Submit data or trigger processing
  `PUT`       Create or replace a resource at a known URL
  `PATCH`     Partially update a resource
  `DELETE`    Request deletion of a resource
  `OPTIONS`   Discover supported communication options

The method describes the intended operation; the server's implementation
determines what actually happens.

### Two useful technical terms

-   **Safe:** A method is intended not to change server state. `GET` is
    defined as safe.
-   **Idempotent:** Repeating a request has the same intended effect as
    making it once. `GET`, `PUT`, and `DELETE` are defined as
    idempotent.

For example, submitting an order repeatedly with `POST` could create
duplicate orders unless the application uses safeguards such as
idempotency keys.

------------------------------------------------------------------------

## 5. Frontend, Backend, and Database

### Frontend

**Simple explanation:** The frontend is what users see and interact
with.

**Technical view:** The browser uses HTML to structure content, CSS to
style it, and JavaScript to add behavior. Frameworks and libraries such
as React or Angular help organize larger user interfaces. Tailwind CSS
provides utility classes for styling.

The frontend may validate a form for usability, display loading
indicators, and call backend APIs. However, client-side validation is
not a substitute for server-side validation.

### Backend

**Simple explanation:** The backend handles application operations
behind the scenes.

Examples include checking whether a user can place an order, calculating
totals, and retrieving product information.

**Technical view:** The backend receives requests, validates input,
checks authentication and authorization, applies business logic,
accesses data stores or other services, and returns a response.

JavaScript can be used on the backend through Node.js. Python, Java, C#,
PHP, and Go are other common backend language choices.

### Database

**Simple explanation:** A database stores information so it can be
retrieved and updated later.

**Technical view:** A database manages persistent data and supports
operations such as querying, inserting, updating, and deleting records.

-   **MySQL:** A relational database that organizes data using tables
    and relationships.
-   **MongoDB:** A document-oriented database that stores data as
    documents.

A backend typically mediates access to a private application database.
This lets the application enforce permissions and avoid exposing
database credentials to the browser.

------------------------------------------------------------------------

## 6. Status Codes and Error Handling

HTTP status codes tell the client the general outcome of a request.

  Range       Meaning
  ----------- ---------------
  `100–199`   Informational
  `200–299`   Success
  `300–399`   Redirection
  `400–499`   Client error
  `500–599`   Server error

### Frequently used codes

  -----------------------------------------------------------------------------
  Code                          Meaning                 Example
  ----------------------------- ----------------------- -----------------------
  `200 OK`                      Request succeeded       Product details
                                                        returned

  `201 Created`                 A resource was created  New account or record
                                                        created

  `400 Bad Request`             Request is invalid      Malformed input

  `401 Unauthorized`            Authentication is       Invalid or missing
                                missing or unsuccessful credentials

  `403 Forbidden`               Access is not allowed   User lacks permission

  `404 Not Found`               Resource not found      Product ID does not
                                                        exist

  `500 Internal Server Error`   Unexpected server       Unhandled application
                                failure                 error

  `503 Service Unavailable`     Service is temporarily  Maintenance or overload
                                unavailable             
  -----------------------------------------------------------------------------

### Why status codes matter

The frontend can use the status code to decide what to show the user.
For example, a `404` may produce a "Product not found" message, while a
`500` may produce a general error message and a prompt to try again.

A status code alone may not explain the full problem. Applications often
include a structured error body, while avoiding disclosure of sensitive
internal details.

------------------------------------------------------------------------

## 7. A Practical Example

Imagine a user opens an online store and requests product ID `42`.

### Request

``` http
GET /api/products/42 HTTP/1.1
Host: shop.example.com
Accept: application/json
```

### Successful response

``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": 42,
  "name": "Running Shoes",
  "price": 1999,
  "available": true
}
```

### What the application does

1.  The browser sends the request to the API.
2.  The backend checks the requested product ID.
3.  The backend retrieves the product from a database or cache.
4.  The backend returns a JSON response with status `200 OK`.
5.  The frontend reads the response and displays the product name,
    price, and availability.

If product `42` does not exist, the API might instead return
`404 Not Found`.

This example is illustrative. Real API paths, response formats, and
error-handling rules vary by application.

------------------------------------------------------------------------

## 8. Key Takeaways

-   A web application is a collection of cooperating components, not
    just a webpage.
-   The browser is the client; server-side components process requests
    and manage access to shared data.
-   DNS, network connections, HTTP, and browser rendering all contribute
    to loading a website.
-   HTTP requests contain information about the requested operation;
    responses communicate the outcome.
-   Frontend code handles presentation and interaction, while backend
    code enforces application rules and coordinates data access.
-   Databases provide persistent storage; different database types serve
    different needs.
-   Status codes help clients handle success, redirection, and errors
    consistently.
-   Security-sensitive checks must be enforced on the server, not only
    in frontend code.

## Further Reading

-   [MDN: How the Web
    Works](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Environment_setup/How_the_web_works)
-   [MDN: HTTP
    Overview](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
-   [MDN: HTTP Request
    Methods](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods)
-   [MDN: HTTP Response Status
    Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
-   [MDN: HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)

------------------------------------------------------------------------

*These notes expand the Day 1 fundamentals. Examples are simplified for
learning and may not match the implementation of a specific production
system.*
