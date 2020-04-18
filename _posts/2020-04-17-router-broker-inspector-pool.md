---
layout: post
title:  "Friday Facts #29: Router, Broker, Inspector, Pool"
date:   2020-04-17 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/04/17/router-broker-inspector-pool.html

image: /assets/images/perspective-6.png
description: Putting a team together
---

*NOTE: We are doing community game nights every Friday, including tonight at 8pm PST. Find us on [Twitch] to join!*

{% include image.html class="caption-bottom"
  url="/assets/images/perspective-3.png"
%}

Have you heard? Lone Pine Games is growing! We already had a Tinker, Tailor, and a Spy, so we thought it was time to add a Soldier—someone who could hold down the fort on the art front. After about a month’s worth of Reddit posts and interviews, we have our Game Artist (Generalist) onboard and ready to rock. Folks, please give a warm welcome to Gainos. He took some time out of his busy schedule to answer a few questions and introduce himself in his own words: 

***

**Tell the NewCity community a little about yourself, who are you?**

My name is Mateus, I’m a twenty years old 3d Artist from Brazil. Other than the fact that I love games for as long as I can remember and that I almost never leave the house, not much to tell.

**In your own words, what is your role on the team?**

The team already has so much in terms of art assets in game, and most of that was made in a smart procedural way, so now it’s the time for some more hand-crafted details here and there, and of course add several art-y things for the upcoming updates. And that’s my part :)

**How did you get your start in gamedev?**

My first attempt at creating a game was when I was sixteen years old and while it didn’t reach the stage I aspired at the time, it taught me so much to continue on the journey to create game assets and reach the skill level I have today.

{% include image.html class="caption-bottom"
  url="/assets/images/purple-bart.png"
  description="An early prototype train model, by Gainos"
%}

**Any tips for aspiring game artists?**

Get yourself inspired by games you enjoy and create stuff related to that universe. Draw a prop, a character, have fun at it. No one is naturally good at art. The begining can be tough and if you are able to keep yourself inspired you’ll grow in skill much faster.

**Favorite work-related software?**

Definitely Blender3D. I’ve been using it since I started and the amount it changed is incredible. You can model, texture, sculpt, animate, edit videos, whatever you want in blender, and Blender’s community is incredible. If you know nothing about digital art and want to try it, don’t excitate and give Blender a go. It’s free and open-source.

**What are your top three favorite games? ( They don’t have to be citybuilders, of course :P )**

World of Warcraft, Hearthstone and an old browser flash game called Epic War (probably the first game I ever played seriously). Obviously there are so many games that I enjoyed but these are some of the most memorable ones. A good game may or not have art on it, but I always fell in love with games that had a memorable art style.

**What is your favorite food?**

I’m probably the weirdest human being on this planet since I really don’t know the answer for that. I suppose I could say it’s lentils or any other home-cooked food.

**What does the fox say?**

Probably something nice and wholesome such as: “You’ll succeed, keep at it!!” No?

***

Thank you, Gainos. Feel free to say hello to him on Discord if you see him around. Also be sure to let one of us know; that means he escaped from the art dungeons. 

{% include image.html class="caption-bottom"
  url="/assets/images/perspective-5.png"
%}

As far as my (supersoup’s) role in development this past week, I got to serve as the [rubber ducky](https://en.wikipedia.org/wiki/Rubber_duck_debugging){:target="_blank"} for Lone Pine while we worked through some significant challenges with the engine. Specifically regarding the new Perspective camera mode. I might know how to write a line of code or two, but I am decidedly not what’s known in the industry as an “engine-level” programmer. And my best efforts were soundly rebuffed by the merciless forces of linear algebra and [homogeneous coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates){:target="_blank"}. So I simply handed off my research and days worth of pitiful attempts to Lone Pine… who proceeded to make it all work in a matter of hours. Oh well, back to implementing new heatmaps for me.

First up is the Community heatmap. Community, as we envision it, will represent the strength of the community bonds in your city. Do people shy away from others as they pass on the street, or do they welcome one another with a smile and a wave? Is your city an ocean of isolated homes and families, or one where everyone knows everyone else’s name? These are the conflicts at the core of the Community metric, and the potential effects are plentiful. 

Strong Community in a city will potentially drive up demand for both residential zones and tourism, as well as increasing the use of mass transit (people feel more comfortable in crowds). Likewise, Community could provide an increase in Prosperity, as the community rallies together against adversity. 

{% include image.html class="caption-bottom"
  url="/assets/images/perspective-4.png"
%}

Sources of Community could be agriculture (farmer’s markets), parks and other recreational amenities, educational amenities, mixed use buildings, the Social Services amenity, and more. And keeping your Community high as Density increases would be a real challenge. How do you keep your citizens from feeling like just another face lost in the surging crowd? Well, perhaps by restricting the density of certain areas.

Dovetailing well with Community is another planned feature: the ability to limit the maximum Density level of zoned lots. Want to keep certain parts of your city rural, either to maintain high Community levels or preserve your suburb of single-family homes? Limit the Density, and you can mix in retail or other density-producing structures to your heart's content. Just remember that some zones like Industrial and Offices require a certain amount of density to get started.

Keep an eye out for these and other features in the coming weeks! While you wait, perhaps you could crack open a newspaper...

***

Lone Pine: We focused on quality this week. We fixed a few problems that caused crashes, implemented a new data gathering tool, and made several changes to improve performance.

At the heart of the game is a beast called the router, which finds paths through the city for every traveller. The bigger, more complicated a road network is, the more time it takes to compute a route. With tens of thousands of trips every game hour, that’s a significant source of stress on the game’s performance.

{% include image.html class="caption-bottom"
  url="/assets/images/route-inspector-1.png"
%}

The obvious solution? Introduce a cache. The game stores past computed routes so it doesn’t compute them twice. This works great up to a point. Beyond this point, we must slow down the game. This means that larger cities slow to a crawl.

We can address this by having citizens choose trips from which there is a known cached route. This week we introduced a subsystem called the route broker. Citizens request a destination with the type of service they desire (usually retail or a job) and the broker answers with a location that is known to have a good route in the cache. Previously, citizens would try random destinations which might be on the far side of the map or completely inaccessible.

As we continue to improve the router, we need to know how it’s performing and what routes it is returning. We need to introspect on what basis a citizen chooses to go by bus rather than car. For this reason, we added a route inspector. This tool shows how a citizen would travel between two locations in the city, including a private car route and a transit route (if available). This tool also shows how travel time and cost influenced the traveller’s decision to go by car or transit.

{% include image.html class="caption-bottom"
  url="/assets/images/route-inspector-2.png"
%}

We also addressed an issue where vehicle and travel group indexes would collect and slow down the game. We use object pooling, where every vehicle (and person, building, etc) has a unique index. It’s as if the game has a fleet of rental cars at the ready for every citizen to travel in. When a person wants to travel, the game gives them a car from the fleet. If all of the cars are in use and none are free, the game buys a new car from the manufacturer and adds it to the fleet.

In version 51 I introduced a bug which causes too many vehicle indexes (unused rental cars) to build up in the virtual parking lot of the object pool. Even when not being used, the excess vehicles slow down the game. To address this, I introduced a system to defragment our object pool and remove unused vehicles over time. If you had a city from version 51 or version 52.0/52.1, it might stall when it loads as it defragments the object pools, but once it starts running you should notice a performance improvement.

***

We’re excited to continue our weekly Community Factorio stream! Join us on Discord and Twitch for a fun-filled night of building elaborate automated assembly lines, running train rails hither and yon, and watching supersoup get destroyed over and over again as he tries to cull all alien life from the planet. We’ll be live on the [Lone Pine Games Twitch] Friday evenings; specific times to be decided, keep an eye on the Discord for details. 

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support!

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Lone Pine Games Twitch]: https://www.twitch.tv/lonepinegames
[Twitch]: https://www.twitch.tv/lonepinegames
[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games

