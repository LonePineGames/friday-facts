---
layout: post
title: "Friday Facts #93: First Blood"
date: 2022-02-11 00:00:00 -0700
Author: supersoup
#categories: new-cities friday-facts
image: /assets/images/93/93_hero.png
description: Well, sorta...
---

{% include image.html class="caption-bottom" url="/assets/images/93/93_hero.png" %}

supersoup:

The cutting room floor was splattered with lines of code this week. 

Perhaps it's not as bad as it sounds. Many NewCity players won't even notice it. Not overtly at least. Whereas most often the cutting room floor will involve content that's gone without anything to replace it, in this instance we're making a cut in order to replace it with something better.

What we're cutting is the current approach to organizing designs and textures. The plan is to replace it with "design packages," or bundles containing both the designs and the other files needed to render them. Our goal is to vastly improve the experience from both the front-end and the back-end of the system. If you're a modder or a developer on NewCity, this change is for you! 

{% include image.html class="caption-bottom" url="/assets/images/93/93_school.png" %}

This all came about from a conversation between Lone Pine and myself. We were dealing with some odd behavior around the assignment of textures to a particular design. Under the current system, designs and textures are grouped via a key/value pair embedded in their filenames. It's worked well enough until now. But in this particular instance, we were struggling with some odd texture assignment.

As often happens in development, we started building a workaround. It quickly grew in size and complexity. And at one point, I finally said "We need to scrap this." 

I think Lone Pine thought I meant the workaround. So I elaborated: "All of it. The whole key value pair system."

It was hard to tell who was more surprised. I knew that discarding such a deeply entwined system would involve a great deal of retooling and rethinking. Easier said than done and all. But the more we discussed what a replacement might look like, the more sharply the image of a "design package" driven future came into focus. Let me tell you, it looks real good. Not just for us developers behind-the-scenes but for you modders out there as well. 

And I think it was the improvements to the modding experience that finally sold Lone Pine. 

{% include image.html class="caption-bottom" url="/assets/images/93/93_farm.png" %}

While the design of the new system is still in flux, at present it looks like folders. Folders in the ./design directory (Can I mix terminology like that? Well I did.) that contain not only the .design file but the textures as well. Instead of matching up designs and textures with keywords in the filename, they'll now be grouped together in a folder. Directory. Whatever. Depends on your preferred operating system, I suppose. 

This dramatically simplifies the experience. No longer will you see terracotta roofing tiles on your farm's amber waves of grain. No more wondering *how in the world* that texture got applied to that design. The game will now use the .png files in the same folder as the design for texture assignment. Illumination textures too. 

On the modding side, now you'll be throwing around these design package folders on the Workshop. It all stays together in a nice little package. Hence the name. Files aren't split between designs and textures. And distributing your work, textures and decos and all, just got that much easier. 

Full disclosure: this change will break all existing mods/designs on the Workshop. But the time to do this is before v1.0 rather than after – and with this done, we'll be that much closer to the goal with a smoother experience to show for it. Consider it a partial fulfillment of our commitment to polish up modding for the release. 

It's all rather succinct to describe. But there's still quite a few lines of code ahead of us to make it work. Pardon our dust in the meantime. 

As always, we look forward to seeing what you build. 


---

At Lone Pine Games we are always looking for feedback to improve our game! The best way to provide it is through the [NewCity Discord]{:target="_blank"}.

We are thankful to have such a lively and dedicated group of Mayors participating in discussions regarding new features, city planning strategy, development news, and just about anything else.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. 

Steam Reviews are always appreciated as well!

[NewCity Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games


