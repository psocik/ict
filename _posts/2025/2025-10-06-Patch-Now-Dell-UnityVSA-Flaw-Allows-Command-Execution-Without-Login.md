---
title: Patch Now Dell UnityVSA Flaw Allows Command Execution Without Login
date: 2025-10-06
categories: [VULNS]
tags: [DELL,UNITYVSA,CVE-2025-36604,CYBERSECURITY,PATCH]
---

Cybersecurity researchers at WatchTowr have published their analysis revealing a vulnerability in Dell UnityVSA, tracked as CVE-2025-36604. The flaw allows an attacker with no authentication to issue commands on the appliance, all by exploiting a flaw in the login redirection logic.

The exploit originates from the way UnityVSA handles login redirect URIs. Under certain conditions, a user-controlled URI is inserted directly into a command execution string, without proper sanitisation.

When a request arrives without the expected authentication cookie, the system invokes a redirect to the login flow. That redirect logic funnels a raw URI into a function () where, if the "type" parameter equals "login," the URI is concatenated into a command executed via Perl’s backtick operator.

WatchTowr’s analysis indicates that multiple versions before 5.5.1 are vulnerable. Dell’s own advisory (DSA-2025-281) confirms that versions 5.5 and earlier are affected, and recommends upgrading to 5.5.1 or later.

To read the complete article see: [Read More](https://hackread.com/dell-unityvsa-flaw-command-execution-without-login/) .