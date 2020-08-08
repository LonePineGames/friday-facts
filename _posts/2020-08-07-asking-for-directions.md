---
layout: post
title:  "Friday Facts #43: Asking for Directions"
date:   2020-07-31 00:00:00 -0700
author: supersoup
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/08/07/asking-for-directions.html

image: /assets/images/43_jam.png
description: Sometimes it pays to study a HashMap
---

{% include image.html class="caption-bottom"
  url="/assets/images/43_jam.png"
  description="I bet they wish they had a HashMap"
%}

supersoup:

This week, I've been working on performance. But before I dig in let me clear the air. If you've noticed an improvement in performance over the past few weeks, that's all Lone Pine. Frankly, he's made some innovations around view culling that are uniquely suited to our proprietary engine. We still have a ways to go however, and one significant area of opportunity is memory usage. 

At the beginning of the week, I felt a fire I hadn't felt in a long time. I was going to branch off from our main Git trunk, sink beneath the surface of our rendering code, and I wasn't going to surface until I had some answers. In the process I discovered that I can hold my breath for about four days. Besides that, I came back with some metrics thanks to heap profiling that are going to help us narrow down the memory hogging culprit. 

[Data structures]{:target="_blank"} (DS). They're everywhere. Believe it or not, you're surrounded by them this very minute. And I'm not just talking about the web browser you're using to read this or the game you're going to play afterward. Don't get me wrong; any application you use from a text editor to an operating system is going to incorporate DS in their design. But data structures exist as a means to make our job easier as programmers. They're modeled off of real-world hierarchies and relationships. One of the most common data structures in modern programming is the class/object structure: perhaps you've heard it said that a Dog "[is an]{:target="_blank"}" Animal "is an" Organism. The object for a dog might contain data like "number of legs" or "length of tail," specific fields that an Animal as the superclass for the Dog class would lack. Not all Animals have legs or a tail, after all. Well your Chair "is a" Fabricated Structure and your Cell Phone "is a" Communications Device too. 

{% include image.html class="caption-bottom"
  url="/assets/images/43_rvs.png"
  description="Gainos added RV parks while I wasn't looking"
%}

So that's a crash course on data structures. Which I brought up simply to say that, according to my metrics, our data structures may be the source of the memory usage issues. It's one thing to have a problem without a clue how to approach it, it's quite another to have a clear trailhead to start down. While previously all we've been able to say is "We're working on it," now I can confidently add "And we know just where to start." 

The trick will be able to find the right DS to facilitate our needs and prevent any impact to the performance gains we've fought for while also better managing our memory footprint. "Trailhead" is right; this is going to be a quest. Perhaps a sidequest to our main quest of making the best citybuilder we can. But sidequests are where you level up and get the gear you need to tackle the main quest. So forgive us if the changelogs look a bit different until we sort this issue out. The name of our new quest is "[HashMaps]{:target="_blank"}... Friend or Foe?" and I'm really eager to see what the [Dungeon Master]{:target="_blank"} has in store for us this time around. 

That said, we aren't writing off new features in the meantime. In fact, we're full steam ahead preparing for our next epic release: The Read All About It Update. As I've teased and will now formally reveal, the Read All About It Update will include an in-game newspaper that provides dynamic feedback on your city and your relationship to it as mayor, as well as a Citipedia which will become the one-stop-shop for all NewCity information. We have an incredible community that has been willing to engage with one another and share tips, tricks, and quirks, but it's about time we improved the experience for info access in-game. This is where I really get to cut loose and have fun. As you may have guess, words are sort of my trade. It just so happens that writing code involves a lot of words too. 

{% include image.html class="caption-bottom"
  url="/assets/images/43_wip.png"
  description="Admire the work that is currently in progress"
%}

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Data structures]: https://www.geeksforgeeks.org/data-structures/
[is an]: https://en.wikipedia.org/wiki/Is-a
[HashMaps]: https://stackoverflow.com/questions/2592043/what-is-a-hash-map-in-programming-and-where-can-it-be-used
[Dungeon Master]: https://en.wikipedia.org/wiki/Dungeon_Master
[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games




