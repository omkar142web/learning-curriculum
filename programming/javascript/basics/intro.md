---
title: Introduction
description: Get started with JavaScript by writing your first program.
order: 1
---

# An Introduction to JavaScript

JavaScript is one of the most important technologies on the web. If HTML defines what a page contains and CSS defines how it looks, JavaScript is what allows that page to **think, react, and respond**.

When you click a button and something happens, submit a form without reloading the page, open a dropdown, see new messages appear in a chat application, or watch a dashboard update its data — JavaScript is often involved.

But JavaScript is much more than a language for making buttons work.

Today, JavaScript can run in browsers, servers, command-line applications, desktop applications, mobile applications, development tools, and many other environments.

In this lesson, we'll build a clear mental model of what JavaScript actually is, how it runs, what it can do in a browser, why browsers restrict it, and how it fits into modern web development.


## What is JavaScript?

JavaScript is a programming language originally created to make web pages interactive.

A JavaScript program is commonly called a **script**.

For example:

```javascript
console.log("Hello, world!");

This is a JavaScript program.

When JavaScript is used inside a web page, the browser can execute it automatically.

For example:

```html
<!DOCTYPE html>
<html>
<body>

  <h1>Hello</h1>

  <script>
    console.log("JavaScript is running!");
  </script>

</body>
</html>
```

The JavaScript can also be placed in a separate file:

```html
<script src="app.js"></script>
```

with:

```javascript
// app.js

console.log("JavaScript is running!");
```

This separation is what you'll usually see in real projects.

---

## JavaScript is a programming language

It is easy to get the impression that JavaScript is simply a tool for changing HTML.

It isn't.

JavaScript is a full programming language with:

* variables
* values and data types
* operators
* conditions
* loops
* functions
* objects
* arrays
* classes
* modules
* error handling
* asynchronous programming
* promises
* closures
* and much more

For example, JavaScript can perform ordinary programming tasks without touching a web page at all:

```javascript
function calculateTotal(price, quantity) {
  return price * quantity;
}

const total = calculateTotal(499, 3);

console.log(total);
```

The result is:

```text
1497
```

Nothing in this example is specific to HTML.

That's an important distinction to understand from the beginning:

> **JavaScript is a programming language. The browser is one environment in which that language can run.**

---

## JavaScript and Java are different

Despite their similar names, JavaScript and Java are different programming languages.

They were developed independently and have different specifications, ecosystems, and runtime environments.

The name "JavaScript" is largely a historical result of the popularity of Java when JavaScript was being introduced.

Today, there is no reason to think of JavaScript as a version of Java or as Java's "web language".

They are separate languages.

---

## JavaScript and ECMAScript

You'll often encounter another name when learning JavaScript:

**ECMAScript**.

ECMAScript is the standardized specification that defines the JavaScript language.

A useful way to think about the relationship is:

```text
ECMAScript
    ↓
Defines the language
    ↓
JavaScript implementations follow the specification
```

For example, features such as:

```javascript
const
let
class
async
await
```

are part of the evolving JavaScript language specification.

You don't normally need to worry about the specification while writing everyday JavaScript. But you'll see the term **ECMAScript** frequently in documentation and technical discussions.

---

## Where does JavaScript run?

JavaScript was originally created for web browsers, but it is no longer limited to them.

JavaScript can run anywhere there is a suitable JavaScript runtime.

For example:

```text
Browser
├── Chrome
├── Firefox
├── Safari
└── Edge

Server
├── Node.js
├── Deno
└── Bun

Other environments
├── Desktop applications
├── Mobile applications
├── CLI tools
└── Developer tooling
```

This leads to an important question:

**If JavaScript is the same language, why can it do different things in different environments?**

The answer is the **runtime environment**.

---

## The language and the environment

Consider this:

```javascript
console.log("Hello");
```

This is basic JavaScript and can run in many environments.

Now consider:

```javascript
document.querySelector("h1");
```

This requires a browser-like environment because `document` is provided by the browser.

And consider:

```javascript
import fs from "node:fs";

const data = fs.readFileSync("notes.txt", "utf8");
```

This requires a runtime such as Node.js that provides filesystem APIs.

So it is useful to think about JavaScript in two layers:

```text
JavaScript language
        +
Runtime environment
        =
What your program can actually do
```

The language gives you the programming language itself.

The environment gives you additional APIs and capabilities.

This distinction will become extremely useful as you move into frontend and backend development.

---

# JavaScript in the Browser

The browser is one of the most important environments for JavaScript.

A simplified view of a browser looks like this:

```text
                  Browser
                     │
        ┌────────────┼────────────┐
        │            │            │
       HTML         CSS       JavaScript
        │            │            │
        └────────────┼────────────┘
                     │
               Web Platform
                     │
        ┌────────────┼────────────┐
        │            │            │
       DOM         Fetch       Storage
     Events       Network       APIs
```

JavaScript can interact with the HTML document, respond to user actions, communicate with servers, store certain information, and use many other browser capabilities.

---

## HTML, CSS, and JavaScript

A useful beginner mental model is:

```text
HTML        → Structure
CSS         → Presentation
JavaScript  → Behavior
```

Imagine a button.

HTML creates the button:

```html
<button id="saveButton">
  Save
</button>
```

CSS can make it look like a polished application control:

```css
#saveButton {
  padding: 10px 18px;
  border-radius: 8px;
}
```

JavaScript can give it behavior:

```javascript
const button = document.querySelector("#saveButton");

button.addEventListener("click", () => {
  console.log("Saved!");
});
```

Now all three technologies work together.

This relationship is one of the reasons JavaScript became so important to the web.

---

# What can JavaScript do in the browser?

Modern browser JavaScript can do a huge amount.

Let's look at some of the most important capabilities.

---

## Change the page

JavaScript can change existing content.

Suppose we have:

```html
<h1 id="title">Welcome</h1>
```

JavaScript can change it:

```javascript
const title = document.querySelector("#title");

title.textContent = "Welcome to ScriPAcademy";
```

The browser updates the page immediately.

You don't have to manually rewrite the HTML file.

---

## Create new elements

JavaScript can also create new HTML elements.

```javascript
const paragraph = document.createElement("p");

paragraph.textContent = "This paragraph was created dynamically.";

document.body.append(paragraph);
```

This ability is fundamental to interactive web applications.

For example, a social media application might receive a new comment from a server and create the corresponding UI element dynamically.

---

## Change styles and classes

JavaScript can interact with CSS as well.

For example:

```javascript
document.body.classList.add("dark");
```

If your CSS contains:

```css
.dark {
  background: #111;
  color: white;
}
```

the page changes appearance.

In real applications, it's usually better to let CSS handle the actual styling and use JavaScript to change classes or state.

For example:

```javascript
document.body.classList.toggle("dark");
```

This is the basic idea behind many theme-switching systems.

---

## React to user actions

Web pages aren't static documents anymore.

Users interact with them constantly.

JavaScript can respond to events such as:

* clicks
* keyboard input
* mouse movement
* pointer movement
* scrolling
* form submission
* touch interactions
* drag and drop
* focus changes

For example:

```javascript
button.addEventListener("click", () => {
  console.log("The user clicked the button.");
});
```

This is the foundation of interactive interfaces.

---

# A simple real-world example

Imagine a login page.

The user enters:

```text
Email: omkar@example.com
Password: ********
```

and presses **Login**.

JavaScript might:

1. Detect the form submission.
2. Read the entered values.
3. Perform basic client-side validation.
4. Send a request to the server.
5. Wait for the response.
6. Show an error or redirect the user.

The interaction might look like this:

```text
User
 ↓
Login form
 ↓
JavaScript
 ↓
HTTP request
 ↓
Server
 ↓
Database / authentication system
 ↓
Server response
 ↓
JavaScript
 ↓
Updated interface
```

This is the basic architecture behind countless web applications.

---

# JavaScript can communicate with servers

Modern websites rarely contain all their data inside the HTML document.

Applications constantly communicate with servers.

JavaScript can make network requests using APIs such as `fetch()`.

For example:

```javascript
const response = await fetch("/api/users");

const users = await response.json();

console.log(users);
```

A server might return:

```json
[
  {
    "name": "Aarav",
    "age": 21
  },
  {
    "name": "Riya",
    "age": 20
  }
]
```

JavaScript can then use that information to update the interface.

This is how applications can load:

* user profiles
* products
* messages
* notifications
* search results
* course information
* dashboards
* comments

without necessarily reloading the entire page.

---

# What is AJAX?

You may encounter the term **AJAX** in older documentation.

AJAX originally stood for:

**Asynchronous JavaScript and XML**

The name comes from an older style of communicating with servers.

Today, modern applications commonly use JSON instead of XML:

```javascript
const response = await fetch("/api/products");

const products = await response.json();
```

The underlying idea remains important:

> JavaScript can communicate with a server without requiring a traditional full-page reload for every interaction.

---

# JavaScript can store data in the browser

Browsers provide several mechanisms for storing data.

One simple example is `localStorage`.

```javascript
localStorage.setItem("theme", "dark");
```

Later:

```javascript
const theme = localStorage.getItem("theme");

console.log(theme);
```

A website could use this to remember something such as:

```text
User chooses dark mode
        ↓
JavaScript saves preference
        ↓
User closes browser
        ↓
User returns later
        ↓
JavaScript reads preference
        ↓
Dark mode is restored
```

Other browser storage technologies include:

* `sessionStorage`
* IndexedDB
* cookies

Each has different characteristics and use cases.

---

# JavaScript can interact with browser APIs

The browser gives JavaScript access to many APIs.

For example:

```text
DOM API
Fetch API
Storage APIs
History API
URL API
WebSocket API
Clipboard API
Canvas API
Geolocation API
Notification API
Web Workers
IndexedDB
```

These aren't all part of the core JavaScript language itself.

They are capabilities provided by the web platform.

This distinction is worth remembering.

For example:

```javascript
document.querySelector(...)
```

isn't simply "JavaScript magically knowing about HTML."

The browser provides the `document` object and DOM APIs.

---

# Browser security

If JavaScript can modify webpages, access network resources, use storage, and communicate with devices, an obvious question appears:

**What stops a malicious website from abusing these abilities?**

The browser's security model.

Browser JavaScript is intentionally restricted.

These restrictions are not weaknesses in JavaScript.

They are necessary to make the web safe.

Imagine visiting an ordinary website and the page could execute something like:

```text
Read your private files
Read your banking information
Access your saved passwords
Turn on your microphone
Read another website's private data
Delete files from your computer
Run arbitrary programs
```

The web would be completely unsafe.

Browsers therefore place strong boundaries around websites.

---

# What can't ordinary browser JavaScript do?

A normal webpage cannot simply access arbitrary files on your computer.

For example, a webpage cannot casually execute:

```javascript
readFile("C:/Users/Omkar/Documents/passwords.txt");
```

and obtain the contents.

Instead, browsers provide controlled mechanisms for working with files.

For example:

```html
<input type="file" id="fileInput">
```

Then:

```javascript
const input = document.querySelector("#fileInput");

input.addEventListener("change", () => {
  const file = input.files[0];

  console.log(file.name);
});
```

The user explicitly selected the file.

That distinction is fundamental:

```text
Website silently accessing files
        ❌

User selects a file
        ↓
Browser gives controlled access
        ✅
```

---

# Camera and microphone access

Modern browsers can interact with devices such as cameras and microphones.

But sensitive capabilities require permission.

For example:

```javascript
const stream = await navigator.mediaDevices.getUserMedia({
  video: true
});
```

The browser can ask the user whether the website is allowed to access the camera.

This permission system exists for the same reason as filesystem restrictions:

**the browser must protect the user from untrusted websites.**

---

# The Same-Origin Policy

One of the most important browser security concepts is the **Same-Origin Policy**.

Imagine you are logged into your bank:

```text
https://bank.example
```

Then you open another website:

```text
https://random-site.example
```

You obviously don't want the second website to freely inspect the private information inside your bank page.

The browser therefore separates websites into security boundaries called **origins**.

An origin is determined by:

```text
scheme + host + port
```

For example:

```text
https://example.com:443
```

is an origin.

A different scheme, host, or port can mean a different origin.

---

# Why does Same-Origin Policy matter?

Imagine a malicious website:

```text
https://evil.example
```

and your banking website:

```text
https://bank.example
```

Without browser security, malicious JavaScript could potentially attempt to inspect sensitive information from the banking site.

Same-Origin Policy helps prevent this kind of cross-origin access.

It is one of the foundations of browser security.

---

# What is CORS?

Sooner or later, you'll encounter **CORS**.

CORS stands for:

**Cross-Origin Resource Sharing**

Suppose your application has:

```text
Frontend
https://app.example.com

API
https://api.example.com
```

These are different origins.

The API server can explicitly tell the browser which origins are allowed to access certain resources.

For example, a server may return a header such as:

```http
Access-Control-Allow-Origin: https://app.example.com
```

The important idea is:

> Cross-origin access isn't simply "allowed" or "forbidden forever". Servers can explicitly participate in controlled cross-origin communication.

You'll learn CORS in much more detail when you study HTTP and APIs.

---

# Different browser tabs are isolated

Suppose you have:

```text
Tab A
https://my-app.com

Tab B
https://bank.example
```

JavaScript running on `my-app.com` cannot simply reach into the banking tab and inspect everything inside it.

Again, this is intentional.

Web applications can communicate in controlled ways using mechanisms such as:

```text
postMessage
Broadcast Channel
Server communication
Shared browser mechanisms
```

but these mechanisms follow security rules.

---

# JavaScript engines

How does the browser actually execute JavaScript?

The browser contains a **JavaScript engine**.

The engine is the software responsible for understanding and executing JavaScript code.

Different environments use different engines.

Some well-known examples are:

| Engine         | Commonly associated with               |
| -------------- | -------------------------------------- |
| V8             | Chrome and Chromium-based environments |
| SpiderMonkey   | Firefox                                |
| JavaScriptCore | Safari/WebKit                          |

You don't need to memorize every engine.

The important concept is:

```text
JavaScript source code
        ↓
JavaScript engine
        ↓
Execution
```

---

# What does a JavaScript engine do?

Consider:

```javascript
const total = 10 + 20;

console.log(total);
```

The engine has to understand the structure and meaning of this code.

A simplified model looks like:

```text
Source code
     ↓
Parsing
     ↓
Internal representation
     ↓
Execution
     ↓
Optimization
```

Real JavaScript engines are considerably more sophisticated.

They can:

* parse source code
* build internal representations
* execute code
* optimize frequently executed code
* monitor how code behaves
* compile optimized code
* deoptimize when assumptions change
* manage memory
* perform garbage collection

The exact implementation differs between engines.

---

# Is JavaScript interpreted or compiled?

This is a common interview and beginner question.

You may hear:

> "JavaScript is interpreted."

You may also hear:

> "JavaScript is compiled."

Both statements can be misleading when treated as complete explanations.

Modern JavaScript engines use sophisticated execution strategies, including interpretation and **Just-In-Time (JIT) compilation**.

A simplified idea is:

```text
JavaScript
    ↓
Engine analyzes it
    ↓
Engine executes it
    ↓
Frequently executed code is identified
    ↓
Engine can optimize it
    ↓
Optimized code executes efficiently
```

So saying simply:

> "JavaScript is only interpreted"

doesn't accurately describe modern engines.

---

# What is a runtime?

A **runtime** is the environment in which your JavaScript program executes.

A runtime usually consists of:

```text
JavaScript engine
        +
Environment-specific APIs
        +
Runtime behavior
```

For example, a browser gives JavaScript access to things such as:

```javascript
window
document
navigator
fetch
localStorage
WebSocket
```

Node.js provides different capabilities, including filesystem and process APIs.

Therefore:

```text
Same JavaScript language
        ↓
Different runtime
        ↓
Different available APIs
```

---

# Browser JavaScript vs Node.js

This distinction becomes especially important when you start learning backend development.

In the browser:

```javascript
document.querySelector("button");
```

works because the browser provides the DOM.

In Node.js:

```javascript
import fs from "node:fs";

const content = fs.readFileSync("notes.txt", "utf8");

console.log(content);
```

works because Node.js provides filesystem APIs.

A simplified comparison:

| Capability       | Browser    | Node.js            |
| ---------------- | ---------- | ------------------ |
| JavaScript       | Yes        | Yes                |
| DOM              | Yes        | No by default      |
| Browser events   | Yes        | No                 |
| Filesystem       | Restricted | Yes                |
| Server processes | No         | Yes                |
| HTTP/networking  | Yes        | Yes                |
| Browser storage  | Yes        | No as browser APIs |

This doesn't mean Node.js is a different language.

It means the **environment is different**.

---

# A useful mental model

Whenever you're unsure whether JavaScript can do something, ask:

> **Is this a JavaScript language feature, or is it an API provided by the environment?**

For example:

```javascript
const numbers = [1, 2, 3];
```

Arrays are part of JavaScript.

But:

```javascript
document.querySelector("button");
```

uses a browser API.

And:

```javascript
fs.readFileSync(...)
```

uses a Node.js API.

This distinction will save you a lot of confusion later.

---

# JavaScript isn't just for webpages

Because JavaScript became popular in browsers, people sometimes think:

> "JavaScript is a web-page scripting language."

Historically, that's understandable.

Today, however, JavaScript is used in many areas.

For example:

```text
Frontend applications
        ↓
React / Vue / Angular / etc.

Backend applications
        ↓
Node.js / other runtimes

Command-line tools
        ↓
JavaScript runtimes

Desktop applications
        ↓
JavaScript-based frameworks

Development tooling
        ↓
Build tools / testing / automation
```

The language is much more capable than its original use case suggests.

---

# A real-world scenario: an e-commerce website

Imagine you're shopping online.

You open a product page.

The browser loads:

```text
HTML
CSS
JavaScript
```

You click:

**Add to cart**

JavaScript responds to the click.

It might update the interface immediately:

```text
Cart: 0 items
        ↓
User clicks Add to cart
        ↓
Cart: 1 item
```

The application may also send a request to the server:

```text
Browser
   ↓
POST /api/cart
   ↓
Server
   ↓
Database
```

The server responds:

```json
{
  "success": true,
  "items": 1
}
```

JavaScript receives the response and updates the interface.

The user experiences this as one simple interaction.

Underneath, several systems are working together.

---

# A real-world scenario: a chat application

Consider a chat application.

You type:

```text
Hey!
```

and press Send.

A simplified flow might be:

```text
User types message
        ↓
JavaScript detects interaction
        ↓
Message is sent to server
        ↓
Server processes message
        ↓
Server distributes message
        ↓
Another browser receives it
        ↓
JavaScript updates the interface
```

Technologies such as WebSockets can allow applications to maintain real-time communication.

Again, JavaScript isn't simply "changing HTML".

It's participating in an application architecture.

---

# A real-world scenario: an e-learning platform

Imagine you're using ScriPAcademy.

You open a JavaScript lesson.

The page might contain:

```text
HTML
 ├── Lesson content
 ├── Navigation
 ├── Code examples
 └── Exercises

CSS
 ├── Typography
 ├── Layout
 ├── Responsive design
 └── Theme

JavaScript
 ├── Sidebar interactions
 ├── Progress tracking
 ├── Search
 ├── Code copying
 ├── Quizzes
 ├── Tabs
 └── API communication
```

When you click **Mark as complete**, the application might do:

```text
Click
  ↓
JavaScript event handler
  ↓
API request
  ↓
Server
  ↓
Database updates progress
  ↓
Response
  ↓
JavaScript updates UI
```

This is the kind of system JavaScript can become part of.

---

# JavaScript and asynchronous programming

Web applications frequently need to wait for things.

For example:

```text
Network request
File operation
Timer
Database request
User interaction
```

Consider:

```javascript
const response = await fetch("/api/courses");
```

The browser may need to wait for the server.

JavaScript provides mechanisms for handling such operations without making the entire interface unusable.

You will eventually learn:

* callbacks
* Promises
* `async`
* `await`
* the event loop

For now, understand the basic idea:

```text
Start operation
      ↓
Runtime handles waiting
      ↓
JavaScript can continue other work
      ↓
Operation finishes
      ↓
Result becomes available
      ↓
JavaScript handles the result
```

This is one of the most important concepts in modern JavaScript.

---

# A first look at the event loop

Consider this:

```javascript
console.log("A");

setTimeout(() => {
  console.log("B");
}, 0);

console.log("C");
```

The output is:

```text
A
C
B
```

Why doesn't `B` appear immediately?

Because `setTimeout()` doesn't mean:

> "Interrupt the current JavaScript execution and run this function right now."

Instead, it schedules the callback to run later according to the runtime's event-loop mechanism.

You'll study this deeply later.

For now, remember:

> **JavaScript execution and asynchronous operations are coordinated through the runtime and event loop.**

---

# JavaScript is dynamically typed

JavaScript is a dynamically typed language.

For example:

```javascript
let value = 42;

value = "hello";

value = true;
```

The variable can refer to values of different types during its lifetime.

Some important JavaScript types include:

```text
string
number
bigint
boolean
undefined
null
symbol
object
```

For example:

```javascript
const name = "Omkar";
const age = 20;
const loggedIn = true;
const nothing = null;

let unknown;
```

Don't worry about memorizing every detail yet.

We'll explore values and types properly in later lessons.

---

# JavaScript supports different programming styles

JavaScript is a **multi-paradigm** language.

You can write code using different programming approaches.

For example, an imperative approach:

```javascript
let total = 0;

for (const price of prices) {
  total += price;
}
```

A functional approach:

```javascript
const total = prices.reduce(
  (sum, price) => sum + price,
  0
);
```

And an object-oriented approach:

```javascript
class User {
  constructor(name) {
    this.name = name;
  }

  greet() {
    return `Hello, ${this.name}`;
  }
}
```

You don't need to choose a single style immediately.

As you become more experienced, you'll learn when different approaches are useful.

---

# Languages built on or targeting JavaScript

JavaScript's syntax and dynamic nature don't suit every developer or every project.

As a result, several languages and tools have been created that can ultimately target JavaScript.

The most important modern example is **TypeScript**.

---

# TypeScript

TypeScript builds on JavaScript by adding a static type system and additional developer tooling.

JavaScript:

```javascript
function add(a, b) {
  return a + b;
}
```

TypeScript:

```typescript
function add(a: number, b: number): number {
  return a + b;
}
```

TypeScript source is transformed into JavaScript for typical browser and runtime execution.

The important lesson is:

> **TypeScript does not remove the need to understand JavaScript.**

In fact, the better your JavaScript foundation, the easier TypeScript becomes.

---

# Should you learn JavaScript before TypeScript?

For most beginners, yes.

A sensible progression is:

```text
JavaScript fundamentals
        ↓
Modern JavaScript
        ↓
DOM and browser APIs
        ↓
Asynchronous JavaScript
        ↓
Modules
        ↓
TypeScript
        ↓
Frameworks
```

You don't need to follow this sequence perfectly, but learning the language underneath the abstractions makes everything easier.

---

# Why is JavaScript so successful on the web?

JavaScript has a unique combination of strengths.

### It integrates directly with HTML and CSS

JavaScript can interact with the document and browser.

### It is supported by major browsers

Users don't normally need to install a separate JavaScript interpreter before visiting a website.

### It is capable of handling complex applications

The language and ecosystem have grown enormously.

### It works outside the browser

The same language can also be used on servers and in many development environments.

### It has a massive ecosystem

Developers have built libraries, frameworks, runtimes, tools, testing systems, package managers, and countless applications around it.

---

# JavaScript has evolved far beyond its original purpose

JavaScript started with a relatively simple goal:

> Make web pages interactive.

Today, it can participate in systems such as:

```text
Interactive websites
Single-page applications
Real-time applications
REST APIs
Backend services
Command-line tools
Desktop applications
Mobile applications
Automation
Testing
Developer tooling
```

The language grew because the web grew.

---

# A note about frameworks

Once you start learning JavaScript, you'll quickly hear names such as:

* React
* Vue
* Angular
* Next.js
* Express
* Node.js
* TypeScript

It can be tempting to immediately jump into one of them.

But frameworks are abstractions built on top of fundamental programming concepts.

For example, if you understand:

```text
functions
objects
arrays
events
state
modules
asynchronous programming
```

then frameworks become much easier to understand.

Without those fundamentals, frameworks can feel like magic.

So don't worry about learning everything at once.

First make JavaScript itself comfortable.

---

# A small experiment

If you have a browser open right now, you can experiment with JavaScript directly.

Open Developer Tools and go to the **Console**.

Try:

```javascript
2 + 2
```

Then:

```javascript
const name = "JavaScript";

console.log(`Hello, ${name}!`);
```

Now try interacting with the page:

```javascript
document.body.style.fontFamily = "system-ui";
```

You can even temporarily change the page's appearance:

```javascript
document.body.style.background = "black";
document.body.style.color = "white";
```

You have just used JavaScript to interact with a real webpage.

---

# One important security lesson

Never assume that code running in the browser is secret.

Anything delivered to the browser can potentially be inspected by the user.

For example, this is **not** a safe place for a secret API key:

```javascript
const secretApiKey = "my-super-secret-key";
```

If the browser receives it, the user can potentially see it.

Sensitive information belongs on the server.

A useful rule is:

```text
Browser
  ↓
Public / user-controlled environment

Server
  ↓
Sensitive operations and secrets
```

Client-side JavaScript can improve user experience, but the server must enforce security.

---

# Common misconceptions

## "JavaScript is Java for websites."

No.

They are separate languages.

---

## "JavaScript only changes HTML."

No.

JavaScript is a complete programming language. DOM manipulation is only one of its uses.

---

## "JavaScript only works in browsers."

No.

It can run in many environments, including server-side runtimes.

---

## "Node.js is another programming language."

No.

Node.js is a JavaScript runtime.

---

## "JavaScript is always interpreted."

That is an oversimplification.

Modern JavaScript engines use sophisticated execution and compilation techniques.

---

## "Browser JavaScript can access my entire computer."

No.

Browsers intentionally restrict sensitive capabilities.

---

## "CORS is a server security system that replaces Same-Origin Policy."

Not exactly.

Same-Origin Policy is a fundamental browser security rule. CORS is a mechanism that allows servers to explicitly control certain cross-origin requests.

---

## "If I validate something in JavaScript, my server is secure."

No.

Client-side validation can be bypassed.

The server must validate and authorize requests independently.

---

# The bigger picture

At this point, you can think about JavaScript in four layers:

```text
Your JavaScript code
        ↓
JavaScript language
        ↓
JavaScript runtime
        ↓
Environment APIs
```

For a browser:

```text
Your code
   ↓
JavaScript
   ↓
Browser runtime
   ↓
DOM / Fetch / Storage / Events / Web APIs
```

For Node.js:

```text
Your code
   ↓
JavaScript
   ↓
Node.js runtime
   ↓
Filesystem / Network / Processes / Server APIs
```

The language is still JavaScript.

The environment changes what the program can interact with.

---

# What you should remember

JavaScript began as a way to make web pages interactive, but it has grown into a general-purpose programming language used across many kinds of software.

The most important ideas from this lesson are:

* JavaScript is a programming language.
* ECMAScript is the specification that defines the language.
* JavaScript and Java are different languages.
* JavaScript can run in browsers and other runtimes.
* A JavaScript engine executes JavaScript code.
* A runtime provides the environment in which JavaScript operates.
* Browsers provide APIs such as the DOM, Fetch, Storage, and many others.
* JavaScript can modify webpages and respond to user interactions.
* JavaScript can communicate with servers.
* Browser JavaScript is restricted by security rules.
* The Same-Origin Policy protects data between different origins.
* CORS provides controlled cross-origin resource sharing.
* Node.js is a JavaScript runtime, not a different language.
* Modern JavaScript engines use sophisticated execution and optimization techniques.
* JavaScript is much more than DOM manipulation.
* TypeScript builds on JavaScript.
* Understanding JavaScript fundamentals makes frameworks much easier to learn.

---

# Where do we go from here?

Now that you understand **what JavaScript is and where it fits**, the next step is to start working with the language itself.

We'll begin with the building blocks every JavaScript program uses:

```text
Values
   ↓
Variables
   ↓
Data types
   ↓
Operators
   ↓
Expressions
   ↓
Conditions
   ↓
Loops
   ↓
Functions
```

Once these concepts become comfortable, you'll be able to start writing programs rather than simply reading JavaScript syntax.

> **The goal isn't to memorize JavaScript. The goal is to learn how to think in JavaScript.**

```

This is the style I would use for **ScriPAcademy going forward**: textbook-like, explanatory, polished, and with formatting serving the learning experience rather than the other way around.
```
