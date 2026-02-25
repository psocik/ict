---
title: Hackers Hide Pulsar RAT Inside PNG Images in New NPM Supply Chain Attack
date: 2026-02-22
categories: [CYBERSECURITY]
tags: [MALWARE,NPM,CYBERATTACK,SECURITY]
---

## New Cyberattack Discovered 🚨

A new type of cyberattack has been discovered that uses ordinary images to hide a dangerous virus. Experts at Veracode Threat Research found a malicious package on NPM, which is a massive website used by millions of software developers to share tools. The package was designed to look like a normal piece of software, but its real goal was to take over a person’s computer. The package was named **buildrunner-dev**. The hackers used a **typosquatting technique** where they gave it a name that is almost the same as a real, safe tool called **buildrunner**, hoping someone would make a spelling mistake and download it by accident. This shows that the attack starts the moment the software is installed.

Once the package is on a computer, it runs a script that downloads a file called **packageloader.bat**. This file is huge and very confusing, containing over 1,600 lines of text, but most of it is just "noise" to hide the virus from security scanners. According to Veracode researchers, the file is full of random words like **raven**, **glacier**, and **monsoon** that don’t actually do anything. Out of the whole file, only about 21 lines are real commands.

Further probing revealed that the malware is also quite smart; it checks to see if you have antivirus programs like **ESET**, **Malwarebytes**, or **F-Secure**. If it finds them, it uses different tricks to sneak past them without setting off any alarms.

It first copies itself to a hidden folder as **protect.bat** so it can stay on the computer. It then checks if it has **Admin** rights. If it doesn’t, it uses a Windows tool called **fodhelper.exe** to bypass security warnings, so the user never sees a pop-up asking for permission.

The most interesting part of this attack is how it hides the actual virus inside an image. This is called **steganography**. The malware downloads a PNG image from a free hosting site, which, to a normal person, just looks like fuzzy, grainy "noise." However, the malware is programmed to read the tiny bits of color data, known as **RGB pixel values**, to find hidden code. Researchers also found that the malware uses a trick called **process hollowing**, where it replaces the "insides" of a safe program with malicious code to look like a normal process. It then installs a final malware called **Pulsar RAT**.

To read the complete article see:
[Read full article](https://hackread.com/hackers-pulsar-rat-png-images-npm-supply-chain-attack/)