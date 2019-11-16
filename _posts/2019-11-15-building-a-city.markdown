---
layout: post
title:  "New Cities Friday Facts #8: Building A City"
date:   2019-11-15 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts buildings economics
redirect_from:
  - /blog/2019/11/15/building-a-city.html

image: /assets/images/pavement2.png
description: The Pavement Must Grow.

---

*There will not be a New Cities Tribune this week.*

Today's post is about buildings. In fact, it's about a problem I'm still struggling to solve, so you'll be able to see some of my thought process.

I've always wanted a city builder with a more flat, suburban city. Real cities sprawl and fill the available space, until businesses are forced to build vertically by constraints like land value, terrain, and transportation. (That's how it works in North America, anyway.)

Ten floors was the original definition of a skyscraper, as opposed to today's minimum of 40. Back when just ten floors was an impressive feat, land use was maximized by scrunching buildings close together, with no open space left other than the long lines of roads and sidewalks. This creates an interesting "cut-out" effect when seen from above.

{% include image.html class="caption-bottom"
  url="/assets/images/flat-iron.jpg"
  description="When ten stories is a feat, you don't leave empty space."
  link="https://en.wikipedia.org/wiki/Wicker_Park,_Chicago#/media/File:View_of_the_Flat_Iron_Arts_Building_from_the_Coyote_Tower_(5266790849).jpg"
  %}

But cities built in the late 20th century actually weren't under those constraints. Instead, city administrators impose rules on how buildings are to be arranged, how much open space to leave, and so on. There's many tradeoffs to the decisions city administrators make, such as the character of the city, how much space to leave for parking, availability of transportation, issues of pollution and nature, and the health effects (physical and psychological) of packed-in spaces.

It isn't actually pleasant to be boxed in by endless brick walls, so these days it isn't unusual to see a skyscraper surrounded by wide pavement, green space, or even single family homes. But, *it looks weird.*

{% include image.html class="caption-bottom"
  url="/assets/images/spacious-downtown2.png"
  description="Why is there so much empty space?"
%}

And that brings us to today's frustration: making city centers in New Cities look realistically dense. As the game stands today, there are six issues that cause empty space:

# Issue #1 - Unfilled Lots

Sometimes there isn't a zoneable lot where there should be. For example, when destroying a road (such as to rebuild an intersection with traffic problems), any lots that the road was overlapping are not restored, leaving an empty space. I expect to fix this soon.

Other times there is a zoned lot available, but it doesn't get filled due to lack of demand in that zone. This is a matter of tuning the density heatmap to match changes in zone demand.

# Issue #2 - Nothing to Fill the Lot

These are problems with the "building set" or collection of building designs. Every building in the game was designed using the Building Designer. Players will be able to create their own designs and even entire building sets. The quality and completeness of the building set is actually important for gameplay. It's essential that there are multiple designs of every size and density, both high land value and low -- otherwise the game might have no appropriate building to place in a location. Every building design in the game has a density tier between 0 and 10. For visual density, open space in the building design is empty space in the game. Tiers greater than 5 will be redesigned to leave little empty space.

# Issue #3 - Imbalanced Growth

As the density heatmap grows, it takes a while for the buildings to be rebuilt. This is how you get the "house next to skyscraper" situation.
This can be aggravated by differential growth between residential and commercial, or due to problems with the building set (no buildings with the right density, value, and zone). For this and other reasons, the density heatmap grows slowly.

# Issue #4 - Gaps Between Buildings

Sometimes there are gaps between buildings smaller than the size of a lot. The game could detect these gaps and place a thin building there. Alternately, the game could stretch out a building to fill the space.

# Issue #5 - Triangles

Any two roads that are not at 90 degree angles to each other create a triangular space that can't be filled by the rectangular building designs. I could add a feature to the building designer to allow for triangular buildings. Triangular Buildings would have to be stretched to fit different triangle shapes.

# Issue #6 - Setbacks

Inevitably there will be some empty space, such as the space between roads and buildings (the setback). That space should be pavement rather than grass, and so the game now renders pavement on the terrain starting around density tier 5. This means that there can't be any grass in the city center, unless I add a decoration for a "box of grass". Additionally, the road edges should look more like sidewalks than a dirt shoulder, so I'm working on graphics for sidewalks. (Note that we are a long way from pedestrian simulation, but you can use your imagination for now.)

{% include image.html class="caption-top"
  url="/assets/images/pavement2.png"
  description="The Pavement Must Grow."
%}

I expect to make progress on most of these issues in the month of December, or during the closed alpha starting in January. If this is important to you, or if it isn't and you would rather I prioritize something else, let me know! The IndieGoGo crowdfunding campaign starts before the end of the month, and hopefully as soon as next week. Contributors will have the opportunity to vote in the development priorities poll, allowing you to influence the design direction of New Cities!

To know just when the crowdfunding campaign goes live, join the [discord], [subreddit], and [twitter].

[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games




