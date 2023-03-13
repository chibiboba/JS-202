# Lesson 1

# Welcome

Welcome to the first Front-end course at Launch School! This course introduces you to the basics of HTML and CSS. Along the way, we'll explore the tools and technologies you will use throughout the front-end section of the curriculum.

## A Few Words About Mastery and This Course

When you visit a website, you see the result of HTML and CSS coding. Without HTML or something like it, the Web wouldn't exist; there would be no way to display content. Without CSS, pages would be dull, lifeless, and primitive. If you were on the Internet in the 1990s, you probably remember how crude websites looked. They weren't pretty, and often they did not work across different browsers. Before CSS and the browser advances we enjoy today, HTML development was the Wild West, with no rules to guide developers. Different browsers - sometimes even different versions of a browser - displayed elements in different ways, and there was no way to normalize the appearance or tailor the presentation to your needs. To some extent, these differences continue today, but, thanks to standardization and CSS, most are subtle and easy to work around.

Most front-end jobs expect that you know HTML and CSS well. However, it's not essential for most engineering jobs. Unlike every other topic we cover at Launch School, employers seldom quiz engineering applicants on HTML and CSS. They will quiz you on almost everything else, but not HTML and CSS.

In light of this, we don't expect the same degree of mastery in this course that we look for elsewhere. In fact, there is no assessment.

That said, we still recommend trying to master the material as much as possible, but don't get bogged down trying to do so. There's a lot of content, but familiarity will almost always be enough to help you find the information you need.

## Where to Find More Information

Engineers sometimes need to do front-end work, but you don't always need to be an HTML and CSS expert. In fact, you can do almost everything with a small portion of the features available. We'll take advantage of that in this course, and focus on the most used parts of HTML and CSS.

We're going to leave material out. The best time to learn more about HTML and CSS is when you find that you need a feature you've never used. We intend to make use of this, and we'll expect you to learn details on your own, sometimes without telling you. Don't panic, but be ready to find information.

[Google](https://google.com/) (or whatever search engine you prefer) is your leading resource when you have a problem or question. Often, all you have to do is ask a question, and one of the top results will provide an answer. For example, try "How do I create superscripts in HTML?" It's also helpful to provide `mdn` or `w3c` in your search to access two of the most useful resources:

- The [Mozilla Developer Network](https://developer.mozilla.org/), or **MDN**, is perhaps the best resource for extensive and accessible information about the Web, specifically HTML, CSS, and JavaScript. In fact, it's so good that we suggest that you get in the habit of adding **mdn** to your searches. For instance, `mdn form tag` will find the MDN documentation on the `<form>` tag. If MDN fails to help, a more global search will often turn up a video, tutorial, or Stack Overflow question that provides all the information you need.

  MDN is free and continually updated. Mozilla, the makers of the Firefox Web browser, maintains the site. MDN isn't official, but it's up-to-date, generally accurate, and easier to use than the official specification documents at W3C.

- The [W3C](http://www.w3.org/), the World Wide Web Consortium, is the standards body for Web technologies, so it serves as the official source of information for HTML and CSS. The content is often dry and academic, but it's an essential resource that you shouldn't ignore. You can add the word **w3c** to your searches to find W3C information about specific topics, e.g., `w3c textarea tag`.

- In mid-2019, W3C announced that it would collaborate with the Web Hypertext Application Technology Working Group, [WHATWG](https://whatwg.org/), on future HTML and DOM standards, effectively giving up control over those standards. The effects of this collaboration are still unclear at this time. However, it may lead to more rapid development of HTML and DOM standards. The most recent standards documents for the HTML and browser DOM standards can be located at the WHATWG site:

  - [HTML Standard](https://html.spec.whatwg.org/multipage/)
  - [DOM Standard](https://dom.spec.whatwg.org/)

If you omit "mdn" or "w3c" from the search query, the first result is often from a website called W3 Schools. Material from this site is frequently outdated and incorrect. We suggest that you steer clear of those results.

Don't confuse W3 Schools with W3C; W3C has no affiliation with W3 Schools.

# Introduction

In this lesson, we'll take a brief, fast-paced tour of both HTML and CSS. You'll learn about the most used HTML tags, as well as how to apply some of the simplest and oft-used CSS properties. Along the way, you'll learn how to write coherent HTML and CSS, and then build two simple web pages, one which you will do on your own (but with a bit of help).

Please follow along with the text, videos, and external reading. When you see code examples in the assignments, you should write that code in files on your development system and display them in your browser so you can see it in operation. Don't copy and paste the code; write it out line-by-line. Yes, typing is tedious, but it helps train your "muscle memory" and helps solidify the concepts in your mind. It also provides experience using the syntax that you'll use when writing HTML and CSS.

Some project videos in this course differ from the assignments and completed projects. It's not always possible to update videos when we become aware of differences or make changes, so the videos become outdated with time. Where there are discrepancies, the written material, design files, and completed projects take precedence over the videos.

This lesson has more projects and practice problems than most to give you plenty of practice as you start out. Most remaining lessons have fewer practice opportunities until we get near the end of the course.

## What to Focus On

Understanding HTML and CSS, and being proficient enough to construct attractive web pages, either from scratch or a provided design, is a fundamental skill for web developers of all kinds. However, not everybody must be an expert; in fact, few are. Thus, our goal is to provide a solid foundation to get you started, not to make you an expert.

Use the following guidelines to focus your study and practice as you move through this lesson:

### Vocabulary

As with everything else in the developer's world, there's a wealth of specialized terminology you must learn to converse with other developers and designers. The vocabulary you need here, though, is small compared to most languages, and most terms are easy to learn. In particular, you should become comfortable with:

- element and tag
- self-closing tag
- document type definition (DOCTYPE, DTD)
- attribute
- selector
- property
- id, class, and name

### The Difference Between HTML and CSS

These two technologies are so intertwined in contemporary Web pages that it seems like they do the same thing, and that they are dependent on each other. However, they are distinct and independent with different purposes. 

- HTML provides the structure and content of a web page; CSS describes the appearance, or presentation, of the page. 

There is a bit of overlap that can lead to some confusion: CSS can dictate the apparent structure, while HTML can inform the browser of some presentation elements.

### HTML and CSS Syntax

HTML and CSS both have simple syntax; you can learn nearly all you need for each language in a few minutes. Take the time you need to learn it well, and both HTML and CSS will become routine in no time.

For the most part, you shouldn't worry about the specific tags, attributes, selectors, and properties yet. Instead, focus on how to put these items together to create well-formed HTML and CSS. The rest will come with time and practice.

### Structure of a Web Page

All web pages start with some routine code that defines the basic layout of the document. It includes a DOCTYPE (we'll explain this later), an `<html>`, `<head>`, and `<body>` element, and a few other tags in the `<head>` section. Learn what this **boilerplate** code does, and how to use it in your web pages.

### Basic HTML Elements

The best way to learn HTML is to use it. The more you use it, the less often you'll need to refer to the documentation; however, you'll probably never learn it all, so don't try.

Start by learning to use the `<p>` (paragraph), `<a>` (anchor), and `<h1>`-`<h6>` elements. 

- Paragraphs are the primary organizational construct for text on web pages.
- anchors represent links to other pages.
- headings occur on most pages. 

These elements are so common that you want to learn them as soon as possible, so go ahead and memorize them.

You should also become familiar with these elements:

- `<em>`, `<strong>`
- `<header>`, `<main>`
- `<article>`, `<section>`, `<aside>`
- `<div>` and `<span>`

You don't have to know them by heart; you will remember them through repeated use.

### Using CSS With HTML

Become familiar with the three ways to use CSS in an HTML document: inline, internal, and external. For now, you should learn to use the `<style>` tag to provide internal CSS.

### Basic CSS Selectors

CSS has three primary types of selectors (tag, id, and class) that select elements based on the tag name, `id` attribute, or `class` attribute. Learn the syntax for these three selectors, but don't get bogged down trying to memorize how you can combine them. For now, rely on the documentation.

### CSS Properties

Stick to the documentation as you start out; don't try to memorize CSS properties until you've used them a few times and seen how they work and interact with your HTML. This way, you'll learn the features you need most often without spending a lot of time absorbing material that you may never use.

- The most important properties introduced in this lesson are `color`, `background-color`, `font-family`, and `font-size`; we recommend memorizing these. 

The other properties you see in this lesson will become familiar with time and practice.

### Use Your Browser's Inspector

Much of your work in this course involves looking at the structure and styling of web pages: sometimes in your web pages, sometimes from another site. Either way, the best way to examine these features and determine how the HTML and CSS work is with your browser's Inspector software (this may be an add-on in some browsers).

### Study From The Summary

Spend time with the Summary at the end of this lesson. It reviews the topics and terminology you should master before moving on.

# Install Software

We'll get the ball rolling on this course with a brief introduction to some of the software you may want or need to install before you proceed.

## Browser

If you haven't already done so, you should install [Google Chrome](https://www.google.com/chrome/browser/desktop/index.html) on your system. You don't have to use Google Chrome as you work through this course, but most assignments assume that you are using it.

## HTML and CSS Validators

Always check your HTML with [W3C's HTML Validator](https://validator.w3.org/#validate_by_input). The validator ensures that your HTML is valid and helps catch potential issues before they become mystifying bugs. You can tell W3C to link directly to a page if you have it online, upload the HTML file from your local filesystem, or copy and paste the HTML to the direct input tab. Most students find that copy and paste is a good solution for this course.

Validate your HTML often:

- after the first draft of your HTML
- after any significant changes to your HTML
- when you're having problems with the way your page renders
- before submitting your HTML for a code review
- before deploying your HTML

[W3C's CSS Validator](https://jigsaw.w3.org/css-validator/#validate_by_input) provides similar functionality for validating CSS. Check your CSS when you validate your HTML, and also when you make significant changes to your CSS.

Don't underestimate the value of validation. It may seem like a pain at times, but validation **will** save you much grief. Small errors in your HTML and CSS can cause confusing and subtle bugs; the validators help you find and fix problems before they become bugs.

## Linters

**Linters** check computer code for errors, misuse, and style issues. Unlike the W3C validators, linters look at style and usage rather than conformance to standards. The validators find uses of deprecated elements, poor element nesting, and non-standard attributes and properties; linters detect poor indentation and formatting as well as failures to follow best practices.

You can find linters for most development languages, and HTML is no exception. Here are some you can install in the Sublime Text editor; similar tools exist for most code editors, and you can run most linters from the command line if your editor doesn't support them directly.

- [SublimeLinter-contrib-htmlhint Package for Sublime Text](https://packagecontrol.io/packages/SublimeLinter-contrib-htmlhint)
- [SublimeLinter-html-tidy Package for Sublime Text](https://packagecontrol.io/packages/SublimeLinter-html-tidy)

CSS also has linters, though good ones are a bit difficult to find. Unfortunately, we are no longer able to find one we like. If you find one you like, suggest it via the Feedback button!

## ESLINT (my notes)

Download node.js and npm on WSL

Download eslint

Download plugin extension for html

Create a `.eslintrc` file and put code in it.

