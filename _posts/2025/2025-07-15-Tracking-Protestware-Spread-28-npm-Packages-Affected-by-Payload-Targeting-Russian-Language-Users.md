---
title: Tracking Protestware Spread 28 npm Packages Affected by Payload Targeting Russian-Language Users
date: 2025-07-15
categories: [SECURITY]
tags: [NPM,PROTESTWARE,SECURITY,RUSSIAN-LANGUAGE]
---

Socket’s Threat Research Team recently reported on two npm packages with hidden functionality for Russian-language users visiting Russian domains in a browser. In the last few weeks, the team has found the same protestware script across at least 28 new packages with nearly 2,000 versions.

As a reminder, this code will stop UI interactions on websites from working for any Russian-language users visiting Russian or Belarusian websites, falling under the classification of Socket’s protestware alert.

### Technical Recap: How the Protestware Works

Most of these packages have had 100,000+ lines of code in them:

Deep within the code, usually towards the end, there is an identical code snippet to the one discussed in our original blog post.

It is a complex if statement that requires the user (1) is using a browser (2) has their browser language settings set to Russian and (3) is visiting a Russian or Belarusian domain. If all three stipulations are met, the protestware will disable all mouse-based interaction on the page and play the Ukrainian national anthem.

To read the complete article see: [Full Article](https://socket.dev/blog/protestware-update-28-npm-packages-affected-by-payload-targeting-russian-language-users)