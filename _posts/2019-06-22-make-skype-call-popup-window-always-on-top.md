---
layout: post
title: Make Skype Call Popup Window Always-on-top
date: 2019-06-22 11:00 +0200
---

Many months ago, Microsoft forced everybody to use the new Skype version 8, stating that it had all the features of the old Skype and more. This happened to not be the case, at least in my experience.

One thing the new Skype still doesn't seem to be able to do, at least on Ubuntu Budige, is keep the little call popup window always-on-top. This annoyed me so greatly that eventually I had to come up with a solution.

<!-- more -->

After searching the internet for a while, I discovered [devilspie2](https://www.nongnu.org/devilspie2/):

> Devilspie2 is a window matching utility, allowing the user to perform scripted actions on windows as they are created. For example you can script a terminal program to always be positioned at a specific screen position, or position a window on a specific workspace.

... which sounded very promising to me. So after tinkering with it for a while (using a debug script based on the script found on [this blog post](https://www.justingedge.com/linux/devilspie2-automatic-window-placement/)), I was able to whip up this script:

{% gist a7472b2083c9d67ce7183cf31d5cb81d %}

It waits for Skype to open the popup window and then sets it to be always-on-top. Pretty simple.

To use it, just place it in `.config/devilspie2/` as e.g. `skype-always-on-top.lua`. After that, add devilspie2 to your startup applications - no arguments needed - and you're good to go.