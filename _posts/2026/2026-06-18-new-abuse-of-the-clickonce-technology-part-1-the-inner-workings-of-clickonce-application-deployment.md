---
title: New Abuse of the ClickOnce Technology, Part 1 The Inner Workings of ClickOnce Application Deployment
date: 2026-06-18
categories: [TECHNOLOGY]
tags: [CLICKONCE,TECHNOLOGY,MALWARE,SECURITY]
---

## New Abuse of the ClickOnce Technology, Part 1

To help solve the challenge of application deployment, Microsoft offers multiple solutions including its Microsoft Store, the native Windows Installer component (.msi packages), and a lesser-known but powerful option: **ClickOnce technology**. ClickOnce is a deployment technology that enables developers to package and distribute applications that users can run, install, and automatically update with minimal interaction and without requiring administrative privileges. However, ClickOnce's user-friendly deployment process is a double-edged sword -- while it simplifies software deployment for legitimate developers, it also provides threat actors with an easy way of spreading malware. 🚨

In this two-part series, we document -- for the first time, to our knowledge -- the internals of this little-documented technology and discuss its security implications. Part 1 examines how the technology works under the hood, from the publication of the app to its installation on the user endpoint.

### Understanding ClickOnce

ClickOnce is a "deployment technology," which refers to the process of getting an application published with the ClickOnce technology to run and optionally install on a remote system. Its scope is therefore twofold: It provides developers with a streamlined way to distribute applications across different environments, and it offers users a standardized mechanism to execute (and optionally install) software. The concept is pretty straightforward: Developers can share one of the ClickOnce deployment files, on which the user would only have to "click once" to deploy the application.

These deployment files can be hosted on the vendor's website, where they introduce their app alongside an "Install" button. When clicked, the button triggers the download of the ClickOnce deployment file, and after some prerequisites are met, directly initiates the deployment. First, the OS asks for the user's confirmation if the publisher's signature cannot be verified, and upon confirmation, uses a standardized procedure to deploy the app alongside a dedicated wizard to keep the user informed of every step. 

In Part 2 of this series, we will focus on how threat actors can take advantage of ClickOnce apps. We will summarize known weaponization methods, disclose what we believe to be a previously unknown abuse our research uncovered, and discuss detection strategies.

[Read full article](https://www.crowdstrike.com/en-us/blog/new-abuse-of-the-clickonce-technology-part-one/)