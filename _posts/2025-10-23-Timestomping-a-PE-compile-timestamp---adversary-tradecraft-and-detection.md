---
title: Timestomping a PE compile timestamp - adversary tradecraft and detection
date: 2025-10-23
categories: [INFORMATION SECURITY]
tags: [ADVERSARY TRADECRAFT,DETECTION,TIMESTOMPING]
---

If you’ve wondered how advanced adversaries (red teams or real threat actors) try to blend into a target system or deceive CTI/IR analysts, this post shows how COFF timestomping (overwriting a PE’s compile timestamp) is used and why it matters, as well as offering advice for spotting this.

We will also discuss why this technique is of value to adversaries of higher sophistication, and why understanding these internals can enhance the accuracy and depth of SOC or DFIR assessments. What I want to demonstrate is - don’t always take forensic data at face value, because adversaries can and will deceive you…

In this blog post, we look specifically at timestomping the compile timestamp that is imprinted in a Windows Portable Executable when it is compiled. This is a feature coming in v0.4 of the Wyrm C2 that I am building; it is already built on the dev branch and should be merged in the near future (early November 2025). Depending upon when you read this article, my Wyrm C2 may already have it on the stable branch!

To read the complete article see: [Timestomping a PE compile timestamp - adversary tradecraft and detection](https://fluxsec.red/timestomping-pe-compile-time) 
