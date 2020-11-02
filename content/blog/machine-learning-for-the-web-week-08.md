---
path: ml4w-week8
date: 2020-11-02T19:46:12.447Z
title: Machine Learning for the Web - Week 08
description: HW8 for ml4w - Yining Shi, Fall 2020
---
#CoralGAN

For this week's assignment, I decided to use Runway to create my own Image Generation model.

Using the existing StyleGAN, I wanted to generate reef fish that do not exist. 

First, I found [this](https://www.coralreefimagebank.org/coral-reefs) website, which had a ton of different coral reef pictures from all over the world.

I tried to choose the ones that had a bit more color and life to them, I also had to remove a ton of images because they were shot with land or in odd shapes (circles). But I still had about 400 images to use.

So, I got to training. I trained using StyleGAN2 against the Scenery pre-trained dataset. It worked out quite well.

`vimeo: https://vimeo.com/474809844`

After it was completed I was incredible happy with the results. I wish I trained it with a couple thousand pictures, but with 400 images and 5000 steps, I got a mix of hyper-realistic, artistic, and haunting reefs. Here are some examples. 

`vimeo: https://vimeo.com/474809731`

![Realistic Image A](/../assets/ml4w/CG_RealisticA.jpg)
![Realistic Image B](/../assets/ml4w/CG_RealisticB.jpg)
![Artistic Image A](/../assets/ml4w/CG_ArtisticA.jpg)
![Artistic Image B](/../assets/ml4w/CG_ArtisticB.jpg)
![Haunting Image A](/../assets/ml4w/CG_hauntingA.jpg)
![Haunting Image B](/../assets/ml4w/CG_HauntingB.jpg)