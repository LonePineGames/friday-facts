---
layout: post
title:  "Friday Facts #56: A Beautiful Day in the Neighborhood"
date:   2020-11-13 00:00:00 -0700
author: supersoup
#categories: new-city friday-facts

image: /assets/images/56/56_main.png
description: Gaining affinity

---

Lone Pine:


This week I made a change to the game we're calling "Neighborhood Affinity." This is a change in how a system called the Route Broker finds destinations for people. Every time a person wants to find a job, go shopping, or visit a friend, and every time a business needs to send freight to another business, the Route Broker must find a valid destination for that activity. The Broker prefers to give a result for which there is a known (cached) route from where the person is to that destination.

{% include image.html class="caption-bottom"
  url="/assets/images/56/56_chunks.png"
%}

Previously, the game would then randomly choose a destination from anywhere in the map. This meant that any given trip, and any person's workplace, could be on the far side of the map and on the other side of a giant traffic jam. Now with Neighborhood Affinity, the Broker will search for a close-by destination that meets the person's needs. The Broker searches chunk by chunk, in a spiral pattern, up to 12 (CBrokerSearchDistance) chunks away, covering a 25x25 square. If no destination is found, the game falls back to choosing a random destination anywhere in the map.

This should encourage a more regional playstyle. For example, I started making my farms with a little "farming town" to provide workers, and a small amount of retail so that farmers and townspeople don't have to travel far. I also noticed that retail locations farm away from farms and industry tend to not get freight, meaning that we have to distribute our industry a bit more. Once players understand the implications of this change, I think it will add a lot to the game.

{% include image.html class="caption-bottom"
  url="/assets/images/56/56_farm_town.png"
%}

---

supersoup:  
  
...  
  
...  
  
INFO - 12:33:07.108:  
Signal detected, SNR @ 42.6dB  
Gathering information...  
 
INFO - 12:33:07.111:  
Signal info -  
\[ BAND:LTE-BAND-30, DUPLEX:FDD, UPLINK:2307MHz, DOWNLINK:2352MHz \] \[ source UNK \]  
 
INFO - 12:33:07.113:  
MITM in progress...    
Locking frequencies...    
\[ UPLINK:2307MHz \] lock successful!  
\[ DOWNLINK:2352MHz \] lock successful!  
 
INFO - 12:33:07.118:  
Enabling packet analysis, scanning...  
Detected \[PacketType:PlainText\], contents:  
"Extant 2km from SITE-1463"  
Detected \[PacketType:FILE-HEADER\]\[FileType:RAW-IMAGE\] transmission, extracting info...  
\[ENDIAN: LITTLE-ENDIAN, SIG: HEAPCCDR, OFFSET: 16\]  
Scanning for remaining packets to reconstruct...  

INFO - 12:33:24.829:  
Input: 'str_search -r "extant" *.txt /home/heroesfall/CPRC-PUBLIC-TRANSCRIPTS/ &'  
Output: 1 match, in file \[/home/heroesfall/CPRC-PUBLIC-TRANSCRIPTS/jan20/cprc_hmanning_pressconf.txt\]  
"There's vast untapped potential in the extraordinary abilities of the entities we encounter, contain, and study. They carry genetic code the likes of which we've never seen before, holding the potential for surges in medical science beyond our wildest dreams. For breakthroughs in quantum physics and other abstruse fields of study. Given enough time and the right sources, we may even be able to make extant species out of those once resigned to extinction."  

INFO - 12:33:29.332:  
\[FileType:RAW-IMAGE\] interception completed! 

{% include image.html class="caption-bottom"
  url="/assets/images/56/56_extant.png"
%}

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we're incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven't, and we'll keep you up to date on what's new with NewCity!

[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games








