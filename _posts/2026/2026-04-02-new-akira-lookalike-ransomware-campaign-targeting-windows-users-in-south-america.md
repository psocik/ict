---
title: New Akira Lookalike Ransomware Campaign Targeting Windows Users in South America
date: 2026-04-02
categories: [CYBERSECURITY]
tags: [RANSOMWARE,CYBERSECURITY,SOUTH-AMERICA,WINDOWS]
---

## New Akira Lookalike Ransomware Campaign 🚨

A new and dangerous ransomware campaign has surfaced across South America, targeting Windows users with a carefully crafted strain that closely imitates the well-known Akira ransomware. While the two may appear nearly identical on the surface, this new threat is built on an entirely different foundation -- one that quietly borrows from another notorious ransomware family to carry out its attacks.

The campaign has raised serious concern within the cybersecurity community because of how convincingly it mimics Akira. Victims who fall prey to this threat find their files encrypted and their systems held hostage by a ransom note that looks almost identical to one from Akira -- complete with matching Tor URLs and similar wording. The deception is deliberate, designed to mislead victims and possibly even seasoned investigators into misidentifying the actual threat actor behind the attack.

ESET Research analysts identified this campaign after closely examining the ransomware's behavior and inner workings, confirming that despite its Akira-like appearance, the encryptor powering the malware is actually Babuk-based. This discovery was significant, as Babuk is a separate ransomware family whose source code was leaked publicly years ago and has since been repurposed by various threat actors.

The operator behind this campaign uses a Babuk-based encryptor that appends the .akira extension to encrypted files, while also dropping a ransom note that mirrors Akira both in its Tor URLs and overall content. This effective disguise points victims toward Tor-based URLs that closely resemble those used by the real Akira group, making it easy for organizations to misattribute the attack and potentially delay a proper and timely response.

The regional targeting of South America marks a notable shift in ransomware geography. Historically, ransomware groups have focused heavily on North American and European organizations, where larger volumes of sensitive data and higher ransom payment rates make attacks more profitable. This latest campaign suggests that threat actors are actively expanding their reach into South American markets, possibly using this lookalike strain as a testing ground before escalating to larger or more complex operations.

Organizations across South America and beyond should take immediate steps to reduce their exposure to this type of threat. Keeping all Windows systems fully patched and updated is a basic but critical step. Network segmentation can help contain damage if ransomware reaches a system. Maintaining regular offline backups ensures recovery without paying ransom. Security teams should monitor endpoints for unexpected .akira file extensions as an early warning sign. It is also important to avoid attributing attacks solely based on ransom note content, as this campaign clearly demonstrates how effective and misleading ransomware impersonation tactics can truly be.

[Read full article](https://cybersecuritynews.com/new-akira-lookalike-ransomware-campaign/)