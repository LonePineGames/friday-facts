---
layout: post
title:  "Friday Facts #75: Demanding Specifications"
date:   2021-05-14 00:00:00 -0700
Author: supersoup
#categories: new-cities friday-facts

image: /assets/images/75/75_hero.png
description: The Demand You Crave
---

{% include image.html class="caption-bottom"
  url="/assets/images/75/75_hero.png"
  description="The Demand You Crave"
%}

supersoup:

This week, Lone Pine and I set out to tackle the growing demand issue in NewCity. It's been on our radar for a while, but taking community feedback and our internal playtests as a whole, it could be frustrating at times but not showstopping overall. 

More recently it has crossed over into the latter realm. So we put our heads together and spent a week prototyping some possible solutions. 

The issue here is that any solution we put together will be little more than a band-aid for now. We have some other systems in the works which would provide a novel and unique experience in a few different realms — including zone demand — but these systems are broad and touch on many different systems in turn, so they'll take time to make and test. And there's always the concern that just when the community gets used to the new flow and feel of the band-aid we'll drop the new-new system on them out of a clear blue sky. 
But rest assured, we hear you loud and clear. Demand is an urgent issue that requires an urgent response. We're looking to make it happen as soon as possible. 

There's a lot of levers and switches under the hood of the NewCity engine. Sometimes you might see an obvious solution, but quickly realize it has unintended consequences elsewhere in the simulation. Take my approach to demand for example:

I started reworking zone demand from scratch, building my own algorithms for calculating the demand based on a variety of in-game factors that the player could reasonably affect. Like giving residential demand coefficients based on the sum of the land value, community, and health scores, with a negative coefficient based on the crime score. Open positions were also a consideration in my approach to residential, but instead of using unemployment as a sort of weight bringing the demand down, I used open positions to bolster the demand. 

The difference was immediately apparent. Residential buildings fairly flew up from the bare earth and population boomed in the early game. One of my concerns was our tendency on the dev team to fast forward through the first few years. We understand that such an approach isn't intuitive for a first-time player, so I wanted to offer the player more feedback even at base speed. 

However, this means that from the get go, traffic for all these simultaneous job interviews is a concern. As well as accessibility to retail. 

Retail demand is a function of agricultural and industrial businesses, both open and existing, with open weighted more highly than existing. The result is then divided by the number of retail businesses, naturally ensuring that there won't be too many retail spots competing for insufficient freight. Which sounds good on paper, except that with my new approach retail simply refused to grow, demand be darned. 

Another dynamic here is that demand doesn't immediately translate into a building provided a zone of the proper type is available. At least, not all the time. The game tries to fairly divide time between the different zone types asking for buildings, with business zones like retail, agricultural, and industrial having another algorithm entirely determining when they get plopped into the world. What seemed like a straightforward solution on paper turned into another spelunking expedition into a separate subsystem. 

Suffice it to say, Lone Pine and I met today and discussed our findings. Frankly it looks like the solution will be "a little of column A" and "a little of column B." There were elements in both of our approaches that we were excited about. And at the end of the day, the real question is what you, the community, will think of the band-aid. 

Please understand when I say we won't push it out the door before it's ready. But you won't have to wait too long to try it out for yourself. 

{% include image.html class="caption-bottom"
  url="/assets/images/75/75_end.png"
%}


---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we're incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven't, and we'll keep you up to date on what's new with NewCity!

[Hearthstone]: https://playhearthstone.com/
[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games


