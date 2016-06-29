#Bootstrap and Transition Workshop
##CS52 16X
###Presenters: Jessie Anderson, Manmeet Gujral, Alex Beals, Jean Zhou, Emma Oberstein, Rob Sayegh
###Date: June 30, 2016
---
###Section 1: Bootstrap grid
Now that you understand the grid system and its purpose, let’s implement it to create a grid of images and/or text.

To begin, let’s create a create a container for our grid with the following code:

	<div class="container">
	</div>

Our container will hold all the rows and columns for our grid, so let’s create a row nested within our container, with the following line of code:

	<div class="row">
	</div>

So now we have a row to work with within our container, so let’s create a column that contains an image of a nice little puppy, like this:

	<div class="col-lg-3 col-md-4 col-xs-6 thumb">
		<a class="thumbnail" href="#">
			<img class="img-responsive" src="https://stiney98.files.wordpress.com/2011/05/cute-welsh-corgi-puppy-400x300.jpg?w=400" alt="">
		</a>
	</div>

Some things to note about the above code:
The line 
	
	<div class="col-lg-3 col-md-4 col-xs-6 thumb>


creates a column that takes up 3 blocks on a large screen, 4 blocks on a medium screen, and 6 blocks on a small screen. As you know, the bootstrap grid is made up of 12 total blocks, so this line determines what fraction of the screen you are working with.
The code following that is to use an image that links to nothing, you can simply copy that format if you would like to use images from the web!
 
__NOTE:__ 

	“href="#"” 
means that clicking your images links to nothing. Try and focus on the grid!

Now that you know how to create a container, row, and column, try and add three extra rows of a varied number of columns to create a grid of images and text that demonstrates the power of the bootstrap grid for clean web design.

Check out this page for some more specific info on the nuances of the bootstrap grid: http://getbootstrap.com/css/#grid

---
###Section 2: Buttons

Let’s add in some buttons. To begin, let’s add in the following code:
 
```html
<button type="button" class="btn"> A Primary Button</button>
```

This is a primary button. In Bootstrap, there are six predefined styles: primary, secondary, success, info, warning, danger and link. To add in these styles, simply add the class ``btn-<style>`` (i.e. btn-info). 

So let’s make our original button a primary button.

We can also change the size of our buttons by adding in the classes ``btn-lg`` or ``btn-sm``. 

Let’s add in a large secondary button, a regular success button and a small info button. 

We can disable our buttons by adding in the disabled property.  

Let’s add in a disabled warning button.

In a new row, let’s add in a danger button with the class btn-block. This will ensure the button spans the entire width of its parent element.

Bootstrap also allows us to group our buttons together using button groups. Let’s add in a basic example:

```html
<div class="btn-group" role="group" aria-label="...">
  <button type="button" class="btn btn-default">Left</button>
  <button type="button" class="btn btn-default">Middle</button>
  <button type="button" class="btn btn-default">Right</button>
</div>
```

We can change the size of the group by adding in the class ``btn-group-<size>``.
We can use a button toolbar to group together multiple button groups.

Let’s try changing the group size or creating a button toolbar.

Bootstrap also allows us to easily add in button dropdown menus via nesting. 
Let’s add in an example in the next row of what a dropdown button menu could look like:

```html
<div class="btn-group" role="group">
    <button type="button" class="btn btn-default dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      Dropdown
      <span class="caret"></span>
    </button>
    <ul class="dropdown-menu">
      <li><a href="#">Dropdown link</a></li>
      <li><a href="#">Dropdown link</a></li>
    </ul>
  </div>
```
---
###Section 3: Transitions and Animations

In this tutorial, we’ll make one transition and one animation (the sample solution has more, and you can make more if you like). The grid is already set up in `index.html`; take a look at the `<!-- Transitions and Animations -->` section of `index.html` to see the setup.

The first `<div>` in this section will be a transition. Now open `css/main.css` and find the section that looks like this: 

```css
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

Since the ID of the first `<div>` is `transition`, you'll be working on the first 2 selectors first. The selector `#transition` will specify the "normal" state of the object (size, color, etc.). You'll need to give it values for `transition-property` (the easiest value is “all”), `transition-duration`, and (optionally) `transition-timing-function` (some fun ones are `ease-in`, `ease-out`, and `ease-in-out`). If you want your div centered, use the line `margin: 0 auto;`.

Now you need to write the selector `#div:hover`. Whatever you put in here will be the state of the object when you hover your mouse over it. The transition between the “normal” and “hovering” state of the object will occur in the time period specified by `transition-duration`, and with the timing specified by `transition-timing-function`. Again, make this whatever you want. Some cool things you can do are change the color of the object, make it grow, and make it rotate or skew using transform.

Now let’s make an animation using the second div. Animations are different from transitions because they happen without the user performing any action with the mouse. Let’s say you gave your second div the ID `animation`. Like with the transition, specify the “initial” state of the object with the selector `#animation {}` (color, size, etc.).

Now, you need to add at least 2 values to the selector: `animation-name` and `animation-duration`. `animation-name` specifies the name of the animation you want the object to undergo, and `animation-duration` says how long you want the animation to take. 

**Keyframes rule**

The animation is specified using the `keyframes` rule. This is basically another selector with the syntax `@keyframes animation-name {keyframes-selector {css styles}}`. The `keyframes-selector` can either be a percentage 0-100% (what you want the animation to look like at a certain moment in the animation) or the keywords `from` and `to`. Here are two examples using each of these possibilities (with `animation-name: colorchange;`):

```css
@keyframes colorchange {
	from{background-color:blue}
	to{background-color:green}
}
```
Or, if the background-color specified in #animation{} is blue, then the following would accomplish the same thing:

```css
@keyframes colorchange {
	to{background-color:green}
}
```
Using percents (this does something different):

```css
@keyframes colorchange {
	0% {background-color:blue}
	50% {background-color:purple}
	100: {background-color:green}
}
```
**Animation duration and repetition**

Add the field `animation-iteration-count` if you want your animation to repeat itself; `infinite` is an option. Other fields you can add are `animation-direction` and `animation-delay`. `animation-direction` specifies which direction you want the animation to run in (reverse, alternate, etc.), and `animation-delay` specifies an amount of time you want to wait before starting the animation.

Note: guidance taken from [w3schools](http://www.w3schools.com/cssref/) CSS and CSS3 tutorials. 

---
###Section 4: Media Queries

---
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

Your end product should look similar to: 

![alt text](glyphicons.png)

Perfect! You have now experienced how easy it is to spice up bootstrap pages with glyphicons. 

Glyphicons are just one of many additional components and cool features that bootstrap implements for ease of use. Check out the rest of [http://getbootstrap.com/components/](ttp://getbootstrap.com/components/) to see what else is available.

---
###Section 6: Adding your own section

Bootstrap makes it easy to create navbars.  There's already a navbar set up, but let's create a new section to the navbar, after the Input Section.

The first thing to do is add in a list element to the navbar.

```html
<li>
    <a class="page-scroll" href="#custom">Your Own</a>
</li>
```

The ‘page-scroll’ class is for use with ‘scrollspy’, the Bootstrap plugin that allows the navbar to change the highlighting as you scroll.  The ‘href’ tag is a link to a section with an id of ‘custom’.  However, that section doesn’t exist yet, so while the section will show up in the navbar, clicking on it won’t do anything.  So let’s add in the section!

```html
<section id="custom" class="custom-section">
    <h1>Custom Section</h1>
    <!-- Whatever you want! -->
</section>
```

This section has an id of ‘custom’, matching the link so that the link will actually function, and has a class ‘custom-section’, which can be separately styled in ‘main.css’.  To match, add a section with a min-height of 100%, a top padding of 60px, centrally aligned text, and a background color of either #fff or #eee depending on where you’re inserting the section.

Now it will work!  Feel free to add custom styles to your section, and add whatever you want from the previous sections into this one.
