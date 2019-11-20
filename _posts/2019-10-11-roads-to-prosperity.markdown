---
layout: post
title:  "New Cities Friday Facts #3: Roads to Prosperity"
date:   2019-10-11 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts transportation
redirect_from:
  - /blog/2019/10/11/roads-to-prosperity.html

video: interchange
image: /assets/images/interchange.png
video-prefix: https://newcities-videos.s3.amazonaws.com/
description: New Cities has a unique road planning system.
---

{% include video.html class="caption-top"
  video="interchange" image="/assets/images/interchange.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="A stack interchange" %}

Cities are really about transportation. People choose where to live based on estimated travel time to work, school, or amenities. "Research<sup>[&#91;1&#93;][1]</sup> has shown that ease of access to transport has a stronger influence on whether someone will earn more than their parents did, than the level of crime in their area or whether they grew up in a two-parent household," according to [Wendover Productions].

New Cities features many kinds of roads, from tree-lined boulevards to high-speed expressways to traffic-corralling one way streets, from stop signs to stop lights to stack interchanges. But currently the only kinds of transportation in New Cities are private automobiles and freight trucks. There are no buses, bikes, pedestrians, trains, airplanes, boats, or even carpools -- yet.

After the crowdfunding champaign, there will be a contributors-only vote to determine which new features to prioritize, and most of the candidate features will be related to transportation -- so don't worry, your inner train geek will be satisfied.

{% include video.html class="caption-below" video="planner"
  image="/assets/images/planner.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Designing an expressway ramp in Planner Mode, which allows you to evaluate road designs before paying for them." %}

In order to lay the groundwork for these many modes of transit, I needed to refactor and improve "the graph." The graph is the internal representation of the road system. In the language of [graph theory], the intersections and junctions are "nodes" and the road segments connecting them are "edges". Each edge connects two nodes, and each node to can connect up to six edges.

{% include image.html class="caption-below"
  link="https://xkcd.com/2036/"
  url="/assets/images/edgelord.png"
  description="XKCD 2036" %}

Currently, there are only roads and expressways, but in the future this system might represent train tracks, bus routes, airways, and sea lanes. Underneath the graph is the lane system, which tells vehicles where to go. Lanes are also used for routing. The lane system is managed automatically by the game based on modifications of the graph. Sidewalks, bike lanes and HOV lanes would be implemented as special kinds of lanes on roads and expressways.

When you place an edge (road), the game detects any place where that edge crosses another. It then "splits" both edges by placing a node (intersection) between them. When placing one segment of road, there might be a dozen splits or more.

But it gets even more complicated. The roads are split in order to conform to the elevation of terrain. Then there is Planner Mode, which allows you to plan roads before paying for them, and this means that splits must keep track of whether roads are completed or just planned.

{% include video.html class="caption-top"
  video="splits" image="/assets/images/splits.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="How splits work" %}

Once the splits are all resolved, intersections must be geometrically arranged, illegal states must be detected (underwater, too steep, etc), and costs must be computed. Terrain must be leveled, buildings must also be leveled, buildings and lots must be reassigned, new zone-able lots must be allocated, and the lane system must be updated. Finally, everything has to be rendered to screen.

The game has to do all of this in less than 16.667 milliseconds.

The graph was the very first thing I implemented, and therefore was most in need of a refactor. There were three issues I addressed with this refactor. Firstly, there were performance issues. I improved performance by making sure that things like rendering happened only once per frame, not once per split. (Performance issues are usually caused by redundant work.)

Secondly, it was possible to accidentally create duplicate, overlapping road segments (two roads connecting the same two intersections). This not only looked ugly but caused further glitches. Now when you overlap one road with another, it upgrades or modifies that section of road instead. In addition, building-by-overlap corrects the direction of one-way roads and expressways, meaning you can change the direction of a long stretch of one-way road using just two clicks -- a really powerful tool.

{% include video.html class="caption-top"
  video="one-way-switch" image="/assets/images/one-way-switch.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Reversing the direction of a one-way road while upgrading it to four lanes and installing traffic lights -- all with just two clicks." %}

Thirdly, it was difficult to predict where intersections would happen. Sometimes roads would go under or over each other unexpectedly. When you actually did want an overpass, sometimes you'd get an intersection instead.  This was particularly frustrating when building expressways. Now the game computes and displays splits as you're placing the road, making connection points clear. It also computes and displays an accurate price tag for the road you're about to place.

Transportation is really at the core of New Cities, and building roads is part of the [core gameplay loop]. I'm very glad that I've made these improvements. This project is moving forward at HOV lane speeds, so I'm thankful that you're riding carpool with me.

If you're excited about the project, join the [discord] or [subreddit].

[Wendover Productions]: https://youtu.be/fwjwePe-HmA
[1]: https://nascsp.org/wp-content/uploads/2018/02/issuebrief-benefitsofruralpublictransportation.pdf
[graph theory]: https://en.wikipedia.org/wiki/Graph_theory
[core gameplay loop]: https://gameanalytics.com/how-to-perfect-your-games-core-loop.html
[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
