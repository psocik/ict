---
title: AWS to Quick Admins Access Control Issues and Customer Impact
date: 2026-05-13
categories: [SECURITY]
tags: [AWS,QUICK,SECURITY,ACCESS-CONTROL]
---

## AWS to Quick Admins: Access Control Issues and Customer Impact

On May 12, Fog Security disclosed an authorization bypass in Amazon Quick, a BI service. AWS responded, stating that "no customer data was at risk." 🚨

Fog reports that when an Amazon Quick administrator uses **custom permissions** to explicitly deny access to AI Chat Agents, the UI correctly hides the feature. However, the API continued to respond to chat requests from any user in the account who knew how to send them. For instance, a non-admin could ask the agent, "Tell me about mangoes," even when they were supposed to be locked out. 🍋

AWS deployed a fix between March 11 and March 12, eight days after Fog reported it via HackerOne. 

### AWS's Response

AWS classified the severity of this issue as **none** and issued no customer notifications or advisories. After Fog disclosed the HackerOne report, AWS provided a statement saying: "We appreciate Fog Security's coordinated disclosure. This issue was addressed in March 2026. No customer data was at risk and there is no customer action required." 

AWS further commented that the researcher was using the Admin Control capability that no customers were actively using when the server-side validation was absent. Essentially, AWS's defense is that while the access control didn't enforce what was promised, it was acceptable because no real customer had configured it during the time it was ineffective. 🤔

### Conclusion

Amazon Quick's access model is unique: IAM policies, SCPs, and RCPs do not apply. Custom permissions are the only option available. If these don't enforce, nothing else does. A severity rating of **none** on a bypass of the only access control a service offers raises significant concerns about security communication practices.

[Read full article](https://www.theregister.com/paas-and-iaas/2026/05/13/aws-patched-quick-auth-bypass-says-customers-werent-using-control/5240041)