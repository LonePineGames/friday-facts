---
layout: post
title:  "Friday Facts #16: Terrain Delay"
date:   2020-01-19 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/01/19/terrain-delay.html

image: /assets/images/hill-neighborhood.png
description: Rising prospects, sinking roads

---

Welcome to New Cities Sunday Facts. We had a busy week and I fell behind on the blog, but I didn't want to completely miss a week.

If you're following along, you know that, starting Thursday night, we sent out keys for crowdfunding contributors to start the closed alpha. The IndieGoGo campaign ends this Tuesday, so if you are considering buying, now is your chance. If you wait, you will not be able to play until our Steam Early Access release sometime this spring. You will also have to pay $4.93 more.

Those who have played the game have been universally positive about the experience, describing it as fun, deep, engaging, addictive, and even "a dream come true." For me, it's a pretty heartwarming experience seeing fans create cities of their own:

{% include fans.html %}



But not everything is perfect in the land of New Cities. In fact, I am dealing with a problem in the land itself.

The game's terrain has always been represented as a big grid, divided into chunks. Every chunk has 625 (25x25) tiles, which is 1250 polygons to render. For a 100x100 map, that's 12.5 million polygons. For this reason, we need some way to simplify the terrain meshes.

My first solution was to render a second, simplified mesh when zoomed out. This mesh has one fifth the resolution (25x25 → 5x5), meaning that our 12.5 million polys become just 500,000. This performs great and looks fine, but there is one problem: sunken expressways sink under the lower resolution terrain. This not only looks weird, it confuses players (many think there is a gap in the road) and it makes the traffic heatmap useless.

{% include image.html class="caption-top"
  url="/assets/images/sunken-roads.png"
  description="An expressway sinking below the terrain."
  %}

To address this issue, I lowered the rendered height of every tile to the minimum of its immediate neighbors. But this means that the terrain can be dramatically below roads and buildings, especially on hills, making things appear to float. It also changes the shape of coastlines and can make coastal buildings appear to be underwater, although I have a way of addressing that issue.

This is the state of the version that was released Thursday. The floating was certainly noticed by several players, and I needed a better solution. Over the weekend I developed a method that recursively subdivides the terrain until it reaches a desired level of accuracy.

{% include image.html class="caption-top"
  url="/assets/images/hill-neighborhood.png"
  description="A neighborhood on a hill, rendered using the recursive method."
  %}

This is a pretty good solution all around, so I'll release it as part of a general update next week. Then I will finally start implementing mass transit, beginning with buses.

This is your last chance to buy the game at a 24% discount from the retail price, get exclusive access to the closed alpha in January, and many more perks! Check out our [crowdfunding campaign]. And join the [discord], [subreddit], and [twitter].

[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[crowdfunding campaign]: https://igg.me/at/new-cities




