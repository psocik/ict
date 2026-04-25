---
title: PayU Plugin Flaw Allows Account Takeover on 5000 WordPress Sites
date: 2025-06-09
categories: [SECURITY]
tags: [VULNERABILITIES,WORDPRESS,API SECURITY]
---

**Vulnerability in Shipping Cost API Enables Account Hijack**  
The flaw, discovered in version 3.8.5, stems from insecure logic in the `/payu/v1/get-shipping-cost` API route. Attackers can exploit this to impersonate any registered user, including site administrators, without needing login credentials.  
  
Tracked as CVE-2025-31022, the vulnerability is caused by unsafe handling of the `update_cart_data()` function. This function, which is supposed to process order and shipping details, accepts user IDs and sets session data without verifying user identity.  
  
Because the API call only checks for a valid token linked to a hardcoded email – commerce.pro@payu.in – an attacker can generate a valid token using another exposed endpoint, `/payu/v1/generate-user-token`. With that token, they can send a malicious request that grants them control over any existing user account.  
  
To read the complete article see: [InfoSecurity Magazine](https://www.infosecurity-magazine.com/news/payu-plugin-flaw-wordpress-account/)  
