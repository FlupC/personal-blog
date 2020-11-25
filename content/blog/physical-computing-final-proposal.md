---
path: pCompFinalProposal
date: 2020-11-25T00:38:01.869Z
title: "Physical Computing: Final Proposal"
description: Final Project Proposal for Physical Computing
---
# 3D Topography

### Concept

For my final I want to explore the topography of Connecticut. 

My family sold the house I grew up in this year, which was very sudden, but for the best. I had never really been that connected to my home state, but when I realized I may never go back there, I realized that I had come to really appreciate it as a place to grow up. 

We ended up renting a house not too far from where I grew up to get through the pandemic, but it made me think about what it was that caused me to become so nostalgic. What kept popping into my head was that it is a beautiful place. It has lovely forests, beautiful colors, coastal towns, and even a few mountains. 

Then, I stumbled across [this site](https://cteco.uconn.edu/viewers/ctelevation/), which shows the elevation in CT using colors.

When I started thinking about my pComp final, I wanted to do something that visualized something different. One of my favorite artists is Refik Anadol, who creates brilliant visuals with machine learning. Often, they almost look 3D, like they are about to pour into our world. I thought I could sort of make that happen.

So,

I am going to visualize the topography of CT using machine learning and Physical Computing.

### How it Works

I want to create a square of motors that linearly actuate pieces of wood or acrylic in and out depending on the elevation of the image loaded.

I think that using the same set of images could get repetitive, so I am going to use RunwayML to train a model that creates fake topographies of CT. I will then pass that into P5, which will simplify the image to a 5x5 grid, then based on the color in the grid. The motor will push it in or out a certain distance.

Unfortunately, linear actuator stepper motors are super expensive, so I found [this](https://www.youtube.com/watch?v=2vAoOYF3m8U&list=WL&index=9&t=5s&ab_channel=PotentPrintables) online. I am going to 3D print these, then use them to push things in and out.

My initial instinct was to use the large motor, but the more I think about it, the more I want to use the small ones. They take up less room, and I can use fewer and lighter materials to actuate. 

### Structure 

These are not done because I need to 3D print the piece before I can get exact measurements and see it better, but here are the approximate measurements for the large motor mod. 

![Measurements](/../assets/pComp/final/measurements.png)

I think I want to put them next to one another equidistantly and drill the motor mounts into a thin sheet of wood.

![Mounting](/../assets/pComp/week8/mounting.png)

Then, I want to slide that piece into a frame that I will build on the floor somehow. Like so:

![Frame and Connection](/../assets/pComp/week8/frame.png)

### Progress 

My plan before next class is to have the ML model DONE, the p5 sketch to simplify it done, and have 4 motors mounted and moving (not linked to sketch yet). It will be a push, but I can do it.


