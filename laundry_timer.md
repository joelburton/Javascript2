Laundry Timer
=============
Covers:
	Complex State
	Timers
	The Date object
	setInterval and setTimeout


Bonus:
	Queues
	Configuration


Almost no one has private laundry in SF. Fortunately, most people have a laundromat near enough to their house, and so they leave their laundry there. I usually do multiple loads at once, so I've developed a queueing system to handle it.

Here's what we want to happen:
We want to be able to start a timer
	The timer's length should be variable depending on whether or not it's a washer or dryer
	We should be able to configure how long the washer / dryer goes.
We want to be able to have multiple timers going
We want to be able to watch the countdown of each timer update
Once a timer is done, we want to indicate that it's finished, and mark the load "picked up" or "Moved to dryer" depending on the kind
"move to dryer" should automatically create a dryer load

Start by opening [laundry.html](https://github.com/hackbrightacademy/Javascript2/blob/master/laundry.html)
We're going to modify it so we can get some information from the user, and interact with it to make our timers run.

We need to get this information initially:
How long does a washer load take?
How long does a dryer load take?

Create a form that gathers that information using number-type input fields. 

Next, we'll need buttons for creating a new load - one for washer, one for dryer. Remember to give them IDs so you can attach events to them.

Attach events to the buttons, and create functions that respond to them. We'll do this in stages, so right now the functions should do 3 things:  
- Create a table row
- Create 4 columns in the row
	- Load ID (just one larger than the last ID)
	- Load Type (just put "wash" or "dry")
	- Time remaining - put the number of minuites as a string + the string ":00"
	- Actions - this should be two buttons, "cancel" and "move to dryer" or "finish load" depending on the type.
- Attach actions to the buttons



