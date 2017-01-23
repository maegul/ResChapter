# What's involved?

## HTML

This is the easy stuff.  It's not actually programming.  With this you set up your text and pictures and titles and fonts and colours.  I like to think of it as lego.  You have different blocks of different shapes and colours, and you simply pile them up on top of each other as you see fit.  There's only some mechanical stuff to learn, and there isn't anything that isn't a single google search away.

## Javascript

This is the magic.  Javascript is the programming language for websites.  It is much like python/Matlab/R.  But, it is built to create the interactivity we want from a webpage.  If you've programmed before, there's nothing really new to learn here \(apart from some minor differences between javascript and the other languages\).  What will be new, though, is the idea of using javascript to make a web page dynamic and interactive.

### Plotly \(and D3\)

Plotly is a javascript library of functions that will help us a lot in making interactive data visualisations.  It is based on D3, which does the same sort of thing but with a lot more work and control.  We recommend starting out with Plotly, as it's a fantastically user friendly and versatile tool \(see _Where to from here_ on more details about Plotly's features\).  Once you realise that you need to do something especially unique, then you may want to think about digging deeper into D3. 

## Github Pages

Github is something you've probably heard of before.  It is used for a number of things.  For us, it provides a very straightforward way to put our website online without us having to worry for a second about servers or anything like that.

## What the process looks like --- The three steps to getting online

### 1. "The Document" --- A web page is just an HTML document

A web page is just a document, like an MS Word document.  The web browser makes the document look nice for us \(and also allows us to program the document, which comes next\).  The browser "speaks" HTML, which stands for _HyperText Markup Language,_ a nearly meaningless acronym that you can safely never use again ... saying 'HTML' is fine.

This means that the formatting of the document — ie, making text bold or italic, or inserting a picture or a table –is done using bits and pieces of descriptive text, called **tags,** rather than clicking buttons.

So typically, HTML, that is, a web page before the browser makes it look nice, will be done as is below.  This is a page with a heading, some paragraphs, a picture, a button and a slider.

```HTML
<body>

    <h1>This is the Heading of an HTML Demo</h1>

    <!-- the 'p' tag stands for paragraph.  Often used for making paragraphs! -->

    <p>This will be a paragraph of text ... blah blah blah</p>
    <p>And more text ... so boring</p>

    <!-- below is a picture -->
    <img src="my_cat_picture.jpg">

    <button type="button">I'm a Button!!</button>

    <!--  And below is a slider-->
    <input type="range" min="2002" max="2016" step="1" > 


</body>
```

The arrows or greater/less than symbols \(ie `<, >` \) and the text between  \(eg, the 'h1' in`<h1>`\) are called **tags**.  Each tag creates an **element**, which is like a piece of lego.  The text inside the tags tells the browser what kind of element or lego block it is and how to format it.  Essentially, the tags tell the browser what colour and shape each "lego piece" is going to be.

To be clear, **the HTML above is a webpage**.  It's not a terribly interesting one, but it does illustrate the straightforwardness of HTML.  All it needs is somewhere to live online, which is step three below, and we could all visit and enjoy it.

### 2. "The Magic" --- Javascript makes HTML dance and play

Javascript is a programming language that looks much like Python, R or Matlab.

```js
// A tiny little data set
my_data = [1, 2, 3, 5, 7, 11, 13, 17];

// Looping three each number in the data set
for (i in data) {
    console.log(my_data[i]);   // console.log() is the print for javascript
}
```

What's special about javascript is that it is built to let you program your web page to be dynamic and interactive.

So below we have a simple page, with a heading and a button.

```HTML
<body>

    <h1>This demo will be dynamic</h1>

    <button> I Like Cats </button>

</body>
```

And with javascript, we're going to make the button change the web page.  The key to how this works is that javascript does three main things:

1. Javascript is aware of all the HTML "lego blocks" we've already written in the page and can specifically identify them.
2. Javascript can write new HTML for us or modify any of the pre-existing HTML in the page.
3. Javascript is aware of the user and their input.  It is paying attention to the mouse and keyboard.

You'll see all of this in action below.

```js
// Select and identify the bit of the page we want to make dynamic

// Then, look out for whether the button is clicked ...

d3.select('button').on('click', function(){

    // ... And now, when it is clicked, we do whatever we want to our page...

    // We identify & select our page itself 
    // (notice that 'body' = the main HTML tag in the HTML above)
    my_page = d3.select('body');

    // Now we get javascript to write our own HTML

    // Here we add or 'append' a 'div' element for some text
    // And then we add the text
    my_page.append('div')
        .text('So ... you like cats ha!')

    // Here we add an 'img' element, 
    // and provide the 'src' information, ie the picture file, 
    // which is of course a cat.
    my_page.append('img')
            .attr('src', 'my_cat_picture.jpg')

}
```

To recap, the following has just happened:

1. We made a simple web page with a button
2. We made a javascript program that will kind of live inside the web page
3. That program pays attention to whether anyone has clicked the button
4. And if that button is clicked, the program adds some text and a picture to the web page \(ie, adds more HTML or lego blocks to the page for us\), 

### 3.  "Getting Online" --- GitHub pages is our internet home

The two ingredients above form a complete and dynamic web page.  Unfortunately, the only people who could view it would be those who have a copy of the file on their computer.  To make it accessible to everyone on the internet, we need to give it a home on the internet.

GitHub makes this super easy.

The best way to learn it is to do it, which we'll be doing soon when we get our own web page up.  So we'll go through the details then.  Here though we'll just outline the fundamental steps:

1. **Have a GitHub account. Which is free.  **
   It is mainly used for backing up and versioning files in the cloud, in conjunction with `git` , which is very useful.  But, when those files are web page files, then GitHub are more than happy to turn them into a web page for us.
2. **Make a 'Repository'.**
   A 'repository' is simply a bunch files that go together in a single collection and are managed by GitHub and git together.  For us, we need one repository for every web page we make, as all the files for a GitHub web page need to come from a single respository.
3. **Tell GitHub to make a web page out of our repository.**
   This is a matter of changing one setting for our repository.  Once done, the page will available online with a simple URL.



