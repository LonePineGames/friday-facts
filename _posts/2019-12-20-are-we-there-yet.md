---
layout: post
title:  "Friday Facts #12: Are We There Yet?"
date:   2019-12-20 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts vehicles roads mods education
redirect_from:
  - /blog/2019/12/20/are-we-there-yet.html

image: /assets/images/concord/concord.png
description: Things are really coming together.

---

{% include image.html class="caption-bottom"
  url="/assets/images/concord/concord.png"
  description="Concord, population 327,000"
%}

For the past 2 and a half years, I've been building a game so that I, myself, could play it. Allowing others to share in the experience, and making it my career, was just icing on the cake. There simply wasn't a game on the market that I knew of with the gameplay mechanics I wanted (particularly around transportation).

This week was a "tune and polish" week. When I make a big change (such as a major new feature or subsystem refactor), the change usually "breaks the game" in the sense that the tuning parameters become out of whack. Before sharing the improvement with others, I have to make sure that the game is still playable, from beginning to end, which means I get to play the game again! I start with an empty map and make sure that the early game is correct—that is, that the city starts building right away and nothing crazy happens. As I build up the city, I fix bugs, tune more parameters, improve information feedback and make the tools easier to use. There is a huge amount of information that can be learned from the game's charts and the query tool. The reason why there is so much information is because I need it myself for bug fixes and tuning issues.

{% include image.html class="caption-below"
  url="/assets/images/concord/transportation_charts.png"
  description="Some transportation data"
%}

The latest and greatest New Cities is version 48, and this is the version where I feel like it really came together. The new vehicle system, while still incomplete, is a huge step forward. The performance is great, supporting tens of thousands of vehicles with no trouble, and there's room for even more optimization. The new economic system, featuring college education and office-type businesses, is really fun and challenging. The city can have prosperous areas and areas that struggle to get started. Amenities can (and should) be used to kickstart and build up struggling areas and outlying suburbs. Getting a large number of people into a dense city center is a challenging transportation problem, and you want Prosperity distributed around the region, so you’ll want to build up ancillary city centers once your main city is thriving.

{% include image.html class="caption-top"
  url="/assets/images/concord/suburb.png"
  description="A suburb developing its own city center, thanks to the presence of a technical college. (Don't mind the traffic.)"
%}

Version 48 includes Universities. There are 19 university buildings, starting with the University Quad, which must be placed first. Every University building must be within a block or two of the quad. There are 10 schools (science, art, business, and so on). Before you can place a school, you have to place dorm space for 1000 students, meaning two dorm buildings, or one dorm tower. The buildings are designed to tile together nicely. Originally I had intended for it to be impossible to place all 19 buildings in such a small space, but with the dorm tower you can squeeze them all in. (The dorm tower has a negative crime impact, making it a compromise.)

{% include image.html class="caption-top"
  url="/assets/images/concord/university.png"
  description="Concord University: 9 Colleges, 440 Professors, and 7,000 students"
%}

Together with the Technical College and Community College, Universities provide the primary source of bachelor's degrees in the game. You need a large number of workers with bachelor's degrees in order to build the office towers of the late game, and ultimately the goal -- the skyscraper. Additionally, you need lots of schools (non-college), as well as police and Community buildings, parks to mitigate the pollution, and finally a good transportation system. It's fun and challenging -- which means that we’ll probably need to implement difficulty levels.

I've very proud of version 48. I think we are ready for you guys to play in January, and I'm extremely excited to see the whole community playing the game. We also need your feedback and bug reports. I said before that I made the game for myself, and that the rest of you are along for the ride. But having a team and community will help me chart a course forward. Not only will we get to our destination faster, but we'll enjoy the journey more along the way.

{% include image.html class="caption-bottom"
  url="/assets/images/concord/concord_expressways.png"
  description="Zoom in on this one."
%}

You can buy the game now at a 24% discount from the retail price, get exclusive access to the closed alpha in January, and many more perks! Check out our [crowdfunding campaign]. And join the [discord], [subreddit], and [twitter].

Oh, and one more thing. I implemented modpacks.

{% include video.html class="caption-top"
  video="vapor" image="/assets/images/vapor.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Wait for it..."
 %}

You can modify the textures, shaders, palette colors, names of things in the game (people, businesses, roads), sounds, and the "building set", meaning the designs of all the buildings in the game, including amenities. Modders will also have access to the same set of tuning parameters I use. For example, if you want to make the city have relatively more or less traffic, you would modify the parameter CTrafficRate. Currently we do not have scripting or programmability, but that is in the pipeline.

We’re looking forward to seeing what you build!

[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[crowdfunding campaign]: https://igg.me/at/new-cities



