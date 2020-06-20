---
layout: post
title:  "Friday Facts #37: The Journey Begins"
date:   2020-06-19 00:00:00 -0700
author: supersoup
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/06/19/the-journey-begins.html

image: /assets/images/37_summer.png
description: The road goes ever on and on
---

We launched the game. And with a few days to spare for our “Spring” target here in the Northern Hemisphere. 

Now we enter the Summer of NewCity.

{% include image.html class="caption-bottom"
  url="/assets/images/37_summer.png"
  description="Summertime in NewCity"
%}

When you’re making a game it’s hard to know what to expect. You have a vision of the game in your mind. You can see how the pieces are coming together. But sharing that mind-baby with the world is another matter entirely. It’s sort of like getting into your car to drive somewhere with the windows all covered up. Maybe it’s a Tesla running on autopilot. Hopefully. 

Point is, you know what the world around you looked like when you got into the car. And now you find yourself months and miles removed from where you started. When you open that door and step out, what are you going to see? Will you be where you thought you’d end up? Or will you be somewhere completely different? 

As Indie Devs, we had no idea what we would see when we reached our destination. Doubly so considering that NewCity is our first game as a studio. We’re still fresh-faced game developers with a dream and the hubris to try and make it happen. We have minimal-to-no experience with launching a game. And this is just the first stop on the long journey we’ve set ourselves on. 

So what did we see when we opened the door and stepped out squinting into the sunlight? 

We saw people playing the game. And not just a few. Not just our friends and family. Not just our Closed Alpha testers. We saw hundreds and hundreds of people. All of them coming together to support us on launch, spreading the NewCity love on Twitter and Reddit, and sharing their feedback and cities with us on Discord. We saw people streaming NewCity for their own communities on Twitch. Most of all, we saw people discussing what they planned to **build**. Plans for mods, building designs, and city planning paradigms. 

To call it humbling is an understatement. 

It’s time to get back in the car and drive on to our next destination—the first major patch of Early Access. But now we have a whole caravan crossing the trackless expanse with us, Councilmembers and Early Access players alike. It’s like a swig of cold water in the hot, hot desert to read your stories and see your cities, and to know that we’re not making this journey alone. 

Thank you, each and every one of you, for your support and for playing our game. You have our solemn promise that we will honor your time spent with NewCity. We’re still figuring out what this all means and how it works, so forgive us for any missteps. We’ll be standing by for your feedback and bug reports as we build the citybuilder we all want to play, the vision we had at the outset of this journey. 

And we’ll build it together. That’s a promise too. 


---

{% include image.html class="caption-bottom"
  url="/assets/images/37_dusktown.png"
  description="The bugs come out at dusk"
%}

We’ve already released the first minor patch (as well as a weekend hotfix), and there’s a whole lot to sift through there. Perhaps we’ll let the [patch notes]{:target="_blank"} speak for themselves. Rather than cover the patch line by line again here, we’ll talk here about our thinking behind the work we’ve done since launch, as well as our hopes and dreams moving forward. 

First up: the hotfix. 

Within hours of launch, we started receiving reports of shader errors. Graphics processors are a fickle bunch. What’s good for one may not be good for another. That was part of the reason behind setting the minimum system requirements for the game as needing a dedicated graphics card. They tend to be more flexible when it comes to such things.

That said, we have a lot of players with integrated graphics. And so the first order of business was to tend to our shaders. 

We found some obvious issues based on the common errors across the logs we received. So we set out to solve those first. As is apparent by even a cursory glance at our Steam Discussion board and Discord, we have some work left to do.

With the latest patch (0.0.54.7) we implemented better logging around shader errors to give us more information on the specific issues. We thank you for your patience as we review this data and continue to improve our shaders as we go. As for the rest of it, the [patch notes]{:target="_blank"} pretty much tell the whole story. We heard your feedback regarding unusual interactions with right-click scrolling and the zone tool, we made significant improvements to our orthographic camera (sorry perspective players, we’re working hard on improving your experience as well), and we changed the way logging works to prevent long load times and bloated log files. We made modpack improvements and tweaks (even adding one we used for our trailers), added an option to disable autosaves via Lua if so desired, and hacked away a few gnarled branches of the crash tree thanks to your logs and feedback. 

Oh, and we included a few redistributables that we *thought* had been handled in other ways. Live and learn I suppose.

{% include image.html class="caption-bottom"
  url="/assets/images/37_citycenter.png"
  description="Cities grow in ebbs and flows"
%}

Starting this Sunday, June 21st, our stalwart leader Lone Pine will be taking a much needed vacation to refresh and recharge for the development sprints left to come this Summer. As a result, **there will not be a weekly patch released Thursday, June 25th.** I’ll still be on hand to manage our growing community and field support requests, so please feel free to ping me (supersoup) on Steam or Discord. I’ll be laying the groundwork this coming week for the next patch, and then we’ll resume our weekly patches through the Summer. 

What’s next you ask? Take a look. Of course it’s subject to change, but these are the issues and features highest on our to-do list:

* More work on shader compatibility across different systems and graphics processors
* More work on crashes and showstopping bugs
* Improvements to transit and vehicle logic
* More tooltips and UI/UX improvements
* Improvements to simulation determinism
* Terrain seed sharing

And of course a few new features are on the horizon as well, though they may still be a few months out:

* The first NewCity utility
* Airports
* An in-game newspaper for city feedback
* Steam Achievements
* Steam Workshop support
* Platformization (broadening the modding platform and exposing more of the game to modders)

Suffice it to say, our plate’s pretty full. All our plates. All spinning in the air. But truth be told, I wouldn’t have it any other way. From the bottom of my heart, I want to say thank you to each and every one of you that’s joined us on this journey. Building a citybuilder respectful of the heritage of the genre from the ground up is no small feat. But with your support, we’re making it happen.

As always, we can’t wait to see what you build.
 
---

Let’s wrap up this Friday Facts with a few screenshots of what our community members have been building. Want to see your city here? Share your favorite shots on our Discord in the #share channel. We’ll pick the ones that pique our interest and showcase them here! 

{% include image.html class="caption-bottom"
  url="/assets/images/37_terraingen_morcup.png"
  description="Modding the terraingen - morcup"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/37_peninsula_goodbyejojo.jpg"
  description="City on a peninsula - goodbyejojo"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/37_sunrise_jakewb.png"
  description="Sunrise - jakewb"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/37_farmville_elmoooy.jpg"
  description="Farmville - Elmoooy"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/37_officenight_nohant.jpg"
  description="Offices at night - Nohant"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/37_megacity_cutkin.jpg"
  description="Megacity - cutkin"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/37_colors_baleur.png"
  description="Modding the colors - Baleur"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/37_bigcity_thelyraki.jpg"
  description="Horizon to horizon - TheLyraki"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/37_cheesescraper_doctolad.jpg"
  description="Our scientists forgot to ask if they should - Doctolad"
%}

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game, you can pick it up on [Steam]{:target=”_blank”}! We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!


[patch notes]: https://store.steampowered.com/newshub/app/1067860/view/2447091973458106170
[Discord]:  http://discord.gg/cz6t4J5
[Steam]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games
















