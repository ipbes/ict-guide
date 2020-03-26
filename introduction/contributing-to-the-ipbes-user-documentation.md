# Contributing to the IPBES user documentation

Thank you for helping make our documentation better!

In order to maintain a consistent style and voice throughout our documentation please try to follow these standards and conventions when filing Pull Requests against our documentation.

## Markdown

GitBook \(which we use for documentation\) uses Markdown as its file format.

* All files should end in `.md`. They should be all-lower-case and match the title of the page, or in some cases an abbridged version of it.
* All pages should start with a title, denoted with \# \(first level header\).
* Subsections within a page are encouraged, and should use \#\# for a 2nd level and \#\#\# for a 3rd level. Do not have more than 3 levels of header.
* Inline code statements, file names, and keys that would appear in a file should use backticks `like this`.
* Longer code samples should be denoted with triple backticks before and after, with no extra whitespace between the backticks and the code block. Always specify the language of the code block. See the [highlight.js docs](https://highlightjs.org/static/demo/) for available language options. \(`yaml`, `bash`, and `php` are the most common we're likely to see\).
* Always use inline links.
* Do not hard-wrap prose text. Set your text editor to soft wrapping.
* Internal links should be absolute \(starting with `/`\) and link to a file ending in `.md`, not `.html`. That makes them easier to find when needed to update.

## Language usage

* All documentation should be written in English.

## Process

* Favor many small Pull Requests \(PR\) over larger ones.
* Never push directly to the master branch.

