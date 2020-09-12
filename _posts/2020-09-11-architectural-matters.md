---
layout: post
title:  "Friday Facts #47: Architectural Matters"
date:   2020-09-11 00:00:00 -0700
author: supersoup
#categories: new-city friday-facts
redirect_from:
  - /blog/2020/09/11/architectural-matters.html

image: /assets/images/47/47_architecture_header.png
description: Let's talk about architecture
---

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_header.png"
%}

supersoup:

There's a lot of architectural work in progress for NewCity. You've already gotten your hands on the updated Building Designer as of the Architect Update. And we've spoken fairly regularly about our plans to expand the modding platform, which we're presently focused on by building out our in-house vaporwave modpack and the systems needed to make it happen. Lone Pine has served as the chief architect for those two projects, offering me the opportunity to catch my breath and simply write the code I'm asked to write. But there are two systems for which I'm the chief architect currently in the works: Steam Workshop integration and an improved Tutorial experience.

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_transit_map_01.png"
%}

Adding Steam Workshop support is one of the most frequent feature suggestions we receive. And rest assured, I agree with you. A commit to modding means a commitment to the Steam Workshop. At least in our case, as we don't have the resources to build out our own system for hosting and sharing modded content. The Steam Workshop was built by developers for developers, meaning that it offers everything I need in a handy API to make it all happen. But then comes the client-side experience, the UI elements and data structures we need to build to interact with this external resource, and the edge cases that invariably crop up when handing end users the reins to this new, shiny system. I just finished the [boilerplate code] for our Steam Workshop wrapper this week. Now I can dig into the nitty gritty of the system and how it's all going to work. That puts the Steam Workshop at about 30% completion, in my estimation. 

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_city_01.png"
%}

A few weeks back, I wrote [a blogpost] about my work on the improved Tutorial. Frankly, since then I've been so busy otherwise that I haven't had much time to push it forward. It's probably about 50% complete as it sits. That said, we're in the midst of an epic update interval right now, and the plan is to have both the Steam Workshop and the Tutorial ready to go when we launch the next epic update or shortly thereafter. Not to mention the work on the modding platform. But hey, that's Lone Pine's structure to architect. 

Like code, architecture in the real world comes in all sorts of shapes and sizes. It grows and evolves over time as new ideas are introduced and integrated. You can learn a lot about a culture by studying their architecture, whether its brick and mortar, wood and stone, or C++ and Lua. 

On the topic of real world architecture, our Executive Producer and Business Advisor Galahad took some time out of his busy schedule to share his thoughts.

---

Galahad:

Creating visual beauty by using space to blend function and form is the joy of the architect. This is true for both individual buildings as well as entire cities. Many modern cities around the world have re-envisioned their cityscape by blending old architecture with new designs. And often the architect wishes to reference or ‘pay homage’ to an older design while maintaining the unique characteristics of the new one. 

Visionary mayors in NewCity also aspire to create new designs that not only please the eye but integrate with the existing architecture. We see this on the Discord Chat, as the community begins to create and share their own visions through the use of object importation and the Building Design. Some noteworthy examples can be seen below:

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_01.png"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_02.png"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_03.png"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_04.png"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_05.png"
%}

These are just a few of the many examples you can find on our Discord. And if you find yourself inspired, you can take advantage of the same tools used by the development team of NewCity to add your own visionary designs to the game. 

Every NewCity game starts in the middle of the last (20th) century. At that time, the efforts of great architects such as Le Corbusier, Robert Mallet-Stevens, Meis Van der Roh and others led to the spread of Modernism throughout Europe. 

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_villa_noailles_01.png"
  description="The Villa Noailles in Hyères by Robert Mallet-Stevens (1923)"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_villa_savoye_01.png"
  description="The Villa Savoye in Poissy by Le Corbusier (1928–31)"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_barcelona_pavilion_01.png"
  description="The Barcelona Pavilion (modern reconstruction) by Ludwig Mies van der Rohe (1929)"
%}

American architecture also began to be influenced by Modernism during this period, with great new work and skyscrapers by Frank Lloyd Wright, Louis Sullivan (“Form follows Function”) and others. They created various new trends and designs in modern architecture for buildings like majestic skyscrapers, museums, and homes. Trends like Prairie Stlye and Art Deco eventually led to the full integration of Modernism in American architecture.

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_larkin_admin_01.png"
  description="Larkin Administration Building by Frank Lloyd Wright, Buffalo, New York (1904–1906)"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_carson_pirie_scott_01.png"
  description="The Carson, Pirie, Scott and Company Building in Chicago by Louis Sullivan (1904–1906)"
%}

Asian cultures also produced great examples of architecture that combined modern materials and images in creative ways. I.M. Pei is perhaps one of the most prolific figures of this Asian movement, and his style can be found in many great works of architectural art globally.

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_national_gallery_art_01.png"
  description="East Wing of the National Gallery of Art in Washington, D.C., by I. M. Pei (1978)"
%}

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_louvre_pyramid_01.png"
  description="Pyramid of the Louvre Museum in Paris by I. M. Pei (1983–89)"
%}

Today, the world has moved into a period of ‘Post Modern’ architecture, from the likes of I.M. Pei, Fazlur Rahman Khan, and others. These architects established new methods of design such as X Bracing and the Trussed Tube (used in the John Hancock - Chicago building) and Bundled Tube (Willis Tower nee Sears Tower - Chicago)

Undoubtedly architecture will continue to offer new and exciting designs for as long as there are visionary architects pushing the boundaries of design. To that extent, Lone Pine and supersoup have made tools available to players of New City in the form of the Building Designer and object importation. We see many examples of new building designs and imaginative structures to suit a range of purposes and NewCity players.

{% include image.html class="caption-bottom"
  url="/assets/images/47/47_architecture_building_designer_01.png"
  description="Your innovative and inspirational architectural handiwork, by You (20??)"
%}

We hope that you, the Chief Architect and Mayor of your NewCity, will be able to create designs that delight and inspire not just your mind, but the minds of others in turn. And please be sure to share these images. They may be of use to others and will certainly enable the NewCity community to continue building beautiful environments and stunning cityscapes.

Thank you for everything you do and share. As always, we can’t wait to see what you build next.

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with NewCity!

[boilerplate code]: https://en.wikipedia.org/wiki/Boilerplate_code
[a blogpost]: http://lonepine.io/2020/08/14/tutorial-time.html
[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games

