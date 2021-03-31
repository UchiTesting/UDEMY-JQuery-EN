Introduction
============

## My intro
The related course comes with ready to use code. jQuery does not seem too difficult to understand provided you get to know the specific commands and possibilities given. That's why on this course I will not reproduce the code thouroughly but rather take notes in order to add the value of a more efficient reference. It does not mean to go farther than the related course.

## What is jQuery
jQuery was created by John Resig in 2006 and allows to make cross-browser compatible JS code. Before jQuery JS devs needed to ensure their code is compatible with the various versions of ECMA script.

The general philosophy of jQuery is:
> Search → Select → Listen → Load → Animate

## Including jQuery in a web page

Mostly, it just needs to add the script tag in the html documents that need jQuery.
For instance: 

```js
<script src="js/jquery-{version}.min.js"></script>
```

You can either:
- Download it from the jQuery official page at https://jquery.com/download/
- Use a CDN link from https://code.jquery.com

There are essentially 2 distributions of the script. The human readable which has indentation and white spaces. The minified which remove any unnecessary space to save a little bit of space on drives and particularly bandwidth. The former is of course meant to be readable in a development environment while the latter is use for production when no one is supposed to read the code anymore.

## Documentation

There is no dev work without documentation. jQuery has a good documentation. That said, there are some nice alternatives too.

- [jQuery Official doc](https://api.jquery.com)
- [jQ API](http://jqapi.com)
- [jQuery @ devdocs.io](https://devdocs.io/jquery/)