---
layout: post
title:  "Friday Facts #50: Shipping Updates"
date:   2020-10-02 00:00:00 -0700
author: Lone Pine
#categories: new-city friday-facts
redirect_from:
  - /blog/2020/10/02/workshopping.html

image: /assets/images/50/50_desert.png
description: From the deserts to the seas
---

{% include image.html class="caption-bottom"
  url="/assets/images/50/50_desert.png"
  description="Have you checked out the desert biome recently?"
%}

Lone Pine:

We've finished the Vapor Update and we're rolling straight into our next big project: The Oceanic Update. The month of October will be focused on the water. I have three "macrofeatures" I want to implement for this update, and one of the three I'm already done with.

First, some buildings will now be able to connect to the water. In the building designer, buildings will be marked as "aquatic" and they'll only spawn when they are the right distance from the coastline. The distance is configurable per-building, by setting the "high tide" and "low tide".

Our artist, Gainos, has already designed piers, docks, buoys, lifeguard towers, beach chairs and towels, a sailboat, and other items associated with the water. Over the next month, he'll design buildings that attach to the water, such as a public beach, a marina, industrial fisheries, and lakehouses.

{% include image.html class="caption-bottom"
  url="/assets/images/50/50_piers.png"
%}

The other two "macrofeatures" relate to getting things moving around in the water. I'm not sure if I'll get both implemented, but I will try. Firstly, I will create a type of vehicle which wanders around the waves without a specific destination, like a pleasurecraft or a fishing boat. There will be an algorithm to avoid the coasts, move somewhat randomly but still fluidly, and to eventually return to their starting point.

This wandering vehicles algorithm might be useful in implementing some other things, such as pedestrians wandering around parks or birds wandering the skies.

Finally, time permitting, we will finally implement the seaport system. Here's how it will work: You will be able to mark sea lanes along water where ships can travel. You'll place these sea lanes just like roads, but there won't be any infrastructure other than perhaps buoys to mark the locations.

{% include image.html class="caption-bottom"
  url="/assets/images/50/50_boats.png"
  description="And what would a waterfront be without beaches and boats?"
%}

On the water edges of the map, there will be "cargo ship points". Sea lanes will connect to cargo ship points just like roads connect to neighboring cities. Then, there will be placeable docks which connect to sea lanes. Once everything is connected, the game will spawn cargo ships at the points, and they'll travel to the docks. They'll empty their cargo, and a special building will collect and store the units of cargo.

Then the cargo will, over time, be loaded onto trucks and distributed to the city or to neighboring cities. This will also work in reverse -- freight produced by the city's industry will collect near the docks and once enough is accumulated, the game will spawn a ship at the dock and it will carry the cargo to the cargo ship point and disappear.

{% include image.html class="caption-bottom"
  url="/assets/images/50/50_duck.png"
  description="Behold, the Government Duck!"
%}

Later on, we'll also have freight trains that move larger amounts of cargo than trucks can, and will not clog up your expressways. Businesses will have to hire more employees to move the cargo, increasing employment. The player may also be able to levy a tariff to pay for the docks. The game will track the total amount of cargo moved, and will reward the player with stronger industrial demand.

If we are not able to implement all of this in the next month, it will carry forward into a future "Shipping Update".

---

{% include image.html class="caption-bottom"
  url="/assets/images/50/50_workshop.png"
  description="Steam Workshop preview, now on the Testing branch!"
%}

supersoup: 

We have the first signs of life from the Steam Workshop in the latest Testing branch update. 

As a proof-of-concept (and to help seed the Workshop with designs for the launch) we have file uploading implemented and functional. Currently, you can only search for and upload .design files via the Workshop file browser, but all of the core functionality is there to expand that in any direction we wish. And expand we shall. Everything from custom sounds and textures to full modpacks. 

{% include image.html class="caption-bottom"
  url="/assets/images/50/50_city.png"
  description="Make your city your own with mods"
%}


As we've openly discussed, all this work on the Vaporwave modpack was just a means for us to expand the modding platform and give you better tools. But what good is a modding platform if you have to share files via Discord pins? Steam Workshop support goes hand-in-hand with our longterm vision for the game: giving the community the means to create the exact citybuilder they want to play. It's why we started this endeavor, but being gamers ourselves, we recognize that empowering modders results in a longer lifecycle for the game and a healthier game overall. Make it yours.

We'll be filling out those other tabs in the Steam Workshop preview in the coming weeks. Expect to see something new with each patch. We're so excited to see what you build.

{% include image.html class="caption-bottom"
  url="/assets/images/50/50_trees.png"
%}

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games


