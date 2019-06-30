---
layout: post
title:      "Shape CLI Ruby Gem "
date:       2019-06-24 00:53:05 -0400
permalink:  cli_-_my_first_ruby_gem
---

### Conception 
_____________________________________________________________________________________________

Shape CLI 

Shape.com - Popular articles of the week in fitness/mind-and-body

* The Shape CLI will scrape data from on Shape.com.  It lists the top articles, as well as their respective attributes: date, author, url, in Fitness/mind-and-body catagory.  Shape_cli goes one level deep, prompting the user to chose an article to read.  

* The first running version is a test CLI, which will only dive into lifestyle.  It will ask the user if they want to read the top articles, starting with options in Fitness, Mind & Body.  

[Shape/lifestyle](https://www.shape.com/lifestyle)

* The CLI calls on the Scraper class and takes in the data from Lifestyle - Popular Topics.  Shape CLI returns the details of the article chosen by user input.  It will display the author, summary and date.  

* The user can chose to read the article after examining the details, or browse each article's details, before, if interested in deciding which article to read in full.

* The module will be set up via the Scraper class, Topic Class and the Shape_CLI for our output. 

* The example CLI output and flow can be found [here](https://jessekathryn.github.io/cli_-_my_first_ruby_gem).

* The data being displayed will be scraped through a scraper class method and out put the 5 popular topics for Lifetstyle.  Then, it will iterate through the chosen input and return the author, summary, and the date of the chosen article.  For a second level, the user can chose to read the article and this will be done through a scaper class method that returns the article.

> Example CLI 
> 


```
SHAPE CLI																																														 

Shape CLI is a quick source for the latest popular topics in Lifestyle!    

Want tips and info on beauty, fashion, travel, health, sex, love and everything else you need to live a fuller and happier life?

Yes or  No 

--> Yes

Enter a number from the list of latest popular topics in Lifestyle below to view more details

1.   5 Ways to Change Your Life -- For Good
2.   What Really Helps Get Rid of Cellulite?
3.  10 Simple Rules for a Healthy Life
4.   3 Cool Winter Hairstyles
5.   7 Mind Tricks for Self-Motivation

--> 3

10 Simple Rules for a Healthy Life 

Five no-fail strategies to finally stick to your goals

by Barbara Brody

March 01, 2019

Are you interested in reading, "10 Simple Rules for a Healthy Life?"

Yes or  No 

--> No

Enter a number from the list of latest popular topics in Lifestyle below to view details

1.   5 Ways to Change Your Life -- For Good
2.   What Really Helps Get Rid of Cellulite?
3.   10 Simple Rules for a Healthy Life
4.   3 Cool Winter Hairstyles
5.   7 Mind Tricks for Self-Motivation

--> 5

7 Mind Tricks for Self-Motivation

Experts reveal their time management skills to show you how to be more productive with your daily to-do's

by Sara Angle

December 12, 2015

Are you interested in reading, "7 Mind Tricks for Self-Motivation?" 

Yes or  No 

--> Yes

7 Mind Tricks for Self-Motivation

Experts reveal their time management skills to show you how to be more productive with your daily to-do's

Your alarm goes off at 6 a.m. Go to the gym, or hit snooze? A Law & Order marathon is on...but those stacks of dishes and dirty laundry aren't going to wash themselves. And those 32 unread emails in your inbox? Someone has to answer them. There are tons of things that come up every day that you know you should do, but sometimes getting the motivation to take action just seems unbearable. We asked top experts in productivity, time management, and motivation for the tricks they use to get things done in their own lives. Now, you can try them for yourself! (Need motivation fast? Try these 2-Second Motivation Boosters.)

by Sara Angle

December 12, 2015

Enter Back to return to articles or Home to return to Shape CLI 

--> Back

Enter a number from the list of latest popular topics in Lifestyle below to view details

1.   5 Ways to Change Your Life -- For Good
2.   What Really Helps Get Rid of Cellulite?
3.  10 Simple Rules for a Healthy Life
4.   3 Cool Winter Hairstyles
5.   7 Mind Tricks for Self-Motivation

--> Home

SHAPE CLI		

Shape CLI is your quick source to articles popular in Lifestyle!    

Want tips and info on beauty, fashion, travel, health, sex, love and everything else you need to live a fuller and happier life?

Yes or  No 

```
