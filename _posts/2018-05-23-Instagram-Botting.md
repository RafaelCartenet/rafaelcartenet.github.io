---
layout: single
title:  "Instagram Botting"
date:   2018-05-23 12:00:00 -0600
author_profile: true
excerpt_separator: "<!--more-->"
header:
  overlay_image: /images/paris.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
---

My experience about Instagram Automation, or "Botting".

<!--more-->


# What are we talking about ?

Instagram Automation, or Botting, is the action to automate tasks a user would do on Instagram. Actions you can perform on Instagram are rather simple, liking a post, commenting a post, following an user, unfollowing an user, posting a post, deleting a post etc. Simple tasks that are thus simple to automatize.
The goal of an Automation for Instagram is to save time for individuals or marketing people to generate some audience for an Instagram Account. The Automation (or Robot) will use your account and directly interact with people in order to try to get them follow your account, and thus increase your audience. Most of Instagram automations are designed to be running 24/7, so that you don't have to worry nor spend time on it and just leave it do the job.

I have been "botting around" on Instagram for more than a year now. The goal of this article is to share my experience and my advise if you wanna get into the adventure or want to improve your current solution.

## My experience

I made my own custom bot based on a pretty efficient API-wrapper, called [instabot](https://github.com/instagrambot/instabot).
You can find several of them on the internet, depending on your favorite coding language etc. These APIs (or wrappers) often also provide some scripts in order to demo their API's key features. These repositories sometimes even provide a script that would run 24h and automate basic actions, such as liking celebrities' followers, unfollowing your non-followers followings etc.

However, let's face it, most Instagram Automation scripts available over the internet are often pretty simple, and are not as effective as you would expect. This said, if you're still thinking about getting into botting, you have two options:

- Use some pre-made scripts that would do the job for you, select the proposed features you want and accept the results.
- Or make your own scripts to do the tasks you want, specific strategies that you imagined etc. That implies of course that you are able to code, and that you have time to spend on building it.

I chose the second option and made a bot from scratch based on the API-wrapper in order to accomplish the tasks I thought were wise for a robot to perform.

Before getting into details, you might ask yourself one question that I believe is interesting to tackle in the first place, **is all of this even legal ?**

## Legal aspects

On the Instagram's **Terms of Use** you can read:

> We prohibit crawling, scraping, caching or otherwise accessing any content on the Service via automated means, including but not limited to, user profiles and photos (except as may be the result of standard search engine protocols or technologies used by a search engine with Instagram's express consent).

**It is well known and written everywhere, automating Instagram is prohibited**. We all experienced accounts interacting with us with weird comments, sometimes completely neutral, sometimes completely out of context.
Nevertheless, you are not gonna get in trouble if you've been using an automation tool on your account, neither get fined. **One of the only dramas that can happen to you is that you can get your account deleted.**
It is really rare and pretty unlikely that you'll get your account deleted, but it is important to keep it in mind.

Apart from that, you're all good. If you're ok with the idea that you might get up one morning and find out that your account doesn't exist anymore, then you're good to go!

People are usually ashamed to admit that they have been using automations in the past, because it is considered as a really controversial practice but let's face it, it is nowadays pretty well known that bots are being used. Instagram is well aware of that, and **in my opinion, they are not even trying to block robots**. Instagram engineers are well aware of the whole business about botting, but to my mind, they actually benefit from the bots:

Indeed, bots generate audience, and sometimes even content, why would they prohibit that? People are getting boosted by robots, which often gives them motivation. It is even getting common that bots interact with bots, which generates more audience.


# My advise to get into Instagram Botting

I wont share any code here, this is not the goal. I am just sharing the principles I based my code on. I have been improving my robot a lot, on many different aspects and that's what made the whole adventure interesting. Making such robot implies different skills and more thinking that you would initially think ...

The key features you want your bot to have are:
- **Easy monitoring**
- **Efficient actions**
- **Low risk strategy**
- **Steady process**

## Easy Monitoring

Monitoring your whole automated system is really important. Most of the times you would rather have a robot running 24/7, however, it would never be as steady as you would like, as a matter of fact, it is pretty hard to have a working script 24/7, for these reasons keeping track of what is going on over time is really important. Here are two interesting examples, that I eventually experienced:
- You launch your script on Monday, check its status again on Friday and find out it actually mysteriously stopped on Tuesday, you lost three days of running, which is a shame.
- Now let's imagine you are checking your script status every 30 minutes, then you are gonna be of course catching every single anomaly, but you are going to spending way too much unnecessary time on this.

Building yourself a tool to monitor the whole activity is really important. The most important indicators you wanna keep track of are:
- How good your bot did (how many followers you got, how many you lost, how many replied etc.)
- Run status (is your bot currently running, did it run the whole night etc.)
- Errors management (how many errors did your bot encounter, how often, which ones etc.)

If you manage to get those three points easy to check, then it will make your life easier as correcting your errors, adapting your strategy, or simply improving your robot, will be **MUCH EASIER**. You can't improve a system if you dont know how well it did, nor correct a mistake if you don't where, how or why it happened.
Making an automation robot is a great experience of **Trial & Error**. Change something, see how it goes, adapt it again, see how it goes etc. until you get something good enough satisfying your requirements, making the monitoring a really important aspect of your implementation.

The other important thing about monitoring is that you are gonna save time, a lot of time.
Checking all the different results, or logs of your system is time consuming, and you wanna save that time. With the right monitoring processes, you can automatize all that and focus on the most important aspects.

Here are few ideas that you can use to help you monitor your activity:
- a web application where you would display all the things you wanna monitor
- a chatbot, that would communicate to you everything you wanna monitor
etc.

## Efficient actions

This is, I believe, the most important thing that you can leverage from in order to increase your bot performance.
Having a robot running is great, but having an efficient robot is better. One shall first define the performance for such tool. **The performance for an Instagram Automation is simple, the more followers it gets to the target account over the time, the better it is.**
Most of the time, the only thing that distinguish offers on the internet is the number of followers they promise, as a metric for their performance.

There are two main levers you can play with when setting up your robot behavior, the number of actions it operates (per hour or/per day) and the quality of the actions.


## Steady process

As I said

## Pushing to the limits

As you may guessed, Instagram won't let you perform millions of actions during a day. Instagram established limits, that even humans can reach! Indeed, maybe it happened to you that after unfollowing a certain amount of person really quickly, you got a message saying that you could not unfollow that fast and should wait for a while.
There exists limits for all the actions, and testing them is the only way to find out what they are, approximately. Indeed, they are not fixed, and not written anywhere, when you reach the limit you'll most likely get an error from the request. Mastering these limits is really important when it comes to maximize your efficiency.
Keep in mind that getting close to these limits is also getting close to being banned, which happened to me before.

# Conclusion

Making an Instagram Robot may seem a bit shameful, as it is pretty controversial and but it is not. It is actually pretty smart and the skills you develop working on that
- Errors handling:
Handling errors (numerous of them) in a smart way is a pretty cool skill to have when you need to handle continuous script run. Having a script running 24h a day is much more complicated than it seems, and you're gonna encounter some errors you maybe didn't think about.
- Scheduled tasks:
Most of bots got a set of different actions, that sometimes need to occur simultaneously. Handling them, giving them priorities etc. can sometimes be tricky.
PLAN

# PLAN
- LEGAL ASPECTS
- INFRA STRUCTURE
- SMART AUTOMATION
- TESTING THE LIMITS
- BENEFITS

2 types of automation
AUTO POSTING VS AUTO EVERYTHING
