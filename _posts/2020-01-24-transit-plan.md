---
layout: post
title:  "Friday Facts #17: Transit Plan"
date:   2020-01-24 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/01/24/transit-plan.html

video: bus
video-prefix: https://newcities-videos.s3.amazonaws.com/
image: /assets/images/bus.png
description: Hop on the bus

---

I've finally begun serious implementation of mass transit, starting with buses. This week I implemented a clean, intuitive system to build bus lines, including a "transit view" based on the iconic design of metro maps. The [UX] is similar to other games with mass transit. In New Cities, the game automatically builds the stops as you go.

{% include video.html class="caption-bottom"
  video="bus" image="/assets/images/bus.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Building a loop line around Tacoma University campus."
%}

Next week, I'll start on the actual mechanisms of mass transit. There are three things I'll need to implement to bring it all together. First, commuters will need to weigh the different transportation options to get to their destination (routing). For now, this means deciding between cars and buses. They'll choose the better method according to some metric, which will take into account time and cost (fuel vs ticket).

Once the commuters decide to go by bus, they'll need to actually follow the route. They'll start by teleporting to a bus stop. (Walking simulation will come later, as will pedestrians.) When a bus comes, they'll need to hop on, and then get off at the right spot. 

Finally, the buses themselves need to be simulated. Buses will use the same simulation as ordinary cars, but there will be different rules for spawning and routing. For right now, buses will simply spawn at any stop with enough people waiting. In the future, the player might need to purchase and store rolling stock.

All of this is likely to take more than a week, as I will simultaneously need to engage with the community and make important fixes and improvements to other aspects of the game. We're aiming for weekly patch releases. Therefore, we will have to ask for your patience for major feature rollouts. The bus is coming!

{% include image.html class="caption-bottom"
  url="/assets/images/bus-stop.png"
  description="We built the infrastructure but we're still waiting for the rolling stock."
%}

Once buses are working, I expect to implement trains next. After that, I may go into trams (trains on roadway), pedestrians, or subways and underground infrastructure.

This week I also finished and enabled suspension bridges, which were implemented two weeks back but not fully debugged at the time.

Bridges can be built manually by placing pillars, then stringing roadway across them. Alternatively, there is an automatic bridge builder, but it doesn't choose the most economical path. The pillars get much more expensive the deeper the water underneath, so to keep costs reasonable, you'll have to carefully plan long spans.

The suspension bridge pillar can carry a road three times as long as a regular (truss) pillar. It also costs four times as much, meaning it's most useful to jump a long chasm.

{% include video.html class="caption-bottom"
  video="suspension-bridge" image="/assets/images/suspension-bridge.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Bridges are cheaper to build in shallow water."
%}

In business news, New Cities has earned $12,000 in the last two months thanks to the humbling support for our IndieGoGo campaign. We now have a crowd of almost 500 people playing New Cities. You can still join them and play today by visiting our [IndieGoGo page]. (This is contrary to what we said last week, as our campaign has now successfully transitioned into the InDemand system thanks to hitting our goal. We upped the number of Factory and Office Complex perks available to accomodate for the extended campaign.)

A big thanks to our great community on [discord]. Our passionate fans are striving to understand every part of the game. They're putting together modpacks and they've begun documenting the game in an [unofficial wiki]. Take a look, and perhaps add your own touch!

We're also on [reddit] and [twitter]. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[UX]: https://en.wikipedia.org/wiki/User_experience_design
[unofficial wiki]: https://new-cities.fandom.com/wiki/New_Cities_Wiki
[reddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[IndieGoGo page]: https://igg.me/at/new-cities

