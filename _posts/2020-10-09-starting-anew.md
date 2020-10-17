---
layout: post
title:  "Friday Facts #52: Starting Anew"
date:   2020-10-16 00:00:00 -0700
author: Lone Pine
#categories: new-city friday-facts

image: /assets/images/52/52_trees.png
description: A walk in the forest
---

{% include image.html class="caption-bottom"
  url="/assets/images/52/52_trees.png"
%}

Lone Pine:

On the front page of this website, we describe NewCity as “An upcoming city planning simulation game for Windows and Linux.” And we haven’t been fulfilling that promise. We haven't been distributing a proper Linux version that launches on a bog-standard Linux install, which according to Steam, is Ubuntu 18.04.

From a market perspective, there is no reason to support Linux. The number of Linux sales is pitiful. I thought that a game in the simulation genre, with Linux support (at least in principle), developed by a Linux fanboy, would have a relatively high percentage of Linux players. But it's really a tiny number of players that use Linux. A bit like Citizen Kane, Linux is more popular among industry members than consumers. So it goes.

Nevertheless, I made a commitment to support Linux and I'm going to keep it. So last week I started on an adventure to create a build system based on Ubuntu 18.04. I use Arch (BTW), and my compiler produces a binary that is incompatible with Ubuntu, since Arch uses a newer version of a library called libc. Downgrading libc is not really possible, so StackOverflow recommends I build on a dedicated Ubuntu system. 

{% include image.html class="caption-bottom"
  url="/assets/images/52/52_menu.png"
%}

I set out to build a system-inside-a-system using debootstrap and chroot, which you can think of as being a form of lightweight virtualization. As I went along, I ran out of space on my SSD, and so I started deleting files to make room. I then made the fatal mistake of deleting the NewCity source code, and all my save files!

Now, of course, the source code is backed up on Github (and supersoup's computer), so we didn't lose the whole project. I did lose every save file of the city of Pleasanton, which was featured in the [Steam Launch Trailer]. Pleasanton sadly now only exists in video, and my memories.

But the show must go on. I redownloaded the source code, and completed my debootstrap/chroot "virtual machine." Now I am building on Ubuntu 18.04, and producing a binary that should be compatible with a broad range of Linux systems. If you are a Linux user, I'd appreciate it if you tried it out and gave us feedback, positive or negative.

{% include image.html class="caption-bottom"
  url="/assets/images/52/52_workshop.png"
%}

This experience has made me feel that we must improve our deploy process. Currently the Windows version of the game is built on supersoup's computer, using MSVC, and I manually package the two binaries together into a Zip file which I then manually upload to Steam's website. Neither developer can make the deploy alone. This is a great demonstration of teamwork, but unfortunately it is a vulnerability for the project.

Programmers often talk about what would happen if a certain critical team member "got hit by a bus." (Programmers can be a bit callous.) To be honest, the real threat is not the death of a programmer, it's someone leaving the company. It's also vacation: if either of us goes on vacation, even just for a week, the remaining dev couldn't cut a release of NewCity by himself.

Wouldn't it be great if a friendly computer came along and did all this tedious deploy stuff for us? Computers are our friends, after all. And there is a technology purpose built for our needs -- it's called continuous integration. So I'm spending some time setting up a continuous integration system to automatically build and deploy NewCity. I'm about halfway there.

I already have the Linux version building under continuous integration. It took 15 tries and 2 hours. Then we'll get the Windows version building, after that we have to find a way to integrate it all together and upload it to Steam. Once it's finished, Thursday nights will be a lot smoother for us.

{% include image.html class="caption-bottom"
  url="/assets/images/52/52_15_tries.png"
  description="Try again."
%}

When I was younger, I would have gotten very angry after attempting something 14 times, failing every time. We want progress to happen quicker, but it's always painfully slow. There's always a new obstacle in your way. It's always two steps forward, one step back. Sometimes you lose all the progress you've made due to a simple mistake, like in the game Getting Over It. Sometimes you wonder if you're pounding on a wall you're not strong enough to break.

But the worst choice is always to give up. It doesn't matter if you're angry, or depressed, feel like you don't have what it takes to succeed, or just don’t feel like getting out of bed. Giving up will always make you feel worse. It's a false song. So always try again, my friends!

Anyway, I have to go now and build a new city.

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with NewCity!

[Steam Launch Trailer]: https://www.youtube.com/watch?v=54lOAS4HBvs
[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games


