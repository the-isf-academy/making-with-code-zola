---
title: 3.A.0 HTML
---

# Intro to HTML

As frontend programmers, you'll be getting very familiar with the language for writing web pages: *HTML* or *hyper text markup language*.
HTML is a langauge, but it's not a programming language like Python. Instead, it's a language used by your web browwser to determine how 
to display web content. You've actually already used a langauge like this every time you've read a page on this website or written your
self-assement for a project – MarkDown in a language for rendering content too.

On the internet, HTML runs deep. All webpages are just HTML documents send to your computer and interpreted by your web browser.

## A. HTML Basics
HTML documents are made up of different nested elements. This just means that some HTML elements can contain other elements (like a box
inside of a box).

### The Monster (HTML) Mash

{{< write-action >}} To help get a sense of this, work through the following slideshow to make monsters HTML style:
{{< gdocs src="https://docs.google.com/presentation/d/e/2PACX-1vRYznPe1JhFJ6KoHe5RKLG_vlu3Ujr8l9YyDL1IstA9pTd1xR-7dAaASor4qLXBYth7WORVITBap4oH/embed?start=false&loop=false&delayms=5000" >}}

### HTML Everywhere
Web programmers make web sites just like you made the monsters above (just with different elements. Let's try to figure out what elements websites are
made of.

{{< code-action >}} Go to any website (even this one) and open the inspector by right clicking on the page and selecting "Inspect Element". This
will open a new panel of your browser to reveal the HTML that makes up the page you're currently viewing.

{{< write-action >}} Make a table of HTML elements that sepatates them by whether they can contain other elements. Use the table at the end
of the monster slideshow above as an example.

{{< look-action >}} Once you've tried categorizing the elements you found, check out [this reference guide](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
to see all of the kinds of elements you can include in webpages.

### HTML For Django
That's a lot of elements! While it is useful to eventually understand and be able to use them all, for now we'll let Django handle a lot
of what we do with HTML. For our purposes, the following HTML elements will be most important:

* `<div>` - All "blocks" of content on your page should be wrapped in a `<div>` tag. If elements beside each other are related in any way (i.e.
parts of a form, paragraphs in a block of text, a section of headers and text, etc.) you should put all of that content in a div. Further, you
will probably end up putting your divs inside other divs (i.e. a div containing many other divs that contain different sections of your homepage).
It's important that you use divs frequently because they will be the most useful way to add style to related elements.
* **text elements** - these will make up the bulk of the content of your web pages.
    * headers (i.e. `<h1>`)
    * paragraphs (`<p>`)
* **structural elements** - this helps quickly organize information on your web pages.
    * ordered lists (`<ol>`)
    * unordered lists (`<ul>`)
    * tables (`<table>`)
    * forms (`<form>`)
* **style elements** - these add different kinds of styles to your web content. You can define what the style actually looks like for these
elements, but the idea behind them is the same across the internet.
    * links (`<a>`)
    * strong (usually **bolded**) text (`<strong>`)
    * idiomatic (usually *italicized* text (`<i>`)
    * line break (`<br>`)

## B. Getting Started on the Todo App

### App overview

### Example

### Now you try

