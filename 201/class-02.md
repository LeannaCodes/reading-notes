# HTML Text

## Headings and paragraphs 

### Headings

HTML has six different 'levels' of headings:

`<h1>` is used for main headings. 
`<h2>` is used for subheadings. 
`<h3>` is used for further sections under the headings and so on. 

Browsers display the contents of headings at different sizes, so h1 will be bigger than h2 as its more 'important' and h6 will be the smallest. You can control the sizes of these headings with CSS.

### Paragraphs 

To create a paragraph, surround the words that make up the paragraph with the `<p>` tag. For example, `<p>This is a paragraph</p>`. What defines a paragraph? A paragraph consists of one or more sentences that form a self-contained unit of discourse. The start of a paragraph is indicated by a new line.

## Bold, Italic and Emphasis

### Bold

If you want to highlight text by making it bold, you can enclose what you want to bold, in a `<b>` tag. However, This is no longer used in the industry. The tag used for bold currently, is the `<strong>` tag. 

### Italics

To make a sentence or word appear in italics, wrap what you want to edit in the `<i>` tag. 

## Superscript & Subscript

### Superscript

If you want to contain characters that should be superscript such as the suffixes of dates or mathematical concepts like raising a number to a power such as 2 <sub>2</sub> . We do this by using the `<sup>` tag. 

### Subscript

The `<sub>` element is used to contain characters that should be subscript. It is commonly used with foot notes or chemical formulas. 

## White Space 

To make code easier to read, authors often add extra spaces or start some elements on new lines. 

When the browser comes across **two or more** spaces next to each other, it only displays one space. If it comes across a line break, it treats that as a single space too. This is known as **white space collapsing**

## Line Breaks & Horizontal Rules

### Line Breaks

As the browser will automatically show each new paragraph or heading on a new line, you might want to add a line break inside the middle of the paragraph. To do this you can use a `<br />` tag. **However**, try and avoid using this to break lines on your HTML document. It is industry practice to use CSS to do your line breaks. 

### Horizontal Rules 

To create a break between themes - such as a change of topic in a book or a new scene in a play - you can add a horizontal rule between sections using the `<hr />` tag. 

## Structural and Semantic Markup  