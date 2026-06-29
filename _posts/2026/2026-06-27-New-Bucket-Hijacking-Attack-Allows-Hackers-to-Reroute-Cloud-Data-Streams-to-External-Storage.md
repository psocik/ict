---
title: New Bucket Hijacking Attack Allows Hackers to Reroute Cloud Data Streams to External Storage
date: 2026-06-27
categories: [CYBERSECURITY]
tags: [BUCKET HIJACKING,CLOUD SECURITY,DATA PROTECTION,CYBER ATTACK]
---

## New Bucket Hijacking Attack 🚨

A critical cloud storage attack technique dubbed **"bucket hijacking"** enables threat actors to silently redirect an organization's active cloud data streams, including audit logs and telemetry, into attacker-controlled external storage buckets across major cloud platforms. This technique has been confirmed to affect **Google Cloud**, **Amazon Web Services (AWS)**, and **Microsoft Azure**, with all three providers notified through responsible disclosure.

### How the Attack Works 🔍

The attack exploits a fundamental architectural flaw rooted in the global uniqueness of cloud storage bucket names, where the identity of a destination storage bucket is tied to its name alone, not to a specific account owner. An attacker who compromises a cloud environment and gains bucket deletion permissions can execute the attack in a straightforward sequence:
- Delete the target organization's active storage bucket.
- Immediately recreate a new bucket using the identical name within an attacker-controlled account.

The original data stream, whether a Google Cloud logging sink, AWS S3 replication rule, or Azure Monitor diagnostic export, then continues operating autonomously and begins writing data directly into the attacker's bucket. The attack is particularly dangerous because it is self-sustaining. Once the hijack is complete, the legitimate sink or replication configuration continues to appear valid, generating no obvious error states and triggering no native alerts. Logs, metrics, and sensitive telemetry flow silently into the attacker's environment indefinitely.

### Research Findings 📊

Unit 42 successfully simulated bucket hijacking across multiple services on each major provider. On Google Cloud, this was confirmed on Cloud Logging sinks, Pub/Sub subscriptions, and Storage Transfer Service jobs, requiring `storage.buckets.delete` and `storage.objects.delete` permissions. For AWS, it was confirmed on S3 bucket replication and Amazon Data Firehose pipelines targeting S3 destinations. Azure demonstrated a cross-subscription attack via Azure Monitor diagnostic settings, though limited to same-tenant scope.

### Recommendations for Defense 🛡️

Unit 42 recommends a two-pronged defense strategy combining least-privilege access controls and proactive monitoring. Key recommendations include:
- Restricting deletion permissions (e.g., `storage.buckets.delete`, `DeleteBucket`) to the minimum required administrative roles.
- Enforcing data perimeter controls like AWS Service Control Policies (SCPs) or Google Cloud VPC Service Controls to block writes to buckets outside the trusted organizational boundary.
- Enabling AWS account-regional S3 namespaces to scope bucket names to specific accounts and regions, directly eliminating the hijacking vector.
- Deploying high-priority monitoring alerts for storage bucket deletion API calls, particularly on buckets holding sensitive data.

This research reinforces that shared design philosophies across cloud providers mean a flaw discovered in one ecosystem can serve as a direct blueprint for exploiting another, a reminder for security teams managing multi-cloud environments.

To read the complete article see: [Read full article](https://cybersecuritynews.com/bucket-hijacking-attack/)