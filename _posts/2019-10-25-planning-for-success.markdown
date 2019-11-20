---
layout: post
title:  "New Cities Friday Facts #5: Planning For Success"
date:   2019-10-25 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts transportation performance
redirect_from:
  - /blog/2019/10/25/planning-for-success.html

video: clover-copy-short
video-image: clover-copy.png
video-prefix: https://newcities-videos.s3.amazonaws.com/
video-prefix: https://github.com/LonePineGames/lonepinegames.github.io/releases/download/v0.5.0/
description: Blueprints are awesome.

---

{% include video.html class="caption-top"
  video="clovers-are-bad" image="clovers-are-bad.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="This is why cloverleaf interchanges are bad #BanTheClover" %}

For a few years, I was highly addicted to the fantastic game [Factorio]. Fortunately for you, that addiction has subsided, and now I'm addicted to The Programming Game instead. Factorio's endgame is amazing because of just how much happens in a giant factory --- belts, trains and flying robots, oh my! -- and how much they've done to maximize the performance. A modern gaming PC can easily run what's called a "1KSPM" factory; that is, a factory that produces 1000 of each type of science per minute. This requires launching an orbital-class rocket, the most expensive item in the game, every single minute. By [my math] that 1KSPM factory produces and consumes at least 100,000 plates of iron per minute, and each of those plates must be transported on a belt (or robot).

From a performance perspective, an item on a belt is not very different from a car on a highway, so Factorio convinced me that cities with hundreds of thousands of cars zipping around should be possible with today's hardware. This inspired me to shoot for the moon with my game.

When I playtest, I experience a lot of the early game -- too much! Right now, I need a way to quickly skip past the early game so I can design the giant cities I dream of, while testing the performance and game balance of the mid-to-late game. Building neighborhoods is fun, but it is also the most time consuming part of the game. To accelerate this process, I borrowed a feature from Factorio: Blueprints.

{% include video.html class="caption-top"
  video="clover-copy-short" image="clover-copy.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Duplicate an interchange with just a few clicks." %}

Blueprints are easy to capture -- just click, select, and click again. They can be named and saved to a separate file, allowing you to reuse them across all your cities. Blueprints capture roads and expressways, as well as zoned lots and amenities like schools and parks, allowing you to make repeatable neighborhood layouts. They can be rotated, of course, and can also be flipped (or mirrored) -- a feature that was frustratingly absent from Factorio! And, of course, Blueprints can be exported to the clipboard and shared with the New Cities community.

The obvious use case for blueprints is highway interchanges. In all city builders and transportation sims, interchanges are tricky to make, especially in the standard game mode (non-sandbox). Players hate to tear up their beautiful city to open up planning space that might not even be used in the final design. Terrain and the surrounding city can complicate the design. Worse, every misclick and poor decision is an impact on your budget. If only you could just plan your interchange, and verify it's correctness, before you buy it!

With each highway ramp, you usually try multiple paths before finding the one that meets the game rules and doesn't collide with other roads, meaning you have to build, delete, and try again. In other games, deleted roads leave strange little hills and pits in the landscape. In New Cities, the terrain remembers its original shape. When you delete a road, it's like it was never there.

I want players to trade off price, space and throughput when considering an interchange design. That will only happen if players can easily test different designs without paying for them or cluttering the space. Blueprints, Planner Mode, and Test Mode make this possible.

In Test Mode you can design and test interchanges -- or any other road system -- with an unlimited budget. With the Blueprints Tool, you can copy a perfected design from Test Mode into your city. Combined with Planner Mode, you can remove any colliding objects, account for terrain, connect to existing roads, and see the price, all before making the purchase.

Most cities will only feature a few interchanges, if any, but Blueprints are not a niche feature. The real value of the tool is neighborhood designs, which allow you to plop residential space for thousands of people very quickly. Blueprinting also accelerates the laying out of farmlands.

{% include video.html class="caption-top"
  video="neighborhood-copy" image="neighborhood-copy.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Living space for thousands - just plop it down!" %}

You might have noticed that New Cities strips out a lot of traditional city-builder features. Currently, there is no power nor water, no fires nor natural disasters (and therefore no fire stations), and certainly no dead bodies or individually-simulated blobs of sewage. These aspects are omitted because I don't find them interesting. Utilities add no interesting choices to the game -- either your city has utilities, or it doesn't work as a city. These aspects add developer time, slow down the player, and take up CPU cycles that I'd rather use to make the maximal cities larger. (Power is an exception, since coal vs nuclear vs green is an interesting choice, and so power could be included if crowdfunding contributors ask for it.)

New Cities aims to provide a different kind of game, one that is at the same time new and old-as-in-retro, eliminating things that don't work or are less interesting, and replacing them with mechanics that are fun and new.

Join the [discord], [subreddit], and [twitter]! We love to chat with fans about features and design decisions.

[Factorio]: https://factorio.com/
[my math]: https://kirkmcdonald.github.io/calc.html#zip=fZJBjsMgDEVvk1WRkmYXicO44CZWwSBjpJk5fYkyi2mHdGPk/z74yyIS23m4YVCLX1mwFKMCXHISNbs8+GjzPPibLXt1droOpBiLLRkcmuIIuZ2teSyyTOM4XjZaN6Poti7Nknx1Som7OFIgBfnuwr+ambvqtatOv+oQ2/CAe3pEb45u4RrCW7kUUAwtyglNAaQ9zfiODg7O1VgDaJIuF/DQJ5lyfyQGdCrkzL0Kt9Wf3EZxxKuRVNkXE2GFH+K++U6CIPGzaRVk8CesstEqgvo5cSTeM3mhf6bDSVxQFPsbef2QPcsT
[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
