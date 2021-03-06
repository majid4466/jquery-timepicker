Timepicker Plugin for jQuery
========================

[<img src="http://jonthornton.github.com/jquery-timepicker/lib/screenshot.png" alt="timepicker screenshot" />](http://jonthornton.github.com/jquery-timepicker)

[See a demo and examples here](http://jonthornton.github.com/jquery-timepicker)

[A demo of disabled times could be seen here](http://jqeedu.tuxfamily.org/demos/timepicker_with_disable/)

jquery.timepicker is a timepicker plugin for jQuery inspired by Google Calendar. It supports both mouse and keyboard navigation.

Requirements
------------
* [jQuery](http://jquery.com/) (>= 1.6 recommended; jquery-timepicker has not been tested on 1.5)

Usage
-----

```javascript
$('.some-time-inputs').timepicker(options);
```

```options``` is an optional javascript object with parameters explained below.

Options
-------

- **className**
A class name to apply to the HTML element that contains the timepicker dropdown.
*default: null*

- **minTime**
The time that should appear first in the dropdown list.
*default: 12:00am*

- **maxTime**
The time that should appear last in the dropdown list. Can be used to limit the range of time options.
*default: 24 hours after minTime*

- **showDuration**
Shows the relative time for each item in the dropdown. ```minTime``` or ```durationTime``` must be set.
*default: false*

- **durationTime**
The time against which ```showDuration``` will compute relative times.
*default: minTime*

- **step**
The amount of time, in minutes, between each item in the dropdown.
*default: 30*

- **timeFormat**
How times should be displayed in the list and input element. Uses [PHP's date() formatting syntax](http://php.net/manual/en/function.date.php).
*default: 'g:ia'*

- **scrollDefaultNow**
If no time value is selected, set the dropdown scroll position to show the current time.
*default: false*

- **lang**
Language constants used in the timepicker. Can override the defaults by passing an object with one or more of the following properties: decimal, mins, hr, hrs.
*default:* ```{
	decimal: '.',
	mins: 'mins',
	hr: 'hr',
	hrs: 'hrs'
}```

- **disabledTimes**
Array of times you want to disable and make unselectable. As an example, the following code transforms input#start-time to a timepicker widget in which the second, third, ... times are disabled.

	```javascript
	jQuery('#start-time').timepicker({disabledTimes: [1,2,3,5,6,9]});
	```

Methods
-------

- **getTime**
Get the time using a Javascript Date object, relative to today's date.

	```javascript
	$('#getTimeExample').timepicker('getTime');
	```

	You can get the time as a string using jQuery's built-in ```val()``` function:

	```javascript
	$('#getTimeExample').val();
	```

- **getSecondsFromMidnight**
Get the time as an integer, expressed as seconds from 12am.

	```javascript
	$('#getTimeExample').timepicker('getSecondsFromMidnight');
	```

- **setTime**
Set the time using a Javascript Date object.

	```javascript
	$('#setTimeExample').timepicker('setTime', new Date());
	```

Events
------

- **showTimepicker**
Called when the timepicker is shown.

- **hideTimepicker**
Called when the timepicker is closed.

- **changeTime**
Called when a time value is selected.
*default: null*

Theming
-------

Sample markup with class names:

```html
<span class="ui-timepicker-container">
	<input value="5:00pm" class="ui-timepicker-input" type="text">
	<ul class="ui-timepicker-list optional-custom-classname" tabindex="-1">
		<li>12:00am</li>
		<li>12:30am</li>
		<li class="disabled">01:00pm</li>
		<li class="disabled">01:30pm</li>
		<li>02:00pm</li>
		...
		<li>4:30pm</li>
		<li class="ui-timepicker-selected">5:00pm</li>
		<li>5:30pm</li>
		...
		<li>11:30pm</li>
	</ul>
</span>
```


- - -

This software is made available under the open source MIT License. &copy; 2012 [Jon Thornton](http://www.jonthornton.com), contributions from [Anthony Fojas](https://github.com/fojas), [Vince Mi](https://github.com/vinc3m1), [Nikita Korotaev](https://github.com/websirnik), [Spoon88](https://github.com/Spoon88), [elarkin](https://github.com/elarkin), [lodewijk](https://github.com/lodewijk)
