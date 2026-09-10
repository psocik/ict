---
title: New N0va Phishkit Targets North America and EU A Growing Identity Risk for SOCs
date: 2026-09-09
categories: [CYBERSECURITY]
tags: [PHISHING,IDENTITY,SECURITY,SOCS,NORTH AMERICA,EU]
---

## New N0va Phishkit Targets North America and EU: A Growing Identity Risk for SOCs

Recently, ANY.RUN researchers uncovered **N0va**, a new phishkit targeting organizations across North America and the EU, including government, technology, consulting, and healthcare sectors. What makes N0va especially relevant for SOC leaders is how it spreads the attack across different layers. Legitimate authentication, trusted brand lures, compromised websites, and cloud infrastructure can leave security teams with only part of the picture, making it easier to miss account compromise and harder to investigate the full chain.

N0va relies on lures that imitate tools employees use every day, including Microsoft Teams, SharePoint, OneDrive, DocuSign, Google Drive, Dropbox, Zoom, and Adobe Sign. In one ANY.RUN sandbox session, researchers observed a Microsoft-themed lure that guided the victim through a device code authentication flow. The page closely mimicked a legitimate Microsoft verification experience, making the interaction look familiar while directing the user into the attacker's flow. A successful N0va attempt can give attackers more than just a password. By obtaining access and refresh tokens and abusing device-registration mechanisms, they can establish SSO access to corporate resources and potentially remain active even after the initial phishing interaction is over.

The attack starts with a phishing lure that imitates a trusted business service and directs the victim into a device code authentication flow. Once the user completes the legitimate authentication step, N0va can obtain access and refresh tokens, then abuse token-exchange and device-registration mechanisms to establish SSO access. In short, the chain looks like this: 
- Trusted-brand lure  
- Device code phishing  
- Legitimate authentication  
- Access and refresh token capture  
- Token exchange / device registration  
- SSO access to corporate resources.

N0va turns a familiar business workflow into an identity risk. For CISOs and SOC leaders, the main concerns are: 
- **Account takeover**, where stolen access and refresh tokens can give attackers continued access to corporate accounts;  
- **MFA blind spots**, as legitimate Microsoft authentication can make the activity look less suspicious than a traditional fake login page;  
- **Limited visibility**, because phishing pages, authentication, and backend infrastructure may appear across different tools, making the full chain harder to connect;  
- **Longer attacker access**, as token-based access can remain valid even after the original phishing page is taken down;  
- **Higher investigation effort**, requiring analysts to correlate email, identity, browser, and network activity.

N0va highlights three areas where SOC leaders can strengthen their defenses: faster validation at Tier 1, better threat context across investigations, and broader detection coverage across the security stack. Identity-focused phishing can be difficult to assess from a URL, email, or login event alone. In the N0va investigation, a broader view helped researchers understand not only how the infrastructure was connected, but also where the activity was appearing and which industries were being targeted, including government, technology, consulting, and healthcare organizations across North America and Europe. A relevant TI query is: `url:"/api/verification/init?session=*&flow=*prompt_profile="`. Once your SOC identifies N0va-related infrastructure, the next priority is making sure the rest of the environment can recognize similar activity before another user reaches it. The intelligence is enriched by threat activity observed across a global community of 16,000+ organizations and 700,000+ security professionals, giving SOC teams broader visibility into infrastructure that is actively being used in real attacks. Instead of leaving useful indicators inside an individual case, the SOC can push them into SIEM, SOAR, EDR, firewalls, and other detection systems, helping teams spot related activity earlier and reduce the chance that the same infrastructure reaches another employee. N0va shows how phishing can quickly turn into an identity-security problem when attackers combine trusted services, legitimate authentication, and distributed infrastructure. For CISOs, the priority is giving the SOC enough visibility and context to detect these attacks earlier and respond before access spreads.

[Read full article](https://cybersecuritynews.com/new-n0va-phishkit-targets-north-america-and-eu-a-growing-identity-risk-for-socs/) 