---
layout: post
title:  "New Cities Tribune #3: Start Your Engines"
date:   2019-11-08 00:00:00 -0700
author: supersoup
#categories: new-cities tribune mods
redirect_from:
  - /blog/2019/11/01/tribune-2-fellowship-of-new-cities.html

video: park-pollution
video-image: park-pollution.png
video-prefix: https://github.com/LonePineGames/friday-facts/releases/download/nct3v0/
description: Announcing Mod Support
---

{% include image.html class="caption-bottom"
  url="/assets/images/luaa.gif" %}

Maybe you’ve already heard—but if you haven’t, you’re in for a treat: New Cities is evaluating modding support with Lua!

<!--more-->

For some of you, mod support will be a major bullet point in the feature list. For others, it will induce a shrug and an air of indifference. But the great thing about mods is that whether you plan to dig into crafting your own experiences or not, everyone will benefit from the passionate work of community modders!

But perhaps the golden age of modding some decade or two ago is little more than a distant memory to you, or perhaps it was before your time entirely! What is there to be excited about RE: mod support?

Let’s take a moment to peek under the hood.

{% include image.html class="caption-bottom"
  url="/assets/images/building-designer.png"
  description="The Building Designer" %}

In the early days, mods were the platelets in the blood of PC Gaming, working to cover holes in games that perhaps the developers didn’t see or didn’t have the time to address themselves. Players used mods to patch up old games or add new features in the days before widespread internet connectivity, and some discovered a passion and a potential career in the process. Mods have provided on-ramps to game design and development for thousands of talented artists, programmers, and developers.

Since the advent of the “games-as-a-service” era we now find ourselves in, support for mods has fallen by the wayside in favor of carefully curated experiences with well-defined microtransaction marketplaces. In a sense, this has monetized the modding community and changed it into a first-party endeavor—instead of allowing players to craft new cosmetics or small game-changing experiences, developers have chosen to maintain control of that realm themselves. But in the wild-eyed and frenzied pursuit of every last penny they can Hoover up, they’re missing out on a massive opportunity.

Mods offer unique experiences, with new gameplay mechanics and features which can even flip the genre of the host game into something different entirely. Consider [Natural Selection]( https://www.moddb.com/mods/natural-selection), a mod for Half-Life which turned the First-Person Shooter into a multiplayer FPS/Real-Time Strategy hybrid. Or [Defense of the Ancients]( https://www.moddb.com/mods/dota-allstars), a mod for Warcraft 3 with a focus on the unique hero units which became a world-spanning phenomenon and a new genre in its own right. With mods, anything is possible. All we can do as developers is provide you with the tools and get out of the way.

While we don’t expect to see any first-person shooters result from New Cities modding, the fact is that only time will tell exactly what you will create and what experiences you’ll discover in the process! The visual assets for the game have long been accessible for modding; every texture is simply a png, and the shaders (little programs that run on the GPU) are plaintext and open to modification. But now it’s time to open up the brain of the game for you to poke and prod.

{% include video.html class="caption-top"
  video="park-pollution" image="park-pollution.png"
  prefix="https://github.com/LonePineGames/friday-facts/releases/download/nct3v0/"
  description="Adding a park to reduce the effects of pollution." %}

To start the party, as of the current internal alpha build, we’ve moved the core constants for features like heatmaps, city growth, and more out to a “constants.lua” file. This opens up the core coefficients and values to the end user to tweak and experiment with to your heart’s content. Feel like your city’s growing too slowly? Try tinkering with the Prosperity and Land Value dissipation rates. Tired of dealing with pollution? Change it so all pollution is zeroed out! Game too easy? Turn the Crime effect up tenfold or a hundredfold!

In truth, the move to Lua for constants and values is an experiment. It began life as a developers’ tool which we quickly discovered had value for players as well. Given the success in moving key constants to Lua, there’s now significant interest behind-the-scenes in seeing what else can be moved into Lua and opened up to the players. While it’s impossible to say exactly what that might look like, it’s a safe bet that player-designed buildings, gauntlet-style challenge cities, and easy modes for maxing and relaxing are just a few of the opportunities that await.

In the future, we plan to include support for mods which react to game events, read and write heatmaps, add elements to the user interface, and introduce entirely new features.

As with any new city, there is no limit.

Join the [discord], [subreddit], and [twitter]! We love to chat with fans about features and design decisions.

[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games


