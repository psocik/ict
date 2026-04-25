---
title: New Mic-E-Mouse Attack Shows Computer Mice Can Capture Conversations
date: 2025-10-07
categories: [RESEARCH]
tags: [SECURITY,COMPUTER,PRIVACY]
---

A team of researchers from the University of California, Irvine, has discovered a security risk right on your desk. It turns out that your high-performance computer mouse, an item you probably trust completely, can be turned into a hidden listening device. This new type of attack is called Mic-E-Mouse, and it has the potential to change our understanding of what computer privacy means.

These sensors, which track movement with extreme accuracy (sometimes 20,000 DPI (Dots Per Inch) or even higher), are sensitive enough to detect minute vibrations caused by sound waves traveling through your desk. Basically, your conversation causes your desk surface to shake just a little bit, and the mouse sensor picks up those tiny tremors. This vulnerability is formally known as a side-channel attack, which means it secretly gathers information through an unintended pathway, in this case, the mouse’s movement data.

A study posted on arXiv on 16 September 2025 by Habib Fakih, Rahul Dharmaji, Youssef Mahmoud, Halima Bouzidi, and Mohammad Abdullah Al Faruque from the Department of Electrical Engineering and Computer Science, University of California, Irvine, explains how the researchers created a process that converts raw, seemingly random mouse movement data into clear audio signals. The raw data is initially messy and incomplete, a problem the researchers solved with a multi-step "pipeline" that uses advanced signal processing and machine learning. This process filters out noise and pieces together the actual speech. The team’s experiments showed that they could significantly clean up the audio, achieving an increase of up to +19 dB in signal quality and a speech recognition accuracy between 42% and 61% on common speech datasets.

For your information, this attack does not require a complicated virus or deep system access. An attacker only needs a way to collect the mouse’s packet data, which could be done through common software like video games or creative applications that naturally demand high-speed mouse data. The whole process of data collection is invisible to the average user because it only captures the device’s normal movement reporting, and all the audio reconstruction can happen remotely on the attacker’s own server.

[Read the complete article here](https://hackread.com/mic-e-mouse-attack-computer-mice-conversations/).