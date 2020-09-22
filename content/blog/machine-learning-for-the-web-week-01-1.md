---
path: ml4w-week2
date: 2020-09-21T16:42:13.209Z
title: Machine Learning for the Web - Week 02
description: HW2 for ml42 - Yining Shi, Fall 2020
---
# Teachable Machine Ukulele Visualizer

[LIVE HERE](https://flupc.github.io/ml4w_HW_CDX/Week2/)

For this project, I wanted to use teachable machine to identify Ukulele chords. I was able to train 5 chords and Roomtone, with about 100+ samples each. 

It worked pretty well, but after about 40 samples, it wouldn't let me save it anymore. Because of this, the only well trained model exists on my live demo (you can also pull the link from that code). 

There were 2 challenges with this project. The first was roomtone. I was never able to get my code to accurately identify the roomtone, which was odd because the teachable machine was able to identify it incredibly reliably. Below you can see a screenshot of what TM outputted about roomtone. My code would never give me a confidence value of above .17 (never the winner). 

![background noise](/../assets/Vml4w/bgnoise.png)

This made it really hard to actually visualize things. Without that "null" state, it is always visualizing, but at a certain point, I cut my losses. This may work better with p5.js pitch detection than with ML. 

The second issue I had was about visualizations in general. I didn't have a specific theme or inspiration in mind, so I made 2 very different visualizations. The first was a simple particle system that just bubbled into the aether. 

![version 1](/../assets/ml4w/uke_v1.png)

Then, I made a flowfield that allows particles to flow along it as it rotates. They appear every 1 second and change colors based on the chords. They then dissappear when the opacity reaches 0. After this, I realized there were so many different visualizations I could try, which really shows the versatility of a ML model. 

![version 2](/../assets/ml4w/uke_v2.png)