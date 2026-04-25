---
title: Livewire Flaw Puts Millions of Laravel Apps at Risk of RCE Attacks
date: 2025-07-21
categories: [SECURITY]
tags: [CVE-2025-54068,RCE,LARAVEL,LIVEWIRE]
---

A critical vulnerability discovered in Livewire, a popular full-stack framework for Laravel applications, exposes millions of web properties to unauthenticated remote command execution attacks. 

Tracked as **CVE-2025-54068**, the flaw resides in Livewire versions from **3.0.0-beta.1** up to **3.6.3** and stems from the way certain component property updates are hydrated, allowing an attacker to inject and execute arbitrary commands on the server. 

With no available workaround, developers and organizations leveraging Livewire v3 are urged to upgrade immediately to version **3.6.4** or later to mitigate the risk.

[Read the complete article here](https://gbhackers.com/livewire-flaw-of-rce-attacks/) 

[Learn more also here](https://github.com/livewire/livewire/security/advisories/GHSA-29cq-5w36-x7w3)