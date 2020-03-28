---
layout: post
title:  "Friday Facts #26: A Change of Perspective"
date:   2020-03-27 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/03/27/change-of-perspective.html

video: dolly-zoom
video-prefix: https://newcities-videos.s3.amazonaws.com/
image: /assets/images/dolly-zoom.png
description: Big Annoucements

---

We have two cool things to announce today. Firstly, the game is being renamed! The new name is NewCity. We will be rolling out the change across our web presence over the next week, and Monday’s version of the game will contain the name change.

This is the result of much deliberation behind the scenes. This might seem like a small change, but it is a big deal for us on the team. And it’s not just the matter of avoiding name collisions or playing keep-away with domain names, it represents a fundamental shift from the working title and thought exercise of “New Cities,” to the tangible “NewCity.” Yes, we deliberately ensured it looked like the initial save name for city builders from here to there and back again. But as always we want the focus to be that we’re building something New. So here we are. NewCity.

{% include image.html class="caption-bottom"
  url="/assets/images/newcity-title.png"
%}

Just imagine that scene from Iron Man 2 where War Machine walked out (with a new actor) and said: “Look, it’s me. I’m here. Deal with it. Let’s move on.”

The second big piece of news: I have relented to public pressure and implemented a perspective camera. The orthographic camera was important to me from the beginning -- I just love the look of it -- but it ended up being way more controversial than I expected. In my mind, the ortho view will always be the default and “correct” version of the game, but Monday’s version will allow players to switch from the ortho view to a conventional perspective view, if they desire.

Something that is obvious about the new camera: it makes the scale of NewCity that much more dramatic. It wasn’t as obvious before just how big our cities can be. So perhaps it is for the best, since the dramatic perspective views do a much better job of selling the game.

{% include image.html class="caption-bottom"
  url="/assets/images/perspective-1.png"
  description="The tall blue building in the background is the same size as the ones in the foreground."
%}

Here’s supersoup to talk about the process of implementing the perspective camera:

---

Is time a line? Or perhaps a non-linear progression of events, tossed in a bowl like a salad? It’s all a matter of perspective.

And that brings us to today’s topic: Perspective. Specifically the difference between perspective and orthographic views. Despite the miracles of modern technology, when you’re forging your own engine from whole cloth, switching from one to the other isn’t as easy as flipping a switch. There’s a lot of vectors and matrices and fun mathematical stuff hard at work under the hood to make it happen.

First and foremost as far as my efforts were concerned, I needed to figure out where the camera was. Sure, there were algorithms and formulas spitting out the “position” and “direction” your camera faces based on various inputs and angles. But the exact world position of the camera simply wasn’t something we stored before now.

Why does this matter? Raycasting.

Orthographic camera perspectives, like we’ve used until now with NewCity, treat everything as if it’s the same size when presenting it back to you. This makes things like collision checks and frustum calculations fairly easy. Your camera frustum is just a simple box, and rays travel straight without interference.

But when you add a little perspective, it all goes out the window. Now we’ve got fields-of-view and trapezoidal frustums to deal with.

{% include image.html class="caption-bottom"
  url="/assets/images/perspective-2.png"
  description="When I close my eyes… I still see the frustums…"
%}

Ahem. So in order to calculate something as simple as a raycast, we need to know a few things: the position of the camera (or ray source), the position of the mouse on your 2D user interface, and then the minimum distance to the terrain. Using the first two, we can calculate a vector that represents the direction of your raycast, and then using the latter (and hopefully little more than the latter) we can perform a relatively efficient collision test to find out what node is nearest where the ray intersects with the terrain.

Whew. I made myself tired just writing that out. And that’s just a sliver of the fun I’ve been elbows deep in for the past two days. I’m proof that you can make games without having a math major. But golly, does it ever help.

---

By the way, this is our 26th post, and since we've been pretty consistent, that means that we've been blogging for a 6 months. And what a crazy half-year it's been!

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support!

If you want to play the game and haven’t contributed yet, you still can! Head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games





