This word id **bold** using *

This word id _italic_ using _
<hr>

Coding:
There are two ways to format code in Markdown. You can either use inline code, by putting backticks (`) around parts of a line, or you can use a code block, which some renderers will apply syntax highlighting to.

1.Inline code:
You can use inline code formatting to emphasize a small command or piece of syntax within a line you’re writing.
For example, you may wish to mention JavaScript’s Array.protoype.map() method. By using inline code formatting, it is clear that this is a piece of code.
`Array.protoype.map()`
`npm install`

2.Code Blocks:
Code blocks allow you to use multiple lines, and markdown will render it inside its own box and with code type font.
```
var add2 = function(number) {
  return number + 2;
}
```


3.Syntax highlighting:
While not supported natively by markdown, many markdown engines, including the one used by GitHub, will support syntax highlighting. This means that by telling markdown what language you're using inside the code block, it will add colors like an IDE would.
You can do this by adding the name of the language on the same line as your opening three back ticks. 
```js
var add2 = function(number) {
  return number + 2;
}
```

```html
<div class="row">
  <div class="col-md-6 col-md-offset-3">
    <h1>Hello World</h1>
  </div>
</div>
```
<hr>
The Title Sequence:

For h1 through h6 tags, all you'll need is a # before your text

## This is an h2.
### This is an h3.

<hr>
Creating a table:
You can create tables with pipes | and hyphens -. Hyphens are used to create each column's header, while pipes separate each column. You must include a blank line before your table in order for it to correctly render.

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

Note:Cells can vary in width and do not need to be perfectly aligned within columns. There must be at least three hyphens in each column of the header row.

Formatting content within your table:

You can align text to the left, right, or center of a column by including colons : to the left, right, or on both sides of the hyphens within the header row.

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |

<hr>

Organizing information with collapsed sections:

Any Markdown within the `<details>` block will be collapsed until the reader clicks  to expand the details. Within the `<details>` block, use the `<summary>` tag to create a label to the right of .
  
<details><summary>CLICK ME</summary>
<p>

#### We can hide anything, even code!

```ruby
   puts "Hello World"
```

</p>
</details>

<hr>
Crating Diagrams:
https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-diagrams

<hr>

Writing mathematical expressions:

1.Writing inline expressions:

To include a math expression inline with your text, delimit the expression with a dollar symbol $.

This sentence uses `$` delimiters to show math inline:  $\sqrt{3x-1}+(1+x)^2$


2.Writing expressions as blocks:
To add a math expression as a block, start a new line and delimit the expression with two dollar symbols $$.
**The Cauchy-Schwarz Inequality**

$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$

<hr>
Creating a permanent link to a code snippet:
https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-a-permanent-link-to-a-code-snippet

<hr>
Creating Links in Markdown
Markdown syntax for a hyperlink is square brackets followed by parentheses. The square brackets hold the text, the parentheses hold the link.

[Git hub]([https://link-url-here.org](https://github.com/BasmaElhoseny01))

Internal Links:
[Link to H2](https://github.com/BasmaElhoseny01/Git-and-Github-commands/new/master#this-is-an-h2)

<hr>
Lists:
1.Unordered List of items in markdown:

Also, called bullet lists, represent the list of items in an unordered way. It uses asterisk *, hyphen - or plus + to create an unordered list

* item 1
* Item 2
- Item 3
- Item 4
+ item 5
+ item 6
* item 7

Generated Html code is
```html
<ul>
    <li>item 1</li>
    <li>Item 2</li>
</ul>
<ul>
    <li>Item 3</li>
    <li>Item 4</li>
</ul>
<ul>
    <li>Item 5</li>
    <li>Item 6</li>
</ul>
<ul>
    <li>Item 7</li>
</ul>
```

2.Ordered List items in markdown:

The list of items represents numbers starting from 1,2 etc, and followed by a period . symbol or right parenthesis. These can also be called numbered lists

1. Ordered list element one
2. Ordered list element two

Generated Html code is
```html
<ol>
    <li>Ordered list element one</li>
    <li>Ordered list element two</li>
</ol>
```
<hr>
Inserting Images in Markdown:

Images can be added to any markdown page using the following markdown syntax:

```
![alt text for screen readers](/path/to/image.png "Text to show on mouseover")
```

![MarineGEO circle logo](/assets/img/MarineGEO_logo.png "MarineGEO logo")


Inserting Images using html:

Images can also be inserted on pages using the html <img> tag. One advantage of using the html tag is the ability to control size and other style elements.

<img src="/assets/img/MarineGEO_logo.png" alt="MarineGEO circle logo" style="height: 100px; width:100px;"/>
