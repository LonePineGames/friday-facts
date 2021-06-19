---
layout: post
title:  "Friday Facts #79: Golden Source"
date:   2021-06-18 00:00:00 -0700
Author: supersoup
#categories: new-cities friday-facts

image: /assets/images/79/79_hero.png
description: In which we discuss the origin of all things
---

{% include image.html class="caption-bottom"
  url="/assets/images/79/79_hero.png"
%}

supersoup:

It's become a bit of a joke behind the scenes. Anytime our discussions turn toward game systems and mechanics, I invariably begin my contribution with "Well in GoldSrc, they did it like this..."

As a refresher, [GoldSrc]{:target="_blank"} was Valve's first proprietary engine, with the heart of the Quake engine still beating deep within. Engines are functionally a bundle of decisions; preconstructed systems, covering everything from rendering to sound and often networking as well. Whoever built the engine — here starting with the team behind Quake and layering Valve's work on top — tailored it to meet certain demands and purposes as dictated by their game design. And perhaps to satisfy requirements for games yet to come as well. Engines are most valuable when they can be reused, after all. 

{% include image.html class="caption-bottom"
  url="/assets/images/79/79_beach.png"
%}

I played Half-Life at far too young an age. Then I replayed it over and over until I had committed the maps, dialog, and animations to memory. It wouldn't be far off to say I know Black Mesa like the back of my own hand. I was browsing [ModDB]{:target="_blank"} and downloading mods like Sven-Coop and They Hunger before Steam was even a twinkle in Gabe Newell's eye. I found Worldcraft on the Half-Life retail disc and started charting a mysterious and exciting new world as I tinkered with level design. I learned a bit about how GoldSrc worked by reverse engineering, feeling out the edges of entities, console commands, and WAD files without digging into the code. Programming wasn't quite on my horizon yet, but it was here that the spark began. 

Why am I telling you all this? Well, I'm responsible for a few key systems in NewCity: the console, the Steam Workshop integration, and now our upcoming keymap system. And as these systems have taken root and grown across the codebase, I keep coming back to one key question: "How would they do this in GoldSrc?"

{% include image.html class="caption-bottom"
  url="/assets/images/79/79_waterfront.png"
%}

Perhaps I simply lack imagination. I'm no tenth-level technomancer and herald of the coming robot apocalypse [John Carmack]{:target="_blank"}. But where I excel is in figuring out how things were done, and then doing them my own way to the extent that I am able. I don't simply "play games" anymore, I study them. I'm constantly feeling out the edges of the engine whether I'm playing Call of Duty of the Elder Scrolls. Studying how their movement systems work, how NPCs interact with the player and the world, trying to determine whether they're using behavior trees or finite state machines. Frankly I'm not always able to derive a clean and tidy answer by observation alone. But once you start digging into this realm, you can make some educated guesses. Where it might ruin the magic for most people to see the man behind the curtain of their favorite games, I find myself endlessly fascinated instead. 

Our console isn't exactly a clone of the Quake/GoldSrc console — but it's heavily inspired by it. Our keymapping won't be a one-to-one copy, but I'm spending time studying Half-Life's config files and how Valve uses them to both store and load important settings including binding keys to actions. No matter what your field is or what you're interested in, it never hurts to study and emulate the greats. 

{% include image.html class="caption-bottom"
  url="/assets/images/79/79_downtown.png"
%}

So if you want a glimpse into the future of NewCity — and any other games I contribute to the codebase of — look to the past. It's foolhardy to try and reinvent the wheel when there's a perfectly good one staring you in the face. And I still have a lot to learn from the teams behind the games that captured my imagination as a young and impressionable supersoup.

Thanks, John, for teaching me how to build a console. I look forward to many more years of following in your footsteps.

---
At Lone Pine Games we are always looking for feedback to improve our game! The best way to provide it is through our community Discord, which can be found here: http://discord.gg/cz6t4J5

We are thankful to have such a lively and dedicated group of Mayors participating in discussions regarding new features, city planning strategy, development news, and just about anything else.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. 

Steam Reviews are always appreciated as well!

[GoldSrc]: https://en.wikipedia.org/wiki/GoldSrc
[ModDB]: https://www.moddb.com/
[John Carmack]: https://www.youtube.com/watch?v=SQKSzRbfxQI
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games