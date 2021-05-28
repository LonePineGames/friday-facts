---
layout: post
title:  "Friday Facts #76: Atomic Coding"
date:   2021-05-28 00:00:00 -0700
Author: Lone Pine
#categories: new-cities friday-facts

image: /assets/images/76/76_hero.png
description: How to do multiple things at the same time
---

{% include image.html class="caption-bottom"
  url="/assets/images/76/76_hero.png"
%}

Lone Pine: 

As game development on NewCity progressed, I introduced multithreading in many different places. Multithreading is hard, particularly around making sure that two threads don’t try to write or access the same memory at the same time. Over the decades, many strategies have been proposed for how to do multithreading, and in NewCity I ended up experimenting with just about every one of them. I learned many things, and now it’s time to consolidate to a multithreading approach that we know works.

My first approach was to use mutexes. A mutex is essentially a lock, where one thread locks part of memory and prevents other threads from using it. I do not recommend this approach. It’s brittle, complicated, and leads to pauses in execution while waiting for a mutex to unlock.

A much, much better approach is atomic variables. This is a special CPU feature, essentially just an ordinary number, but the CPU guarantees that all operations on it will happen in a sensible way without multiple threads stepping on each other's toes. We only need to use a few of these atomics to coordinate work between threads, and the performance is great. It’s also super easy to use, since atomic variables can be modified just like regular variables (with some limitations).

In version 58, I implemented a task system, which divides up the work of simulating the game and rendering the frame into fine-grained tasks. These tasks are still run in a single thread, one after the other, but can be run out of order. The task manager only does the tasks that it can do within a single frame, which is typically 16 milliseconds for a 60 FPS experience.

There are some tasks which take more than 16 milliseconds to complete. (And of course this varies from machine to machine.) I can optimize these tasks and break them into smaller pieces, but it would also be convenient if the frame didn’t have to wait for a background task. 

Therefore, the next phase is to allow multiple tasks to run simultaneously in separate threads. In version 59, the game will determine how many CPU cores you have and it will spawn that number of “executor” threads. The task manager will assign tasks to executors, making sure that they don’t conflict with each other and prioritizing the frame deadline for a smooth, fast framerate.

These changes do have an impact on stability. That is, the game crashes more often. This can be fixed given enough time, but we want to deliver a stable game to players. Taking more time between releases will allow us to make each release better, and allow us to sprint harder in between releases. Therefore, we are switching to a monthly release cycle. 

We will not have a release on June 3rd. (Wow, it’s almost June already?) The next planned release will likely be June 17th. We’ll keep you posted. And of course, if there is any pressing issue we will be quick to release a hotfix. 

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we're incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven't, and we'll keep you up to date on what's new with NewCity!

[Hearthstone]: https://playhearthstone.com/
[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games


