---
path: pCompWeekAssignment2
date: 2020-11-11T10:50:14.384Z
title: "Physical Computing: Assignment 2"
description: Physical Computing Assignment 2
---
# Artist's Portal

Hi! I am sorry that this blog post is unfinished - I ran out of time before class, but I did a good job documenting and do plan on finishing this blog.

I "completed" the piece, but it doesn't work perfectly, which is new for me (I always finish everything on time). I have been up all night trying to make every piece work, but p5 is working against me. Still though, I want to have something accessible so here is a video of my project:

`vimeo: https://vimeo.com/477973468`

You'll see everything appears fine! I have no issues with the arduino or serial communications. The issues lay in p5 and how it processes/loads videos. Even though I am only drawing one video per draw loop, it has a hard time handling this many videos (12). It seems to randomly decide which videos to start and how many. Sometimes a video will also just pause for no reason, which throws the rest of the videos out of sync (making the illusion of continuity between videos vanish). 

I will also get some seemingly random errors involving start(), stop(), pause(), and loop(). I know it feels silly to say "random error," but while I can recreate it for one case, it will occur in another for seemingly no reason. What I have presented here is the most frequently successful version I've made.

I have exhausted my repertoire of coding skills trying to implement workarounds for what appears to simply be the limitations of p5. I have asked plenty of people on the floor, but nobody could come up with any solutions I hadn't already tried :( 