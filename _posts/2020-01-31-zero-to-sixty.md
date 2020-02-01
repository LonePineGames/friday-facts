---
layout: post
title:  "Friday Facts #18: Zero to Sixty"
date:   2020-01-31 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/01/31/zero-to-sixty.html

image: /assets/images/recursive-terrain.png
description: The race to performance is a marathon

---

A serious performance issue is a bug. This was demonstrated a few weeks ago by the [route starvation issue.](/2020/01/10/taming-the-beast.html) I often find myself unsure about how I should prioritize performance issues relative to correctness issues and new features like mass transit. About once a week, I ask my fellow developer Mitch "What do you think is the most important thing I should be working on?"

Today he answered the question with a challenge: "Get my machine to 60 FPS on a blank map."

{% include image.html class="caption-bottom"
  url="/assets/images/recursive-terrain.png"
  description="The new recursive terrain rendering, with the tiling outlined."
%}

The terrain has always been the #1 cost to render. A late game city is heavy on the CPU but the cost to the GPU is not appreciably higher. The number of trees, the complexity of the terrain mesh, and the animated water all contribute to making just the blank terrain slow to render.

This week, I made several changes to try to address this issue. I finished the recursive terrain rendering method that reduces the overall land mesh complexity. I changed the water animation to use textures instead of trigonometric functions. I added a new game menu, with the option to remove those FPS-compromising trees. And I introduced an official mod called "performance," to help those whose machines struggle to play the game.

{% include image.html class="caption-bottom"
  url="/assets/images/sin-water.png"
  description="The old trigonometric water rendering, a victim of our relentless pursuit of frames."
%}

Nevertheless, there is still more to do. I'm going to make some changes to our graphics engine that hopefully will speed things up. At the same time, we are using profilers to see where the pain is. I'm reading a book on GLSL shaders that I bought with the crowdfunding money, and I'm already getting good insights. If you have any reading recommendations for me, please drop us a line!

The game has become [known](https://www.escapistmagazine.com/v2/new-cities-brings-unprecedented-scale-to-the-city-builder-genre/) for it's impressive scale. In order to fulfill that promise, we need to work hard to get the best render performance possible. It's not enough for New Cities to run -- it must run fast.

A big thanks to our great community on [discord]. Our passionate fans are striving to understand every part of the game. They're putting together modpacks and they've begun documenting the game in an [unofficial wiki]. Take a look, and perhaps add your own touch!

We're also on [reddit] and [twitter]. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[UX]: https://en.wikipedia.org/wiki/User_experience_design
[unofficial wiki]: https://new-cities.fandom.com/wiki/New_Cities_Wiki
[reddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[IndieGoGo page]: https://igg.me/at/new-cities


