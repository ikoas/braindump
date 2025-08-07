---
aliases:
  - Markdown
---

[Wikipedia](https://en.wikipedia.org/wiki/Markdown) describes Markdown as follows:

> **Markdown**[\[9\]](https://en.wikipedia.org/wiki/Markdown#cite_note-philosophy-9) is a [lightweight markup language](https://en.wikipedia.org/wiki/Lightweight_markup_language "Lightweight markup language") for creating [formatted text](https://en.wikipedia.org/wiki/Formatted_text "Formatted text") using a [plain-text editor](https://en.wikipedia.org/wiki/Text_editor "Text editor").

You can learn more about Markdown here:
- John Gruber's website: https://daringfireball.net/projects/markdown/
- Learn X in Y minutes' page on Markdown: https://learnxinyminutes.com/markdown/
- GitHub's on it's own implementation of Markdown: https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

# Basics

Markdown is meant to be a simple way to write a HTML formatted page that is readable as plain text and easily understandable. Because of this you can make use of HTML elements inside a Markdown document, but for most cases you should be able to get by not using any HTML.

Plain text on a Markdown document is formatted as simple text, nothing too fancy so far, but you can format that text as [headings](#Basics##Headings), [Bold and Italics](#Basics#Bold%20and%20Italics), [quotes](#Basics##Quotes), [lists](#Basics##Lists), [code](#Basics##Code), [links](#Basics##Links) and you can even add [images](#Basics##Images).

## Headings

Markdown lets you make use of 6 level's of headings. If you are familiar with HTML this is like using `<h1>`, `<h2>`, `<h3>`... `<h6>`.

To format text as a header you just have to write a line starting with `#`(Hashtag). To make a level 2 header you just use two `#`, like this `##`. For a level 3 header you use three `#` and so forth. So if you want to create a level 5 header you use five `#`. The text on the same line following the `#` then is formatted as a header.

Here is how you would create a level 3 header saying "_Hello World_": `### Hello World`

**Note:** Make sure to separate the text from the `#` because some implementations of Markdown will interpret a `#` followed by text without any space between them as a tag or hashtag.

## Bold and Italics

You can format text as bold, italics or both by putting it inside `*`(Asterisks) or `_`(Underscores).

You can format text as bold by using two `*` or `_` to encase the text you want to format, like this: `**Hello World**` or `__Hello World__`

You can format text as italics by using one `*` or `_` to encase the text you want to format, like this: `*Hello World*` or `_Hello World_`

You can format text as both bold and italic by using three `*` or `_` to encase the text you want to format, or combining `*` and `_`, like this: `***Hello World***`, `___Hello World___`, `**_Hello World_**`, `__*Hello World*__`, or any other way to encase the text.

## Quotes

You can format text as a quote by starting a line of text with `>`.

The same rules as Heading apply to quotes. The only exception being that you can extend a quote by adding another line beneath also starting with `>`. Here is some examples:

```
> This is a single line quote.

> This is a separete single line quote.

> This
> is
> still
> a
> single
> quote
> .

> This is a quote.
>> This is a quote inside the previous quote.
> This is the same quote.
```

## Lists

You can format text as an unordered list by starting a line `-`, `+` or `*`, where every line starting with any of the previous symbols is an element of the list. Here is and example:

```
- This is a list with a single element
```

This is a list with three elements:
```
+ One
+ Two
+ Three
```

This are also lists with three elements:
```
- One
- Two
- Three
```

```
* One
* Two
* Three
```

You can format text as an order list by starting a line with a number followed by a dot, like this `3.`. Note that I chose an arbitrary number, depending on the Markdown implementation, this will result on an ordered list where the element uses the number before the dot or an ordered list where the number is ignored and the number displayed is defined by the implementation of Markdown.

Here are some examples of ordered lists:

```
1. This is an ordered list with a single element.
```

This is an ordered list with three elements:
```
1. One
2. Two
3. Three
```

You can create nested lists by indenting the lines using tabs or spaces. In the case of indenting using spaces the number of spaces that is consider a level of indentation depends on the implementation of Markdown. Personally, I prefer using tabs for indenting. Here are some examples of nested lists:

```
- This is list.
	- This is a list inside a list.
```

```
- One
- Two
    - A
    - B 
    - C
- Three
```

```
+ One
	- A
		* Dog
		* Cat
	- B
	- C
+ Two
	1. Hi
	2. There
	3. You
+ Three
```

As you can see, you can mix and match lists, just beware that the rules for this depend on the implementation of Markdown, so try to keep a consistent style while creating lists.

## Code

**Note:** The styling of the examples on this section is a bit off because most implementations of Markdown prioritize backticks when parsing the styling for code blocks. I hope these examples are still legible.

As you have seen throughout this document, there are sections where the text has a very simplistic format. These sections are formatted as code.

You can format text as code in one of two ways, as a inline block or as a separate block of text.

To format text as an inline code block you just have to encase your text using **\`**(Backtick), like this **\`Hello World\`**.

To format text as a separate code block you can encase your text using three **\`**(Backtick), or indenting your text using four spaces or a tab. Here are some examples:

\`\`\`  
Hello word  
\`\`\`

```
	Hello word
```

```
    Hello word
```

**Note:** Most implementations of Markdown expect that if you are using backticks you are using text encased on single backticks, like so **\`Hello World\`**, or using text encased on three backticks where the backticks are separate from the text by line breaks(New lines), like this:

\`\`\`  
Hello World  
\`\`\`

My personal experience has been that using indentation for formatting text as code or using backticks on a different way that the one explained results in inconsistent and unexpected behavior.

## Links

A big part of documents online are links and, arguably, they are also a pretty big part of Markdow. You can format a text as a link by encasing it in square brackets and then parentheses and adding inside the parentheses the link you desire, like this `[Google](https://www.google.com)`

Links are a very powerful tool and come with many features but most of the time these features depend on the implementation of Markdown. For example, most implementations of Markdown will let you create links to local files using relative paths, like this `[File on my machine](./path/to/file)`. Other implementations will let you [Uniform Resource Identifiers(URI)](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) and in those cases I would recommend sticking to the specifications of URI's.

## Images

You can also add images to your Markdown documents by adding a `!`(Exclamation mark) before a link, like this `![Image description](https://link.to.image)`. This is also true for other types of links like relative paths and URI's.

**Note:** You can nest links and images in anyway you want results maybe determined my your implementation of Markdown. An useful case for nesting links and images can be images that function as links by creating a link and putting an image where your text should be, like this `[![Image description](https://link.to.image)](https://www.google.com)`

---

**Note:** As you maybe have noticed, I keep repeating that there are things that depend on the implementation of Markdown, this means that people chose how to implement the basic rules of Markdown and the way they chose to implement these rules may result on some weird behavior for specific cases. People may also add other rules to add things like tables, underscored or strikeouted text, etc.
