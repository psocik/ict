---
title: Default Admin Password Let Researchers Unlock and Start Cars
date: 2026-11-10
categories: [SECURITY]
tags: [RESEARCH,CARS,SECURITY,VULNERABILITIES]
---

## Default Admin Password Let Researchers Unlock and Start Cars 🚗🔐

Researchers have successfully taken over customer accounts at two car brands, demonstrating how they could remotely unlock and start a test car. This was made possible after discovering an administration console on the brands' login servers that was still protected by its default password.

Security researchers Shubham Shah and Sam Curry detailed their findings in a write-up published on November 7. The customer logins for both brands utilized OpenIDM, an identity management software from ForgeRock, which is now part of Ping Identity. The specific brands were not disclosed at the request of the automakers.

In early 2026, the researchers bypassed the web application firewall (WAF) in front of the login servers and found that the console still accepted its documented default credentials. They then executed their own code on the identity servers, changing the email address and password on a test account. By logging in as that customer through the normal app, they were able to unlock and start the test car with the owner present. This session also exposed the vehicle's location and telemetry. The researchers noted that they could have created a session for any customer account on the affected deployments. Additionally, changing an account's login details left the owner's existing app session active, allowing the researchers to divert notifications away from the owner's phone.

Both automakers addressed the issue approximately two hours after it was reported and rotated the affected credentials, according to the write-up. The researchers also pointed to ForgeRock's hardening guidance to remove or protect the console before deployment.

In a companion post, Shah described a separate chain against one of the automaker's Australian systems, researched in July 2026. This chain could start from a car's number plate. Hardcoded administrator credentials, a WAF bypass, and a misconfigured multi-factor authentication (MFA) step allowed for account takeover and remote unlocking. The exposed data included customers' names, phone numbers, and password hashes. Together, the write-ups covered vehicles in Australia, the US, and Canada. The researchers emphasized that they tested only on cars they owned or had permission to use. Shah's post does not specify when the Australian findings were reported or whether they have been fixed.

[Read full article](https://www.infosecurity-magazine.com/news/forgerock-openidm-default-password/)\n