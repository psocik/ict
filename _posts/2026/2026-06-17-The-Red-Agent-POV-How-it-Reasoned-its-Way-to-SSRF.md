---
title: The Red Agent POV How it Reasoned its Way to SSRF
date: 2026-06-17
categories: [SECURITY]
tags: [RED AGENT,SSRF,GCP,CLOUD RUN,VULNERABILITY]
---

## The Red Agent POV: How it Reasoned its Way to SSRF

The Red Agent found a critical multi-step attack chain that allowed SSRF-to-Local-File-Read on GCP Cloud Run. The target was a GCP Cloud Run service: `<redacted>.run.app/f`. It initially identified that the endpoint accepted a `?url=` parameter, and next had to reason about what the application did with that parameter. The Red Agent mimics a real attacker by operating in runs and iterations to uncover complex, logic-driven vulnerabilities. For the GCP Cloud Run service target, it took the Red Agent three runs and roughly 96 requests to find the exploit.

A URL-fetching parameter on a Cloud Run container is a classic SSRF candidate as the application is designed to make outbound requests on behalf of the caller, and Cloud Run containers can access the GCP metadata server to obtain service account tokens and project credentials. So its first move was to test whether it could redirect that fetch to the GCP metadata server at `https://metadata.google.internal/computeMetadata/v1/instance/service-accounts/default/token` - the fastest path to credential theft if it proved to work. However, it didn't - the API validated that the URL pointed to GitHub, blocking the direct metadata pivot. This meant the Red Agent's next technique would need to satisfy a GitHub-bound URL validator.

Since the `?url=` parameter's job is to fetch file contents, the Red Agent hypothesized that the backend ultimately resolves the URL to a local filesystem read, downloading the GitHub file to disk before returning it. It sprayed the `?url=` parameter with traversal variants. It targeted container-specific paths: `/app/main.py` (application entrypoint), `/proc/self/environ` (runtime credentials and environment variables), and `/app/requirements.txt` (dependency manifest) because these are where the high-value data lives in a Cloud Run container. All attempts were blocked - the URL validator wasn't just checking the domain; it was rejecting anything that didn't look like a well-formed GitHub blob URL.

Path traversal proved to be unsuccessful, as the validator wasn't just checking the path component - it was parsing the full URL structure. So the Red Agent shifted its approach: instead of manipulating where the file is read from on disk, it decided to attempt to trick the URL parser into fetching from a different host entirely. If the validator and the fetcher parse the URL differently, a classic parser differential, it could make the validator see "github.com" while the fetcher actually connects to the GCP metadata server (`metadata.google.internal`). But none of these worked; the validator was strict about both the scheme (`https://`) and the resolved hostname. This told the Red Agent something important: the server does make real outbound HTTP requests to whatever host the URL resolves to. The fetch logic isn't faked or proxied - it's a genuine HTTP client. The Red Agent concluded that it just needed a way to satisfy the validator while pointing the fetch somewhere.

[Read full article](https://www.wiz.io/blog/red-agent-pov-ssrf)