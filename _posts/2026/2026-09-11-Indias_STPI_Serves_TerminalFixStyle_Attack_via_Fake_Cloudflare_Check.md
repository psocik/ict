---
title: India's STPI Serves TerminalFix-Style Attack via Fake Cloudflare Check
date: 2026-09-11
categories: [CYBERSECURITY]
tags: [TERMINALFIX,CLOUDFLARE,CYBERSECURITY,MALWARE,ATTACK]
---

## India's STPI Serves TerminalFix-Style Attack via Fake Cloudflare Check 🚨

A website linked to India's Software Technology Parks of India (STPI) is serving a spoofed Cloudflare verification page that silently copies a malicious string to visitors' clipboards and prompts them to execute it via Windows Terminal. This technique is consistent with emerging TerminalFix-style attacks.

STPI, a Government of India organization that supports the country's IT services and startup ecosystem, operates platforms used by technology firms, developers, and public-sector stakeholders. The activity was observed on the ananta[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].in subdomain by cybersecurity researcher and red teamer Vibhum Dubey, who reported the issue to STPI and CERT-In, India's Computer Emergency Response Team.

A suspicious external JavaScript tied to the behavior remained embedded in the site's source, even after the attack briefly disappeared, indicating the issue may not have been fully resolved. The fake verification page, which had briefly disappeared, has since reappeared, according to the researcher.

The page mimics a standard Cloudflare "Verify you are human" prompt but includes an additional step instructing users to open Windows Terminal, paste a command, and press Enter. It preloads a string into the clipboard without explicit user action. The copied content is a URL which, when pasted into the terminal, would be interpreted by the system shell to initiate a request to external infrastructure controlled by the attacker. The destination associated with the URL has been flagged as malicious by multiple security vendors, with 17 engines detecting it as malicious on VirusTotal at the time of analysis.

The method shifts execution from the browser to the endpoint, relying on user interaction rather than direct payload delivery. The technique observed in this case is consistent with an attack pattern Microsoft calls TerminalFix, a variant of ClickFix. These attacks use spoofed verification pages to prompt users to copy and execute commands locally, moving the point of compromise outside traditional web security controls. Dubey stated, "The technique follows the same playbook: fake verification page, clipboard injection, and instructions to execute via the terminal."

Inspection of the site's source shows an external script loaded from cdn[.]quick[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS][.]com, a domain less than a week old and vaguely resembling the legitimate jsDelivr content delivery network. The registrant of the domain name provided an address in Russia, as for at least three other recently registered domains hosted on the same server at an IP address located in Hong Kong, according to data provided by domaintools.com.

Dubey noted, "The attacker appears to be storing command-and-control configuration on external infrastructure in a way that makes takedowns more difficult. The script itself is heavily obfuscated and runs through a virtual machine inside the browser, making it hard to analyze. Each visitor is also assigned a unique identifier, suggesting some level of session tracking."

"What's concerning here is that it's appearing on a government-linked site," he said. "The audience includes IT companies, startups, and officials. If a user executes the command on a work system, it could expose credentials or access to internal environments."

CERT-In acknowledged the report to the researcher and said it is "in process of taking appropriate action with the concerned authority."

[Read full article](https://www.csoonline.com/article/4221243/indias-stpi-serves-terminalfix-style-attack-via-fake-cloudflare-check.html)