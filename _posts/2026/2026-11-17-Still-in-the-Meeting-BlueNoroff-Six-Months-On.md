---
title: Still in the Meeting - BlueNoroff Six Months On
date: 2026-11-17
categories: [CYBERSECURITY]
tags: [BLUENOROFF,CYBERSECURITY,SOCIAL-ENGINEERING,WEB3,AI]
---

## Still in the Meeting - BlueNoroff Six Months On

**Published on:** November 17, 2026  
**Source:** Arcticwolf  

BlueNoroff has industrialized the social-engineering layer of its operation, expanding from fake meetings into the everyday workflows of Web3 leaders, while retaining a stable, behaviorally detectable compromise mechanism. Across document sharing, media playback, identity verification, wallet tools, and security assessments, the actor follows the same pattern: establish professional trust, manufacture a technical problem, and persuade the target to execute a threat actor-supplied command, script, shortcut, or workflow. 🚀  

The campaign is deliberately concentrated on individuals with the greatest authority over cryptocurrency assets and trusted business relationships. C-suite executives and founders account for the vast majority of identified targets, reflecting a focus on people who may control funds, signing keys, authenticated communications, sensitive information, and access to broader professional networks.  

Organization-specific infrastructure, individualized delivery paths, and professionally relevant pretexts demonstrate targeted preparation rather than broad, opportunistic phishing. Additionally, AI tooling has increased the speed, variety, and visual credibility of BlueNoroff's lure production. The actor uses AI-assisted tools to create platform graphics, verification prompts, synthetic media, and supporting content at greater scale. AI has not changed the underlying intrusion model; it has merely accelerated the production layer, supporting an operation that still depends heavily on target research, tailored engagement, and manual user execution.  

Six months after Arctic Wolf first documented BlueNoroff's fake-meeting campaign, the operation no longer depends on convincing a target to join a counterfeit Zoom or Microsoft Teams call. The threat actor has expanded into document-sharing services, media players, identity-verification prompts, browser updates, wallet tools, and security-audit workflows. This diversification makes the campaign more difficult to recognize by brand or ruse, but it does not represent a fundamental change in their compromise model.  

Across the recovered lure types, we found BlueNoroff follows the same sequence:  
- Select a target and develop a pretext aligned with the target's professional activity;  
- Impersonate a recognizable service, organization, or workflow;  
- Present content the target expects or has a reason to access;  
- Manufacture a technical problem that prevents the target from continuing;  
- Provide a purported fix that requires the target to run a command, script, shortcut, or workflow;  
- Use that execution to retrieve the next stage of the intrusion.  

Evidence from the actor-controlled media library and campaign infrastructure indicates that targeting begins before a lure is delivered. The actor meticulously collected profile images, professional biographies, organizational affiliations, public interviews, and conference recordings, and combined it with previously captured webcam footage. Upstream, reconnaissance has both widened and become more deliberate. Lure material has been scraped not just from profile photos and prior victims' webcam streams, but from YouTube interviews and conference talks, increasing the richness of the source material the actor can pull from.  

According to recovered assets, artifacts retained "raw ingredient" labels in the filenames, such as "[REDACTED] Talks -YouTube - Google Chrome 2026-05-19" and "Blockchain Interviews.mp4", showing the operator screen-recording a YouTube video to capture a specific person's likeness and voice. We identified highly specific subdomains (i.e. [company name].team-meet[.]xyz) associated with the actor's newly established infrastructure. We assess with high confidence that BlueNoroff was identifying and selecting specific targets versus striking opportunistically.

[Read full article](https://arcticwolf.com/wp-content/bluenoroff_still_in_the_meeting.pdf)