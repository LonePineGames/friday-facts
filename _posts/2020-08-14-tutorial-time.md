---
layout: post
title:  "Friday Facts #44: Tutorial Time"
date:   2020-08-14 00:00:00 -0700
author: supersoup
#categories: new-city friday-facts
redirect_from:
  - /blog/2020/08/14/tutorial-time.html

image: /assets/images/44_overview.png
description: Back to Basics
---

{% include image.html class="caption-bottom"
  url="/assets/images/44_overview.png"
  description="A bird's eye view only helps if you know what you're seeing"
%}

supersoup:

Behind the scenes, we're shifting our focus to the next major version bump: version 56. There's a lot that's going to go into it. Too much to cover in a single blog post. Not to mention we don't have the exact bullet points nailed down yet. But for today, we're going to talk about the overhaul to our Tutorial system. 

Tutorials make or break a game in the simulation and strategy genres. Though a game should be as intuitive as possible, there's simply too many different interacting mechanics and nuances for these sorts of games not to plainly address the specifics somewhere. While we plan to do some of this with our Citipedia as well, there's something to be said for an actual tutorial that teaches players through gameplay. We can cover all the bases regarding how people learn in this way. 

{% include image.html class="caption-bottom"
  url="/assets/images/44_infodump.png"
  description="This is the deep end of the pool"
%}

So we have a User Interface (UI), and we can obviously respond to in-game events per our achievement system. Sounds like a tutorial is lurking in there waiting to be assembled, right? Not quite. There's a few fundamental things our tutorial system will have to do in order to do its job well. Things like responding to user input for interactivity, controlling the game state in ways like pausing or unpausing the game, as well as saving the overall tutorial state so as to ensure when you return to a tutorial in progress, you pick up where you left off. While its true that we have the basic framework for some of the tutorial systems already in place, we have a long way to go to put it all together.

So that's what I've been working on this week.

The first thing I did was build a TutorialState structure, with its own little API for interacting with it. I added a tick function, which gets called in our game update function, so that we can do things like run a timer in the tutorial state to trigger events. And on that topic, what about tutorials that ask you to do something like "Move the camera," how will we monitor that? Well, simply enough, we'll send the info for certain things like the camera to the TutorialState as well, so that it can tell whether you accomplished what that particular tutorial step asked you to do. This will be aided by the concept of the TutorialAction, allowing us to define whether the next step should trigger when you zoom the camera, build a specific building, or simply wait out the timer. 

All things considered, the end result will be an interactive, informative tutorial that actually guides you through the early stages of building your city. Hopefully it will provide a massive reduction in the learning curve for new players. We may even have some info in there that will surprise long-time players. When you're making something as complex as a city-builder, it's easy for some of the more subtle nuances to elude detection. And that simply will not do. 

Expect to see the new and improved tutorial go live with or shortly before version 56. We have a lot more to cover regarding version 56 as we draw near to the launch date, so stay tuned! 

{% include image.html class="caption-bottom"
  url="/assets/images/44_labeled.png"
  description="Labeling things is half the battle"
%}

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with NewCity!


[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games




