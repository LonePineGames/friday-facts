---
layout: post
title:  "Friday Facts #10: Microeconomics"
date:   2019-12-06 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts economics
redirect_from:
  - /blog/2019/12/06/microeconomics.html

image: /assets/images/issues-icons.png
description: How to put a chicken in every pot

---

The [crowdfunding campaign] has gone very well, and we're well on track to make our goal. The next milestone is to launch the closed alpha, which we've promised to do in January. I set an agenda for December:

- Week 1: Microeconomics Improvements
- Week 2: Vehicle Simulation Improvements
- Week 3: Post-Processing (including SSAO)
- Week 4: Tune, Polish, Prepare for the Alpha

A couple weeks ago, I implemented "Issues Icons" which are red icons that appear over buildings, indicating one of a number of issues, including jobless people and businesses in need of workers, freight, or customers. Unemployment is one of the primary challenges of New Cities, so there needed to be a way for players to see which neighborhoods have the most unemployment. The icons can be toggled off if you find them annoying.

{% include image.html class="caption-bottom"
  url="/assets/images/issues-icons.png"
  description="Consequences of a 0% unemployment rate"
%}

Once the icons were working, I learned a lot about the employment dynamics of the game and found a bunch of bugs. I fixed those bugs and filled out the implementation of employment, education, and amenities.

In New Cities, there are people, buildings, and businesses. People can have one of four education levels: high school diploma, bachelor's degree, doctorate, or no education. Businesses also come in four types: farms, factories, retail, and offices. Farms and retail can develop anywhere, but factories will only develop in a city that has enough high school grads. Likewise, offices will only develop if the city has enough college grads. Schools = Factories, Colleges = Offices.

Since the goal of the game is to get a downtown area with towers of glass, it's not hard to understand why you'd want offices. But why do you want factories over farms? Why not just build endless tracks of farmland? Those of us living in rich countries who want a clean environment see factories as a bad thing -- NIMBY, we say! But 60 years ago, and still today in poorer places, a different logic applies: we'll tolerate the pollution as long as we have a good job.

{% include image.html class="caption-bottom"
  url="/assets/images/beachline.png"
  description="Beachline City, Population 90,000"
%}

How do you make sure there are enough jobs? The maps in New Cities are quite large (I've never filled a 50x50) so you could just build farms after farms until everyone is employed. However, people can't drive that far, so you'll have to build small towns distributed around the map. I call this the Los Angeles approach. You won't get density as fast, but it'll be cheaper, since schools are expensive. You'll also have to be strategic about the placement of commercial, since the game doesn't give you very much in the early on.

Fundamentally, this is a transportation issue. You can build farms as long as you can bring the workers there. You could even build early game expressways to put off building schools even longer. But at some point, you'll have to progress your economy. Once you build schools, factories will start to appear, and factories employ ten times as many people as farms.

How do people find a job? Originally, people just took jobs randomly from a global jobs board. When they went to work, if the commute was longer than 4 hours, they quit that job and got another. This created a problem where unemployed people would take and quit jobs thousands of times. It looked very strange on the economic charts and caused other problems.

Now, they actually go for a job interview before accepting the position. Interviewing for a job is an "activity", and each person is always engaged in some activity, be it working, shopping, visiting friends or a park, sleeping, or just chilling at home.

{% include image.html class="caption-bottom"
  url="/assets/images/interview.png"
  description="The first step to getting a job is to show up."
%}

The AI for a person just decides which activity to engage in based on a scoring system, then finds a location for that activity. A route is planned from where they are to that location, and a time estimate is computed. If it would take over 4 hours to travel to that location, they'll look for something else to do.

For job interviews, they have to start from home. When the time estimate for the route is computed, their commute is confirmed to be under 4 hours. Only when they make the trip and arrive at the job site are they marked as employed.

Only 3% of the time do they actually drive anywhere, the other 97% of the time they teleport. This is to keep the amount of traffic reasonable. The game still computes the route. This is to enforce the game's core transportation mechanic.

I made one other change this week: I finally established the benefits, or "effects" of amenities (parks, schools, police, etc). Each effect is associated with one of the 6 heatmaps, with a 7th type of effect (Community) as an alternative to policing. There are also 7 global effects.

- Education: Each Education point provides +1000 max citizens that can have a HS Diploma, +500 that can have a bachelor's, and +100 that can have a doctorate. Some educational institutions will educate citizens nearby. (Examples: Schools, Colleges)

- Technology: Effect of education is increased by 1% (Examples: Technical College, Science Museum)

- Nature: Reduces Pollution nearby (Examples: Parks)

- Environmentalism: Reduces pollution globally by 1% (Example: Nature Museum)

- Law: Reduces Crime nearby (Examples: Police)

- Order: Police are 1% more effective (Examples: Courthouse, Jail)

{% include image.html class="caption-top"
  url="/assets/images/jail.png"
  description="The Jail: A relatively good item with a serious drawback."
%}

- Community: Helps hungry and jobless people in the area. In addition to the warm fuzzies this might give, it'll reduce Crime and raise Value. (Examples: Clinic, Social Services, Library)

- Health: Reduces crime globally by 1% (Examples: Clinic, Hospital)

- Prosperity: Increases Prosperity nearby

- Business: 5% less unemployment (meaning, 20% unemployment goes to 19%)

- Value: Increases Value nearby (Examples: Parks, Schools)

- Tourism: Currently unimplemented. Once we have neighboring cities and/or airports, tourism will increase the number of visitors.

- Density: Increases Density nearby (this is a good one!)

- Prestige: Increases maximum Residential Density by 0.1 Density tier. (Examples: City Hall, Zoo, Hospital.) The maximum Residential Density starts at 4, so 60 Prestige points are needed for Density 10 highrises.

For example, the Hospital gives +20 Health, +5 Education, +5 Community, and +10 Prestige. It also currently is the only building that provides doctorates (medical training) since we don't have universities yet. It costs $20M (in 1950 dollars) and $3.75M/yr to maintain.

I'm still bug fixing and tuning this microeconomic system, and I want to get it right, so the schedule above might slip. The post-processing might therefore be pushed out to late January. But you will certainly get access to the game next month, because we're excited for you to play!

You can buy the game now at a 24% discount from the retail price, get exclusive access to the closed alpha in January, and many more perks! Check out our [crowdfunding campaign]. And join the [discord], [subreddit], and [twitter]. Thanks!

[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[crowdfunding campaign]: https://igg.me/at/new-cities

