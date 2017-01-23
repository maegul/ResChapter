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

`Plotly.animate` can take a third argument which defines how long the animation takes to complete.  This can be useful for controlling the amount of information that is being changed in your specific visualisation.  The structure of the third argument looks like:

```Javascript
{
    // length of the whole transition, including any static time
    frame: {duration: 2000}, 

    // length of any actual animation or movement
    transition: {duration: 2000}
}
```

The thinking here is that there are two time lengths defined.  The first, **frame**, is the total time of the transition.  The second, **transition**, is the time for any animation.  So if the **frame** time were longer than the **animation **time, then the left over time would involve nothing happening, everything being still, until the next animation or transition occurred.  Having the two times essentially allows for pausing for a precise amount of time, if that's something that's useful you.  Otherwise, we simply change both durations if we want to increase the duration of the animation.

Adding the above to our animate function looks like:

```JavaScript
Plotly.d3.select('#my_butt').on('click', function(){

    Plotly.animate(
            my_plot, 
            {data: [{x: data.a.x, y:data.a.y}]},
            {
               // length of the whole transition, including any static time
               frame: {duration: 2000},

               // length of any actual animation or movement
               transition: {duration: 2000}
            } 
    )

})
```

---

##### _Further down the rabbit hole ... adding another animation_

There's no need to stop at one.

* Add another `Plotly.animate` function after the first one.  They will be run one after the other.  You change the data to another dataset, `data.z.x` and `data.z.y` for instance.
* Instead of changing the dataset, can you change the size or colour of the markers of the plot?
* Add and adjust the duration parameters to see how they work, especially when there are differences between **frame** and **transition**.

---

## Fixing some minor issues ... Changing the layout of the plot

You may have noticed a few things:

* The dataset `data.a` depicts the letter "A".
* But it is upside down.
* You may have also seen the ranges of the axes change a little abruptly in between individual animations.

This is because the dataset was made with graphics coordinates, which puts the y-axis the other way round so that zero is at the top left and goes down the page.

Also, Plotly tries to automatically optimise the ranges of the axes to suit the data being viewed.  When animating a change in the data though, you generally want the axis to stay unchanged so that you have a point of reference for the changes in the data.

Fortunately this is all resolved with one simple line.  If you go back to the `Plotly.newPlot()` function that made the original plot and add a third argument, called **layout**, which we've met before, you can do the following:

```JavaScript
layout = {
        // The range of the xaxis,
        xaxis: {range: [-5, 105]}, 
        
        // The range of the y axis, made backwards here to reverse the upside down letters.
        yaxis: {range: [105, -5]}
        };


Plotly.newPlot(my_plot, traces, layout)
```

The layout argument allows many aspects of the general look of the plot to be customised, including the title and the axis titles.  Here, we're setting the ranges of the axes.  This turns off the automatic adjustment that was happening before.  And, because we've put the range of the y-axis backwards, we've put it in reverse to put our letters the right way round.

---

_**Further down the rabbit hole ... Titles**_

This was a challenge earlier, bit we'll repeat it here.  Can you give the axes a title, as well as the plot as a whole.  Hint: to give something a title, use the parameter "title".

---

## Final Challenge

Can you animate a sequence of letters that spell out a word that is funny?  Don't forget the punctuation, which can totally be funny!

Can you then put your new web page online \(either as a new one or by replacing the old one with it\) and share it with a friend?

### 



