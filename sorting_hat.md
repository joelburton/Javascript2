Sorting Hat
===========

Welcome to our first foray into the DOM! Today, we're going to make ourselves a sorting hat.

Our project starts as most javascript-based projects do, with a webpage. We'll need to do a bit of setup first, so let's create a new HTML page. Call it `sorting_hat.html`.

We're going to need the standard HTML boilerplate - a `head`, a `body`, and an `html` wrapped around them. 

Next, we'll need a few components for our sorting hat - we'll need a container `div` to put everything in, first.

Next, make a `div` box for each of the houses - Gryffindor, Slytherin, Hufflepuff and Ravenclaw. Put an `h2` into each of the divs with the name of the house, so we know by looking which house is which.
Visually, we have the houses separated. To javascript though, it's going to be a bit tough to differentiate between all of these divs. Let's give them each an `id`, like so:
 
```html
<div id="gryffindor">
```

Giving each div as an individual object is easiest when they have a unique ID that makes them different. Any time you want to treat a group of HTML tags programmatically differently, you'll need to give them something that makes them unique.

Once you've made a `div` for each house, we'll need to make two more divs, for the information we're going to take in from the user. 
The first `div` is for the number of students we need to sort.
The next `div` is for the name of each student.
List the houses

Take in a name (input field)

Keep the houses somewhere in memory so you can keep track of who is in it

Add an event to the button

	get the name
	randomly sort the name into a house
		first make sure the name hasn't been used before
		then pick a house
			make sure the house isn't "full" (IE, no more than students in class / num houses)
		add students name to house
		display text that they've been added to house
		clear input field
	Once number of students in class have been sorted, remove form from page
	display hats going up gif

