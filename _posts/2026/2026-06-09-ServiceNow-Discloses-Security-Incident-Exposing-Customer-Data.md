---
title: ServiceNow Discloses Security Incident Exposing Customer Data
date: 2026-06-09
categories: [SECURITY]
tags: [SERVICENOW,SECURITY,CUSTOMERDATA,API,INCIDENT]
---

## ServiceNow Discloses Security Incident Exposing Customer Data 🚨

ServiceNow is warning about a security incident after attackers exploited an unauthenticated access flaw through a vulnerable API endpoint, allowing them to query data from customer instances. The company quietly warned impacted customers through a support bulletin and direct support cases after detecting "anomalous activity" related to the issue.

On June 5, 2026, ServiceNow applied a security update to hosted customer instances. This update addressed a security issue that could allow an unauthenticated user, in certain circumstances, to gain greater access to ServiceNow instances than intended. ServiceNow confirmed that attackers exploited this flaw to successfully query the customer instance tables.

While ServiceNow has not publicly disclosed technical details about the flaw, administrators discussing the incident on Reddit say the issue appears to be tied to a REST endpoint at '/api/now/related_list_edit/create'. One commenter claimed the endpoint was configured with 'requires_authentication=false', potentially allowing unauthenticated requests to access instance data. The security update released on Friday was allegedly used to set `requires_authentication` to `true`, limiting access to authenticated users only.

Although ServiceNow did not disclose which data was accessed during the attacks, instances commonly store sensitive enterprise information, including IT support tickets, employee records, internal documentation, asset inventories, security incident reports, workflow data, and configuration details for corporate systems and services. The bulletin states the issue primarily impacts customers running the Australia platform release or customers on older releases who made certain configuration changes.

Numerous admins shared indicators of compromise, including API requests from the IP address '51.159.98.241,' advising other administrators to review logs for requests to the vulnerable endpoint. According to the advisory, ServiceNow has now opened support cases with affected customers. If a customer has not received one, they are not believed to be affected by the incident.

Administrators are advised to review ServiceNow logs for requests to /api/now/related_list_edit, particularly from the IP address [REDACTED BY DNB EDITORS FOR GOOGLE FILTERS]. Impacted organizations should review exposed tickets and records for sensitive information, rotate credentials or tokens shared through support workflows, and ensure API logging is enabled. ServiceNow says it is still evaluating whether it will publish a CVE for the issue.

[Read full article](https://www.bleepingcomputer.com/news/security/servicenow-discloses-security-incident-exposing-customer-data/)\n