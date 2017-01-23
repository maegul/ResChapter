# Our First Web Page

## Objectives

1. Get set up with the tools we need to make a web page.
2. Make our first HTML file.
3. Add our first interactive data visualisation with javascript to our web page.
4. Upload the files to our first internet home.

---

&lt;!-- toc --&gt;

&lt;!-- toc --&gt;

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

### Internet connection

You will need to be connected to the internet.  Making web pages, given that they live on the internet, tend to rely on downloading things from the internet.

---

## Our First Page ... Lego Time!

### The File

With your text editor, start a file called `index.html` .  This is where the document of HTML that will be our web page will live.

---

##### _**Detail ... if you dare**_

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
<p> I am a paragraph of text ... I think. </p>
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

##### _**Further down the rabbit hole ... More elements**_

There are more elements than those we've dealt with so far, though to be fair, you generally don't need many more than what you know already.

* Nonetheless, go to `http://www.w3schools.com/tags/`  \(the first quick reference you should use for anything for making web pages\) and look through the elements there.  
* Try to use some of them in your page.  Some suggestions are: `<input>, <em>, <code>` and `<img>` \(which will require a picture file to work\).

---

---

##### _**Further down the rabbit hole ... Styling and CSS**_

You may wish for the layout of your page to be nicer.  When it comes to styling a web page, this is generally the most common aspect to be worked on.  Styling is a whole little world of its own that we won't cover too much here.

But as an introduction, add the following to **the head** of your HTML file:

```HTML
<head> <!-- No need to copy the head tags if you already have them!! -->

    <style>

    /* This style applies to both p and h1 elements  */
    p, h1 {  
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

This is **CSS**, which stands for **C**ascading **S**tyle **S**heets** **\(saying just the acronym alone , again, is fine\).  The idea is that you can style every element in your page, or all the `<p>` elements or any number of groupings, all in the same way.  This is the "cascading" in CSS.

The styling above makes all the &lt;h1&gt; and &lt;p&gt; elements have a width of only 50% of the screen width and a centered position.

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
<script src="http://tinyurl.com/zdcvgn6"></script>
```

or if that fails:

```HTML
<script src="https://rawgit.com/maegul/ResChapter/master/page_data.js"></script>
```

Two things are happening here.  First, we're using a new tag or element: `<script>` tags.  This is where javascript lives inside of an HTML file.  Second, this element has been given the attribute of `src='https://somewhere.on.the.internet.js'` which is the location of a javascript file on the internet.  In this file is the data that we're going to use.  The effect of importing it like this is that this data set will already be defined and given a variable name, which is `data` , in any javascript we want to write ourselves.

### Start Javascripting

To write javascript, we need to set up another pair of `<script>` tags.  This time, not in the `<head>` section, but in the `<body>` section.  In fact, put them at the very bottom of the body section so that they will always be last.  This is so that the javascript will know about all the HTML that we have defined before it.

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

##### _**Further down the rabbit hole ... console logging**_

At this point, you can use one of the most used javascript functions to check whether the data import done above worked.  In programming languages like Python `print my_variable` is often used as a sanity check for whether a variable is what it should be.  We do the same thing with javascript.  We don't print though, instead we log something in the browser's console.

So, between the script tags, add the following:

```js
console.log(data);
```

Nothing will happen to the web page itself.  You need to open up the console of your browser.  How\`to do this will vary from browser to browser, but search in help for "console" or google your browser and "console" and you'll get there.  All it takes is finding it in your browser's menus.  What you'll see in the console is the word "Object" somewhere.  This is your data set.  You should be able to click it to expand it and see the whole data set.  Also note that this console is a javascript command line; you can have some fun in there!!

---

### Make a Plot

#### Prepare the HTML

First, we need to give the plot somewhere to live on the page.  So, we need to give it an HTML element.  We will use a &lt;div&gt; element, which stands for division.  This is a catch all element for containing other things.  Add the following to your HTML \(in the body section, as with all your other content, but before the script tags, because they need to stay at the bottom\)

```HTML
<div id="my_plot"></div>
```

Notice that we gave this element an `id` attribute.  This id or name allows us to refer back to this particular element in javascript \(and CSS\) later on.

#### Plotly

Plotly needs to know two things:  Where you want the plot to go, and what kind of plot with what data you want to make.

To tell Plotly what kind of plot with what data, we need to define a **trace**.  If ever you've plotted in Python, Matlab or R, this will look very familiar.  A trace is simply where you specify the data and say that you want a scatter plot, for instance.

Put the following in your script section:

```JavaScript
<script>

trace1 = {x: data.rand.x, y: data.rand.y, mode: markers, type: 'scatter'};

</script>
```

As we may have many different traces in a single plot, our trace needs to go into a list of traces, even if, as will be the case for us, it's a list of only one trace:

```JavaScript
<script>

trace1 = {x: data.rand.x, y: data.rand.y, mode: 'markers', type: 'scatter'};

traces = [trace1];

</script>
```

Now we plot our trace.  We provide the id we gave to our `<div>` element above, and then the traces list we just made.

```JavaScript
<script>

trace1 = {x: data.rand.x, y: data.rand.y, mode: 'markers', type: 'scatter'};

traces = [trace1];  // not curly brackets, but square for a list.

Plotly.newPlot(my_plot, traces);

</script>
```

Look at your web page again.  There should be a plot.  Hover your mouse over it.  You'll see buttons appear at the top.  These let you interact with the plot in different ways including zooming, and panning.  Hover over particular data points and you'll see the raw data values appear.  Your page should look like this now:

![](/assets/first_plot_eg.png)

---

##### _**Further down the rabbit hole ... styling the plot**_

In defining `trace1` above you set a few parameters, such as `'mode': 'markers'.` Try the following and see what they do:

* Change the mode to 'lines'.
* Add the following parameters and set them as you wish \(hint, color can take the names of common colors, or 'rgb\(x, y, z\)':

```JavaScript
trace1 = { ...  marker: {color: , size: , line:{color: , width: }}}
```

* `Plotly.newPlot` takes a third argument, which is the **layout**.  Go to [https://plot.ly/javascript/figure-labels/](https://plot.ly/javascript/figure-labels/) and figure our how to add a title and axis titles to this plot.  Eg:

```JavaScript
layout = {title:  , xaxis: {...}} 
Plotly.newPlot(my_plot, traces, layout)
```

---

---

##### _**Further down the rabbit hole ... Making the plot centered and 50% wide with CSS**_

Your plot will be filling the whole width of the page, whilst, if you added the CSS from above, your text and heading should all be nicely centered.  You can make the plot do exactly the same thing by adding it to the styling.  If you recall, the styles we defined applied to all `p` and `h1` elements.  All you need to do is add your plot to the same style definition.

Use the `id` of the `div` we made for the plot \(ie, `my_plot`_\) \_but put a hash in front of it_ \_\(CSS needs to know whether we're dealing with element types or ids\) and add it to the beginning of the style rule.

```
#my_plot
```

You can go even further and make the plot change as the size of your browser window changes.  Insert the following at the bottom of your javascript.  I hope you can tell what this code is doing \(hint: `onresize` = on resize\).  This is what we mean when we say that javascript is built to make interactive web pages.

```JavaScript
window.onresize = function(){
    Plotly.Plots.resize(my_plot);
}
```

---

## Find a Home for Your Page

An animated GIF showing the whole process can be accessed here: `https://maegul.github.io/plotly_cheat_sheet/github_pages_gif.html`

#### 1. GitHub account

* Log in and sign up if you haven't to `https://github.com`

#### 2. Make a Repository

* This is a collection of files that go together on GitHub

![](/assets/new_repo.png)

#### 3. Name your Repository

* Generally, give it a name that makes sense as it will be part of the URL to the web page.
* Initialise with a README.md \(this makes things easier later on\)

![](/assets/name_new_repo.png)

#### 4. Upload Files

* Click "Upload Files"
* Add your `index.html` file \(remember, it should be named exactly this change the file name if you need to\)

![](/assets/click_upload.png)

* "Commit" your file \(which means upload it\).  You can put some text in the fields if you want to.

![](/assets/commit.png)

#### 5. Tell GitHub to make it a webpage

* Go to Settings

![](/assets/settings.png)

* Scroll down to "GitHub Pages" and change the Source to the "master branch"

![](/assets/gh_pages.png)

#### 6. Visit your page

* Your page will be at the following address:

```
https://<your github user name>.github.io/<your repository name>/
```

* You can find this out directly by going back to the GitHub pages section of the settings.  There GitHub will let you know about your page.

![](/assets/page_address.png)

