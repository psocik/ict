---
title: Is b For Backdoor? Pre-Auth RCE Chain In Sitecore Experience Platform
date: 2025-06-17
categories: [RESEARCH]
tags: [VULNS,RESEARCH]
---

We’ve spent a bit of time recently looking at CMSs given the basic fact that they represent attractive targets for attackers.

As you may remember, Kentico Xperience CMS obtained our gaze earlier in 2025, and patched rapidly (typically the leading inhibitor to our publishing schedule). In the blog post, you can read about how we leveraged authentication “weaknesses” to gain full control of fully patched (at the time) Kentico deployments.

Today, we’ll be following a similar path - it does appear that CMSs and password security are actually mutually exclusive concepts, and struggle to exist in the same universe.

Sitecore’s Experience Platform is a vastly popular Content Management System (CMS), exposed to the Internet and heavily utilized across organizations known as ‘the enterprise’. That means that it doesn’t compete with WordPress, and has an expectation of being enterprise-ready (we’re not sure, either).

To read the complete article see:

[Full Article](https://labs.watchtowr.com/is-b-for-backdoor-pre-auth-rce-chain-in-sitecore-experience-platform/)