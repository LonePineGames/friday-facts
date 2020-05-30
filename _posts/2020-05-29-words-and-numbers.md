---
layout: post
title:  "Friday Facts #35: Words and Numbers"
date:   2020-05-29 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/05/29/words-and-numbers.html

image: /assets/images/35_budget.png
description: Humane Computing
---

It’s Early Access time! 

We’ve finally locked a release date for the Steam Early Access launch. The wait is almost over. Starting June 12th, you’ll be able to pick up the game on Steam and join the Closed Alpha testers who have been building, modding, and sharing feedback. The base price will be $19.93, a bump up from our discounted IndieGoGo price at the Apartment Complex tier. If you’ve been waiting to make a decision on an IndieGoGo perk tier, time is running out. We’ll be locking the IndieGoGo campaign sometime in the next few weeks. Expect to see the physical perks like t-shirts, 3D printed skyscrapers, and the Skyscraper conversations with Lone Pine to go out in the next month or two. We’ll keep you updated.

{% include image.html class="caption-bottom"
  url="/assets/images/35_neighborhood.png"
%}

On that topic, we have a design for the t-shirt that we’re making a few final revisions to before sending it off to be printed. And the 3D printed skyscraper is ready; we’re just going to have to wait for some sample prints to come back for us to ok before we give the go-ahead. Thank you for your patience as we get all this sorted. If you contributed at any tier and haven’t joined our  [Discord]{:target="_blank"} yet, what are you waiting for? That’s the best way to stay in contact with the development team, as well as taking advantage of the Councilmember role and exclusive contributor channel access that come with your contribution.

I can’t say enough how thankful we are for your support. Whether you contributed to our IndieGoGo or have been following along with our development updates and waiting for the Steam launch, we’re so grateful for your interest in our humble citybuilder. We hope you enjoy your stint as mayor, and we can’t wait to see what you build. 

It goes without saying, but Early Access is only the beginning of the next leg of our journey. There’s lots of work left to do, and we’ll be counting on your feedback to help shape NewCity into the best game it can be. Long-time community members, we’ll be counting on you to welcome the new mayors with open arms. But of course you will. We simply have the best community, hands down. And it’s your passion for the game that fuels us on the journey. 

The road goes ever on and on. Thank you again for joining us on this adventure; it wouldn’t be the same without you. 

---

{% include image.html class="caption-bottom"
  url="/assets/images/35_bridge.png"
%}

A computer is only really capable of doing one thing: manipulating a series of numbers. Everything else is an abstraction. For example, text is represented as a series of numbers. The letter “A” (upper case) is the number 65 to a computer, “B” is 66, and so on. Modern programming has become very abstracted, with concepts like “Objects” and “Monads”, but for the computer’s sake, those abstractions have to be reduced to a numerical structure.

For us mere mortals, our eyes glaze over when we start seeing lots of numbers. I don’t know if humans actually think in words, but certainly it is a lot easier for us to use words over numbers. It is easier for us to remember a seven word passphrase than a seven digit pass*code*, even though seven words contain a lot more information. (There are thousands of words in the English language, but only ten digits.) 

{% include image.html class="caption-bottom"
  url="/assets/images/35_budget.png"
%}

Many programming languages today, such as JavaScript and Python, are heavily word based. They essentially work by maintaining associations between keywords and numbers, structures, etc. These systems are a lot easier to program, and that makes it possible to do more with less developer time. 

What these languages gain in ease of use, they lose in performance. For example, in NewCity, there is a concept of a hatchback car (as opposed to a pickup truck or sedan.) To the game, “hatchback” is just the number 4. If the game remembered “hatchback” instead of “4”, it would have to store and process about 9 times as much information, since “hatchback” is 9 letters long. (Actually it’s worse than that. For the technically inclined, it relates to a hash table requiring O(log n) time versus an array requiring O(1) time. If you have no clue what that means, don’t worry about it.)

NewCity’s system of numbers is extremely fast. However, our reliance on numbers has painted us into a bit of a corner. For example, we want it to be possible for anyone to add a new type of vehicle. Suppose you decide to take up modding NewCity and you want to add a Nuclear Powered Rocket Train as a type of vehicle. (I can’t blame you, sounds awesome.) You decide that the rocket train is number 90, since it runs on [thorium](https://en.wikipedia.org/wiki/Thorium). However, later on the developers (us) add a Mazda People Mover as we expand the mass transit options in vanilla. We’ve added 89 other vehicles, and now it’s time to use number 90. Uh oh, we have a conflict.

{% include image.html class="caption-bottom"
  url="/assets/images/35_maglev.png"
%}

It would be much more sensible for you to call it “VhNuclearRocketTrain” rather than “90”. That way, as long as the developers don’t introduce their own nuclear rocket train (don’t tempt us) there won’t be any conflict. Even better, if you put your modder name in front, like “CoolDude::VhNuclearRocketTrain”, then there is no possibility of conflict at all. 

But how can the game use numbers *internally* while using words *externally*, from the perspective of modders and players? Easy - the game just has to translate the word into a number at load time. Since it’s not predictable what vehicle types will be loaded from run to run, what number goes with which vehicle type can vary from run to run. The association is determined at load time by a “renumeration table”. This is essentially a hash table which associates words with numbers. It’s really the best of both worlds, and an extremely elegant solution for what otherwise would have been a frustrating problem.

This method will be used all over the game. Now that custom vehicles are working, our next step is to add custom building decorations that can be loaded from OBJ files. This will allow our artist, Gainos, to add his talent to the building designs, and I’m sure we’ll also see lots of cool stuff coming from modders like you. Stay tuned.

{% include image.html class="caption-bottom"
  url="/assets/images/35_clinic.png"
  description="A prototype of a new clinic design, by Gainos"
%}
 
---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Lone Pine Games Twitch]: https://www.twitch.tv/lonepinegames
[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games






