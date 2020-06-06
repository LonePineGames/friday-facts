---
layout: post
title:  "Friday Facts #36: Pest Control"
date:   2020-06-05 00:00:00 -0700
author: supersoup
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/06/05/pest-control.html

image: /assets/images/36_closerroads.png
description: The closer they get, the more bugs there are to squish
---

This has been a bug fixing sort of week.

We’re officially feature locked for Early Access. I know it’s been said before, but it bears repeating. Because we really mean it this time. 

New features are often saddled with unexpected interactions and more new bugs than you can shake a can of bug-b-gone at. In the interest of actually shipping a playable game into Early Access as opposed to an exception riddled mess, we’re focusing on polishing and preparing what we’ve got. And what we’ve got is a vertical slice of the NewCity experience. 

{% include image.html class="caption-bottom"
  url="/assets/images/36_distantcity.png"
  description="Room to grow"
%}

It’s all there. Every feature is represented in some way. You can build your city up from the bare earth. The amenities and hidden heatmaps affect the simulation and the state of your city at large. You can control density manually, connect to neighboring cities, build tunnels through mountains, and cross rivers and lakes with bridges. Even mass transit has a presence, allowing you to build your own bus and train transit systems—when they aren’t crashing of course. That’s why we put the breaks on new and expanded features. You may have seen more updates than usual and thick changelogs, but fewer new toys to play with. That will change once we get into Early Access proper. One more week.

Good heavens, only one more week!

Early Access launches June 12th. I may sound like a broken record but it’s just hard for me to believe. And I’ve been present for every internal meeting discussing release dates, including the one where we finally locked on next Friday. Time to get the game on Steam and out before the crowds. One more week to get the game as stable and accessible as we can.

Anyone else feel like it’s hot in here? Just me? Maybe I’ll step out for some air before starting the next section.

---

{% include image.html class="caption-bottom"
  url="/assets/images/36_perspective.png"
  description="New perspectives mean new bugs"
%}

Bug fixing is a mysterious and amorphous skill. Just when you think you’ve got the hang of it, something else comes along and knocks you off your high horse. The more info, the better for hunting the most insidious and covert of bugs—so at the beginning of the week (actually a bit before) Lone Pine tasked me (supersoup) with implementing better stacktraces for Windows builds of NewCity.

What’s a stacktrace you ask? Buckle up.

When a program is running, functions within the program contain the logic and algorithms that keep things humming along. Each function has a header that defines the sort of function it is and what parameters it accepts, along with a body that contains the set of statements to be run. In pseudocode, a function might look something like this:

Function MyFunction (Accepts two numbers, Num1 and Num2) <br />
Begin Function <br />
    Create a Sum variable <br />
    Set Sum to Num1 plus Num2 <br />
    Return (send back) Sum <br />
End Function <br />  

Functions make the programming world go ‘round. But what happens when something goes awry within one? In that case, an exception is raised, and a stacktrace is dumped from the program. The stacktrace contains the list of functions that were called in the chain up until the point of error, and it’s an invaluable tool when debugging. Imagine if the program crashes and didn’t provide any info on when or where the crash occurred? 

Don’t imagine too hard. For our Windows builds of NewCity, that was the case up until a week ago or so. It wasn’t that it didn’t provide any stacktrace at all, it’s just that the stacktrace was run from the compiled code; as you might imagine, the computer doesn’t need all the human-readable function names and such to do its job. Once the code is compiled, the program becomes a bundle of memory addresses and hexadecimal identifiers. I’m sure “Exception occurred at memory address 0xFFFFFFFFFFFFFFFF” is useful to someone. But a meaningful stacktrace can tell us that the exception actually occurred in MyFunction. That makes the debugging process dramatically easier. 

Not easy, mind you. Just easier. 

{% include image.html class="caption-bottom"
  url="/assets/images/36_closerroads.png"
  description="Closer roads means crazy bugs"
%}

We ended up implementing the [StackWalker]{:target=”_blank”} library, which is tailor made for verbose Windows stacktraces. Now when a crash occurs on a Windows machine running NewCity (our largest install base; who knew?) the resulting stacktrace looks something like this:

concallbacks.cpp (28) conCallbackCrash <br />
coninput.cpp (208) handleCmd <br />
coninput.cpp (231) consoleParseInput <br />
console.cpp (90) consoleEntryKey <br />
part.cpp (152) acceptInput <br />

So we can clearly see the crash occurred in the function at the top of the stacktrace, conveniently named conCallbackCrash. Yes, that’s a debug console command that forces a crash. Sometimes you need a way to produce a crash on demand to verify that certain systems work as expected. We spend all this time trying to keep the game from crashing just to implement a way to do it on purpose. Game development is a weird business. 

Besides stacktraces and crashes, we’ve been hard at work polishing up the rest of the game and ensuring things work as intended. That even involves organized playtests, where one of us watches over the shoulder of a player with a pen and paper taking notes as they play the game. The feedback gained from such an experience includes additional bugs to fix, new features to consider, or simple user experience optimizations to keep things consistent. 

And of course, some of it is simple confirmation of what our Councilmembers on [Discord] have already been telling us. Thank you all for playing, weathering corrupted saves, and sounding off on the issues you encounter and what you feel is important for NewCity. It’s invaluable support in the effort to forge a better game, one bug at a time. 

Next week, the bug hunt continues. All the way up to the release candidate. Will we lock in a release candidate early, or will we be slamming the Steamworks build pipeline into the evening hours (UTC-7) of June 12th? Stay tuned to find out!
 
---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[StackWalker]: https://github.com/JochenKalmbach/StackWalker
[Lone Pine Games Twitch]: https://www.twitch.tv/lonepinegames
[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games















