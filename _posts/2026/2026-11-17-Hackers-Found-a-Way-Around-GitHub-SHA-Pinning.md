---
title: Hackers Found a Way Around GitHub SHA Pinning
date: 2026-11-17
categories: [CYBERSECURITY]
tags: [GITHUB,SECURITY,WEBINAR,SUPPLYCHAIN]
---

## Hackers Found a Way Around GitHub SHA Pinning

**Date Published:** November 17, 2026

Pinning GitHub Actions to an exact version of their code, known as SHA pinning, has become the go-to defense against software supply chain attacks. However, attackers have already found a way around it. In March 2026, hackers hijacked Trivy, a widely used open-source security scanner, and planted malicious code disguised as a security fix from GitHub's official checkout tool. Teams that pinned to it would have passed every check! 🚨

The trick works because GitHub allows copies of a project, called forks, to share code with the original. In May, the same technique targeted the popular actions-cool/issues-helper tool, stealing credentials from the pipelines that ran it. 

### The Lesson Learned
Pinning guarantees that the code won't change, but it doesn't guarantee who wrote it. When the tj-actions/changed-files compromise redirected tags to a malicious commit across more than 23,000 repositories in March 2025, teams that had pinned to SHAs were unaffected. GitHub now allows administrators to enforce pinning as an organization-wide policy. However, a pinned SHA leaves three critical questions unanswered:

- **Authorship:** A SHA doesn't reveal who wrote the commit. Any fork commit can be pinned.
- **Project Membership:** Org-level enforcement checks that a reference is a 40-character SHA, not that the commit actually exists in the upstream project.
- **Runtime:** A Docker-based action pinned to a SHA can still build its image at runtime, pulling in dependencies that were never frozen.

With agentic development pushing more code through CI than ever, each of these gaps is exercised more frequently and reviewed less closely. 

### GitHub's 2026 Actions Security Roadmap
GitHub's 2026 Actions security roadmap, published on March 26, put deterministic dependency locking front and center. Workflow lockfiles entered public preview on October 14 and became generally available on October 28, 2026. They tie every run to recorded commits for actions and their transitive dependencies, even if a tag moves later. That's real progress! 🔒

Locked commits must exist on a branch of the source repository, which mitigates fork-only impostors. However, GitHub's changelog clarifies that locking "does not determine whether the dependency itself is safe." Commit authorship and runtime builds remain open issues; immutable releases only help when maintainers opt in, and lockfiles aren't currently supported on GitHub Enterprise Server.

### Conclusion
Attackers have already demonstrated their ability to disguise a malicious commit as a hardening fix. The next one won't announce itself either. Stay vigilant! ⚠️

[Read full article](https://thehackernews.com/2026/11/hackers-found-way-around-github-sha.html) 
