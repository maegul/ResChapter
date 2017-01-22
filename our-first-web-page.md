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

The "lego pieces" of HTML, or the **elements**, are written in the following way.  We'll be making a `<div>` element \(often used for paragraphs\).

First, there is the **opening tag**:

```HTML
<div>
```

Then comes the **closing tag**, which is exactly the same but has a forward slash at the beginning

```HTML
</div>
```

Then, and most importantly, the content.  **This simply goes between the opening and closing tags**

```HTML
<div> I am a paragraph text ... I think. </div>
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

    <div>
        This is my web page. There are many like it, but this one is mine.
    </div>

    <div>
        My web page is my best friend. It is my life. 
        I must master it as I must master my life.
        Without me, my web page is useless. Without my web page, I am useless.
    </div>

</body>
```

Save the file.  And open it by double-clicking \(your operating system should open the file with the default web-browser on your computer\).  **You just made a web page!!  It looks a bit simple and rough, but we'll sort that out soon.**

---

_**Down the rabbit hole ... if you want to challenge yourself**_

There are more elements than those we've dealt with so far, though to be fair, you generally don't need many more than what you know already.  

Nonetheless, go to `http://www.w3schools.com/tags/`  \(the first quick reference you should use for anything for making web pages\) and look through the elements there.  Try to use some of them in your page.  Some suggestions are: `<input>, <em>, <code>` and `<img>` \(which will require a picture file to work\).

---

## 

## You're a Wizard Harry ... Data Viz magic time!

## Find a Home



