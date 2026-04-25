---
title: Fault Injection – Follow the White Rabbit
date: 2025-06-18
categories: [RESEARCH]
tags: [FAULT INJECTION,SECURITY,RESEARCH]
---

**Intro**  
A few months ago, I read the work of Jeroen Delvaux, Cristofaro Mune, Mario Romero, and Niek Timmers on bypassing Secure Boot on an ESP32 V3 chip with both Secure Boot and Flash Encryption enabled. Their research demonstrated how it was possible to modify the flash memory to obtain an arbitrary CRC value, which would then be used through a single glitch (through EMFI) to execute arbitrary code.  

I found this research particularly interesting because it was not the typical “glitch and pray” (© Raelize) fault injection, but rather a well-thought-out approach that leverages a chain of issues to reach a specific goal. It clearly demonstrated that fault injection is increasingly becoming a viable and practical attack vector – not just about escaping a single instruction, but involving much more complex scenarios.  

The presentation and paper are available here:  
[Presentation Paper](https://www.usenix.org/system/files/woot24-delvaux.pdf)  
[Slides](https://www.usenix.org/system/files/woot24_slides-delvaux.pdf)  
[YouTube Video](https://www.youtube.com/watch?v=vx_j0L7xL8Y)  

The main goal of my research, documented in this article, is to verify whether the attack could also be performed using voltage injection, and to explore possible ways to improve on it.  

To read the complete article see:  
[Full Article](https://security.humanativaspa.it/fault-injection-follow-the-white-rabbit/)  

***  

***Working at Team Cymru is more than a job — it’s a chance to be part of something meaningful.  
Enjoy outstanding benefits, work with incredible people, and contribute to a mission that truly matters.  
  
Explore open roles and join us: [Careers at Team Cymru](https://www.team-cymru.com/careers)  
