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
//        selects the button     listens for mouse clicks  and does anything inside the function
Plotly.d3.select('#my_butt').on('click', function(){


        }
)
```

* The `select('#my_butt')` function \(yea, I hear it, but I'm sticking with this functional id\) grabs the button for us to use in javascript.
* The `on.('click', function(){})` function listens for a click, and on a click, does what ever is in the function.

Test to see that your event listener is working by placing the following into the function and clicking the button:

```JavaScript
//        selects the button     listens for mouse clicks  and does anything inside the function
Plotly.d3.select('#my_butt').on('click', function(){

        // This all happens whenever the button is clicked.

        window.alert('You've just made an annoying pop up.  Congratulations.')

        }
)
```

You could have also used a `console.log();`.

## Animation with Plotly

Plotly has functions that will animate its visualisation for us.

What we're going to do is animate a change in the data, where each circle of our scatter plot is going to move, smoothly, to a new location represent the new data set.

### What is the data I've uploaded?

To recap, by importing a javascript file located on the internet, we imported a dataset into our web page, that is called, simply enough, `data`.  We've already used this to make our first plot, which really just looked completely random.  And it was random.  But the whole data set we've loaded, which we access as `data`, has multiple single data sets inside of it.  For the first plot, as you should remember, we made our plot as follows:

```JavaScript
trace1 = {x: data.rand.x, y: data.rand.y, mode: markers, type: 'scatter'};
```

... using a single dataset called "rand", which is inside data \(thus the `data - dot - x` syntax\), and then assigning the individual x-axis and y-axis components of the data to the appropriate axes.  Besides "rand", there are other datasets inside data.  This includes one for each letter of the alphabet, and come named with punctuation marks as well.   The code below demonstrates how to access the various datasets inside `data`.

```JavaScript
var trace1 = {
    // x coord data for letter 'a'
    x: data.a.x,
    
    // y coord data for letter 'a'
    y: data.a.y,
    
    mode: 'markers'
};

// letter 'R'
data.r.x

// letter 'Z'
data.z.x


// space
data.space.x

// apostrophe
data.apost.x

// question mark
data.quest.x

// exclamation mark
data.exclam.x
```

### Let's change the data

Our plot was a scatter plot of `data.rand.x` and `data.rand.y`.   Let's animate a change of the data to `data.a`.  

The animation function needs to know what plot it's going to animate, and then what change is going to be animated.  So, to animate a change to data.a, the function looks like below.  Add it to your button event listener \(and maybe get rid of pop up too\).

```JavaScript
Plotly.d3.select('#my_butt').on('click', function(){

    Plotly.animate(
            my_plot, 
	    {data: [{x: data.a.x, y:data.a.y}]}
	)

})
```

* The first argument, `my_plot`, identifies our plot by the id of the element it is in.
* The second argument contains the new parameters for our plot.  In this case, a change of the data.  The new settings are all inside curly brackets.  What's inside the curly brackets, though, is exactly the same sort of list of traces we made when we first made the plot.  We called `traces` .

Refresh and look at your page again.  Clicking the button should animate a change.



### Changing the Duration

`Plotly.animate` can take a third argument which defines how long the animation takes to complete.  This can be useful for controlling the amount of information that is being changed in your specific visualisation.  The structure of the third argument looks like

 

### Introduction

### 



