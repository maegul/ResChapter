* Walk through making first web page and getting online
* Make it a simple page with a Plotly plot of some simple data \(or a modulating sine wave ... two fundamentals summed, plot all three\)
* Challenge to modify the look and text of the traces
* Put online at the end!

# Our First Web Page

## Objectives

1. Get set up with the tools we need to make a web page.
2. Make our first HTML file.
3. Add our first interactive data visualisation with javascript to our web page.
4. Upload the files to our first internet home.

---

... TOC ...

---

## Let's get set up

### **Text Editor**

#### Sublime Text

A highly recommended text editor for making web pages is [Sublime Text](http://www.sublimetext.com/2) \(either 2 or the newer version 3\).  It is a nice and popular text editor for any programming you may want to do, but for web pages, it has some basic features like auto completion and HTML and Javascript syntax awareness built in that will help you.

They provide an unending free trial of the complete editor.  If you wish, you can pay for the product, without any feature improvements other than the warmness of your heart.

#### Atom

An editor with some features made specially for making web pages is [Atom](https://atom.io).  \(Interestingly, it is also made with the web page making technology we're learning here\).  It is free and open source, and may be the future of web page text editors.

#### Other

Otherwise, if you already have a text editor that you know and love, stick with that one, there are no special requirements at all.

### Folders

Each web page we make is best done in a separate folder.  So let's make a folder for all our web pages, and then in that folder we will make a new one for every new web page we want to make.

### GitHub account

This isn't necessary right now, but if you like to set everything up before you get started, go to github.com and sign up with your email.

---

## Our First Page ... Lego Time!

### The File

With your text editor, start a file called `index.html` .  This is where the document of HTML that will be our web page will live.

---

_**Detail ... if you dare**_

We use `index.html`because web browsers use whatever is in that file as the default home page for any website.  You can name your HTML file whatever you like, and it will work fine.  But, when we put your page online, you need at least one file to be called `index.html` .  As our pages will likely only have one HTML file, we will almost always be calling all our HTML files this.

---

### HTML Tags

The "lego pieces" of HTML, or the **elements**, are written in the following way.  We'll be making a `<p>` element \(often used for paragraphs\).

First, there is the **opening tag**:

```HTML
<p>
```

Then comes the **closing tag**, which is exactly the same but has a forward slash at the beginning

```HTML
</p>
```

Then, and most importantly, the content.  **This simply goes between the opening and closing tags**

```HTML
<p> I am a paragraph text ... I think. </p>
```

### Structure of an HTML file

There are two main sections to an HTML file.  Like everything in HTML, they are just another lego block made with tags.

```HTML
<head>

    <!-- Settings that affect the whole page go here -->

</head>


<body>

    <!-- The actual content of the page goes here -->

</body>
```

**The Head**

Things that affect the whole page go here.  We won't be using it straight away, but will later on.  These include:

* Overall title for a page
* General styling for the whole page \(this get's to be quite fun, powerful and important\)
* Importing external files

**The Body**

In the name really ... simply where all the content of your page goes.

### ... Go!

So go ahead and put something like the HTML below in your `index.html` file.

_Feel free to copy the code below, but please type it all out yourself, as that will help you learn._

```HTML
<head>
    <!-- Settings that affect the whole page go here -->
</head>

<body>

    <h1>My First Page</h1>

    <p>
        This is my web page. There are many like it, but this one is mine.
    </p>

    <p>
        My web page is my best friend. It is my life. 
        I must master it as I must master my life.
        Without me, my web page is useless. Without my web page, I am useless.
    </p>

</body>
```

Save the file.  And open it by double-clicking \(your operating system should open the file with the default web-browser on your computer\).  **You just made a web page!!  It looks a bit simple and rough, but we'll sort that out soon.**

---

_**Further down the rabbit hole ... More elements**_

There are more elements than those we've dealt with so far, though to be fair, you generally don't need many more than what you know already.

* Nonetheless, go to `http://www.w3schools.com/tags/`  \(the first quick reference you should use for anything for making web pages\) and look through the elements there.  
* Try to use some of them in your page.  Some suggestions are: `<input>, <em>, <code>` and `<img>` \(which will require a picture file to work\).

---

---

_**Further down the rabbit hole ... Styling and CSS**_

You may wish for the layout of your page to be nicer.  When it comes to styling a web page, this is generally the most common aspect to be worked on.  Styling is a whole little world of its own that we won't cover too much here.

But as an introduction, add the following to **the head** of your HTML file:

```HTML
<head> <!-- No need to copy the head tags if you already have them!! -->

    <style>

    /* This style applies to both div and h1 elements  */
    div, h1 {  
        /* Makes the width 50% of the screen width  */
        width: 50%; 

        /* automatically puts equal margins on the sides so that it they are centered horizontally */
        margin: auto; 

        /* Adds a little space on the bottom of each div or h1 element */
        margin-bottom: 20px;
    }

    </style>

</head>
```

This is **CSS**, which stands for **C**ascading **S**tyle **S**heets** **\(saying just the acronym alone , again, is fine\).  The idea is that you can style every element in your page, or all the `<div>` elements or any number of groupings, all in the same way.  This is the "cascading" in CSS.

The style above makes all the &lt;h1&gt; and &lt;div&gt; elements have a width of only 50% of the screen width and a centered position.

* Delete some of these settings \(eg width\) or adjust the values to see what they do.
* Go to `http://www.w3schools.com/css/default.asp` and find some other style settings to add \(eg, font and border\). 

---

By now, with the styling added from above, your page should look something like this.

![](/assets/first_web_page_eg.png)

## You're a Wizard Harry ... Data Viz magic time!

Now comes the fun part.

We're going to use Plotly and javascript to add an interactive data visualisation to our plot.

### Load the data

First, let's get a data set.  Add the following in the `<head>` section \(but not inside of the `<style>` tags of your HTML file:

```HTML
http://tinyurl.com/h37rggy
```

or if that fails:

```HTML
<script src="https://raw.githubusercontent.com/maegul/ResChapter/master/page_data.js"></script>
```

Two things are happening here.  First, we're using a new tag or element: `<script>` tags.  This is where javascript lives inside of an HTML file.  Second, this element has been given the attribute of `src='https://somewhere.on.the.internet.js'` which is the location of a javascript file on the internet.  In this file is the data that we're going to use.  The effect of importing it like this is that this data set will already be defined and given a variable name, which is `data` , in any javascript we want to write ourselves.



### Start Javascripting

To write javascript, we need to set up another pair of `<script>` tags.  This time, not in the `<head>` section, but in the `<body>` section.  In fact, put them at the very bottom of the body section so that they will always be last.

```HTML
...
<p>
My web page is my best friend. It is my life.
I must master it as I must master my life.
Without me, my web page is useless. Without my web page, I am useless.
</p>

<script>

    // My javascript will go here

</script>

</body>
```

---

_**Further down the rabbit hole ...**_



---





## Find a Home



