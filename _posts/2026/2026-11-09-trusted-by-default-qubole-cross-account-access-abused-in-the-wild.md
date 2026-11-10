---
title: Trusted by Default Qubole Cross-Account Access Abused in the Wild
date: 2026-11-09
categories: [SECURITY]
tags: [QUBOLE,AWS,SECURITY,BREACH,IAM]
---

## Trusted by Default: Qubole Cross-Account Access Abused in the Wild

A threat actor exploited IAM credentials from Qubole's AWS account to assume integration roles in customer AWS environments. Working alongside Sentra and Mandiant, Wiz observed this malicious activity occurring between **October 14 and October 26, 2026**. The actor utilized these credentials to access IAM roles that customers had established to trust Qubole's account.

Once inside multiple victim AWS environments, the threat actor engaged in various activities:
- Enumerated resources
- Collected configuration and secrets
- Accessed S3 data
- Validated additional credentials discovered along the way

Sentra identified suspicious activity across several customer environments, recognizing it as a broad supply chain attack, which prompted this investigation.

### Timeline of Events
The first activity observed by Wiz CIRT occurred on **October 14**, when an IP address belonging to Mullvad VPN (`45.83.220.211`) called `AssumeRole` against integration roles in customer environments. This activity originated from AWS account `805246085872`, which is associated with Qubole's platform. The IAM user `AIDA3W7DIFLYOLTK63SFS` was linked to this threat actor, and Wiz CIRT has not observed this IAM user in any other activity.

From **October 15**, most of the activity was traced back to a VPS hosted by OVH (`57.129.54.120`). On **October 18**, the threat actor began using a second IAM user from the same account, `AIDAJYRRH5Y3A7AAJM2HW`, which also carried legitimate Qubole platform traffic. The same day, a second Mullvad address (`185.209.199.73`) assumed integration roles across multiple victim environments in quick succession. Every `AssumeRole` request attributed to the threat actor was successful and included an External ID.

### Actions Taken by the Threat Actor
The threat actor employed role session names that followed a consistent format, starting with the prefix `quiam-`, followed by a suffix describing the actions taken, such as `quiam-enum` and `quiam-scope-full`. Once inside an environment, they broadly enumerated across services, including:
- **Storage and Data:** `ListBuckets`, `ListObjects`, `GetDatabases`, `ListTables`, `DescribeClusters`
- **Compute:** `DescribeInstances`, `DescribeImages`, `DescribeSecurityGroups`, `DescribeVpcs`
- **Databases:** `DescribeDBInstances`, `DescribeDBSnapshots`
- **Identity and Keys:** `ListRoles`, `ListKeys`, `ListAliases`, `DescribeKey`, `GetKeyPolicy`

Additionally, the threat actor targeted common locations for credential storage in AWS. This included listing Lambda functions and calling `GetFunctionConfiguration` on each, which returns function environment variables. They also performed `ListSecrets` followed by `GetSecretValue` from Secrets Manager, and used `DescribeParameters` and `GetParameter` for SSM Parameter Store. The threat actor utilized TruffleHog to test credentials found in victim environments, which belonged to the affected organizations, not the vendor. For AWS, TruffleHog called `GetCallerIdentity` with discovered IAM user access keys, confirming whether a key is valid without needing permissions.

Using the assumed integration roles, the threat actor exfiltrated data from S3.

For more details, you can read the full article here: [Read full article](https://www.wiz.io/blog/qubole-cross-account-access-abused-in-the-wild) 🚀