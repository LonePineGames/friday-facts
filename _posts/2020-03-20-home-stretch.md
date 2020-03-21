---
layout: post
title:  "Friday Facts #25: Home Stretch"
date:   2020-03-13 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/03/13/home-stretch.html

image: /assets/images/24_selection_panel.png
description: More of the same
---

I'm back from vacation, and just in time to hunker down at the computer and churn out code. We're pivoting towards Steam Early Access and leaving alpha. Now is the time to make critical "in-or-out" decision for what features will be implemented in the next few months.

Before Early Access, I want to have pedestrians, neighboring cities, and most of the mass transit done. We also need to fulfill our promises to IndieGoGo backers, which means implementing new naming features and a statue decoration. We are in the process of hiring an artist to help us with the statues and with other things so that supersoup and I can focus the core features.

Neighboring cities is more important than it seems, because having a partially simulated "outside world" will be essential to implementing airports, seaports and freight rail. Those features may come after the Steam Early Access launch, but it's important to lay the groundwork now.

We're also planning a change to the save file format. The current system is a brittle adhoc binary format and I've become more worried about it over time. It's risky to add data to the format, making new features risky to implement. I expect a format like BSON will be more reliable and extensible.

A related issue is file size. The files have ballooned dramatically. The primary file size culprits are the terrain and the route cache. Supersoup has been beating the drum about file size for a while now, we're currently discussing how to decrease file size.

Because of the time pressure, we had to officially close the door on a much desired feature: parking. Unfortunately, we cannot take the time to add it right now and it seems unlikely that we could add it after a switch to beta. I agree it would be cool if we had it, but right now we have to make tough choices about what to include.

A few more things will be delayed until after the Early Access launch. We probably will not have mod scripting for a few months. Trams (rail on roads) might not appear right away, and the much-demanded curved roads will have to wait too.

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support!

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games



