---
path: ml4w-week9
date: 2020-11-10T20:08:06.344Z
title: Machine Learning for the Web - Week 09
description: HW9 for ml4w - Yining Shi, Fall 2020
---
# iMessages Text Data

When I was thinking about what I could train for this week, I wanted to do something that was representative of my life.

I couldn't really come up with anything until I remembered that I haven't deleted any texts since 2017. Immediately, I tried to find where the logs were saved on my computer.

I was very quickly able to find where they live, but they are saved as .iChat files. 

Finding a way to convert them to .txt took a while, but I eventually came across [this](https://github.com/peterkaminski09/baskup). GitHub user PeterKaminski09 made BaskUp, which located and turned into text files all of my iChat messages.

There were some drawbacks, though. Firstly, it seems my oldest logs left out what I wrote in response, but the newer logs seem to have kept that data in tact. Additionally there was a "|" at the end of a lot of lines, but I simply did not have the means to easily remove that from 500 text files.

There were 2 more issues too, but I will start with what I trained.

### Model 1

This week, I trained 2 models. The first was inspired when I stumbled across every single text my ex and I sent during our 2+ year relationship. The issue where my responses were missing was present for the first year - year and a half, unfortunately. Here is a sample of what it looked like. 

![TommyText](/../assets/ml4w/tommytext.png)

Anyways, obviously I trained with this data. It was small, so its not great, but here are a couple samples of what was generated:

```
Input: 
So, how do you feel about [the finale of the DC/Vertigo animated series]

Output:
Friend: I enjoyed it a lot, I think it’s one of my favorite shows
Friend: I loved it too! I have so many questions
Friend: On my way back, give me your autocorrect key!
Friend: Yay!
Friend: Okay! I’m at Whole Foods!
Friend: And yeah I’m headed to Lars’ party tonight! I was going to hang out with the pals from last night’s party, and Jenn’s family was here, too!
Friend: It’s awesome that you’re with us, I’m very connected!
Friend: Yeah! Yeah tell me about it when you get back
```

It was very odd to see names and events that I recognized. It was almost as if my whole 2 year relationship flashed before my eyes, or at least I had a massive memory collision and it all happened at once. 

```
Input:
Can we talk?

Output:
Friend: Actually, I have to catch up soon! I’m going to deplane from La Jolla to San Fran around 9:30 because of the heat and I have to be there around 1:25. But I’ll be able to catch up soon!
Friend: Was it easy to make it?
```
```
Input:
Hey! [Are you hungry or free tonight?]

Output:
Friend: I’m free tonight, that’s good! But I’m also going to dinner with my mom, who’s studying for the CIA interview at 4pm
Friend: Yeah I’ll make food before I leave. My flight is at 12:20, and the flight attendants are asking to get on to the next bus at 2:45, which would’ve been awkward if we were sharing a bathroom
Friend: Haha I agree
Friend: Ah okay see you at ~2:45!
Friend: Let’s meet at your place!
Friend: Sweet😘
Friend: Hopping in the shower, I’ll be ready in 20 mins
Friend: Woooo!!
Friend: Going to bed now, should be at the same time
```
It almost reminds me of Eternal Sunshine of the spotless mind. Where the memories are all mixed up, or like a dream. It's surreal to think about the relationship in this way. I apologize for not articulating it well, but imagine reading a sentence that says one thing, but remembering every segment of that sentence as a different event. 

Even a year post-breakup it is weird to think about it. Still, the fact that I am over him makes this a lot more of an intellectual journey than a deeply emotional one. 

### Model 2:

This one was less interesting. It ended up being not that great despite being a huge dataset. 

The way the text files downloaded was in folders marked by dates. With so many text files (and so little time), I couldn't go through and pull them into one folder, instead I just uploaded them all to runway and hit go. Probably not the best idea given the "|" syntax. 

It also removed the "friend: " starting text, which didn't make sense to me. Here are some examples. 

```
Great, so I will make, but for more current spoilers, check out my gaming news channel.

E-mail to Eric Blank at @[REDACTED] or follow him on Twitter @[REDACTED]
```
```
Great, so I will be so happy!!!

)
- At the same time, I recommend taking a lot of the time to cook myself. I love how some things taste and taste, making them so tender, and letting them cook for long enough. Some times I add some oatmeal or apple and make it to it, but I find it to be too spicy. I cook it once in a while and then add a little extra sugar. There's so much flavor to it that I can't really give it a try. Be sure to take a break and have a very happy morning!
```
As you can see, it sort of fell apart in the process. 


