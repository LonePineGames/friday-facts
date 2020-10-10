---
layout: post
title:  "Friday Facts #51: Two Steps Forward..."
date:   2020-10-09 00:00:00 -0700
author: supersoup
#categories: new-city friday-facts
redirect_from:
  - /blog/2020/10/09/two-steps-forward.html

image: /assets/images/51/51_bay.png
description: And a step or two back

---

{% include image.html class="caption-bottom"
  url="/assets/images/51/51_bay.png"
%}

supersoup: 

Folks like to talk about the [gamification]{:target="_blank"} of society. Of our jobs, our menial tasks, and our leisure time. When sociologists and psychologists discuss gamification, they're talking about ways to reward participants for tasks, time, or effort in a positive way. Imagine leveling up every time you made a sale at a retail job, unlocking a special social media avatar for volunteering at the animal shelter, or having a quest to mow twenty-five lawns that would net you a small pay raise. The purpose of gamification is to harness the sort of gameplay and incentive loops that designers baked into videogames from the start to add a little something to everyday life. 

But there's two sides to the gamification token. There's a dark side that's rarely discussed. It comes down to the very definition of a game. 

{% include image.html class="caption-bottom"
  url="/assets/images/51/51_coast.png"
%}

Games present players with obstacles and challenges, while offering a series interesting decisions to overcome them. That's a rough approximation of a game. But with every obstacle, every challenge, there are invariably two outcomes: either you succeed, or you fail. Win or lose. Challenges have only two conclusive final states.

In order to gamify everyday life you would ideally have to define what the failure state looks like. And that's an issue that's not often tackled, at least as far as I can see. No one likes to lose. No one likes to take a step backward. So gamification applications generally only acknowledge positive accomplishments, choosing instead to represent failure with stagnancy. 

With this understanding, let's talk about the gamification of game development and the challenge presented to me in particular on Thursday, October 8th.

{% include image.html class="caption-bottom"
  url="/assets/images/51/51_cityscape.png"
  description="You can't build a city without deleting a few files"
%}

I (supersoup) am working on Steam Workshop support for NewCity. That's nothing new. In the process, I had to consider how to handle uploading files from the end-user to the Workshop backend. It used to be as simple as selecting the specific file and calling the update function. But Valve, rightly so, opted to switch to a folder based system. This makes things like modpacks or user-generated content with multiple dependencies (other assets or code required for it to work) very easy to throw into a folder and upload all together. So when you subscribe to a modpack, the Workshop knows you want all the files in that modpack folder and handles them as a single, conceptual unit. 

All well and good, but since we have all our assets organized into folders like Designs, Sounds, and Textures, I needed a way to isolate just the files we want to upload. 

{% include image.html class="caption-bottom"
  url="/assets/images/51/51_bridge.png"
  description="The bridge between your NewCity and the Workshop"
%}

I came up with the idea of a staging area. When uploading a file, NewCity uses a new staging folder for the item(s) that are to be uploaded. It sends them off, and everyone's happy. But then we have these folders and files just lying around in the staging area. That's no good. So we need a way to clean them up, right? 

Recursive functions (bits of code that call themselves based on certain conditions) are fickle beasts. Sometimes you think you have all the file path specific stuff figured out, then the next thing you know, your staging area cleanup code is recursively going through your NewCity development folder and deleting everything it can find. If we were to gamify the development of NewCity, cleaning up the staging area would be a challenge, and I would have triggered the failure condition. 

{% include image.html class="caption-bottom"
  url="/assets/images/51/51_overview.png"
%}

The good news is that failures are themselves obstacles to be overcome. No one failure represents the end of an endeavor so long as you continue to work toward the goal. You can learn from failures, grow from failures, and emerge better because of them. It took me a few hours to get my NewCity development environment back into working order. But fortunately the only cost for me was time -- I managed to salvage the code in progress. Coupled with the challenges Lone Pine faced on Thursday as well, we simply weren't able to push a patch out. I'll let him speak more on that if he wants in some future post. 

Suffice it to say, life goes on. We do apologize that we weren't able to manifest a patch for you. It wasn't the first patch delay, and realistically it won't be the last. But from each mistake, we learn. Every failure is another switchback on the path to the top of the mountain. And we're in this for the mountain peak. 

We have some fun stuff in the works, some of which I can't talk about just yet. But boy, once I can, I'll have a lot to say. Rest assured that we're reading your feature suggestions and support requests. Full and robust Steam Workshop support is very near. We'll keep doing our best to add FPS to your framerate. And we will make that pesky Bulldozer tool default to demolition instead of Terrain Editing. We're paying attention to your feedback, and together we'll keep chiseling the citybuilder we all want to play from the hunk of marble. One challenge at a time. 

---

Questions? Comments? Feedback on the game? Sound off on our [Discord]{:target="_blank"}.

As always, we’re incredibly thankful for our great community across the web. We love seeing the hard work and attention to detail you pour into your cities, and it inspires us every day to keep building. Thank you again for your support.

If you want to play the game and haven’t got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. Give us a follow if you haven’t, and we’ll keep you up to date on what’s new with NewCity!

[gamification]: https://en.wikipedia.org/wiki/Gamification
[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games


