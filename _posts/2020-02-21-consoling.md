---
layout: post
title:  "Friday Facts #21: Consoling"
date:   2020-02-21 00:00:00 -0700
author: Lone Pine
#categories: new-cities friday-facts
redirect_from:
  - /blog/2020/02/21/consoling.html

image: /assets/images/console_import.png
description: Building something New

---

Hello New Cities community! This week, you’ve got supersoup at the pen of the Friday Facts post. You may remember me from such films as “Moderating Discord: The Banhammer is a Two-Edged Sword” and “How to Lose Function Pointers and Alienate Objects.” 

Today I’ll be talking about my project for the past week: The In-game Console. What’s a console, you ask, and what does it do? An excellent question! One which I’m happy to answer at length. So kick back, get comfortable, pour yourself a cuppa, and let’s talk a bit about game development.

{% include video.html class="caption-bottom"
  video="console_floatingpanels" image="/assets/images/console_webmgoeshere.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
%}

Consoles are nigh ubiquitous in modern games. Every Unreal Engine, Source, GoldSrc, and idTech game has a console ready and waiting for you to open it up and punch in some commands. They’re an interface for developers and players to interact with the engine and other behind-the-scenes data, in addition to providing useful commands for spawning objects, changing settings, and much, much more. If you’ve ever typed “sv_cheats 1” in a Half-Life or Half-Life derived game, or “boolProp testingCheatsEnabled” as a longtime Sims fan, then you’ve interacted with a console.

As you might imagine, simply having data doing things in the engine isn’t enough; it’s immensely helpful to be able to read it back and modify it at runtime for testing purposes. Not to mention the opportunities that a console opens up for the modding community. Yes, it could be said that the console is the multitool of the development world. A modern game simply isn’t complete without it. So after some discussions with Lone Pine, I was tasked with the mission of bringing a console to New Cities. 

{% include image.html class="caption-bottom"
  url="/assets/images/console_hello.png"
  description="Every programming journey begins with a Hello World!"
%}

First things first, I had to build a home for the console to live in. After modifying a bit of our UI code, I was able to produce the first of what I call a “floating panel,” meaning that you can click and drag to reposition it on the screen. While this may be reused in other places, don’t expect to see it in the next update (or two). We’re going to be very deliberate and thoughtful in how we deploy floating panels elsewhere in the game. 

Once that was done, I had to engineer a way for the console to:  
1. Read user input
2. Map it to commands
3. Run any associated subroutine
4. Display feedback

Fortunately, I’ve dabbled with implementing consoles before, so I had previous code I could reference. And I was able to leverage the textBox UI element (used when naming a game save) for user input. In short order, I had the foundation for console commands, modifiers, and displaying text back to the user. All the ingredients you need for a tasty console. So what exactly are console commands and modifiers? 

A console command represents a subroutine, which is programming talk for “one or more things to do.” For instance, in the Source engine, you can enter “connect (IP address here)” in order to call the subroutine for connecting to a remote server. This allows the user to perform actions that aren’t necessarily mapped to keys. And the line between commands and changing variable values is often blurred; also in Source, typing “sensitivity (value here)” allows you to change your mouse sensitivity right from the console, as opposed to going through the settings. You could look at this as calling something like “setvariable sensitivity (value here).” The console has logic built in to determine if you’re trying to set a variable or call a command to keep things simple. I chose to implement the same feature in our console, so entering a Lua constant for instance will either display the current value or attempt to modify it depending on how you “invoke” the command. 

Modifiers, in our console at least, represent shortcuts to invoke commands or modifiers for how the command will be invoked. Entering ‘?’ prior to a command is the same as typing “help (command).” Likewise, I’ve set the capital ‘C’ prefix we use for Lua constants to serve as a modifier that basically translates to “setvariable (Lua constant) (value).” This will enable you to make changes to the constants comprising the game rules without exiting out to make the change through a text editor. 

{% include image.html class="caption-bottom"
  url="/assets/images/console_import.png"
  description="Just a hop and a skip from .obj model importation, for the dev team and modders"
%}

For the programmers out there, we use an open source library for handling .obj importation, which you can find here: [GitHub Link](https://github.com/Bly7/OBJ-Loader){:target="_blank"}. The library took care of the heavy lifting so we can focus on getting the models in-game. Hats off to the developer, Robert Smith (Bly7). 

There’s still a lot of work to be done, but the console is coming along. In a few short patches you’ll be able to try out the console (or at least a bare bones version of it) for yourself! We’ll be adding commands as needed to fill needs for both the development team and modders alike, so the console’s usefulness will grow over time. 

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support!

If you want to play the game and haven’t contributed yet, head over to our [IndieGoGo page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with New Cities!

[Discord]:  http://discord.gg/cz6t4J5
[IndieGoGo page]: https://igg.me/at/new-cities
[Reddit]: https://www.reddit.com/r/New_Cities
[Twitter]: https://twitter.com/lone_pine_games



