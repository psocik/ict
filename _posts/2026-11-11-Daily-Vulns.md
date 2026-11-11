---
title: 2026-11-11 Daily Vulns
date: 2026-11-11
categories: [VULNERABILITIES]
tags: []
---

# NEW:

| CVE            | vendor-product    | description                                                                                                                                                                | metric                | Referenceurl                                                                     | title                                                       | GithubURL                                                                     |                                                                                                                                   |
| -------------- | ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| CVE-2022-27892 | Palantir - Gotham | Palantir Gotham versions prior to 3.22.11.2 included an unauthenticated endpoint that would have allowed an attacker to exhaust the memory of the Gotham dispatch service. | CVSS3.1: 5.3 - MEDIUM | [0](https://github.com/palantir/security-bulletins/blob/main/PLTRSEC-2022-11.md) | Exploitation: noneAutomatable: yesTechnical Impact: partial | Palantir Gotham included an endpoint that would log arbitrary sized payloads. | [github](https://github.com/cisagov/vulnrichment/raw/b01229f77e6b4d21814f208035b7aeabe6f3a6ef/2022%2F27xxx%2FCVE-2022-27892.json) |