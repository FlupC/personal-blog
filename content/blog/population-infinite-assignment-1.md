---
path: popInf-asgn1
date: 2020-09-23T18:16:55.004Z
title: "Population Infinite: Assignment 1"
description: Puppeteer.js Assignment for Population Infinite
---
# Puppeteer Assignment

For this specific assignment, I chose to make something that breaks up with your partner, unfollows them, then watches all your stories and likes some posts to help you cope. 

VIDEO HER

First it was a matter of logging in, which was not too tough as it was in the examples from class.

```
import puppeteer from "puppeteer";

const browser = await puppeteer.launch({
  headless: false,
  slowMo: 10,
});

const context = await browser.createIncognitoBrowserContext();
const page = await context.newPage();

await page.goto("https://www.instagram.com", { waitUntil: "networkidle2" });

await page.setViewport({
  width: 1280,
  height: 720,
});

console.log("open the browser window, and login to instagram:");

await page.type("input[name=username]", "YOURS@MAIL.com", {
  delay: 50,
});
await page.type("input[name=password]", "PASSWORD", { delay: 50 });
```

After that, there were a couple of popup prompts that I needed to get through. I tried to ignore them, but they were really getting in the way. I was also having issues with my browser not detecting them early enough and causing an error. I was able to find online: ```await Promise.all([]);``` that forced things to wait until they happened. 

```
//wait for credentials to be typed in
await Promise.all([
  page.click("button[type=submit]"),
  page.waitForNavigation({ waitUntil: "networkidle0" }),
]);

//Not now A
await Promise.all([
  page.click("button.yWX7d"),
  page.waitForNavigation({ waitUntil: "networkidle0" }),
]);

//Not Now B
await page.click("button.HoLwm");
```
Obviously, after you get into instagram, you need to tell your partner that you're THROUGH. So, puppeteer needs to navigate to the individuals page and select message. 

```//Send a Message over insta DM
//click searchbar
await page.click("a.xWeGp");

//type name
await page.type("input[type=text]", "ACCOUNT", { delay: 50 });

//wait while it loads
await page.waitFor(3000);

//Click name
await page.click("div.fuqBx");

//wait as to not freak it out
await page.waitFor(8000);
//click message, which is the first button on the page :)
await page.click("button[type=button]");

//wait for everything to load
await page.waitFor(3000);
//tyle message
await page.type("textarea[placeholder='Message...'", "Hey... we're OVER", {
  delay: 50,
});
//send message
await page.keyboard.press("Enter");
await page.waitFor(3000);
```
After, you OBVIOUSLY need to unfollow them, so we go to their page and unfollow

```
//go to their profile
await page.click(
  "#react-root > section > div > div.Igw0E.IwRSH.eGOV_._4EzTm > div > div > div.DPiy6.Igw0E.IwRSH.eGOV_.vwCYk > div.PjuAP > div > div > div.m7ETg > div > div.Igw0E.IwRSH.eGOV_.ui_ht.n4cjz > button > div > div.Igw0E.IwRSH.eGOV_.ybXk5._4EzTm > div"
);

await page.waitFor(1000);
//unfollow
await page.click(
  "#react-root > section > main > div > header > section > div.nZSzR > div.Igw0E.IwRSH.eGOV_.ybXk5._4EzTm > div > div:nth-child(2) > div > span > span.vBF20._1OSdk > button"
);
await page.waitFor(1000);
await page.click(
  "body > div.RnEpo.Yx5HN > div > div > div > div.mt3GC > button.aOOlW.-Cab_"
);
await page.waitFor(2000);

//back to home
await page.click("img.s4Iyt");
```
Then, we need to watch some other people's stories and like some posts to get our mind off of it. This was a little tricky because my usual methods for building arrays and iterating through them were slightly altered. I also have an issue where it should like posts continuously, but it kind of doesn't? Not sure exactly the issue, but I suspect it has something to do with the infinite scroll nature of instagram. 

```
//stories
await page.click("div.Fd_fQ");
await page.waitFor(2000);

//click through all stories
while (!!(await page.$("div.coreSpriteRightChevron"))) {
  await page.click("div.coreSpriteRightChevron");
  await page.waitFor(1000);
}

//like a bunch of stuff on your page
const likesArray = await page.$$("[aria-label='Like']");
console.log(likesArray);
for (const like of likesArray) {
  await page.waitFor(1000);
  await like.click();
  await page.waitFor(1000);
}

await page.waitFor(5000);
await page.close();
```
