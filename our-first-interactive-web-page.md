* Challenge exercise
* Add to first page a button that adds and takes away the fundamentals \(use normal JS or the plotly API for buttons?\)

# Animation and Interaction

## Objectives

You made a web page, with a plot in it, that is interactive.  But you can go further.  As promised in the Introduction, one of the key advantages of making web pages is that you can easily build data exploration applications.  An interface that lets one easily move through different parts or aspects of their data in the search for patterns.  That's what we're going to do here.  We're going to animate the transition from data set to another.

1. Add a button which triggers a change in the data visualisation.
2. Make that change an animated change in the data.

## Add a Button ... back to the HTML

To add a button we use, can you guess, the HTML button element.  The text between the tags will be the text in the visual button on the page.  Add it to you HTML, preferably before the `<div id='my_plot'>` element.  And give it an `id` too, so we can use it later.

```HTML
<button id='my_butt'>Let's Dance</button>
```

## Listen for the click

Now we want our web page to do something whenever the viewer clicks this button.  We do this with what's called an event listener.  Here we will be using the D3 library, which is built into Plotly.  Add the following to your javascript, after the plotting function.

```JavaScript
Plotly.d3.select('#my_butt').on('click', function(){


        }
)
```

* The `select('#my_butt')` function \(yea, I hear it, but I'm sticking with this functional id\) grabs the button for us to use in javascript.
* The `on.('click', function(){})` function listens for a click, and on a click, does what ever is in the function.

Test to see that your event listener is working by placing the following into the function and clicking the button:

```JavaScript
Plotly.d3.select('#my_butt').on('click', function(){

        window.alert('You've just made an annoying pop up.  Congratulations.')

        }
)
```

You could have also used a `console.log();`.



## Animation with Plotly

### Introduction

### 



