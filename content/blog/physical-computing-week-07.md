---
path: pCompWeek07
date: 2020-10-24T22:57:45.360Z
title: "Physical Computing: Week 07"
description: Labs from Physical Computing Week 7
---
# Lab: Two-Way (Duplex) Serial Communication Using An Arduino and P5.js

### Sending Multiple Serial Data Using Punctuation
So, to begin, the lab asked me to set up an accelerometer, but I do not have one, so I will be using the built in accelerometer for this lab. I also wired a pushbutton to the Arduino on pin D2. Here is my Circuit:

![Accelerometer Circuit](/../assets/pComp/week7/circuit.png)

From here, I took input from the built-in accelerometer and was outputted it to my serial monitor. 

![Output](/../assets/pComp/week7/output.png)

Here, however, I began to get slightly weird numbers. I think that the way that the Arduino's built in accelerometer processes the data is approximately between -1 and 1, so I will use those ranges for now. I am sure there is something more to it, though. 

### Receive the data in P5.js

While working on this section, I had some issues with errors in the beginning, but I was able to sort them out very quickly. I think it was mostly syntax errors, so nothing major. 

I also had to be careful not to use all the same numbers because of my sensor range being different. When I was done, my serialEvent() looked like:

```
  let inString = serial.readStringUntil('\r\n');
  
  if (inString.length > 0 ) {
    var sensors = split(inString, ',');
    if (sensors.length > 2) {
      locH = map(sensors[0], -1, 1, 0, width);
      locV = map(sensors[1], -1, 1, 0, height);
      circleColor = 255 - (sensors[2] * 255);
      console.log(locH,locV,circleColor)
    }
  }
}
```
The sketch can be found [here](https://editor.p5js.org/FlupC/sketches/uRnRdhpk8)

And the final product looks like:
`vimeo: https://vimeo.com/471962819`

### Flow Control: Call and Response (Handshaking)

Here, I simply followed the instructions to add the code to make it so the code doesn't immediately fill the Serial Buffer. I did have an issue where Serial.println() was giving me a string of ASCII codes instead of "hello", but it was because I used a single-quote delimiter, which C doesn't like.

After implementing all of the proper code to limit the speed at which things deliver, the functionality remains unchanged, so i am confident that the results are correct. 

### Get Creative

[Sketch Here](https://editor.p5js.org/FlupC/sketches/mqCVLbxHR)

For this part, I chose to make a motion controlled drawing.

For this, I quickly changed a few things. I wanted the user to hold the breadboard like a remote, so I swapped the X and Y positions, so that tilting up would bring the circles up, and down will send them down.

Next, I realized that I didn't want to have circles at all, but instead a line that could be cleared by hitting the button. 

To do this, I used 2 previous Location variables, that held the last value of the locV and locH. This would create lines.

The final product looks as follows:

`vimeo: https://vimeo.com/471962840`

You'll see its quite wonky, but it has the basis for some potentially great ideas. 
