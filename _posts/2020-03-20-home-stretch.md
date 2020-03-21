---
layout: post
title:  "Friday Facts #25: Home Stretch"
date:   2020-03-20 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/03/20/home-stretch.html

image: /assets/images/neighboring-cities.png
description: What's in and what's out
---

Lone Pine: I'm back from vacation, and just in time to hunker down at the computer and churn out code. We're pivoting towards Steam Early Access. Now is the time to make critical "in-or-out" decisions for what features will be implemented in the next few months.

Before launching Early Access, I want to have pedestrians, neighboring cities, and most of the mass transit done. We also need to fulfill our promises to IndieGoGo backers, which means implementing new naming features and a statue decoration. We are in the process of hiring an artist to help us with the statues and with other things so that supersoup and I can focus on the core features.

Neighboring cities are more important than they seem, because having a partially simulated "outside world" will be essential to implementing airports, seaports and freight rail. Those features may come after the Steam Early Access launch, but it's important to lay the groundwork now.

We're also planning a change to the save file format. The current system is a brittle adhoc binary format and I've become more worried about it over time. It's risky to add data to the format, making new features risky to implement. I expect a format like BSON will be more reliable and extensible.

A related issue is file size. The files have ballooned dramatically. The primary file size culprits are the terrain and the route cache. Supersoup has been beating the drum about file size for a while now, we're currently discussing how to decrease file size.

Because of the time pressure, we had to officially close the door on a much desired feature: parking. Unfortunately, we cannot take the time to add it right now and it seems unlikely that we could add it after a switch to beta. I agree it would be cool if we had it, but right now we have to make tough choices about what to include.

A few more things will be delayed until after the Early Access launch. We probably will not have mod scripting for a few months. Trams (rail on roads) might not appear right away, and the much-demanded curved roads will have to wait too. For technical reasons, it will be easier to add these features later.

All in all, since the start of closed alpha, you have many more features and options and will have more as we go into early access. Thanks for your advice, input and patience.

***

And now a word from our regularly scheduled supersoup:

Good evening, folks. I greet you now not as a programmer, but as an artist. 

I know. I didn’t realize I had it in me either. And truth be told I’m not well suited to the visual arts. We do what we must to make the magic happen, right? 

As Lone Pine mentioned, we’re looking into hiring an artist for some mid-term art. Both of the 2D and 3D variety. We’ve got our first batch to sort through, and should have our responses out shortly. Then it's simply a matter of confirming a choice or casting wide the net for another round. These things, they take time. I’m looking forward to working with them to turn our concepts and mockups into worthy artworks. And perhaps overhauling anything we have that could benefit from an artistic eye. 

{% include image.html class="caption-bottom"
  url="/assets/images/ui_mockup_03age.png"
  description="A Mock-up for a revised UI"
%}

Meanwhile, this week I’ve busied myself making the mockups I alluded to earlier. Our UI is due for an overhaul. We’ll keep brainstorming ideas until we can hand them off to our artist and get them off our mental desk. I’ve also been processing the data gathered from the last contributor poll, implementing some new console logging, and overhauling our branding artwork. 

Yes, a branding overhaul; but for what? Simply a chance to tune it up for maximal effectiveness? Or something more? You’ll have to tune in next week to find out.

Rm9yIDEgQmlsbGlvbiBEb2xsYXJzOiBQcmVzaWRlbnQgQnVzaCBSaWRpY3VsZWQgVGh1c2x5Lg==

***

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support!

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games





