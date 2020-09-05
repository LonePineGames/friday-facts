---
layout: post
title:  "Friday Facts #46: Read All About Modeling"
date:   2020-09-04 00:00:00 -0700
author: Lone Pine
#categories: new-city friday-facts
redirect_from:
  - /blog/2020/09/04/read-all-about-modeling.html

image: /assets/images/46/46_gainos_uv01.png
description: It's Blender O'Clock
---

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_fullbuilding.png"
%}

Lone Pine:

Yesterday we released an early preview of The “Read All About It Update”. We’ve been working on it for a while and I actually forgot just how far this release takes us in terms of modding. 

* Achievements are now in Lua, allowing modders to add their own achievements and unlock amenities, as explained in the previous post, “Modder’s Dream”
* The game’s statistics can be read by Lua, including present and past values as well as national statistics. (The game keeps multiple groups of statistics called “econs”.)
* Buildings can have min and max years, allowing mods that span different eras. Mods can already change the in-game year, so we can now have historical or sci-fi mods.
* Buildings can now have any number of homes and businesses inside. Previously it was limited to 50 of each. Arcologies, anyone?
* The new Citipedia and newspaper features are fully moddable.

So far, I have not introduced any way to run a script in Lua and modify the game’s state as the simulation is running. I won’t lie to you -- I’m somewhat anxious to cross that threshold, because that’s when it becomes possible for modders to do damage. And until modders can move fast and break things, we won’t have “real” modding.

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_skyscraper.png"
  description="May your mods fly as high as your dreams"
%}

However, we are close. We only need two more elements: 1) a way to run Lua code after certain events are triggered, or every game update, and 2) something to do or modify in the game’s state that would be of interest to a modder.

The most logical place to start would be statistics. If a modder could edit any statistic, they could do a lot of damage, and therefore change a lot of things, in the game’s internal state. For example, it would be possible to force the city to have 100% demand for all zones at all times.

The goal is to have everything (or almost everything) in the game editable to modders. The game can be broken down into a number of systems: statistics, achievements, people, buildings, heatmaps, graph (roads and transportation networks), vehicles, routing, and so on. Over time, we will add ways to create, read, update, and delete (CRUD) objects in these systems.

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_pollution.png"
  description="Perhaps you could mod pollution to be a lovely, radioactive green"
%}

We don’t want anything to slow us down, so the first version of the modding API will be implemented with the understanding that it is far from the final version. Like in other games, mods will be incompatible from version to version until we are much closer to 1.0. We will move fast and break things.

In order to develop the modding system, we’ll need to put ourselves in the shoes of a modder. Therefore, the team will develop an official total-conversion mod to prove the system. I’ll be open to suggestions on what kind of mod we should make.

---

Gainos:

Hello everyone, Gainos here again. For these last two weeks I worked mostly on houses, apartments, industrial buildings and textures.

Most of the work was to make sure that the city centers have buildings that make sense, have appropriate textures and don't repeat as much (altho that last one is pretty tricky).

One thing that was brought over quite a few times was modding and community-made designs and because of that, I wanted to give some thoughts on the subject.

Each week as I make decorations to be included on the weekly patches, I try to listen to the community as much as possible and add decorations that can be added on whatever buildings modders want to create, but that isn't so simple.

There are so many possible results to a request such as "add more trees" and as such, the decorations I add to solve that may not be what the community was looking for.

The main focus currently is to finish the assets for the base game and not for modding. With that in mind I wanted to talk a bit about 3D and Blender.

Blender is a 3D computer graphics software that can be used to create models, animations, textures, videos and quite a bit of other stuff. It’s free and open source meaning anyone can head over to their official website and download it no questions asked. I personally find it very easy to use but then again, I’m not exactly getting started on it. With a few sentences, I’ll try to explain how you can get a custom decoration in-game.

Open blender and delete the initial cube on the scene. On the menu on top of the interface go to import and then Wavefront (.obj).

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_gainos_obj.png"
%}

Navigate to the game’s folder, open models and then inside it, open decorations. There you will see quite a few .obj files that the game uses. You can import any of those into blender and modify them. Let’s do this with the grass-patch.obj. After you import it you will see the model on blender’s viewport.

Alright you have the model there, but you probably won’t see any color on it. On the top part of the interface you will see interface settings such as Layout, Animation, Shading (you may have less or more depending on your version). Click on Shading.

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_gainos_shading.png"
%}

You will see this darker area on the bottom middle part of your screen. There you can select your texture. Click on the dark area with the grid and then hit CTRL + A and search “Image texture”

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_gainos_node01.png"
%}

You will see a yellow dot on the end of that node. Drag it over to “Base Color” on the big node on the center (Principled BSDF in most cases). Then hit open on the image texture and find your palette texture. The palette should be under the textures folder on NewCity.

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_gainos_node02.png"
%}

Great! Now whatever decoration you imported will be seen with it’s actual color. Now on those top tabs again to “UV” and zoom in on the left window. You should see something like this.

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_gainos_uv01.png"
%}

That little dot on the green area is the UV location of this model’s faces. You can drag that dot by first selecting it (you can box select by hitting B and then dragging your mouse cursor over the dot) and then move it with the G key. (If you don’t see the dot, go back to your right window and make sure you are in edit mode (hit tab) and then select all vertices (hit A)).

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_gainos_uv02.gif"
%}

In this case I just changed my grass decoration to blue.

{% include image.html class="caption-bottom"
  url="/assets/images/46/46_gainos_bluegrass.png"
  description="Blue grass, but not like the music"
%}

Now since this is a decoration that already exists, all I need to do is export this back to the folder with the exact same name and it will appear in the game, yay!

The same way as we changed the color here, you could have gone into edit mode and changed the vertices of the model in whatever way you wanted and then export that and you will see it in-game.

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games

