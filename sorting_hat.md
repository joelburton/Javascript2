Sorting Hat
===========

Open up [sorting_hat.html](https://github.com/hackbrightacademy/Javascript2/blob/master/sorting_hat.html). It's got a basic bootstrap template there for you, so you don't have to look at those ugly default-internet fonts. It doesn't have much else though, so we'll need to add some things:

First, let's take inventory of the things we need:  
- We need to know how many people we'll be sorting, so we can sort them evenly  
- We need the names of the students who are being sorted  
- We need places to put them after having been sorted  

Since we need to gather some information, let's put a form on the page. Since this form doesn't have to submit anywhere, we don't want an actual `form` tag. 
Add a `div` somewhere in the container, give it the `class` of `form`. 

Inside the `div`, put an `input` tag, another `div`, and a `button`. Give them all IDs.
```html
	<div>
		<input type="number" id="student_count">  
		<button id="set_student_count">Set Student Count</button>  
		<div id="count"></div>
	</div>
```
Next, we're going to practice button-clicking actions that modify the page.

First, we're going to create a `<script>` tag - like this: 
```html
	<script type="text/javascript">
		//Javascript goes here, and runs when the page loads.
	</script>
```
Next, we need a place to store the information we get from the user. Create a globally scoped variable like this, outside of any functions.
```javascript
	var studentCount = 0;
```
Next, we're going to look at what gets put in the input field and add it to the student count. 

First, we'll need to make something that responds to a button click, but for that we'll need to find the button in the DOM. Good thing we gave it an ID. IDs are supposed to be unique, so we can target single DOM nodes with them.
```javascript
	var button = document.getElementById("set_student_count");
```
Now we can add an event listener
```javascript
	button.addEventListener(event, function)
```
The first argument is what event we need to use. It should be "click".  
The next argument is a function. We can pass it any function by value, or we can write idomatic javascript by declaring a function right then and there.  
  
```javascript
	button.addEventListener('click', function(){})
```
Now, within that function, let's tell it what to do.
```javascript
	button.addEventListener('click', function(){
		//assign the value of document.getElementById("student_count").value to a variable
		// add the value to the variable we were using earlier
		// find the 'count' div in the DOM (use getElementById again)
		//write the current count to the 'count' div (use countDiv.innerHTML)
		//clear the input box
	})
```
Great! Now we've used a button click to get data out of a form, without having to use a server at all!

Next, we're going to do that again, but in a more complicated way.

We need to add another input field and button, but this time the type will be `text`, and the button will say "Sort!"

Instructions:  
- Take the value from the student name input field  
- Pick a house at random  
- Check to see if the house is "full". Full means that the house has less than the number of students we're sorting divided by the number of houses. Yes, that does mean you'll need to keep track of who is in each house. (Protip: document.getElementsByClassName() will help you here )
- If the house is full, make sure you pick a new house.  
- Put the student into the house you picked, by displaying the student's name inside the house  
- Decrement the count of students from the count div.

Bonus:  
- Show the sorting hat, as well as the student's name, al la: "Stella LeFevre: Gryffindor!!"  
- Turn house names green as they get full  
- Display a random quote from the sorting hat that goes with the house it's saying (or make up hilarious new ones)  
- Once you've sorted all the students, display a gif and get rid of the input field.  
		If we add more students to be sorted, put the input field back.  
