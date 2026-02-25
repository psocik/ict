---
title: Go Library Maintainer Critiques GitHub's Dependabot as a 'Noise Machine'
date: 2026-02-24
categories: [TECHNOLOGY]
tags: [GITHUB,DEPENDABOT,SECURITY,GO,PROGRAMMING]
---

## Go Library Maintainer Critiques GitHub's Dependabot as a 'Noise Machine' 🚨

A Go library maintainer has urged developers to turn off GitHub's Dependabot, arguing that false positives from the dependency-scanning tool "reduce security by causing alert fatigue." Filippo Valsorda, formerly in charge of the Go security team at Google, now maintains the cryptography packages in the Go standard library. Last week, he published a security fix for one of the libraries he maintains, [filippo.io/edwards25519](https://filippo.io/edwards25519), which is used for EdDSA (Edwards-curve Digital Signature Algorithm) cryptography.

As a result, Dependabot "opened thousands of PRs [pull requests] against unaffected repositories," Valsorda said. The automated process also generated what Valsorda called "a nonsensical made up CVSS [Common Vulnerability Scoring System] v4 score" and warned developers of a 73 percent compatibility score, implying a 27 percent chance of breaking code, even though the fix was "one line in the method no one uses." The most common reason for depending on this library is that a Go MySQL database driver uses it, but since this does not call the amended function (MultiScalarMult), it is not affected.

Valsorda called the GitHub tool a "noise machine" and recommended turning it off. 🔕

Dependabot started as a third-party tool, which GitHub acquired in May 2019. It uses data from the GitHub Advisory Database to automate pull requests and security alerts in repositories that include dependencies on the listed vulnerabilities. Valsorda said Dependabot was both too noisy and insufficient for its purpose. It is too noisy because it appears to check only whether the dependency exists, not whether the impacted function or code path is actually used. "Any decent vulnerability scanner will at the very least filter based on the package," he said.

Further, he recommended using a static analysis tool like govulncheck (in the case of Go vulnerabilities) that will identify the reachability of the flaw. Despite its noise, Dependabot is also insufficient, Valsorda added, because a real vulnerability "should be assessed for its impact: production might need to be updated, secrets rotated, users notified." If developers rely on Dependabot to manage dependency vulnerabilities, they are not doing enough.

Valsorda also dislikes another feature of Dependabot: keeping dependencies up to date with the latest versions. He argues that dependencies should be updated according to the project's development cycle, not whenever a new version of a package appears. Updating quickly also carries some risk if malicious code has been added to a package. He recommends testing updated packages in a sandboxed continuous integration process to discover any problems without updating production code. 

A Hacker News discussion on the subject found widespread agreement with Valsorda's points, though customers may not understand the nuances. There is also a view that the value of Dependabot varies according to what would get put in its place. In cases where resources are limited and there is no obvious alternative, Dependabot is likely better than ignoring the problem it addresses.

[Read full article](https://www.theregister.com/2026/02/24/github_dependabot_noise_machine/)