---
layout: post
title:  "Friday Facts #19: Work in Progress"
date:   2020-02-07 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/02/07/work-in-progress.html

video: sunset-lights
video-prefix: https://newcities-videos.s3.amazonaws.com/
image: /assets/images/sunset-lights.png
description: We're building great things.

---

This week we implemented three big things -- and two of them were so big that players will unfortunately need to wait until next week to see them. Mitch implemented tooltips, I implemented a big update to the graph, and together we implemented a completely new visual style for buildings.

Mass Transit has been long in coming - it’s actually quite complicated. This week I implemented several important pieces of infrastructure: railways, pedestrian paths, viaducts, and underground tunnels (including a cutaway view of the underground).

{% include image.html class="caption-bottom"
  url="/assets/images/infrastructure-above.png"
  description="Railways, Pedestrian Paths, Viaducts, and Tunnels - Coming Soon!"
%}


The viaducts and underground tunnels are implemented using the same trick. Roads in New Cities generally try to use earthworks to match the terrain’s elevation to themselves, creating berms or trenches if the road is raised or lowered. I added a feature where pressing tab will prevent earth from being moved (under certain conditions) when placing a road, rail, or pedestrian path. 

When going upward, roads now render small concrete pillars underneath them. They are smart enough to not build a pillar in the middle of another road. This greatly improves the look of expressway interchanges.

{% include image.html class="caption-bottom"
  url="/assets/images/infrastructure-below.png"
  description="See what is hidden beneath your city"
%}

When going underground, a cutaway view of the city is shown, so you can see underground infrastructure. Underground tunnels won’t collide with buildings, so you won’t need to tear up your downtown when placing a subway. 

As mentioned, I also implemented railways and pedestrian paths. Railways use the same mechanics as roads, just with different vehicles and different rules around “merging” -- or switching track, in the case of rail. Railways can have a station platform, allowing you to stop trains there. You’ll set up lines in the same way as buses.

{% include image.html class="caption-bottom"
  url="/assets/images/station-entrance.png"
  description="The turnstiles to enter a train station."
%}

I have decided that pedestrian paths and sidewalks will use a completely new subsystem, since there are important differences from vehicles. Vehicles use a network called “LaneBlocks” to navigate through their world. Pedestrians will use “PathBlocks”, which will have important differences.

There will be a dedicated router for PathBlocks which will run on a different thread than the already overstressed vehicle router. Additionally, we will need a third router for finding paths through the transit system, and then some way to integrate all three routers so that a commuter can make a decision to go by foot, car, or transit.

This robust tripart system will take a little while longer to implement, so I appreciate your patience. Once it is complete, it will be possible to make custom transit stations, and plan how they connect to the city. 

{% include image.html class="caption-bottom"
  url="/assets/images/subway-station.png"
  description="Custom, Modular Transit Stations"
%}

Before too long, you’ll be planning transit-centric walkable cities and fighting car culture. It’ll be a blast!

---

# Update from Mitch

Hello, New Cities community!

You might know me as supersoup around the Discord. I’m the Community Manager for the game, as well as a Developer and Designer. Working on New Cities has been a dream come true for me, and I want to thank you for all your feedback and encouraging words.

This week, I had the opportunity to make good on Development and Design after a few months of onboarding. The first major system I tackled was the introduction of tooltips for the UI. Sounds simple, right?

There were a few key obstacles which complicated things. For one, the tooltips need to size dynamically to the text associated with each UI element. This creates situations where the tooltip might run off the edge of the screen. Likewise, the majority of the UI exists on the edges of the screen, meaning that a static position for the tooltip may push it out of bounds as well. So the first order of business was to include some basic logic to reposition the tooltip based on the cursor position/length of the text.

{% include image.html class="caption-bottom"
  url="/assets/images/tooltip-cropped.png"
  description="New Tooltips UI"
%}

The second obstacle was centralizing the tooltips (which are currently hardcoded) in a way that makes it easy to update them for localization. Eventually we plan to organize every UI string so that locale files can be used to adapt the UI for any language. Our fans hail from all across the globe; we would be remiss not to include support for other languages! The locale framework is going to be another major project, but that’s a topic for another day. 

---

On the design side of things, I’ve been digging deep into textures to prepare for our building visual refresh. Lone Pine implemented a new loader for building textures, allowing for buildings of any style and color. It’s accessible to modders as well so you can poke around with making new buildings your own. Together, we’ve been developing a visual language to govern our approach. We want the specific choice of materials and colors to convey information at a glance to the player, in addition to providing some much needed color to the cities. And it’s been lots of fun finding references for creating new textures. I’ve never considered myself much of a pixel artist, but seeing my texture sheets in-game has been a rare thrill. 


{% include video.html class="caption-bottom"
  video="sunset-lights" image="/assets/images/sunset-lights.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Sunset on a rainy night in Tacoma"
%}

Now that I’m up to speed, there’s lots more in the pipeline. Projects like Steam integration, localization, and performance optimizations dominate my horizon. But I couldn’t be happier to be in the trenches forging a better game for you all. I can’t wait to see what you build.

---

A big thanks to our great community on [discord]. Our passionate fans are striving to understand every part of the game. They're putting together modpacks and they've begun documenting the game in an [unofficial wiki]. Take a look, and perhaps add your own touch!

We're also on [reddit] and [twitter]. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[UX]: https://en.wikipedia.org/wiki/User_experience_design
[unofficial wiki]: https://new-cities.fandom.com/wiki/New_Cities_Wiki
[reddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[IndieGoGo page]: https://igg.me/at/new-cities



