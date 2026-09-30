# Semantic HTML

**By Hassan Moharrem**

## What is HTML?

HTML stands for HyperText Markup Language.

It is used to organize the content of a webpage.

It tells the browser what parts of the page things are, like:
- headings
- paragraphs
- links
- images
- lists
- navigation
- sections

A basic HTML page might look like:
```html
<!doctype html>
<html lang="en">
  <head>
    <title>My Website</title>
  </head>

  <body>
    <h1>My Website</h1>

    <p>This is my first web page.</p>
  </body>
</html>
```

## What is Semantic HTML?

Semantic HTML means using HTML tags that describe what the content is used for.

For example:
```html
<header>
```
tells the browser that the content is the header of the page.

This is more descriptive than using:
```html
<div>
```
for everything.

Semantic HTML makes the structure of a web page easier to understand.

## Semantic vs Non-Semantic HTML

A non-semantic element does not clearly explain what its content is used for.

Example:
```html
<div>
  <div>My Website</div>
</div>
```
The browser and developer cannot easily tell what each 'div' represents.

A semantic version would be:
```html
<header>
  <h1>My Website</h1>
</header>
```
This makes it clear that the content is the page header.

## Why use Semantic HTML?

Semantic HTML can make a website easier to:
- understand
- organize
- maintain
- navigate
- use with accessibility tools

It also helps developers understand the purpose of different parts of a page.

## Common Semantic Elements

Some common semantic HTML elements are:

| Element | Purpose |
|---|---|
| '<header> | Top section of a page or section |
| '<nav> | Navigation links |
| '<main> | Main content of the page |
| '<section> | A group of related content |
| '<article> | Independent content |
| '<aside> | Extra or related information |
| '<footer> | Bottom section of a page |
| '<figure> | Image, diagram, or similar content |
| '<figcaption> | Caption for a figure |
| '<address> | Contact information |

## The Header Element

The '<header>' element is usually used for introductory content.

Example:
```html
<header>
  <h1>My Portfolio</h1>
  <p>Welcome to my website.</p>
</header>
```

A header may contain:
- a page title
- a logo
- an introduction
- navigation

## The Navigation Element

The '<nav>' element is used for navigation links.

Example:
```html
<nav>
  <a href="index.html">Home</a>
  <a href="about.html">About</a>
  <a href="contact.html">Contact</a>
</nav>
```

## The Main Element

The '<main>' element contains the main content of the page.

Example:
```html
<main>
  <h2>About Me</h2>

  <p>
    This is the main content of the website.
  </p>
</main>
```
There should normally only be one main content area on a page.

## The Section Element

The '<section>' element is used to group related content.

Example:
```html
<section>
  <h2>My Projects</h2>

  <p>
    These are some projects I have worked on.
  </p>
</section>
```
A section should usually have a heading that explains what the section is about.

## The Article Element

The '<article>' element is used for content that can stand on its own.

Examples could include:
- a blog post
- a news story
- a forum post
- a product description

Example:
```html
<article>
  <h2>Learning Django</h2>

  <p>
    Today I learned how to create a Django project.
  </p>
</article>
```

## The Aside Element

The '<aside>' element is used for information that is related to the main content but is not part of the main topic.

Example:
```html
<aside>
  <h2>Helpful Tip</h2>

  <p>
    Remember to save your work before closing VS Code.
  </p>
</aside>
```

## The Footer Element

The '<footer>' element is usually used near the bottom of a page or section.

Example:
```html
<footer>
  <p>Created by Hassan Moharrem</p>
</footer>
```

A footer may contain:
- author information
- copyright information
- contact information
- extra links

## Headings

HTML has six heading levels:
```html
<h1>Main Heading</h1>

<h2>Section Heading</h2>

<h3>Smaller Section Heading</h3>

<h4>Heading Level 4</h4>

<h5>Heading Level 5</h5>

<h6>Heading Level 6</h6>
```

Headings should be used in a clear order.

For example:
```html
<h1>My Website</h1>

<h2>About Me</h2>

<h3>Education</h3>

<h3>Work Experience</h3>

<h2>Projects</h2>
```
This gives the page a clear structure.

## Paragraphs

Paragraphs use the '<p>' element.

Example:
```html
<p>
  This is a paragraph of text.
</p>
```
Paragraphs should be used for normal written content instead of placing large amounts of text inside random 'div' elements.

## Lists

HTML includes ordered and unordered lists.

### Unordered List

Use '<ul>' when the order does not matter.

```html
<ul>
  <li>Python</li>
  <li>Django</li>
  <li>HTML</li>
</ul>
```
This normally appears as bullet points.

### Ordered List

Use '<ol>' when the order matters.

```html
<ol>
  <li>Open Powershell</li>
  <li>Activate the virtual environment</li>
  <li>Start the Django server</li>
</ol>
```
This normally appears as a numbered list.

## Links

Links use the '<a>' element.

Example 1:

```html
<a href="https://www.djangoproject.com/">
  Visit the Django website
</a>
```
The `href` tells the browser where the link should go.

Example 2:
```html
<a href="about.html">Read more about our project</a>
```

Example 3:
```html
<a href="about.html">Click here</a>
```
The first example gives the user more information about the link.

## Images

Images use the `<img>` element.

Example:
```html
<img
  src="django-logo.png"
  alt="Django logo"
>
```
The `src` tells the browser where the image is located.

The `alt` text describes the image.

Alternative text is important because a screen reader can read it for someone who cannot see the image.

## Figure and Figcaption

An image and its caption can be grouped together using `<figure>` and `<figcaption>`.

Example:
```html
<figure>
  <img
    src="django-page.png"
    alt="Django success page displayed in a browser"
  >

  <figcaption>
    Django development server running successfully.
  </figcaption>
</figure>
```

## Semantic HTML and Accessibility

Semantic HTML helps accessibility tools understand the page.

For example:
```html
<nav>
```
tells a screen reader that the section contains navigation.

```html
<main>
```
tells it where the main content begins.

```html
<footer>
```
tells it where the footer is.

Clear headings also help users move through a page more easily.

Instead of making something look like a heading using only bold text:
```html
<p><strong>My Projects</strong></p>
```

you can use a real heading:
```html
<h2>My Projects</h2>
```
The second version gives the heading meaning and not just a different appearance.

## Semantic HTML and CSS

HTML describes the structure and meaning of the page.

CSS controls how the page looks.

HTML Example:
```html
<header>
  <h1>My Website</h1>
</header>
```
HTML describes the content.

CSS Example:
```css
header {
  text-align: center;
  padding: 20px;
}
```
CSS can change how it looks.

## Semantic HTML With Bootstrap

Bootstrap can be used with semantic HTML.

For example, instead of:
```html
<div class="container">
  <div class="navbar">
    ...
  </div>
</div>
```

you can use:
```html
<header class="container">
  <nav class="navbar">
    ...
  </nav>
</header>
```
The Bootstrap classes still control the design, while the HTML elements describe what the content means.

## Example of a Semantic Web Page

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    >
    <title>My Portfolio</title>
  </head>

  <body>
    <header>
      <h1>My Portfolio</h1>
      <nav>
        <a href="#about">About</a>
        <a href="#projects">Projects</a>
        <a href="#contact">Contact</a>
      </nav>
    </header>

    <main>
      <section id="about">
        <h2>About Me</h2>
        <p>
          I am learning HTML, CSS, Bootstrap, Git, GitHub,
          Python, and Django.
        </p>
      </section>

      <section id="projects">
        <h2>Projects</h2>
        <article>
          <h3>Django Portfolio</h3>
          <p>
            This project uses Django to create a web application.
          </p>
        </article>
      </section>

      <aside>
        <h2>Current Tools</h2>
        <ul>
          <li>VS Code</li>
          <li>Git</li>
          <li>GitHub</li>
          <li>Django</li>
        </ul>
      </aside>
    </main>

    <footer id="contact">
      <p>
        Created by Hassan Moharrem
      </p>
    </footer>
  </body>
</html>
```
The page has a clear structure:
```text
header
│
├── heading
└── navigation

main
│
├── section
│   └── about content
│
├── section
│   └── article
│
└── aside

footer
```

## Div vs Semantic Elements

The `<div>` element is still useful.

A `div` is a general container that can group content together.

Example:
```html
<div class="container">
  <p>Some content</p>
</div>
```
The problem is not using `div`. The problem is using it when there is a better HTML element that explains what the content means.

For example, instead of:
```html
<div class="navigation">
  <a href="index.html">Home</a>
  <a href="about.html">About</a>
</div>
```

use:
```html
<nav>
  <a href="index.html">Home</a>
  <a href="about.html">About</a>
</nav>
```

## When Should I Use a Div?

Use a `<div>` when you need a general container and there is no more meaningful semantic element for it.

For example:
```html
<div class="container">
  <main>
    <h1>My Website</h1>
  </main>
</div>
```
Here, the `div` is mainly being used for layout while `<main>` explains what the content means.

## Common Problems

### Problem 1: Using Div for Everything

This works:
```html
<div>
  <div>My Website</div>

  <div>
    <a href="#">Home</a>
    <a href="#">About</a>
  </div>

  <div>
    Main content
  </div>
</div>
```
But the structure is not very clear.

A better version is:
```html
<header>
  <h1>My Website</h1>
  <nav>
    <a href="#">Home</a>
    <a href="#">About</a>
  </nav>
</header>
<main>
  <p>Main content</p>
</main>
```

### Problem 2: Using Headings Only for Size

For example, do not use:
```html
<h4>Main Website Title</h4>
```
just because the size looks good.

The main title should normally use:
```html
<h1>Main Website Title</h1>
```

CSS can be used later to change the size.

### Problem 3: Missing alt Text

Avoid:
```html
<img src="django.png">
```

Use:
```html
<img
  src="django.png"
  alt="Django development server success page"
>
```
The `alt` text helps users who use screen readers.

### Problem 4: Links With Unclear Text

Avoid:
```html
<a href="setup.html">Click here</a>
```

A better link is:
```html
<a href="setup.html">
  Read the Django setup instructions
</a>
```
This tells the user where the link will take them.

## Semantic HTML Checklist

When creating a web page, check whether:
- the page has a clear `<h1>`
- heading levels are organized
- navigation uses `<nav>`
- the main content uses `<main>`
- related content uses `<section>` where needed
- stand-alone content uses `<article>` where needed
- extra related information uses `<aside>` where needed
- the bottom section uses `<footer>` where appropriate
- images have useful `alt` text
- links clearly describe where they go
- lists use `<ul>` or `<ol>`
- `<div>` is not being used when a better semantic element exists

## Useful Semantic HTML Elements

| Element | Meaning |
|---|---|
| `<header>` | Introductory or top content |
| `<nav>` | Navigation |
| `<main>` | Main page content |
| `<section>` | Related group of content |
| `<article>` | Independent content |
| `<aside>` | Extra or related content |
| `<footer>` | Bottom or closing content |
| `<figure>` | Image or similar content |
| `<figcaption>` | Caption for a figure |
| `<h1>` to `<h6>` | Headings |
| `<p>` | Paragraph |
| `<ul>` | Unordered list |
| `<ol>` | Ordered list |
| `<li>` | List item |
| `<a>` | Link |
| `<img>` | Image |

## Example From My Bootstrap Page

My original page uses a main Bootstrap container:
```html
<div class="container">
```
Inside that page, I can use semantic elements to make the structure clearer.

For example:
```html
<div class="container">
  <header>
    <h1>Hello, GitHub! I'm NOT Maria.</h1>
    <p>
      This is my first web page using version control
      with Git and GitHub.
    </p>
  </header>

  <main>
    <section>
      <h2>Alert!</h2>
      <div class="alert alert-success">
        <strong>Success!</strong>
        You owe me 5 grand.
      </div>
    </section>

    <section>
      <h2>Pick an Option</h2>
      <ol>
        <li>
          Give me the 5 grand you owe me
        </li>
        <li>
          Don't give me the 5 grand you owe me
        </li>
        <li>
          Installments
        </li>
      </ol>
    </section>
  </main>

  <footer>
    <p>
      Created by Hassan Moharrem
    </p>
  </footer>
</div>
```

## Reliable Resources

- [MDN Web Docs: HTML](https://developer.mozilla.org/en-US/docs/Web/HTML)
- [MDN Web Docs: HTML Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements)
- [W3C Web Accessibility Initiative](https://www.w3.org/WAI/)
