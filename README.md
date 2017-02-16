# Lab 3 : Stopwatch
![Image of Yaktocat](https://akbapu14.github.io/stopwatch.png)

## Due Date
Tuesday, February 21st at 11:59 pm

## General Overview
You will be creating a simple stopwatch app.
Requirements:
1. Start/Stop Buttons that start/stop the time
2. Display down to the seconds the time that's being elapsed

Some helpful methods:

## Swift Timer Library

Timer, which is a Foundation library can be used to instantiate a Timer object which waits a certain amount of time and then fires a message to another object.
This example below might be particularly useful to you. After the time interval of .1 (1 second), it will call the method specified by #selector and repeat this action over and over again until the timer is invalidated. 

        Timer.scheduledTimer(timeInterval: 0.1, target: self,
            selector: #selector(ViewController.callSomeMethodWithParams(_:)), userInfo: nil, repeats: true)
Selectors are weird though! You can't pass in any parameter, you can either pass in the timer object as in the example above OR omit the paranthesis and just call the method without params. "callSomeMethodWithParams" would have this structure:

    func callSomeMethodWithParams(_ timer: Timer) {
    }
To invalidate a timer, simply call

        timerInstance.invalidate()
        
More info at https://developer.apple.com/reference/foundation/timer.
## Swift Date Object
A Swift Date object represents a single point in time. You can see the different properties and methods available here: https://developer.apple.com/reference/foundation/date.

A property you might find particularly useful is:

    dateObject.timeIntervalSinceNow
    
This returns a TimeInterval object representing the time passed in the format of a double. The format of the double is (seconds).(milliseconds) so 42.5 would mean 42 seconds and half a millisecond.

## Representing Time as a String

Initialize a string with the format (using string interpolation) "%02d: %02d.%d".
"2d" just means that 2 digits will be visible.

Example:
    
        let timeString = String(format: "%02d:%02d.%d", double1, double2, double3)