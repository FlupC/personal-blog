---
path: icm1
date: 2020-11-10T03:20:00.242Z
title: "Intro to Computational Media: Assignment 1"
description: "ICM - Mimi Yin Fall 2020 "
---
# Color and Self Reflection

In 1810, Goethe wrote a book about his view on the nature and perception of color. While it was not viewed as legitimate by physicists, his writing has influenced many artists, from J.M.W Turner to Kandinsky, in their approach to the use of color in their respective works. Film directors, such as Wes Anderson and Stanley Kubrick, use color as a primary tool in portraying their films' messages and intentions. The same color can be interpreted different ways given the context, composition or subject matter of the shot. We explore this relationship between color and emotion, with the viewer functioning as the subject matter. Our sketch utilizes a color gradient and a prompt to get the user to confront their emotional relationships to color. How does the viewer feel when they see their reflection in tinted by different color gradients? Does one person have the same reaction to blue as another person? How does the person's day affect their response to our question, "How are you feeling?"? Can someones mood change depending on the color that they see on the screen? Is there even an objective relationship at all, without a subjective narrative in mind? 


We want to move forward with this project by utilizing the data that we receive from the viewers in order to answer some of the questions previously mentioned. 


The first thing you’ll notice is the definitely the gradient and how it seems to move between colors and brightnesses across the screen. The way this was done was by creating a 10x10 image and iterating across the X and Y. For every Y value, we use a linear interpolation, or Lerp, function to gradate the hue vertically, filling in the intermediate colors between the start and end colors. Then, for every X value, we lerp from a minimum brightness and saturation and lerp up or down. This is what creates what is sort of a 3D gradient mapped over 2D space. 


The hue counts up to 360, then down to zero, then back up again. This creates a continuous cycle for hues. The brightness and saturation only change a little using Perlin noise, to keep the values neat. 


In the corner, there is a submit box that will take whatever you write into it and turn it into a text object that floats up the screen. At the same time, it will save a snapshot of what you felt and the colors at that moment. 


We couldn’t really find a clean way to do this with javascript, so we set up a local storage variable that keeps track of how many sentiments you’ve created so you can combine them later.


Link to our demo:

https://vimeo.com/477364731 


link to our code: 

https://editor.p5js.org/FlupC/sketches/vLWTrCerP 