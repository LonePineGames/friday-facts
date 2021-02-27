---
layout: post
title:  "Friday Facts #65: A Tale of Two Operating Systems"
date:   2021-02-26 00:00:00 -0700
Author: lone-pine
#categories: new-cities friday-facts

image: /assets/images/65/65_hero.png
description: 
---

{% include image.html class="caption-bottom"
  url="/assets/images/65/65_start.png"
%}

I don’t like Windows very much. (You might have noticed.) But in this post I’m actually going to say some nice things about a Microsoft product. (Amazing I know!) You can find the standard arguments for and against each OS in other places. But I want to talk about differences between Windows and Linux that you might not have thought about before.

NewCity was of course developed on Linux first, and then ported to Windows. As the lead developer, I have been derelict in my duty to make sure that the game runs well on Windows (and in general). There’s been some negative feedback from this, and we’ve heard you. 

In a bid to improve the game on Windows, I’ve shut down my Linux machine and started developing on my laptop instead. I’m now using Windows exclusively, and will continue to do so until we make a significant improvement in NewCity’s performance and stability. One major issue I will target: the game runs significantly slower on Windows than Linux, and no one knows why. This suggests that there must be a trivial mistake that is impeding performance, like a bad compiler flag.

Why is Windows any different than Linux? And what is the point of an operating system anyway? There was actually a time before operating systems. Back in the stone ages when the USSR still existed, you could slip a floppy disk into a typical computer and it would run it’s program on bare metal, no OS. 

On these machines, the floppy drive was the only storage mechanism -- hard drives were too expensive! (If you’ve ever wondered why there is a C: but no A: or B:, well, A: and B: were floppy drives.) A computer like this can only run one program at a time, and that program takes total control of the screen, the CPU, the memory, the keyboard, and anything else attached to the computer.

But what happens when you want to listen to your tunes through WinAmp while surfing your favorite BBS at the same time? Now you have two programs which must share all the resources of the computer. You can’t expect every computer program to be good at sharing, so a third program was introduced to decide who gets control of which resources at which time. This program is called the operating system.

Thirty-plus years later, you’d think that we’d be pretty good at resource management, but actually, every OS seems to be uniquely horrible at one thing. For example, Linux becomes completely unstable whenever a program takes up too much RAM. (I’m sure there’s a way to fix this but it should just work out of the box.)

Windows, ironically due to its name, becomes completely unusable when a fullscreen window locks up. The screen is one of the resources that the OS needs to manage, so that one program doesn’t hog it. It’s strange that Windows gets this wrong. I can only conclude that it’s because of the incredible 30-year legacy of the Windows API. (There were many mistakes made in the 90s.)

So that was a frustration that I dealt with. Fortunately, I’m past that now. So now for the good things I’ll say about a Microsoft product (no, not Windows itself.) I have to say that MS Visual Studio, the flagship software development suite, has very good performance profiling and debugging. It’s easier to set up and less tedious than the Linux equivalents. And that’s fortunate, because performance and debugging is exactly what I’m going to be focusing on for… a while.

{% include image.html class="caption-bottom"
  url="/assets/images/65/65_end.png"
%}

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we're incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven't, and we'll keep you up to date on what's new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games

