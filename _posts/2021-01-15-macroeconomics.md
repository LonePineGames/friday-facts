---
layout: post
title:  "Friday Facts #61: Macroeconomics"
date:   2021-01-15 00:00:00 -0700
author: Lone Pine, Gainos
#categories: new-city friday-facts

image: /assets/images/61/61_top_down.png
description: Doing Big Things
---

Gainos:

Hello everyone, and happy 2021 from the team’s artist! I’m sure this year will be great for the team and hopefully for everyone else. (We all deserve a better year than 2020.) This week I’ll talk a bit about the upcoming designs additions you’ll see regarding the Tourism update.

Lonepine has already shared some of his experiments with a tourism system, and on  version played internally, the team was able to play with that as well. With this new update, a new checkbox is added to designs, which will turn it into a hotel. But now, if you want a city focused on tourism, you’d expect to see all sorts of hotels and motels, with flashy, over the top signs. You also probably won’t expect to see the same kind of flashy hotel twice (although there is only so much we can do about that in a big city). So yea, that’s where I come in.

{% include image.html class="caption-bottom"
  url="/assets/images/61/61_hotel.png"
%}

The team had a discussion on the game’s artstyle which led to some changes on the game’s shadows. That meeting also led to several experiments of mine with the game’s art. Generally, a game has it’s artstyle set before the development even begins, but NewCity is an awkward scenario. Lonepine not only developed all of the game’s initial systems but also the art and while the initial result was great, many features added later allowed for more flexibility and overall just better art.

So, with all of that in mind, we are currently working to make sure that the game’s art is consistent, interesting and performant. Lonepine already did his part, by significantly improving the shadows. Now, it’s up to me to experiment with the geometry, color schemes, overall inspiration and workflow. Should be fun.

{% include image.html class="caption-bottom"
  url="/assets/images/61/61_light_color.png"
  description="We’re also giving Gainos, and modders, more control over light effects. - LP"
%}

---

Lone Pine:

In the tourist update, each tourism-related building promises to give you X number of tourists per year. Then the tourist rating promises to keep tourists in the city for Y number of days. Multiply X by Y, dividing by 4 days in a NewCity year, and you get an estimate for how many tourists there should be in the city at any time.

Initially, I just fed tourists into the city at a rate determined by X, and had them leave after Y days passed. However, tourists don't always leave exactly at Y (less likely to leave in the middle of the night, etc). This and other complexities caused the number of tourists to consistently exceed the promise by a wide margin.

Now, I don't have a problem giving the player more than is promised. But, trying to tune X and Y so the numbers are at least reasonable became too frustrating. I then hit on the solution: figure out how many tourists there should be at any time, and stop feeding tourists into the city if there are already more tourists than implicitly promised. In terms that I will explain in a moment, I’m using a macro variable to constrain the micro simulation.

Broadly speaking, there are two types of citybuilders. In one type, the game simulates individual agents (people, businesses, vehicles) and derives the high-level "macro" behavior from the interaction of these tiny parts. We can call these micro-sims. In the other type, the game chooses the value of "macros" (macroeconomic statistics) based on simple formulas, and represents agents only as a way of communicating to the player. We can call these macro-sims.

{% include image.html class="caption-bottom"
  url="/assets/images/61/61_top_down.png"
%}

Due to the limitations of 90s computers, all early citybuilders were macro-sims. SimCity 1-4 are macro-sims; Caesar III, Pharaoh, and most modern 3D city builders are micro-sims. NewCity is a micro-sim with some macro aspects.

For example, take unemployment. From a micro view, unemployment is the percentage of *workers* (somehow defined) who don't have an employer. From a macro view, unemployment is a consequence of the macro-economy being unable to "employ" all it's "economic factors", meaning people, land and machinery.

The macro view is certainly a more abstract perspective, and I won't get into the real world reasons why economies are often unable to employ all their factors. For the purposes of the game, we want unemployment to challenge the player and reflect their skill and choices.

{% include image.html class="caption-bottom"
  url="/assets/images/61/61_piers.png"
%}

So from a macro-game view, we want unemployment to be a consequence of tax rates, the national economic situation (recession or no), how many businesses there are, the education level, and so on. But we also want to account for micro factors such as traffic, heatmaps and physical locations. There is also a macro Business score granted by some amenities, which promises to reduce unemployment by some amount.

NewCity has three unemployment rates: the National Unemployment Rate, the Target Unemployment Rate, and the (regular old) Unemployment Rate. The last one is your microeconomic "workers who don't work" measure; the other two are macros. The National Unemployment Rate essentially comes from the RNG, and the Target Unemployment Rate comes from a formula that accounts for the national rate, taxes, number of businesses, and the Business score.

Currently, the two "macro" rates are pretty much irrelevant, because they are swamped by micro factors -- the aspects of the micro-sim that make unemployment more likely. When a person moves to the city, they don't have a job, won't get a job until they drive to a workplace, and can lose their job very easily. I want to force the micro rate to conform to the macro rate by controlling move-ins, but I'm constrained: if unemployment can only fluctuate within a small range, that slows the rate at which people can move in, making the game boring. Newcomers bloat the unemployment rate very fast, especially in small cities.

Now, I could just fake these numbers, but I don't want to do that. I don't want to lie to you, the players. And also, I need accurate information for debugging and game balance.

I do have one tool in my toolbox which I haven't used yet. Remember that from a micro view, unemployment is the percentage of workers (somehow defined) who don't have an employer. "Worker" is essentially an identity: if you don't have a job, and you’re not motivated to go looking for a job, you're not a worker -- you're "outside the workforce."

When unemployment is cripplingly high, I can have people choose to un-become workers, thus lowering the unemployment rate. People will return to the workforce when there are more jobs available. This way, the unemployment rate will reflect macroeconomic variables and contribute to the challenge.

The TL;DR here is that macros are a lot easier to deal with as a programmer, and so NewCity is moving to a hybrid system of macros and micros. The goal of this is to build the promised Recession System and to make NewCity's economy a unique gameplay experience.

{% include image.html class="caption-bottom"
  url="/assets/images/61/61_big_plans.png"
  description="Big Plans"
%}

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we're incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven't, and we'll keep you up to date on what's new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games

