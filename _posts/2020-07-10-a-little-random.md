---
layout: post
title:  "Friday Facts #39: A Little Random"
date:   2020-07-10 00:00:00 -0700
author: supersoup
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/07/10/a-little-random.html

image: /assets/images/39_bad_trees.png
description: More Information than you Require
---

supersoup:

Now it’s time for supersoup’s stream-of-consciousness shindig. The part of the show where supersoup sings a silly song. Or discusses game development. Possibly masked behind allegory and narrative. Who knows? 

I know. And I also know that we shipped Accelerated Mode this past patch, as well as the Seed UI for sharing and regenerating maps. Oh, and the Right Mouse Button behavior consolidation for consistency and contentment. Each of these three bullet points in the changelog were a team effort of course, but I’m going to take credit for them because that’s how I roll. 

Now let’s talk a bit about seeds.

{% include image.html class="caption-bottom"
  url="/assets/images/39_new_game_panel.png"
  description="Now you can share the map seed so your friends can build a city on the same map. But how do these magic numbers work? Read on."
%}

It was in the process of creating the seed UI that I learned (or relearned, more like) a simple but inescapably fascinating fact: computers can’t do anything randomly. Not by design; not without significant help. Let’s talk about that for a second. 

We talk about seeds. What does that mean? When using a random number generation algorithm, it must first be seeded with a value to then produce randomized results. Yes, it’s an algorithm as in a mathematical function. And as you might expect, if you seed the function with the same value, it will return the same results. Every time. Because it’s a function and math doesn’t change. 

It might look like a random sequence of numbers, but with the same input you’ll get that same output pattern no matter what you do. Remember that your computer is largely a gigantic calculator. One that runs on bottled lightning, magnets, and the magic blue smoke that you’re supposed to keep trapped in your power supply.

I hear letting it out is disastrous. 

Anyway, I wanted something more random than the basic random algorithm would produce, perhaps to allow for players to find more interesting or diverse seeds more easily, or perhaps because I was carried away by a fit of whimsy. Thus, after searching around the C++11 random library, I landed on the Mersenne Twister pseudorandom number generator. As we just discussed, the best we can do is pseudorandom with computers, but it’s one of the most random pseudorandom generators around to my unlearned eyes. 

Have you heard of black boxes? The concept that you can put something into a black box and get something else out without knowing the exact inner workings? That happens a lot in software development. Sometimes I include libraries, call black-boxed functions, and just trust that they work. Because that’s how multitudes of software developers have done it before me, and surely someone would have raised a ruckus by now if they were ill-formed, right? 

{% include image.html class="caption-bottom"
  url="/assets/images/39_tree_seed.png"
  description="Properly seeded tree distribution"
%}

But then sometimes I like to dig a little deeper and learn how things work. Just for fun. 
So here I am, it’s 4am local time, and I’m on the [Wikipedia page for the Mersenne Twister]{:target="_blank"}. Just in case you wanted a glimpse into the life of a game developer. I’m cruising through the sections, nodding sagely at times, lips pursed in a vague indication of the mental deadlifts I’m performing inside. 

And you know what? I have no idea what I’m looking at. No, this isn’t going to be one of those blog posts. One where an issue is presented, you follow the narrator on his journey to resolve it, and then you walk away feeling a little wiser. Not so directly anyway. Let’s jump back to black boxes. 

If there’s one thing I’ve learned in my game development journey it’s that anything can be learned. You may struggle with a particular subject, but with enough discipline and focus you can truly learn just about anything. However, there’s always an opportunity cost. Could you have better used the time spent unlocking that arcane or tangential secret in other areas of life? Was it something you truly needed to learn for yourself in order to do what you do? And when all else fails, did you have fun learning it? Honestly it’s fun to learn. Now I know what my teacher was talking about in grade school. 

Sometimes it's best for you, your teammates, and your career to slam on the brakes and study something new like you’ve never studied before. To wrap your mind around the mystical secrets that reside deep in the dusty, dank bowels of mathematics—or whatever your field of study may be. Even in failing to grasp the concept as a whole, you may gain some new minor insight. Some milestone of progression along your own personal journey. In that case, those detours are definitely worth it... 

But sometimes it’s ok to leave the black box alone. I think this is one of those times.

So what’s the next best thing for you, your teammates, and your career? 

Get some sleep. 

{% include image.html class="caption-bottom"
  url="/assets/images/39_night_city.png"
%}

---

Lone Pine: 

I hate to pull out my "I have a degree in computer science with a minor in cryptograph so I know a lot about random numbers" but here I go.

I actually went through the same thought process supersoup did a few months before he joined the team, but with a different outcome. We use a lot -- a LOT -- of random number generation in NewCity. One place we use it is to position trees. Trees are placed randomly in the environment, but with a catch. A "chunk" of terrain can be re-rendered at any time, and we want the trees to stay in the exact same place. Otherwise trees would bizarrely shift around every time the player places a road (since building roads triggers the terrain to redraw.)

So tree placement needs to be both random and not random at the same time. That means that the computer’s limitation to pseudorandom numbers is actually a good thing -- we can generate values that look random but are completely predictable based on initial conditions. 

For keeping important secrets secret, such as your bank information or web browsing activity (no judgements), you want a random number generator to be as random as possible. Criminals and snoops would be able to steal your data if cryptography was based on systems like the Mersenne Twister. Ideally, secret numbers would be generated by truly random things like air currents or quantum mechanics, but most people don’t have the needed hardware in their computers. So we rely on the next best thing: good pseudorandom number generators.

The problem with the Mersenne Twister is that it’s predictable and follows certain patterns. This means that an evil person can figure out where your computer is in the pattern and follow along. Since the Mersenne Twister is based on a single multiplication (in modulo arithmetic), patterns are inevitable. 

Since NewCity is just a fun game, we’re not concerned about evil people following patterns. However, we’re concerned about a much more serious problem: things *looking* bad. And since natural trees don't have a pattern to their placement, any discernible pattern in the trees will be noticed and it will look bad.

{% include image.html class="caption-bottom"
  url="/assets/images/39_bad_trees.png"
  description="Can you see what's wrong with this picture?"
%}

It took a lot of work to solve this.

{% include image.html class="caption-bottom"
  url="/assets/images/39_good_trees.png"
  description="Corporate needs you to find the difference between these two pictures. They're not the same picture."
%}

I originally just used the rand() function, an ancient feature of the C programming language. When I first ported the game to Windows (yes, the game was ported *from* Linux *to* Windows), the Windows version had this patterned behavior, because rand() was implemented in a different way by Microsoft. In fact, it looked much worse than the screenshots above, but I don’t have a screenshot from way back then. So I had to implement a custom random number generator to make the game consistent across all platforms.

That’s when I learned about the problem with the Mersenne Twister and all arithmetic based RNGs. I did some research and settled on a version of [Xorshift]{:target="_blank"}. Xorshift doesn’t use multiplication but instead exclusive or and bit shifting, both strange operations that are only meaningful to computers. These operations are non-linear and don’t display patterns (or at least, the patterns aren’t detectable by the human eye.) 

Xorshift makes a very good RNG for our purposes. The tree placement is nice, and 

I’m sure that’s more than you ever wanted to know about random numbers. Let us never speak of it again.

{% include image.html class="caption-bottom"
  url="/assets/images/39_bayside_city.png"
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
[Wikipedia page for the Mersenne Twister]: https://en.wikipedia.org/wiki/Mersenne_Twister
[Xorshift]: https://en.wikipedia.org/wiki/Xorshift


