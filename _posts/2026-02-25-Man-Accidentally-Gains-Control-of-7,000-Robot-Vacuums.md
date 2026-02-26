---
title: Man Accidentally Gains Control of 7,000 Robot Vacuums
date: 2026-02-25
categories: [TECHNOLOGY]
tags: [ROBOTICS,SECURITY,AI,PRIVACY]
---

## A Surprising Discovery 🚀

A software engineer’s earnest effort to steer his new DJI robot vacuum with a video game controller inadvertently granted him a sneak peek into thousands of people’s homes. While building his own remote-control app, Sammy Azdoufal reportedly used an AI coding assistant to help reverse-engineer how the robot communicated with DJI’s remote cloud servers. 

But he soon discovered that the same credentials that allowed him to see and control his own device also provided access to live camera feeds, microphone audio, maps, and status data from nearly 7,000 other vacuums across 24 countries. The backend security bug effectively exposed an army of internet-connected robots that, in the wrong hands, could have turned into surveillance tools, all without their owners ever knowing. 

### The Robot in Question 🤖

The robot in question is the DJI Romo, an autonomous home vacuum that first launched in China last year and is currently expanding to other countries. For Azdoufal’s DIY controller idea to work, he would need a way for his app to communicate with DJI’s servers and extract a security token that proves he is the owner of the robot. Rather than just verifying a single token, the servers granted access for a small army of robots, essentially treating him as their respective owner. 

That slip-up meant Azdoufal could tap into their real-time camera feeds and activate their microphones. He also claims he could compile 2D floor plans of the homes the robots were operating in. A quick look at the robots’ IP addresses also revealed their approximate locations. None of this, Azdoufal insists, amounts to "hacking" on his part. He simply stumbled upon a major security issue. 

### Responsible Disclosure 🛡️

Luckily, Azdoufal chose not to exploit that. Instead, he shared his findings with The Verge, which quickly contacted DJI to report the flaw. “DJI identified a vulnerability affecting DJI Home through internal review in late January and initiated remediation immediately,” DJI told Popular Science. “The issue was addressed through two updates, with an initial patch deployed on February 8 and a follow-up update completed on February 10. The fix was deployed automatically, and no user action is required.” 

While DJI tells Popular Science the issue has been “resolved,” the dramatic episode underscores warnings from cybersecurity experts who have long warned that internet-connected robots and other smart home devices present attractive targets for hackers. As more households adopt home robots, similar vulnerabilities could become harder to detect. AI-powered coding tools, which make it easier for people with less technical knowledge to exploit software flaws, potentially risk amplifying those worries even further. 

The irony of many robot vacuums and other smart home devices is that, as a category, they have a long history of questionable security practices, despite the fact that they operate in some of our most private spaces.

[Read full article](https://www.popsci.com/technology/robot-vacuum-army/)