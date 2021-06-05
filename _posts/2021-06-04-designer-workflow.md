---
layout: post
title:  "Friday Facts #77: Designer Workflow"
date:   2021-06-04 00:00:00 -0700
Author: Gainos
#categories: new-cities friday-facts

image: /assets/images/77/77_hero.png
description: New Tools, New Look
---

{% include image.html class="caption-below"
  url="/assets/images/77/77_hero.png"
%}

Gainos:

For the past few weeks, I've been using a new workflow for textures. This new workflow allows me to work a little bit faster after the initial setup is finished, get more variations for textures done, and also produce much higher quality building and illumination textures as well.

All of this is possible using a software called Substance Designer. For quite some time I’ve stayed away from it, but at this point the pros greatly outweigh the cons. Being able to work faster is not the only benefit. Using an industry standard tool means that for whatever situation I can think of, there is a node (or combination of nodes) to do exactly what I need.

Previously, all of my texture work was done in a pixel art software. That software was initially used by Lonepine to make building and road textures, and when I joined the team, I chose to keep it going with the same set of tools, mostly because I didn’t know of anything “better”.

One of the problems of working with such a tool for NewCity however, is that many things would benefit from a more automated workflow, such as the window setup. In the previous workflow, each window (on one side of the building) was drawn and then symmetrized. I could not get too many different window setups done since those would just take way too much time. And don’t even get me started on illumination.

With the new workflow I can use nodes to help define shapes that will be tilling over the texture, using other nodes to mask which areas will receive those tilling shapes. The windows are the primary example. Now, instead of drawing every window, I define one (or more) window shapes and then the Tile Sampler node will allow me to quickly fill sections of the texture with shapes exactly like that. I can also use this to add smaller details repeated underneath each window, or only on some of them, using mask variations.

{% include image.html class="caption-below"
  url="/assets/images/77/77_substance.png"
  description="WIP Designer Substance"
%}

One of the challenges I have with creating textures for NewCity is that the game only supports a base color texture (also called albedo, diffuse and honestly whatever you want). Most of the work I’ve done outside of NewCity has been color only, since I do enjoy most games that focus on a nicely painted base color. With Designer, I try to add some extra depth to the textures by combining (to some degree) the Ambient Occlusion and Curvature, along with the “Light” node into the base color.

{% include image.html class="caption-below"
  url="/assets/images/77/77_tower2.png"
  description="Illumination on Designer"
%}

Probably the biggest benefit of this new workflow is how easy it is to create variations. I can very rapidly put together several unique illumination textures, wall colors and many other things by changing some parameters. If I’ve set up the substance well that is.

{% include image.html class="caption-below"
  url="/assets/images/77/77_polygon.png"
  description="The polygon node, the beginning of most Substances"
%}

What does that change for the players, you ask? Well, probably not that much. You can still create the textures in whatever software you want, in case you are into modding. If you’re not, then you’ll simply have better textures for the game. The illumination textures in particular will get a significant glow-up. I’ve been working for a while now doing research, getting started on substances, and just overall learning how to make NewCity look better.

{% include image.html class="caption-below"
  url="/assets/images/77/77_tower1.png"
  description="On the left an old texture and on the right, my attempt to re-create it on the new workflow"
%}

So yes, I’ve been a bit quiet for a while, but I promise you’ll soon see much more in terms of art for NewCity. If you want to discuss this, and more, tune in on one of our streams! This week I’ve done my first stream on the channel, and while I’ve mostly played Fall Guys (spoiler alert: I’ve lost over and over again), next time I want to talk about modding, art for NewCity, and just art in general. So if you are into any of that, keep an eye out for our weekly streams (usually on Thursdays).

Keep creating, and until next time!

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we're incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven't, and we'll keep you up to date on what's new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games


