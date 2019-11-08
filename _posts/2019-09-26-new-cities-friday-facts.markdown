---
layout: post
title:  "New Cities Friday Facts #1"
date:   2019-09-26 15:00:00 -0700
author: Lone Pine
image: /assets/images/city_overview.png
description: Talking about heatmaps
#categories: new-cities friday-facts crowdfunding
---

Hi, Lone Pine here. I’m going to start posting weekly updates on the project to keep you guys informed of what’s going on, what features are being worked on, and our progress on the road to release.

{% include image.html url="/assets/images/city_overview.png" description="A small town, just shy of the 20,000 people needed to officially be a city." %}

If you're new here, I’m working on a city builder called New Cities. Over the last year, I’ve developed a basic city builder with a traffic simulation and customizable 3D rendered buildings. In the past few months I’ve fully implemented “The Prosperity System” which will define the game. It’s a dynamic economic model where neighborhoods thrive or fail based on access to work, shopping, parks, and schools.

{% include image.html url="/assets/images/prosperity.png" description="The Prosperity heatmap. There are two prosperous areas, one around the city center and the other around a small shopping area." %}

The game is based around six “heatmaps”. The heatmaps are Pollution, Crime, Education, Prosperity, Value, and Density. Essentially, Education (plus a good road system) creates Prosperity, Prosperity (among other things) creates Value, and Value (plus Prosperity) creates Density. However, Density creates Crime and Pollution, which have a negative impact on Prosperity and Value, creating a [negative feedback loop]. Negative feedback loops are important to me, since they counteract the explosive nature of positive feedback loops which turn many simulation games into sandboxes.

{% include image.html url="/assets/images/value.png" description="The Value heatmap. There are two high-value areas around the city center and a shopping area. The red in the top right is a low value area, since there isn't a school in that neighborhood. The white buildings are schools." %}

As a player, you have two options. You can buy very expensive city services (schools, parks, police stations, etc) to cut through the negative feedback loop. Alternately, you can build a broad, flat, suburban city, with the intention to grow a dense city center later in the game. I call these two approaches “San Francisco vs Los Angeles.” I consider this to be a kind of morality system, creating the opportunity for different playstyles and different cities.

{% include image.html url="/assets/images/abandoned_city_center.png" description="Downtown in a declining city, where several buildings are abandoned." %}

In this game, a city doesn’t just linearly grow. Instead the community behaves like a living organism, emerging out of chaos and always at risk of dying. You’ll have to shepherd your city through randomized recessions in the national economy as well as the consequences of any blunders you make. It will be a more random game than previous city builders, with a more vulnerable budget maintaining a fundamentally unstable economic system.

We’ll be starting crowdfunding in the next two months. One of the tier rewards will be to participate in a closed alpha, which we hope to start before the end of the year.

If you're excited about the project, join the [discord] or [subreddit].

[negative feedback loop]: https://en.wikipedia.org/wiki/Negative_feedback
[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
