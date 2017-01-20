# What's involved?

## HTML

This is the easy stuff.  It's not actually programming.  With this you set up your text and pictures and titles and fonts and colours.  I like to think of it as lego.  You have different blocks of different shapes and colours, and you simply pile them up on top of each other as you see fit.  There's only some mechanical stuff to learn, and there isn't anything that isn't a single google search away.

## Javascript

This is the magic.  Javascript is the programming language for websites.  It is much like python/Matlab/R.  But, it is built to create the interactivity we want from a webpage.  If you've programmed before, there's nothing really new to learn here \(apart from some minor differences between javascript and the other languages\).  What will be new, though, is the idea of using javascript to make a web page dynamic and interactive.

## Github Pages

Github is something you've probably heard of before.  It is used for a number of things.  For us, it provides a very straightforward way to put our website online without us having to worry for a second about servers or anything like that.

# What the process looks like --- The three steps to getting online

## 1. "The Document" --- A web page is just an HTML document

A web page is just a document, like an MS Word document.  The web browser makes the document look nice for us \(and also allows us to program the document, which comes next\).  The browser "speaks" HTML, which stands for _HyperText Markup Language,_ a nearly meaningless acronym that you can safely never use again ... saying 'HTML' is fine.

This means that the formatting of the document — ie, making text bold or italic, or inserting a picture or a table –is done using bits and pieces of descriptive text, called **tags,** rather than clicking buttons.

So typically, HTML, that is, a web page before the browser makes it look nice, will be done as is below.  This is a page with a heading, some paragraphs, a picture, a button and a slider.

```HTML
<body>

    <h1>This is the Heading of an HTML Demo</h1>

    <div>This will be a paragraph of text ... blah blah blah</div>
    <div>And more text ... so boring</div>

    <!-- below is a picture -->
    <img src="my_cat_picture.jpg">

    <button type="button">I'm a Button!!</button>

    <!--  And below is a slider-->
    <input type="range" min="2002" max="2016" step="1" > 


</body>
```

The arrows or greater/less than symbols \(ie `<, >` \) and the text between  \(eg, the 'h1' in`<h1>`\) are called **tags**.  Each tag is like a piece of lego.  The text inside them tells the browser how to format the document.  They tell the browser what colour and shape each "lego piece" is going to be.

To be clear, **the HTML above is a webpage**.  It's not a terribly interesting one, but it does illustrate the straightforwardness of HTML.  All it needs is somewhere to live, which is step three below.

## 2. "The Magic" --- Javascript makes HTML dance and play

Javascript is a programming language that looks much like Python, R or Matlab.

```js
// A tiny little data set
my_data = [1, 2, 3, 5, 7, 11, 13, 17];

// Looping three each number in the data set
for (i in data) {
    console.log(my_data[i]);   // console.log() is the print for javascript
}
```

* example of manipulating the web page



## 3.  "Getting Online" --- GitHub pages is our webpage home



