---
layout: post
title:  "Friday Facts #82: New New Player Experience"
date:   2021-07-09 00:00:00 -0700
Author: lone-pine, supersoup
#categories: new-cities friday-facts

video: new-tutorial02
image: /assets/images/82/new-tutorial02.gif
video-prefix: https://newcities-videos.s3.amazonaws.com/
description: New New New
---

NewCity is a complex game, and we've struggled to find a way to introduce new players and explain all the concepts. If you delete options.data and launch the current version of the game, you'll see three different systems trying to teach you how to play, and neither of them do a good job.

{% include image.html class="caption-bottom"
  url="/assets/images/82/three-tutorials.png"
  description="What a mess"
%}

This week, I cut through this mess and created one, more complete, tutorial. Supersoup built a great tutorial system, and I added markdown support, allowing images, links and formatting. I even implemented a system to show a slideshow of images, allowing for a kind of "animated gif" (not actually GIF format) to demonstrate actions.

{% include video.html class="caption-bottom"
  video="new-tutorial02" image="/assets/images/82/new-tutorial02.gif"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="\"Animated GIFs\" in tutorial" %}

In my personal playtesting, I find that the tutorial really gets a new city started off right, and I feel like a lot more motivated to keep playing after the tutorial is done, even though obviously I don't need the tutorial to play. This new "New Player Experience" will introduce players to the game in a way that is much less confusing. So if you've been confused playing the game, just be patient -- the new tutorial will be out within a few weeks.

---

supersoup:

There more than first meets the eye with regard to our tutorial system. It’s one thing to simply present information — but quite another to do so in an intelligent and appropriately reactive manner. In my experience, the best tutorials are the ones that initiate a sort of dance with the player, only stepping in response to the players’ actions, waltzing around the game’s mechanics until the player feels comfortable enough to set out on their own. 

In order to accomplish this, I added a new output from our input system.

We use [GLFW]{:target=”_blank”} to handle things like window creation and input for NewCity. If you press a key, we store that key down state in an array for each frame that it’s pressed. Elsewhere in the code, we’ll look for that key down state to know that we should be responding to the input in some way, whether that’s moving the camera or zoning lots in your city. 

It’s in this step that we want to capture and relay additional events that may pertain to the tutorial. 

So let’s say that you zoom the camera in or out. Now, nestled within the zoomCamera function, there’s a few extra lines of code that check whether the zoom is a positive or negative value, then they relay that info via a unique update code to the tutorial state object.

Perhaps it would have been better to explain the state object first then delve into its functionality, yet here we are. Suffice it to say, there’s a unique struct that stores all the pertinent info related to the tutorial, including the active step, active actions, and timers for certain other events. When an update code arrives at the state object, it does a simple check to see if it matches one of the active actions — and if it does, it flags that action as complete. Complete all the active actions and a cooldown will initiate before offering you the opportunity to proceed to the next step.

{% include video.html class="caption-bottom"
  video="new-tutorial03" image="/assets/images/82/new-tutorial03.png"
  prefix="https://newcities-videos.s3.amazonaws.com/"
  description="Cooldown in tutorial" %}

Why a cooldown? Speaking from experience, it’s quite easy to accidentally complete multiple steps just by messing around with keys and clicks before you’d even have time to read the corresponding tutorial text. Placing the next step behind a cooldown with a visual indicator that you completed the step as well as a button to progress gives you time to review the text and ensure you’re ready to proceed. Not to mention that some steps are simply waiting on a timer to complete. Everyone reads at different speeds, and it would be rough if the step jumped ahead while you were still reading. 

And it was somewhat of a happy accident that I worked on the tutorial system just before keymapping. There will likely be a similar system of relaying captured input at the heart of binding keys to actions and sending those actions out to trigger events in turn. But that’s a blog post for another time. 

{% include image.html class="caption-bottom"
  url="/assets/images/82/daily-daily.png"
%}

---

At Lone Pine Games we are always looking for feedback to improve our game! The best way to provide it is through our community Discord, which can be found here: http://discord.gg/cz6t4J5

We are thankful to have such a lively and dedicated group of Mayors participating in discussions regarding new features, city planning strategy, development news, and just about anything else.

If you want to play the game and haven't got it yet, head over to our [Steam page]{:target="_blank"}. We're also on [Reddit]{:target="_blank"} and [Twitter]{:target="_blank"}. 

Steam Reviews are always appreciated as well!

[GLFW]: https://www.glfw.org/
[Discord]:  http://discord.gg/cz6t4J5
[Steam page]: https://store.steampowered.com/app/1067860/NewCity/
[Reddit]: https://www.reddit.com/r/NewCity
[Twitter]: https://twitter.com/lone_pine_games



