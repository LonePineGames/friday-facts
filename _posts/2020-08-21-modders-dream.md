---
layout: post
title:  "Friday Facts #45: Modder's Dream"
date:   2020-08-21 00:00:00 -0700
author: Lone Pine
#categories: new-city friday-facts

image: /assets/images/45_dream.png
description: Opening the Hood
---

{% include image.html class="caption-bottom"
  url="/assets/images/45_dream.png"
%}

Lone Pine:

Just a brief update from me today. We're still working on the Citipedia and Newspaper, and it will take another two weeks before we are ready to share them with you. This has given us an opportunity to build out more of our modding system. The newspaper articles depend on information from the city’s statistics interface, and that interface is now exposed to Lua (and therefore modding). Currently there is no way to modify the game’s state from Lua, so it’s read only. We’ll introduce the ability to modify the game through Lua scripting as we develop this system.

I'm also migrating the achievements to Lua too. An achievement consists of some entertaining and instructional text, a condition for the achievement to be achieved, and the reward for getting the achievement, usually an amenity. This gives me an opportunity to expose more things to Lua. It also makes possible custom achievements. This means that a modder’s amenity can be paired with a custom achievement that unlocks it, if the modder wishes.

{% include image.html class="caption-below"
  url="/assets/images/45_custom_achievements_meme.jpg"
  description="We'll have this soon enough."
%}

I have plans to expose every system in the game to modding. My dream and my plan is to turn NewCity into a platform, on top of which any kind of city builder is possible, as well as perhaps some games outside of the city builder genre. The work we are doing now is a big step forward for that dream.

---

Gainos:

Hello everyone! Let’s have a  small break from the beautiful words of Supersoup and Lonepine to allow me to speak a little bit about what I’ve been doing on NewCity. I’ll be talking mostly about what I’ve been working on after the release of NewCity’s first branded update: the Architect Update.

I’m fairly confident that most people reading this know about the game’s building designs but if you don’t, that’s how the game stores information about the different building layouts you see in your city. A design contains information such as the minimum value and density required for that building to spawn, how many stores or homes it has, what zone type it is, what textures it uses or any decorations that may be present. The main part of the building that you see is a structure, which can use a custom texture; decorations can’t, but that is a smaller limit than you can initially think. Decorations, in fact, are something awesome that can make any design more interesting, but they weren’t always there.

{% include image.html class="caption-bottom"
  url="/assets/images/45_empty_design.png"
  description="An empty design. So much potential."
%}

The game had some preset decorations such as trees, containers, liquid tanks and the like. But since those weren’t generated from a file that can be exported from a 3d modelling software, a modder would have a hard time adding anything other than what was already there. A modder, or myself, the team’s artist. 

With that in mind, the architect update allowed decorations to be added from .obj files, which can be exported from any 3d modelling software. Decorations at first were supposed to be big details to give a bit more life to designs such as crops in farms, some vehicles here and there, some pretty trees and so on. However as time went on and fans requested more detailed buildings, decorations started to be used as building pieces, such as pillars, walls, floors, and even balconies.

{% include image.html class="caption-bottom"
  url="/assets/images/45_towers_complex.png"
  description="They seem pretty happy living there."
%}

How many decorations in a design is enough to give it a good amount of detail and how much is too many that could cause a big performance cost in a big city are questions that I ask myself pretty frequently, and something the team as a whole is invested in finding out. A consequence of that is that you may find some designs changing pretty often.

With all that said, being able to import custom decorations is an amazing feature, and something players can do fairly easily. While I’m sure this wasn’t as interesting or funny as Supersoup or Lonepine’s posts, I hope it still was a good read. Gainos out.

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games

