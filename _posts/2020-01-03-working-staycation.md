---
layout: post
title:  "Friday Facts #14: Working Staycation"
date:   2020-01-03 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/01/03/working-staycation.html

image: /assets/images/mixed-use.png
description: Zones!

---

Another short update today. I took a few (much needed) days to rest this week, and yet somehow still managed to make some major changes to the game. Firstly, I changed the font rendering engine so that we could use a conventional TrueType font. (The previous font was handdrawn in a paint program - talk about developer art!) The new font is Overpass, and it gives a clean, professional look to the UI.

{% include image.html class="caption-top"
  url="/assets/images/overpass.png"
%}

Mitch (soupersoup) made his first feature contribution, adding a zone demand chart to the right sidebar. This allows us to see zone demand without having the zone tool open - a much needed feature. He also fixed a few crashes. Having a second developer who's got my back has been a huge relief. Thanks Mitch!

At the same time, we decided to mix up the zones. Previously, we used the Residential/Commercial/Industrial model that every major game in the genre has followed. I've been reluctant to add density options, since I see density as a reward, not a decision. But this creates a bunch of problems.

{% include image.html class="caption-top"
  url="/assets/images/zone-demand-chart.png"
  description="Pheonix Bay, population 293,000. Notice the zone demand chart ⟹"
%}

The zone tool seemed anemic, with only 3 options. The player had no control over where polluting factories would appear. There were mixed use buildings, but no mixed use neighborhoods. And, I wanted to see the demand for the four types of businesses on the new zone demand chart.

Therefore, we're doubling the number of zones. Now there is Residential, Retail, and Agriculture (early game zones) followed by Mixed Use, Offices, and Industrial (late game zones). The late game zones will only develop if the location has sufficient Education, Density and Value.

Mixed Use buildings are generally apartments above retail, but sometimes offices or even factories. The buildings are designed to align to the edge of the road, creating that "cut-out" look.

{% include image.html class="caption-bottom"
  url="/assets/images/mixed-use.png"
  description="A Mixed Use neighborhood"
%}

You can buy the game now at a 24% discount from the retail price, get exclusive access to the closed alpha in January, and many more perks! Check out our [crowdfunding campaign]. And join the [discord], [subreddit], and [twitter].

[subreddit]: https://www.reddit.com/r/New_Cities
[discord]: https://discord.gg/udgeB2E
[twitter]: https://twitter.com/lone_pine_games
[crowdfunding campaign]: https://igg.me/at/new-cities
[approval voting]: https://en.wikipedia.org/wiki/Approval_voting




