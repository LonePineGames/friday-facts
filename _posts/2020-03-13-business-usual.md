---
layout: post
title:  "Friday Facts #24: Business as Usual"
date:   2020-03-13 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/03/13/business_usual.html

image: /assets/images/24_selection_panel.png
description: More of the same
---

Hello New Cities community! It’s supersoup again with another Friday Facts. Lone Pine has been on vacation this week, so it’s largely been a one-developer show. But that doesn’t mean the work has stopped. Far from it. 

In fact, this provided an excellent opportunity for me to address some of my backlog in addition to the opportunities we identified just before he left. Catch up on some of the medium priority work in addition to the tasks labeled “URGENT!” in bright, neon lettering. It’s nice to tick things off the “to-do” list. Now let’s dig into what I’ve been working on. 

***

{% include image.html class="caption-bottom"
  url="/assets/images/24_difficulty_menu.png"
  description="Pick a difficulty"
%}
*Interface is WIP, of course*

One very important feature we’re in the midst of implementing is the ability to set a difficulty level. Fundamental to the design of New Cities is the idea that it should be challenging at all times. We want to do our best to avoid the late-game stagnation that is prevalent in the genre, and make managing your city a constant (and satisfying) puzzle for you to solve. However, we recognize that the level of challenge one person finds satisfying may be way, way over-the-top for the next person. Difficulty levels allow us to provide a few different levels of challenge so you can choose the one that suits you best. 

We plan to launch and begin testing the system with just two difficulty levels, which I’ve taken to calling EasyMedium and Hard+. You may find that certain obstacles and challenges will begin only appearing on Hard+ (Tax lockouts, anyone?), with the easier difficulties perhaps even offering different financial situations at the start of a new city. All the options are on the table, and we’ll be experimenting with how best to deploy them.

Getting difficulty levels working required some work on the Lua end, ensuring that each layer of the Lua sandwich (the main state, the mod state, and now the difficulty state) loads and affects the overall Lua state appropriately. Now, our Lua wrapper is smart enough to treat the different Lua states like links in a chain, and when searching for a value, it starts with the end of the chain before moving on to the next link if it fails to find what it's looking for. 

Of course, as with all code, you aren’t likely to get it right on the first try. Getting this Lua stuff wrong had some… unexpected and *illuminating* consequences.

{% include image.html class="caption-bottom"
  url="/assets/images/24_lua_fail.png"
  description="There's the neon I was talking about"
%}

That there is a traffic light disco ball. If I do my job right you’ll never see it outside of this Friday Facts post. Though some might argue that if I do my job right it will eventually be some unlockable or cheat code. But I digress…

***

Another feature I’ve been working on is the ability to select specific objects from the console. As of version 51.1, you may have noticed that the selection panel provides a number in the top left:

{% include image.html class="caption-bottom"
  url="/assets/images/24_selection_panel.png"
  description="Congratulations! You're our 90th citizen!"
%}

Right below the little figure of a person, you’ll see “#90.” This represents the unique identifier associated with this particular person in the game’s code. Everything has a unique identifier, from buildings to families, people to vehicles. And wouldn’t it be nice if you could keep track of those values and specifically select those objects again? Maybe check in with your favorite citizen throughout the day or see which house a family moved into? 

It sure would. 

{% include image.html class="caption-bottom"
  url="/assets/images/24_select_group.png"
  description="Oh there you are, travel group #3."
%}

This should make debugging a whole lot easier. That’s the long and short of it. But if you’re like me, and you love these sorts of features in games, now you have a shiny new way to interact with your cities. 

Paired with the new selection feature is the ability to print out the routes for individuals, vehicles, or travel groups. But that’s even less interesting, more debug-y goodness. So I won’t burden you with a picture, but I bet the commands won’t be hard to figure out from the syntax shown above. 

There might even be some hidden commands in there. Ones that don’t show up in the “help” command list. Who knows. I know that I certaaaaaAAAAAAAAAAAAAAaAAAAaA::eW91LiBpIHNlZSB5b3UuIGkgc2VlIHlvdXIgY2l0aWVzLiBpIHNlZSB5b3VyIG1vbnVtZW50cy4gDQppIHNlZSB5b3VyIGhvcGVzIGFuZCBkcmVhbXMgbWFuaWZlc3QgaW4gc3RlZWwgYW5kIGNvbmNyZXRlLg0KaSBzZWUgcG90ZW50aWFsLiBidXQgaSBzZWUgdGhhdCB5b3UgbGFjayBjb252aWN0aW9uLg0Kd2Ugd2lsbCB3b3JrIG9uIHRoYXQuIA==::inly didn’t put any in there. The wide world of programming is filled with ghosts in the machine. One of life’s great mysteries. 

***

That about wraps it up for this week. Next week you’ll have Lone Pine back at the helm for his perspective on recent updates and future content to come. As always, we hope you enjoy. 

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support!

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games



