---
title: Operation Macromaze APT28's New Campaign Unveiled
date: 2026-02-14
categories: [CYBERSECURITY]
tags: [APT28,OPERATIONMACROMAZE,CYBERSECURITY,MALWARE,PHISHING]
---

## Operation Macromaze: APT28's New Campaign Unveiled 🚀

LAB52 has been closely monitoring a campaign dubbed **“Operation MacroMaze”**, attributed to **APT28**, also known as **Fancy Bear**, **Forest Blizzard**, or **FROZENLAKE**. Active since late **September 2025** through **January 2026**, this campaign targets specific entities in **Western and Central Europe**. It relies on basic tooling and the exploitation of legitimate services for infrastructure and data exfiltration.

### Key Findings 🔍
- Documents feature macros, with one spear-phishing document using an alleged agenda from the **Ministry of the Presidency, Justice and Relations with the Courts of Spain** as a lure.
- All analyzed documents share an **INCLUDEPICTURE** field referencing a remote URL hosted on **webhook.site**. This functions as a tracking mechanism: when the document is opened, an outbound HTTP request is generated to the remote server, confirming the document has been opened.

### Macro Variants Identified 🛠️
Four slightly different macro variants have been identified, designed as “droppers” to establish a foothold by dropping six files (VBS, BAT, CMD, HTM, XHTML) into the **%USERPROFILE%** folder with GUID-like names. The GUID matches the **webhook.site** path used as the Command and Control (C2) server.

### Evasion Techniques 🕵️‍♂️
The scripts show an evolution in evasion techniques, from “headless” browser execution in older versions to keyboard simulation (SendKeys) in newer versions to bypass security prompts. The earliest variant (late September 2025) removes **ContentControls** and changes text color to black. A newer variant (October 2025) adds a fake **Microsoft Word** error message. The third variant (December 2025) keeps displaying this error message. The newest variant (January 2026) incorporates user interface manipulation, executing **SendKeys** “{DOWN}”, “{Enter}” and “{UP}” to simulate keyboard presses, automatically dismissing “Enable Content” security warnings.

### Persistence and Execution 🔄
When the **VBScript** is launched, it activates the **CMD** file, triggering remaining script execution. Persistence is established via a **Windows Scheduled Task**, dynamically generated at runtime. This task uses a repeating time-based trigger for periodic payload execution, running every 30 minutes in the first variant, 20 minutes in the second, and 61 minutes in the third and fourth variants.

### Conclusion 📊
The scripts then assemble a randomly named **CMD** from fragments, execute it capturing output, and merge output with **HTM** and **XHTML** templates to generate a final **HTML** file for exfiltration to another **webhook.site** instance. The final HTML file defines an auto-submitting form sending a POST request to a **webhook.site** endpoint, with payload output embedded within an element. When rendered by **Microsoft Edge**, the form submits, exfiltrating collected command output without user interaction.

For more detailed insights, [Read full article](https://lab52.io/blog/operation-macromaze-new-apt28-campaign-using-basic-tooling-and-legit-infrastructure/)