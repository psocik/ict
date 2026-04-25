---
title: Casbaneiro Phishing Targets Latin America and Europe Using Dynamic PDF Lures
date: 2026-04-01
categories: [CYBERSECURITY]
tags: [PHISHING,MALWARE,CYBERSECURITY,LATIN-AMERICA,EUROPE]
---

## Casbaneiro Phishing Campaign 🚨

A multi-pronged phishing campaign is targeting Spanish-speaking users in organizations across Latin America and Europe to deliver Windows banking trojans like **Casbaneiro** (aka Metamorfo) via another malware called **Horabot**. The activity has been attributed to a Brazilian cybercrime threat actor tracked as **Augmented Marauder** and **Water Saci**. 

BlueVoyant security researchers Thomas Elkins and Joshua Green noted, "This threat group employs a wider-ranging attack model focused on a bespoke delivery and propagation mechanism that includes WhatsApp, ClickFix techniques, and email-centric phishing." They added, "It is now evident that while these Brazil-based operators heavily leverage script-based WhatsApp automation to compromise retail and consumer users in Latin America, they concurrently maintain and deploy an advanced, email-hijacking engine to penetrate enterprise perimeters there and Europe as well."

### The Phishing Email 📧

The starting point of the campaign is a phishing email that employs court summons-themed messages to deceive recipients into opening a password-protected PDF attachment. Clicking on an embedded link in the document directs the victim to a malicious link and initiates an automatic download of a ZIP archive, which, in turn, leads to the execution of interim HTML Application (HTA) and VBS payloads. The VBS script is designed to carry out environment and anti-analysis checks similar to those found in Horabot artifacts, including checks for Avast antivirus software, and proceeds to retrieve next-stage payloads from a remote server.

Among the downloaded files are AutoIt-based loaders, each of which extracts and runs encrypted payload files with ".ia" or ".at" extensions to eventually launch two malware families: **Casbaneiro** ("staticdata.dll") and **Horabot** ("at.dll").

### Propagation Mechanism 🔄

While Casbaneiro is the primary payload, Horabot is used as a propagation mechanism for the malware. Casbaneiro's Delphi DLL module contacts a command-and-control (C2) server to fetch a PowerShell script that employs Horabot to distribute the malware via phishing emails to harvested contacts from Microsoft Outlook. According to BlueVoyant, "Rather than distributing a static file or hardcoded link as seen in older Horabot campaigns, this script initiates an HTTP POST request to a remote PHP API (hxxps://tt.grupobedfs[.]com/.../gera_pdf.php), passing a randomly generated four-digit PIN." The server dynamically forges a bespoke, password-protected PDF impersonating a Spanish judicial summons, which is returned to the infected host. The script then iterates over the filtered email list, utilizing the compromised user's own email account to send a tailored phishing email with the newly generated PDF attached.

### Conclusion 🔍

Water Saci has a history of using WhatsApp Web as a distribution vector for disseminating banking trojans like Maverick and Casbaneiro in a worm-like manner. However, recent campaigns highlighted by Kaspersky have leveraged the ClickFix social engineering tactic to dupe users into running malicious HTA files with the end goal of deploying Casbaneiro and the Horabot spreader. 

The researchers concluded, "Taken together, the integration of ClickFix social engineering, alongside dynamic PDF generation and WhatsApp automation, demonstrates an agile adversary that is continually innovating and executing diverse attack paths to bypass modern security controls." They further stated, "This adversary is maintaining a bifurcated, multi-pronged attack infrastructure, dynamically deploying the WhatsApp-centric Maverick chain and concurrently utilizing both ClickFix and email-based Horabot attack paths." 

[Read full article](https://thehackernews.com/2026/04/casbaneiro-phishing-targets-latin.html)