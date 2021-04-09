---
layout: post
title:  "Friday Facts #70: Just Show Me the Data"
date:   2021-04-09 00:00:00 -0700
Author: lone-pine
#categories: new-cities friday-facts

image: /assets/images/70/70_hero.png
description: The big OOP
---

lone-pine:

Since the 1990s, computer programming has been dominated by a philosophy known as Object Oriented Programming, which has the somewhat telling acronym "OOP". OOP is based around the concept of an object, which is a bundle of data about some... thing (could be anything really). The data is stored contiguously in the computer's memory, meaning all the facts about that something are stored in the same place.

In recent years, there has been a lot of resistance to OOP coming from camps such as Functional Programming (FP). OOP largely failed to live up to promises that it would make software modular, easy to maintain, easier for teams to split up work, and easier to learn for the novice programmer. Thirty years later, software still sucks.

Despite its flaws, OOP continues to dominate. I've never used a language that didn't have some concept of an object (sometimes by a different name), and I've been programming for over 20 years. Even the flagship Functional Programming language, Haskell, has objects[^1]. Once you start thinking of programming in terms of objects, it's very difficult to stop. 

Objects seem to have a deep connection to how the human brain works, since we experience reality as a collection of objects in space. But, in actuality, objects are just bundles of atoms, and atoms are made of wave-like fields that lack clear boundaries. Likewise, inside the computer, there is no such thing as an "object". There is only ~~Zuul~~ data.

{% include image.html class="caption-bottom"
  url="/assets/images/70/70_0.png"
%}

Now, the computer is perfectly happy to take a name, followed by a birthday, followed by an account number, etc and treat that as a block of data with a fixed size and interpretation -- an "object". But it's just numbers. And the hardware guys tell us there is a problem with this approach. For some reason that I don't fully understand, the CPU will work much faster if you keep the name data on a separate list from the birthday data, another separate list for the account number data and so on. This is called "Structure of Arrays'' or SOA. The alternative, OOP approach is called "Array of Structures'' or AOS. Again, I don't fully understand why SOA is so much faster, but it has something to do with the memory cache. No surprise -- almost everything in computer performance comes down to the cache.

Thinking of your program as a collection of different types of data is called Data Oriented Programming, which has the equally silly acronym "DOP". SOA and DOP go well together, and together they make the computer really fly. 

But SOA/DOP style is so tedious, because programming languages don't provide first-class support for this alternative way of structuring data. It also requires educating programmers who already know how to do OOP, so most teams don't do it. In NewCity, we've been using SOA recently for high-performance parts of the program, but 90% of the code is still AOS/OOP. And that brings us to modding and Lua.

Our modding API must be OOP because that's what all programmers know. No one wants to interact with a scripting API where you have to select every single piece of data from separate lists, and that probably wouldn't be performant anyway. An old joke about OOP: you asked for a banana, but you got an ape holding the banana, the ground he's standing on, and the entire jungle around him. In our API, you ask for a vehicle (because you want to know it's location, that's it) and you get every fact about that vehicle, who is in front of and behind it, how long it's been alive, and a bunch of other facts you don't need to know.

And all this wasted data costs CPU cycles. In profiling (testing the performance of) the game recently, I discovered that our new wanderers system has a massive performance issue. (I'd be curious to know if anyone gets significant performance benefits by deleting all the entries in data/wanderers.lua -- but don’t worry, I’ll fix it properly soon.) 

{% include image.html class="caption-bottom"
  url="/assets/images/70/70_1.png"
%}

This was a heart-sinking discovery. Every time we call a Lua function there is a significant overhead. This isn't Lua's fault -- every other dynamic (easy to use) language is much worse. If it's easier to use, and closer to how humans think, it's further away from the data and how computers process it.

There's many functions I would like to move to Lua. For example, what is the taxable value of a building? We compute it from a complicated, ad hoc formula based on footprint, density, value, occupants, and so on. This function is in C++, but if I could move it to Lua, then modders could change it to suit their modding ambitions. Modders could also check my work and suggest improvements. As Linus Torvalds said, given enough eyeballs, all bugs are shallow.

In fact, what if the entire tax system was in Lua? Then you could make mods that take place in ancient, communist or far future settings where taxes aren't really a thing, but there are other economic systems and constraints. Even if the setting remained in the modern era, modders still might feel they can do better than I at designing the tax system, and I’d definitely like to see that.

However, if calling into Lua is a huge performance hit, then we can't afford to do it for hundreds of thousands of buildings on a regular schedule. So, I'm worried that we'll have to pair back our modding ambitions. I'll still create a full API for every system in the game, but I don't know if I'll be able to move into Lua any high-performance logic such as the value of a building or the impact of individual people on heatmaps. And that will limit the versatility of the game as a modding platform.

When I write inanely technical posts like this, I'm often hoping that someone in the community will have a suggestion for how to fix it or do it better. I'm also trying to feel out the community for how excited or bummed you all will be as we decide what things to prioritize and where to compromise. Feedback is the fuel we run on.

{% include image.html class="caption-bottom"
  url="/assets/images/70/70_2.png"
%}

[^1]: Some high-level geek will argue this point, and they will be correct in the sense that Haskell does not have Java-like or Smalltalk-like objects. Haskell certainly doesn’t have some of the sillier OO concepts like multiple inheritance or complicated dynamic dispatch. But peel away all the abstractions and Haskell does still rely primarily on AOS structured data types -- the bundles of data that I defined as objects at the beginning of the post.

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we're incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven't, and we'll keep you up to date on what's new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games





