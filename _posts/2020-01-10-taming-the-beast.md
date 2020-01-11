---
layout: post
title:  "Friday Facts #15: Taming the Beast"
date:   2020-01-10 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/01/10/taming-the-beast.html

video: traffic-phases
video-prefix: https://newcities-videos.s3.amazonaws.com/
image: /assets/images/traffic-phases.png
description: Complexity can be fun

---

*A few things before I go into today's post: First, we're nearing the end of our IndieGoGo campaign, and to wrap things up with a bow, we're launching a referral campaign. Anyone whose referral link nets $45 or more (3 Apartment Complex tier donations) in support will receive a prize, which will probably be a T-shirt or mug. [Mitch explains how to get the referral link in an IndieGoGo update.](https://www.indiegogo.com/projects/new-cities/x/22253140#/updates/2)*

*Secondly, for those who have contributed, you will be playing the game as soon as January 17th. I know you're excited! If you haven't contributed [there is still time.](https://igg.me/at/new-cities)*

*Thirdly, I made a youtube video explaining some of the game features and mechanics. You might enjoy this if you are joining us for the closed alpha.*

{% include youtube.html video="4bmyKwUuUa4" %}

*Now, on to today's post.*

In the same way that the soft sciences are accused of [physics envy], software engineering has an envy of other engineering disciplines. A competent civil engineering team can set out to design a bridge, and be sure that they'll finish. And they can expect that the bridge will stand. [Usually.]

But software engineering is notoriously unreliable. Why is this? Many answers have been put forward. Some notice that we are a newer and less disciplined discipline (heh) than bridge building, a skill that civilization has been honing for thousands of years. But we are also doing something very different, something much more complicated than just making a static structure.

(Sidebar: This is not a prelude to saying that New Cities is having development problems. We're on schedule to release the game for our backers January 17th.)

{% include video.html class="caption-bottom"
  video="traffic-heatmap3" image="/assets/images/traffic-heatmap.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="The new traffic heatmap makes it easy to find traffic jams."
%}

Let's go back to the soft sciences. We all know that no simple math formula can predict what the price of pork bellies will be tomorrow, or whether a movie will be enjoyed by audiences. But why? Why is a nation's economy, or a human's tastes, not amenable to the rigid mathematical models that work so well in physics?

The issue is simply that human brains are far too complicated. An economy is really just a system of human brains, with layers upon layers of feedback loops and people responding to stimuli. Even assuming that it is a computable process, the computation is too much to reproduce with even the largest supercomputers.

I believe that the systems that we seek to understand (science) or build and manage (engineering) fall into two broad types: mechanical and organic. A mechanical system can be understood completely. Some things are too complex for one person but can be understood by a team. However, at a certain point the complexity crosses a threshold and becomes incomprehensible. At this point, the system takes on very different properties and can only be called organic.

{% include image.html class="caption-bottom"
  url="/assets/images/stadium-city.png"
  description="I'm trying to draw the density down around this stadium."
%}

I've said before that metropolitan areas in New Cities should feel like living organisms. My intention is for them to have a life of their own, to grow, breathe, and sometimes decay. Transportation is the lifeblood of a city, and so if people cannot travel to the places they need to go, the city should suffer proportionately.

When things aren't working, it can take some detective work to find out why. This is why the game has so many introspection features like the charts and the query tool.

Of the problems that stifle the growth of a city, some are the player's responsibility, but most are the developer's responsibility. Even when a problem is with the player, we still need to know why and make sure that overcoming the challenge is understood, that solving it is fun, and that the difficulty is reasonable.

Over the last two weeks, I've worked hard on the traffic simulation to make sure that it works reliably. Traffic jams are part of the game, and they are player's responsibility to fix. But past bugs would make the traffic stall completely. Now that I've fixed those bugs, the roads always move, although sometimes it's stop and go.

It's easy to make two phases of traffic flow -- free flowing and entirely stalled. But stalled traffic can destroy the economy of a city, which is no fun. And the player should get feedback regarding traffic before it jams entirely. Now instead of stalling, the traffic grinds down, but never comes to a halt. A choke point such as a bridge or onramp might chronically have cars moving at half speed, but the flow will remain constant.

{% include video.html class="caption-bottom"
  video="traffic-phases" image="/assets/images/traffic-phases.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Multiple phases of traffic flow"
%}

The simulated citizens are aware of traffic, and they factor driving time into their decisions about where to work, shop, and do other things. They might try an alternate destination, or even an alternate route. The game doesn't always simulate the trip itself, but to enforce the gameplay rules, a route and time estimate must be generated for every trip.

That's a lot of routing. I've done a lot to optimize the router, but there is still more to do. Currently I am dealing with an issue where the router falls behind the simulation, creating a long queue of routes that need to be computed. This creates an issue of "route starvation", meaning that citizens cannot make trips. By the game rules, this should cause an economic consequence, but that is unfair to the player.

{% include image.html class="caption-top"
  url="/assets/images/shakey.jpg"
  description="You can thank this little guy for the algorithm that routes cars in the game."
  link="https://en.wikipedia.org/wiki/A*_search_algorithm"
%}

I'm currently weighing a few options to solve this problem. I may be able to further optimize the router, or split the router across multiple threads. However, I do not want to introduce changes that major at this time, as we are approaching a soft launch. In the meantime, I will find a way to take stress off the router thread. This means that the fastest game speed will be disabled for now.

New Cities has evolved over many iterations. Like all software, it’s core is a system of mechanical processes. But taken together, it is quite complex. I hope you will choose to join us in learning how to tame the beast.

You can buy the game now at a 24% discount from the retail price, get exclusive access to the closed alpha in January, and many more perks! Check out our [crowdfunding campaign]. And join the [discord], [subreddit], and [twitter].

[Usually.]: https://en.wikipedia.org/wiki/Tacoma_Narrows_Bridge_(1940)
[physics envy]: https://en.wikipedia.org/wiki/Physics_envy
[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[crowdfunding campaign]: https://igg.me/at/new-cities
[approval voting]: https://en.wikipedia.org/wiki/Approval_voting

