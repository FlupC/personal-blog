---
path: ml4w-week3
date: 2020-09-29T20:06:16.232Z
title: Machine Learning for the Web - Week 03
description: HW3 for ml4w - Yining Shi, Fall 2020
---
# Artist Eye

[LIVE HERE](https://editor.p5js.org/FlupC/sketches/mHTxQIZmI)

Starting a program like ITP means that everyone is coming from a different backgrounds. Some students are already software engineers, others are incredible artists in their own right. To see the work being made in class brings with it a lot of imposter syndrome and I caught myself thinking "I wonder what it would be like to see from their eyes. 

Lucky for me, thats kind of possible. I didn't just want to use a style transfer, though. I wanted to use bodyPix to pull people out of those backgrounds. I felt like when an artist looks at the world, they don't change how we look, but rather how the world does. Or, perhaps, I am more inspired by landscape work than portraitures.

First, I had to make bodyPix work, which was no issue. I ran into an issue right afterwards, when I tried to replaced the black BG with a picture. 

![broken bodypix](/../assets/ml4w/broken.png)

It replaced the wrong part, but Yining was able to help me fix it by updating ml5. I was on the wrong version, which was funny. 

![Working Virtual Background](/../assets/ml4w/workingVB.png)

After that, I was not ready to understand style transfer, so I wanted to turn my P5 sketch into a stereoscopic image for google cardboard. 
TURNS OUT, there are currently no functioning p5 libraries that allow me to do so. I will come up with a solution with A-Frame, Three.js, or hard coding, but for the time being, there was more to be done.

Using Runway's arbitrary photo model and with a lot of helpful handholding from Yining, I was just shy of getting it to work. I am 1 error message away from victory.

WORKING MODEL TO BE POSTED 