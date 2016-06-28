#Bootstrap and Transition Workshop
##CS52 16X
###Presenters: Jessie Anderson, Manmeet Gujral, Alex Beals, Jean Zhou, Emma Oberstein, Rob Sayegh
###Date: June 30, 2016

###Section 1: Bootstrap grid

###Section 2: Buttons

###Section 3: Transitions and Animations

In this tutorial, we’ll make one transition and one animation (the sample solution has more, and you can make more if you like). The grid is already set up in `index.html`; take a look at the `<!-- Transitions and Animations -->` section of `index.html` to see the setup.

The first `<div>` in this section will be a transition. Now open `css/main.css` and find the section that looks like this: 

```html
/******** transition/animation style section ********/

#transition {
  /* put style here */
}

#transition:hover {
  /* what do you want the transition to do? */
}

#animation {
  /* put "initial" style of animation here */
}

/* now, need to add in a keyframes rule */

/*************************************************/
```

Since the ID of the first `<div>` is `transition`, you'll be working on the first 2 selectors first. The selector `#transition` will specify the "normal" state of the object (size, color, etc.). You'll need to give it values for `transition-property` (the easiest value is “all”), `transition-duration`, and (optionally) `transition-timing-function` (some fun ones are ease-in, ease-out, and ease-in-out). If you want your div centered, use the line `margin: 0 auto;`.

Now you need to write the selector `#div:hover`. Whatever you put in here will be the state of the object when you hover your mouse over it. The transition between the “normal” and “hovering” state of the object will occur in the time period specified by `transition-duration`, and with the timing specified by `transition-timing-function`. Again, make this whatever you want. Some cool things you can do are change the color of the object, make it grow, and make it rotate or skew using transform.

Now let’s make an animation using the second div. Animations are different from transitions because they happen without the user performing any action with the mouse. Let’s say you gave your second div the ID `animation`. Like with the transition, specify the “initial” state of the object with the selector `#animation {}` (color, size, etc.).

Now, you need to add at least 2 values to the selector: `animation-name` and `animation-duration`. `animation-name` specifies the name of the animation you want the object to undergo, and `animation-duration` says how long you want the animation to take. 

**Keyframes rule**

The animation is specified using the `keyframes` rule. This is basically another selector with the syntax `@keyframes animation-name {keyframes-selector {css styles}}`. The `keyframes-selector` can either be a percentage 0-100% (what you want the animation to look like at a certain moment in the animation) or the keywords `from` and `to`. Here are two examples using each of these possibilities (with `animation-name: colorchange;`):

```html
@keyframes colorchange {
	from{background-color:blue}
	to{background-color:green}
}
```
Or, if the background-color specified in #animation{} is blue, then the following would accomplish the same thing:

```html
@keyframes colorchange {
	to{background-color:green}
}
```
Using percents (this does something different):

```html
@keyframes colorchange {
	0% {background-color:blue}
	50% {background-color:purple}
	100: {background-color:green}
}
```
**Animation duration and repetition**

Add the field `animation-iteration-count` if you want your animation to repeat itself; `infinite` is an option. Other fields you can add are `animation-direction` and `animation-delay`. `animation-direction` specifies which direction you want the animation to run in (reverse, alternate, etc.), and `animation-delay` specifies an amount of time you want to wait before starting the animation.

Note: guidance taken from [w3schools](http://www.w3schools.com/cssref/) CSS and CSS3 tutorials. 

###Section 4: Media Queries

###Section 5: Glyphicons

Bootstrap comes with over 250 [glyphicons](http://glyphicons.com/). These are monochromatic icons and symbols intended for simplicity and ease of use. They are easily incorporated into text, buttons, forms, etc.

Glyphicons are inserted using code in the following format:
`<span class="glyphicon glyphicon-NAME"></span>`

Go to [this link](http://getbootstrap.com/components/) to see a list of available icons under the Glyphicons section. Select one you like, use its appropriate name, and insert it into your page. 

To make something more interesting, let’s create a button that is a link. Find the glyphicon that looks like a download link and add it to your page as a link (This does not need to actually link anywhere).

Now, combine your knowledge of buttons with glyphicons to create a button with an icon on it. Specifically, try to create a “play button” and “pause button” (They do not need to actually do anything). 

These icons are a bit small though, aren’t they? Luckily, we can manipulate the size of these icons. To do so, we may treat them like any component with css. Go to `main.css` and change the size of the glyphicons class to enlarge them from their default size to twice its default. While we’re at it, let’s change their color to red. 

Now let’s place a star glyphicon in the nav bar next to the “Glyphicons” section. See how that looks on the page.

Uh oh! That’s a bit too big to be in the nav bar. To fix this, we want to change the size of just the star icon. Luckily, we can do so by addressing its specific class (`.glyphicon.glyphicon-NAME`). Go to `main.css` and add a section to return the star glyphicon to its default size. 

Finally, let’s combine glyphicons with css transitions to make a “beating” heart. Find the heart icon, add it to your page. Use css transitions to have it gradually grow to a larger size when the cursor hovers over it, and then gradually back to its original size when the cursor moves off of it. 

Your end product should look similar to: ![alt text](glyphicons_section.png)

Perfect! You have now experienced how easy it is to spice up bootstrap pages with glyphicons. 

Glyphicons are just one of many additional components and cool features that bootstrap implements for ease of use. Check out the rest of [http://getbootstrap.com/components/](ttp://getbootstrap.com/components/) to see what else is available.

###Section 6: iFrames