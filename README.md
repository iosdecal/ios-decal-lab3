# Lab 3 : Stopwatch #
![alt text](/README-images/stopwatch.png)

## Due Date ##
Tuesday, February 21st at 11:59 pm

## General Overview ##
If you haven't noticed already, there's no starter code for this lab. That's because today we would like you to get experience creating an application completely from scratch. 

In this lab, you will be making a simple stopwatch app. In particular, your app must include the following: 

- Start/Stop Buttons that start/stop the time
- Display that indicates how much time has elapsed (seconds). Pressing the start button should reset the stopwatch, while pressing stop should stop the the display from updating.

Also, since we would like you to get familiar with the Model View Controller design pattern, your application structure must include the following:

- a Model class **Stopwatch.swift**
- a View (feel free to either use Storyboard or create the view programmatically)
- a View Controller for your Stopwatch view

We'll be looking over your code when grading, so make sure to spend some time thinking about where your data structures/methods should be located within your project before beginning.

## Some Helpful Time Related Methods in Swift ##

### Swift Timer Library ###

Timer, which is a Foundation library can be used to instantiate a Timer object which waits a certain amount of time and then fires a message to another object.
This example below might be particularly useful to you. After the time interval of .1 (1 second), it will call the method specified by #selector and repeat this action over and over again until the timer is invalidated. 

	Timer.scheduledTimer(timeInterval: 0.1, target: self,
					 	 selector: #selector(ViewController.callSomeMethodWithParams(_:)), 
					 	 userInfo: nil, 
					 	 repeats: true)

Selectors are weird though! You can't pass in any parameter, you can either pass in the timer object as in the example above OR omit the paranthesis and just call the method without params. "callSomeMethodWithParams" would have this structure:

    func callSomeMethodWithParams(_ timer: Timer) {
    	// ...
    }

To invalidate a timer, simply call

	timerInstance.invalidate()
        
More info at https://developer.apple.com/reference/foundation/timer.

## Swift Date Object ##

A Swift Date object represents a single point in time. You can see the different properties and methods available here: https://developer.apple.com/reference/foundation/date.

A property you might find particularly useful is:

	dateObject.timeIntervalSinceNow
    
This returns a TimeInterval object representing the time passed in the format of a double. The format of the double is (seconds).(milliseconds) so 42.5 would mean 42 seconds and half a millisecond.

## Representing Time as a String ##

Initialize a string with the format (using string interpolation) "%02d: %02d.%d".
"2d" just means that 2 digits will be visible.

Example:

	let timeString = String(format: "%02d:%02d.%d", double1, double2, double3)
