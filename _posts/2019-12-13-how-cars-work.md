---
layout: post
title:  "Friday Facts #11: How Cars Work"
date:   2019-12-13 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts vehicles roads mass-transit
redirect_from:
  - /blog/2019/12/13/how-cars-work.html

video: how_cars_work
video-prefix: https://newcities-videos.s3.amazonaws.com/
image: /assets/images/how_cars_work.png
description: Screen space particle level fluid dynamics -- simple.

---

This week, I refactored the vehicle simulation. I had three goals to achieve: move cars into their own thread, interpolate their on-screen movement, and prevent them from jamming up. I'm also laying the groundwork for this system to support trains, buses, boats, airplanes, bikes and pedestrians.

{% include video.html class="caption-top"
  video="how_cars_work" image="/assets/images/how_cars_work.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
 %}

I originally planned the game to be 1/60th scale - that is, every real second is a game minute (at game speed 1) and every trip is one 60th the distance it would be in real life. However, that last part doesn't make a lot of sense, and it's not good for gameplay. The layout of the city is restrained by how far people can travel for work. I don't want the game to play any slower (quite the opposite), so a game hour has to comprise a certain amount of real time, a certain number of frames, a finite number of CPU cycles. Therefore, the maximum commute of every virtual citizen is a function of how many vehicles I want to simulate, how far a vehicle can go in an update, and how often the vehicle gets updated.

I'm least constrained on the "how far a vehicle can go" variable. There's no reason why a vehicle couldn't leap across an entire intersection in a single stride. Actually there's one reason -- it wouldn't look good. At game speed 3 (which I call time-lapse speed) you wouldn't notice. However, at game speed 1-2, the cars need to move smoothly. I can address this by interpolating the movement of on-screen vehicles. This creates beautiful smoothed motion, however the vehicles can appear to go off the road or collide with each other, and occasionally they'll jump around. These issues I will address with further tuning.

{% include video.html class="caption-top"
  video="interpolation" image="/assets/images/interpolation.png"
  description="Very much a work in progress."
  prefix="https://newcities-videos.s3.amazonaws.com/"
 %}

Another issue is jamming and gridlock. Certain bugs can cause cars to stop moving forward, which can clog an entire downtown area. Even without these bugs, enough cars in one area can cause the simulation to grind to a halt. In the real world, traffic rarely comes to a dead stop -- eventually someone will find a way to make progress, even if it involves going off road or towing cars. In the game, a deadlocked simulation is no fun and frankly breaks the game. Therefore, I plan to make the simulation "jam-free".

My theory is that if there are no bugs that cause jamming, and if every part of the road system has a firmly enforced capacity, then there will always be at least a small amount of motion. As long as the simulation is moving, however slowly, the traffic game will be fun and challenging. I have achieved a jam-free simulation in a prototype, and I hope this version will be jam-free in the next month.

Another small issue is visual colliding of cars turning left. I've thought about the possibility of doing traditional collision detection on the cars, either for the AI (collision prevention) or to detect crashes. I could then add a mechanic where the player has to deal with the wreckage. Including a form of collision detection would also make possible yielding at left turns. Currently we don't have this simply due to complexity.

Since we started the [crowdfunding campaign], we often get asked "where's the mass transit", or more succinctly, "WTF NO TRAINS?!?"

{% include image.html class="caption-below"
  url="/assets/images/twains.jpg"
  description="Don't worry, trains are coming."
%}

I've been laying the groundwork for mass transit for a while, and this refactoring gets us closer to that goal. I’m currently planning a robust "design your own transit system" mechanic. All transportation will follow the same model, with different vehicles -- planes, trains, and automobiles -- following paths set out by the player. Keep an eye out for more updates on this in the future.

You can buy the game now at a 24% discount from the retail price, get exclusive access to the closed alpha in January, and many more perks! Check out our [crowdfunding campaign]. And join the [discord], [subreddit], and [twitter]. Thanks!

[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[crowdfunding campaign]: https://igg.me/at/new-cities
[linked List]: https://en.wikipedia.org/wiki/Linked_list


