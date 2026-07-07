---
title: Indian Govt Bans Apps Being Misused to Stop E-Rickshaws Remotely
date: 2026-07-03
categories: [GOVERNMENT]
tags: [INDIA,E-RICKSHAW,APPS,SAFETY,CYBERSECURITY]
---

## Indian Government Takes Action Against Misused Apps 🚨

The Indian government has directed Google and Apple to take down three mobile applications, **BAT-BMS**, **Lossigy**, and **Epoch-i-ion**, after they were allegedly misused to remotely disable e-rickshaws and other battery-operated three-wheelers mid-journey, putting passenger safety at risk. Authorities have also warned that any additional apps found to enable similar remote-kill functionality will face the same consequences.

This order follows a wave of viral videos showing individuals using these apps to locate nearby e-rickshaws via connected battery management systems and switching them off with a single tap, sometimes while vehicles were in motion carrying passengers. 

These apps were originally designed as legitimate Battery Management System (BMS) tools, allowing fleet operators, financiers, or vehicle owners to monitor charge levels, track location, and remotely immobilize vehicles in cases of loan default or theft. However, the misuse arose when this remote-kill switch capability was exploited by unauthorized actors, including rival financiers, disgruntled individuals, or even pranksters, to disable e-rickshaws belonging to other operators, regardless of legitimate ownership or consent.

Unlike a standard vehicle-tracking app, apps like BAT-BMS, Lossigy, and Epoch-i-ion reportedly retained an always-on API or Bluetooth/cellular link between the e-rickshaw's battery controller and the app's backend. This design flaw effectively turned a fleet-management convenience feature into a safety hazard, since it lacked adequate authentication controls, driver consent verification, or geofencing restrictions to prevent third-party interference.

Security researchers have long flagged that IoT-enabled kill switches in low-cost electric vehicles are particularly vulnerable because manufacturers often prioritize cost and functionality over robust access control, leaving credential leakage or insider misuse as an easy attack vector.

India has a well-established precedent for such interventions: the Ministry of Electronics and Information Technology has previously invoked Section 69A of the Information Technology Act to block applications deemed prejudicial to public safety and order, as seen in the 2020 ban of 59 apps citing security concerns. This incident underscores a growing concern around IoT-enabled remote disablement features embedded in affordable electric vehicles across India's booming e-rickshaw and last-mile mobility sector.

### Recommendations for Fleet Operators 📋
- Enforce multi-factor authentication for any app command capable of remotely disabling a moving vehicle.
- Implement geofencing and speed-based lockouts to prevent shutdown commands while a vehicle is in transit.
- Maintain audit logs of every remote command issued, tied to verified device ownership.
- Conduct third-party security audits of BMS backend APIs before public release.

For more details, [Read full article](https://cybersecuritynews.com/indian-govt-bans-e-rickshaws-apps/)