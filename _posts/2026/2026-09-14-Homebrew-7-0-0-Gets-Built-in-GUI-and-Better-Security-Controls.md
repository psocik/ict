---
title: Homebrew 7.0.0 Gets Built-in GUI and Better Security Controls
date: 2026-09-14
categories: [TECHNOLOGY]
tags: [HOMEBREW,SECURITY,GUI,MACOS]
---

## Homebrew 7.0.0 Released 🚀

Homebrew package manager version 7.0.0 has been released with a built-in vulnerability scanner, stronger security controls, and the full release of its native BrewUI graphical interface. The open-source package manager is primarily used on macOS, allowing users to install software in a similar way to Linux package managers by automatically downloading packages and resolving and installing their dependencies.

### Key Features:
- **Built-in Vulnerability Scanner**: Users can now utilize the vulnerability scanner through a new command (`brew vulns`).
- **Advisory Database**: Homebrew introduces a Homebrew-specific advisory database that tracks vulnerabilities affecting the formula versions and revisions distributed by Homebrew.
- **BrewUI Interface**: The BrewUI official native graphical interface available on macOS 26 "Tahoe" and later makes it easy to browse and search for packages, as well as inspect and manage their dependencies.

### Enhanced Security Measures:
Homebrew 7.0.0 adds a scanning command that can check installed formulae, a specific one, or formulae and their dependencies declared in a Brewfile. For each formula, Homebrew determines the upstream software repository and its version/tag, while for installed packages, it uses information from the available SBOM or derives the source from the formula definition.

The command sends the upstream repository and version/tag to OSV.dev in a batch query, retrieves the vulnerability records, verifies potential matches, applies optional severity filters, and finally checks whether Homebrew has already applied a security patch to this formula.

### Additional Improvements:
Homebrew's new advisory database publishes OSV-format records documenting vulnerabilities affecting Homebrew formula versions and revisions, including fixes that have been backported without changing the upstream software version. Users also benefit from better sandboxing in Homebrew 7.0.0, as access to users' home directories is blocked by default and network-enabled dependency downloads are separated from offline installation.

For more details, check out the full article here: [Read full article](https://www.bleepingcomputer.com/news/security/homebrew-700-gets-built-in-gui-better-security-controls/) 
