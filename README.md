###SWABATs
+ make custom HTML5 data attributes and use the jQuery data method to retrieve (one argument) and set values (two arguments)
+ retrieve and set values from forms using the jQuery .val method
+ validate form input with common validation functions and regex
+ build their own regular expressions

###Motivation
If you really want to create an interactive web application with JavaScript your going to need to interact with your users with more than just clicks and jQuery animations. For almost any web application you’ll also need to take in some kind of data from your users. Today we’re going to learn how to do that.

###Lesson Plan
+ This morning we were able to create a perfectly usable calculator by clicking buttons, but wouldn’t it be nice to be able to input values instead?
+ The easiest way get and set data values in the DOM is jQuery with the HTML5 data attribute.
+ Here is an example of how you can set the data attribute within an HTML tag: 
		
		<ul id="user-list”>
		<li data-user-id="1" data-online="true"> Bob </li>
	 	<li data-user-id="2" data-online="false"> Joe </li>
	    <li data-user-id="3" data-online="true"> Tom </li>
	    </ul>
+ To use a data attribute you just need to start off with the word “data” followed by a dash and whichever word(s) you want to use to label the data you are storing. 
+ In the example above you can see that each li element in our list has 2 data attributes
	+ user-id - set to each user’s id
	+ online - set to true or false
+ The status of each of these data fields can be retrieved via jQuery like so:
	+ $('#user-list').find('li').each(function(){
	    + alert($(this).data('user-id')); //prints 1, 2, 3
	    + alert($(this).data('online')); //prints true, false, true   
	+ });
+ Here we have set up an each loop to display the data values for each but there are many other ways that these data attributes can be useful - for instance in this case you could set the color or other style of each li based on whether or not the user online.
+ We can also get and set these data attributes in the following way:
	+ // One argument gets data attribute specified
	+ $('#foo').data('online');
	 
	+ // Two arguments (2nd argument) sets the data attribute specified 
	+ $('#foo').data('online', 'true');

	+ // Clearing data by setting to an empty string
	+ $('#foo').data('online', ' ');
+ Another way that we can get and set data is with HTML5 form input tags and the jQuery val method.
+ `<input type="text" name="first-name">`

+ //retrieve value from input 
+ var firstName = $('input[name="first-name"]').val();
+ Input tags always have at least two values:
	+ A type that indicates the type of input tag that should be displayed (text, checkbox, radio button, etc.)
	+ A name that acts like a label for the data 
+ We can also set things like an id or class on the input tag and this can hepl simplify our syntax like so:
	+ `<input type="text" name="first-name" id="first-name">`
	+ var firstName = $('#first-name').val();
+ There are a couple of ways that we can set the value for an input. We can use the .val() method with an argument - when we supply an argument .val() will set the value of the input field rather than get the values
	+ `<input type="text" name="first-name">`

	+ //setting value from input 
	+ $('input[name="first-name"]').val('Bob');
+ We can also set the value within the HTML input tag by setting the attribute value like so:
	+ `<input type="text" name="first-name" value="Bob">`
+ Here is a summary of how to use .val();
	+ // No argument gets value
	+ $('#foo').val();

	+ // One argument sets the value 
	+ $('#foo').val('true');

	+ // Clearing value by setting to an empty string
	+ $('#foo').val(' ');
+ We’re going to spend the rest of the day practicing this with a calculator input lab and a task lister lab.


<a href='https://learn.co/lessons/hs-advanced-web-design-teachers-guide-html5' data-visibility='hidden'>View this lesson on Learn.co</a>
