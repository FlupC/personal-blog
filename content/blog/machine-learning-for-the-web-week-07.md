---
path: ml4w-week7
date: 2020-10-25T18:31:46.689Z
title: Machine Learning for the Web - Week 07
description: HW7 for ml4w - Yining Shi, Fall 2020
---
# ReefGAN

For this week's assignment, I decided to use Runway to create my own Image Generation model.

Using the existing StyleGAN, I wanted to generate reef fish that do not exist. 

First, I found [this](https://reefguide.org/index1.html) website, which had identically sized photos of many common reef fish. 

![fishSite](/../assets/ml4w/fishSite.png)

There were benefits and weaknesses to this. The obvious benefit is that I got almost 500 images of reef fish. The downsides being I only got 1 of each species and finding more would require processing the images to be the same size as what I have already collected. Otherwise I will get artifacts generating over the black borders that runway added to these photos.

I also chose to focus on reef fish with colors. I have some silver-bodies, but mostly pretty tropical fish. I did not add bass, sharks, rays, etc. Adding them would likely mess with the body shapes too much. 

To download all the images, I used a Firefox extension called DownThemAll. This exists on chrome, but doesn't work there for me. It grabs all the images on a page and lets you download them.

![downThemAll](/../assets/ml4w/downThemAll.png)

Next, I opened runway and started a new training model.

First, I had to choose something to base the set on, though. I noticed that none of the StyleGAN2 models fit my dataset well. I also realized that my images were smaller than what StyleGAN2 usually uses, so it made the most sense to use StyleGan1 with the caterpillar dataset. 

I added 5000 steps and ran the piece. Here is the training progress

`vimeo: https://vimeo.com/471969776`

At the end, I was actually really happy with some of the results. Here is some output documentation.

`vimeo: https://vimeo.com/471969780`

![fishA](/../assets/ml4w/fishA.JPG)
![fishB](/../assets/ml4w/fishB.JPG)
![fishC](/../assets/ml4w/fishC.JPG)


