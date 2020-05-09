---
layout: post
title:  "Friday Facts #32: Multithread Time Travel"
date:   2020-05-01 00:00:00 -0700
author: supersoup
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/05/08/multithread-time-travel.html

image: /assets/images/twains2.png
description: Twains!
---

{% include image.html class="caption-top"
  url="/assets/images/twains2.png"
  description="twains!"
%}

Ever fancied yourself a conductor? Do you love all things rails and locomotion? Well you’re in luck! Trains are now in NewCity (as of v53), giving you another choo-choo-choice when seeding your cities with mass transit. Send your citizens to and fro in style and keep that traffic off the roads. 

But that’s not the only development in the works. What’s that on the horizon? Why, if it isn’t the Early Access release candidate! 

We’re getting ready to lock down features in preparation for Early Access. There’s still plenty of rough edges to be sanded down—but with the addition of trains, we finally have the vertical slice of NewCity ready for public consumption! The next few weeks will be spent buffing up what we have and getting it all ready for Steam. It’s an exciting time—and nerve-wracking in equal measure. 

{% include image.html class="caption-bottom"
  url="/assets/images/twains4.png"
  description="The city of Polloc (375,000) built this huge Subway System in 1974"
%}

It would be a mistake to call it the finish line. Really, it’s just the end of the prologue. There’s so much more yet to do as we make our little pool of a game wider as well as deeper. With the vertical slice, all of the core systems and mechanics are represented. Now it’s just a matter of broadening the opportunities available to players with more customization and choice. 

And don’t forget—Fridays aren’t just for Friday Facts. Tonight is also our Community Game Night! We’ll be resuming our ongoing adventure in OpenTTD. This is where I’m supposed to make a joke about my poor showing thus far. But really, what is there to say? I strive not for success in OpenTTD, but the low hanging fruit of breaking even financially. “Tonight’s the night!” He says, for the third week in a row. Oh well. We’ll be live on our Twitch at 8pm for fun and frivolity—catch all the details at the end of this post!  

---

{% include image.html class="caption-bottom"
  url="/assets/images/twains3.png"
%}

## Lone Pine:
The release of trains this week coincides with a big performance improvement. I improved the game update performance and made the game play faster for large cities.

I made several improvements to a system called the interpolator, which interpolates (or smooths) vehicles motion. It was visually glitchy and it performed slowly with lots of cars at high game speed. I fixed the glitchiness and reduced some needless data copying.

The interpolator and vehicle physics simulation run at different time-speeds, and so the game has a bit of "time travel". You can see it happen if you watch intersections closely -- cars react very slowly to the lights. You can also see that cars disappear blocks before their destination and the people inside just teleport to their destinations. This will be smoothed out in future weeks.

I also added more threads for routing. Large cities play more slowly so that the router has more time to catch up. Since most computers now are multicore, we might as well use more of your silicon to keep the game going fast for longer.

{% include image.html class="caption-bottom"
  url="/assets/images/multi-track-drifting.png"
%}

This is the inheritance of Moore's Law: Since about 2005, we are no longer getting *faster* compute but we are still getting *more* compute, we just have to go further out on the die to get it. By adding more threads to the routing, your computer can handle significantly more load, although your battery might drain a little faster. Alas.

---

{% include image.html class="caption-bottom"
  url="/assets/images/twains5.png"
%}

We’re excited to continue our weekly community game stream! Join us on Discord and Twitch for a fun-filled night of automation on an alien world, watching supersoup struggle with even the simplest aspects of OpenTTD, or whatever other game we might be playing. We’ll be live on the [Lone Pine Games Twitch]{:target=”_blank”} Friday evenings @ 8pm, keep an eye on the Discord for details.

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support. 

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Lone Pine Games Twitch]: https://www.twitch.tv/lonepinegames
[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games


