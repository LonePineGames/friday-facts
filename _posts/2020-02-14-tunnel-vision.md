---
layout: post
title:  "Friday Facts #20: Tunnel Vision"
date:   2020-02-14 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/02/14/tunnel-vision.html

image: /assets/images/circle-cull.png
description: Keeping Focus

---

No big news this week, just an update on various things we talked about before. On Monday we will release all the great enhancements mentioned in [last week's post](/2020/02/07/work-in-progress.html).

This week Mitch implemented proper frustum culling. Every frame, the game goes through the entire list of visible objects and selects which ones are visible, before wasting time rendering objects the player can't even see. Previously, I implemented a distance based metric. If you could see off the edge of the screen, you would see a big circle, with objects disappearing and reappearing as you moved the camera.

{% include image.html class="caption-bottom"
  url="/assets/images/circle-cull.png"
  description="Distance based culling - very wasteful."
%}

Everything inside the circle, but outside of the rectangular frame of the screen, should not be rendered. That is wasted work. I knew about this problem, but I didn't expect nearly the improvement that we got.

Mitch implemented a system whereby the game computes every object's centerpoint in screen coordinates. Anything outside the dimensions of the screen is "culled" and not rendered. If you could see off the edge now, you would see a rectangle of land and city slightly bigger than the screen itself. With this method, and some better tuning, we saw frame rates doubling and even tripling in some cases. (Your results may vary.)

{% include image.html class="caption-bottom"
  url="/assets/images/rectangle-cull.png"
  description="Viewspace culling - much more efficient."
%}

We pass around a save file of Concord at 1.25M population and use it to test the game under heavy load. Before, I got less than 30FPS on this file and sometimes less than 15FPS, at which point I consider it to be unplayable. Now, I get around 45FPS and even as good as 60FPS, while the game is paused. Unpaused, I still get just under 30FPS. This means that, for late-game cities, we have moved from a GPU-side issue to a CPU-side issue, at least on my machine.

Mitch also filled out the set of building textures. Here's what it looks like:

{% include video.html class="caption-bottom"
  video="building-textures-pan" image="/assets/images/building-textures-pan.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
%}

Another update on mass transit: we're close. The only delay is my lack of focus -- I am, in fact, human. As previously explained, I have to implement a tripart routing system to help commuters decide whether to travel by car, foot, or transit. Additionally, I have to implement the mechanics of transit vehicle movement. The transit vehicles (buses and trains) will use the same mechanics as cars, but they will have special rules around spawning and waiting at stops or stations. From the game's perspective, a station is just one or more stops on a platform, turnstiles to enter the station, and some walking paths to connect it to the city.

Before I reimplemented the vehicle system, the game had semi-trucks with independently moving trailers. These freight vehicles were implemented as two vehicles, with the trailer just blindly following it's tractor unit. I implemented this feature as a way to test multipart vehicles such as trains and articulated buses.

{% include image.html class="caption-bottom"
  url="/assets/images/clovers-are-bad.png"
  description="An older screenshot showing the semi-trucks."
%}

The new vehicle system has an interpolator to reduce the load on the simulation. This interpolator places vehicles every frame so they appear to move smoothly to the player. The current interpolator does not handle the trailers well. It's bad at a lot of other things too. It's a stopgap solution. Before enabling trains, I want to reimplement the interpolator.

I also want to start planning for the possibility of multiple people traveling together. I call this a "Travel Group.'' A Travel Group might be a family, a circle of friends, a classroom on a field trip, or coworkers carpooling or getting lunch together. I'm not sure yet how the game will assemble these travel groups, but for right now I can put each commuter into their own travel group. Future proofing.

As always, we’re incredibly thankful for our great community on [discord] and across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support!

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]. We're also on [reddit] and [twitter]. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[reddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[IndieGoGo page]: https://igg.me/at/new-cities




