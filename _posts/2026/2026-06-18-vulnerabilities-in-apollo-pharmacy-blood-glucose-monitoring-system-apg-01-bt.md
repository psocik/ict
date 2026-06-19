---
title: Vulnerabilities in Apollo Pharmacy Blood Glucose Monitoring System APG-01 BT
date: 2026-06-18
categories: [HEALTH SECURITY]
tags: [APOLLO,BLOOD GLUCOSE,MONITORING SYSTEM,VULNERABILITIES,HEALTHCARE]
---

## Vulnerabilities in Apollo Pharmacy Blood Glucose Monitoring System APG-01 BT

🚨 **Attention Healthcare Providers!** 🚨

The **Apollo Pharmacy Blood Glucose Monitoring System (Model No. APG-01 BT)** has been identified with critical vulnerabilities that could jeopardize sensitive health-related information. 

### Key Vulnerabilities:
- **CVE-2026-50034**: Attackers within Bluetooth Low Energy (BLE) communication range can intercept wireless traffic, potentially accessing sensitive data such as glucose measurement values. This vulnerability is linked to **CWE-319** (Cleartext Transmission of Sensitive Information).
- **CVE-2026-52866**: This vulnerability allows attackers to monopolize the device's BLE connection slot, preventing legitimate users from connecting. It is associated with **CWE-862** (Missing Authorization).

### Impact:
These vulnerabilities are not remotely exploitable, and no public exploitation has been reported. However, they pose significant risks to users in the **Healthcare and Public Health** sectors in India.

### Recommendations:
CISA advises users to take defensive measures to minimize the risk of exploitation:
- Minimize network exposure for all control system devices.
- Ensure devices are not accessible from the internet.
- Use secure methods for remote access, such as **VPNs**.

For more information, please reach out to Apollo Pharmacy directly or refer to the guidance provided in the [Understanding Bluetooth Technology blog](https://www.CISA.gov/news-events/news/understanding-bluetooth-technology).

Stay safe and secure! 💪

[Read full article](https://www.cisa.gov/news-events/ics-medical-advisories/icsma-26-169-01)