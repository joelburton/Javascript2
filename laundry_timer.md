Laundry Timer
=============

Almost no one has private laundry in SF. Fortunately, most people have a laundromat near enough to their house, and so they leave their laundry there. I usually do multiple loads at once, so I've developed a queueing system to handle it.  

This is a much more complicated exercise than the previous one. We'll be reintroducing the concept of a main event loop. Rather than waiting for user input however, the main event loop will just run every second. Our functions are going to be executed either in response to events (mouse clicks), or once a second.

###Dramatis Persone###
[document.getElementsByClassName()](https://developer.mozilla.org/en-US/docs/Web/API/document.getElementsByClassName)  
[element.className](https://developer.mozilla.org/en-US/docs/Web/API/Element.className)  
[document.createElement()](https://developer.mozilla.org/en-US/docs/Web/API/document.createElement)  
  

###Table of Concepts###
Event Loops  
Timers / Intervals  
Event Listeners  
DOM Node Creation  
DOM Tree Manipulation [(The `document` Object)](https://developer.mozilla.org/en-US/docs/Web/API/document)  
DOM Node Manipulation  [(The `element` Object)](https://developer.mozilla.org/en-US/docs/Web/API/element)  




Sometimes, when someone in the real world wants some software written, you get a set of requirements. Basically it's just a list of behaviors people want, with a little bit of information about what buttons they're interested in seeing. Sometimes you won't have all the information you need in the requirements, which might require a little bit of freestylin'. Sometimes you'll want to go back and demand more information however, especially when you're a junior developer.  
### Requirements:###

- We want to be able to start a timer
	- The timer's length should be specified by an input box
	- We should have an input box for washer length, and dryer length
	- We should have a button that creates a new load of the specified type
- We want to be able to have multiple timers going
- We want to be able to watch the countdown of each timer update
- Once a timer is done, we want to indicate that it's finished somehow


### Let's get some information ###

Start by opening [laundry.html](https://github.com/hackbrightacademy/Javascript2/blob/master/laundry.html)
We're going to modify it so we can get some information from the user, and interact with it to make our timers run.

We need to get this information initially:
- How long does a washer load take?
- How long does a dryer load take?

Create a form that gathers that information using number-type input fields. Also, add two buttons to the form, one that says "New Washer Load" and one that says "New Dryer Load". This is the same kind of "not submitting" form we used in the last exercise, so don't use a `form` tag. Just use a `div`.  
  
### The Main Event Loop ###
Once you've got a form somewhere on the page we need to create 4 functions.  

The first function needs to be able to find all of the times on the page, and decrement them.    
- We'll want to use `document.getElementsByClassName()`. It provides an array of DOM nodes.  
- Loop through the DOM nodes, and get the time from their `.innerHTML` property.   
- Decrement the time by 1 second.  
- Make sure to decrement a minuite if the seconds are at 00.  

Once that works, you'll be able to call it over and over again. Don't try to do anything else in this function - this is why we have functions. They do one job, and then we can call them over and over again.  

The second function needs to be able to stop a timer once it reaches "00:00".  
- Find all the timers again. See if any of them are at "00:00".  
- If so, remove the timer class.   
	- You can do this by setting the `.className` property of the element.  

### The Event Listeners ###

The third function needs to be able to create a new washing machine row. 
- Find the table in the DOM
- Use `document.createElement('tr')` to create a table row  
	- This **returns** an element, so put it in a variable.  
- Use `document.createElement('td')` to create a table column  
- Set the `.innerHTML` property to be the value from the input tag from before.  
- Use `variableContainingElement.appendChild(otherElement)` to put the `td`s inside the `tr`. 
- Then, use the same method to append the TR to the table.

The fourth function needs to be able to create a new dryer row.
- Replicate the functionality from the washer row, but change the type / time.


