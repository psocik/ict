---
title: New Rowhammer Attacks Give Complete Control of Machines Running Nvidia GPUs
date: 2026-04-02
categories: [SECURITY]
tags: [ROWHAMMER,NVIDIA,GPU,SECURITY,ATTACKS]
---

## New Rowhammer Attacks Give Complete Control of Machines Running Nvidia GPUs 🚀

The cost of high-performance GPUs, typically $8,000 or more, means they are frequently shared among dozens of users in cloud environments. Two new attacks demonstrate how a malicious user can gain full root control of a host machine by performing novel Rowhammer attacks on high-performance GPU cards made by Nvidia. The attacks exploit memory hardware's increasing susceptibility to bit flips, in which 0s stored in memory switch to 1s and vice versa.

In 2014, researchers first demonstrated that repeated, rapid access—or "hammering"—of memory hardware known as DRAM creates electrical disturbances that flip bits. A year later, a different research team showed that by targeting specific DRAM rows storing sensitive data, an attacker could exploit the phenomenon to escalate an unprivileged user to root or evade security sandbox protections. Both attacks targeted DDR3 generations of DRAM.

Over the past decade, dozens of newer Rowhammer attacks have evolved to target a wider range of DRAM types, such as DDR3 with error correcting code protections and DDR4 generations, including those with Target Row Refresh and ECC protections. These attacks also use new hammering techniques, such as Rowhammer feng shui and RowPress that zero in on extremely small regions of memory storing sensitive data. Such techniques have been used to make attacks work over local networks, root Android devices, and steal 2048-bit encryption keys. For the first time last year, Rowhammer attacks were shown to work against GDDR DRAM used with high-performance Nvidia GPUs.

This previous feat proved that GDDR was susceptible to Rowhammer attacks, but the results were modest. The researchers achieved only eight bit flips, a small fraction of what has been possible on CPU DRAM, and the damage was limited to degrading the output of a neural network running on the targeted GPU.

To read the complete article see:
[Read full article](https://arstechnica.com/security/2026/04/new-rowhammer-attacks-give-complete-control-of-machines-running-nvidia-gpus/)