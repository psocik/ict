---
title: Attackers Heat French Supermarket Fridges Up to 50°C by Hijacking Danfoss Controllers
date: 2026-10-13
categories: [CYBERSECURITY]
tags: [ATTACKERS,FRENCH,SUPERMARKETS,FRIDGES,HIJACKING,DANFOSS,CONTROLLERS]
---

## Attackers Heat French Supermarket Fridges Up to 50°C by Hijacking Danfoss Controllers

🚨 **Breaking News:** Attackers took remote control of fridges and freezers at hundreds of French supermarkets on the night of October 11, warming them to dangerous temperatures and forcing stores to throw away food. Several retail chains reported the incident, highlighting the vulnerability of their systems.

The attackers accessed the controllers that manage all of a store's refrigeration units, devices manufactured by the Danish company Danfoss. Les Mousquetaires, which owns the Intermarché chain, stated that their fridges and freezers were set to defrost and heated to as much as **50°C**. Intermarché confirmed that affected stores had to discard all compromised products, leading to significant losses.

Thierry Cotillard, head of Les Mousquetaires, expressed concerns over expected losses amounting to **tens of millions of euros** across France. 

### Impacted Stores
- Intermarché and Netto (Les Mousquetaires): At least **300 stores** affected.
- Coopérative U: **80 out of 2,000 stores** impacted.
- Carrefour: **80 supermarkets** hit.
- Monoprix: Approximately **30 stores** affected.

### Government Response
CERT-FR, the French government's computer emergency response team, issued an alert on October 12, acknowledging multiple compromises affecting two Danfoss controller series: the **AK-SM** and **AK-SC**. Vincent Strubel, head of ANSSI (France's national cybersecurity agency), emphasized the urgency of disconnecting these series from the internet or implementing strict access controls.

Danfoss reported that many affected units were older models that no longer receive software or security updates. They identified two specific models: the **AK-SM 800** and the **AK-SC 355**, both of which have been phased out. Some units of the current model, the **AK-SM 800A**, were also compromised due to outdated firmware.

### Recommendations
For older models, CERT-FR and Danfoss recommend:
- Disconnecting or filtering access to the controllers.
- Keeping the firmware of the current AK-SM 800A model up to date, with the latest package being **5.3.x** as of October 13.

CERT-FR's instructions for all AK-SM and AK-SC controllers include:
1. Disconnect or filter access.
2. Limit network access to trusted IP addresses.
3. Perform a factory reset and apply all available security fixes.
4. Change device secrets such as passwords.
5. Check existing accounts.
6. Completely reconfigure the device.

For those with the AK-SM 800 and AK-SC 355 models, the third step offers no new fixes since Danfoss no longer issues updates for these devices.

For more details, visit the full article: [Read full article](https://thehackernews.com/2026/10/attackers-heat-french-supermarket.html)\n