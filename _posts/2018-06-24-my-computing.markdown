---
layout: post
title: "How I Do My Computing"
date:  2018-06-24 21:34:03 -0600
tags: computing emacs gnu
comments: 
---
In the process of publishing most everything that came to my mind in the past few days, I realized that I had neglected to mention what sort of setup I have and why I use it. This will be important going forward for those readers who may wonder why I don't seem to pay attention to their preferred software news.

And yes, the title is a deliberate nod to rms' ancient blog post explaining the same thing. ;)

<br />

------

<br />

I have been an avid GNU/Linux user since about 2007, when a friend who had been reading about the free software ethos told me enough about it to get me excited. What interested me most was that there was such a thing as an operating system which could be freely shared and developed. This squared perfectly with my ideas about how the world ought to be, with everyone freely using the hard work of other people, helping their neighbors, and always learning. I tried out Fedora Core and Ubuntu at that time. I think that friend would be very surprised to see what became of me since then.

Of course, my use in those days was very casual until I developed the determination to become competent with my "new toy". Networking seemed like the most interesting aspect that I wanted to learn, but there isn't much fun to be had in networking when you've never used virtualization and only have one PC. As I wasn't employed, I saved my pennies from different odd jobs and purchased some aged computers to experiment. I quickly hit a wall when I found out that two of them couldn't run X11 out of the box, and I lacked the skills to make them do so. Seeing this, I didn't give up (good thing, too!) and sought out a solution. I looked for a distribution that would give me a fairly complete amount of software that didn't require a GUI. Slackware seemed to fit the bill nicely, so I sent in for a DVD, since my parents' internet connection would have been at it for days. That summer was a time of great growth for me. With my only guide being system documentation and the shell, I grew to love this system. It didn't hurt that I discovered Emacs, either. 

From that time to the present day, I have really seen the free software world from top to bottom. I have learned my way around the *BSD family, built a small but complete Plan 9 grid, tried many free operating systems which are not based on Unix, and found my home at one time or another with dozens of GNU/Linux distributions. Eventually I have developed some preferences from experience, and find that nothing seems right to me anymore if I can't have this workflow.

My favorite programming language by far is Common Lisp. I largely use C for hardware hacking because of its efficiency, but wouldn't really call myself a "fan" of it. I have broad familiarity with other languages and am especially interested in Clojure and Go (mostly for its connection to Plan 9's concepts). I find myself most inclined toward functional programming, though not at the exclusion of other paradigms.

I do very little distro-hopping and always seem to favor modular systems that impose very little on the user. Slackware, Arch, and Gentoo have all been good experiences for this. No matter what the distribution, I spend most of my time in Emacs and use StumpWM as my window manager. Most anything that I want to do is possible this way. I am currently using Slackware 14.2, since I found myself missing its stability. As its package managing facilities are designed to be minimal, I reach for GNU Guix when there is something that I can't quickly get through other channels.

I use KVM extensively for testing and am working toward mastering some of the finer points of DevOps to further my career goals. Having such a solid base in free software before pursuing it in a full-time job has been immensely helpful.

With regard to software freedom, I prefer to use free software without evangelizing or looking down on anyone else. I find that my setup sparks conversation well enough when people see me using it, and it is always a pleasant conversation. 

Most of my work and play are done on a Lenovo TS140 (Xeon processor) with 16GB of RAM and about 2 TB of hard drive space in a software RAID. I found the use of ZFS for this configuration to be the smoothest experience and really wish that BTRFS would catch up with its feature list. :P One can dream!

<br />

And there you have it, folks - a little taste of what you're in for if you stick around. Cheers!
