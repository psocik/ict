---
title: Kubernetes 1.37 - New Security Features
date: 2026-08-26
categories: [TECHNOLOGY]
tags: [KUBERNETES,SECURITY,FEATURES,TECHNOLOGY]
---

## Kubernetes 1.37 - New Security Features 🚀

Kubernetes 1.37 has just been released, bringing **67 enhancements**! In terms of security, we've identified **19 changes** with security implications, spanning new security features to mount volumes, improvements on snapshots, authentication by default on webhooks, and more.

### Key Security Changes 🔒

- **#1710**: Speed up recursive SELinux label change. This feature graduates to stable, meaning that this optimization will be applied to all eligible volumes. This may cause issues in rare cases where Pods with different SELinux labels, or with different privilege levels, share the same volume.
- **#5343**: Make nftables the default kube-proxy backend. Users will start seeing a warning in 1.37 if they are currently using iptables as a default. If you are making the transition now, ensure your security tools are covering the new config files.
- A bug where static Pods could reference Secrets or ConfigMaps is now fixed, and the related PreventStaticPodAPIReferences feature gate has been removed under **#140226**.

### New Enhancements 🌟

Among net new security enhancements:
- **#5855**: Add bind mount options (noexec, nodev, nosuid) support on volumeMounts, introducing a new `bindMountOptions` field on `volumeMounts` to define security-related flags. For example, you could add the `noexec` flag to a volume mounted on `/tmp` to stop attackers from running `chmod +x` on malicious files.
- **#6060**: API server authentication to webhooks. This enhancement enables authentication by default (when the feature gate is enabled), using the TokenRequest API.
- **#5936**: Add user fields to atomic write volumes, allowing restricting the ownership of atomic write volumes' files.

### Default Security Features 🔐

Kubernetes 1.37 will enable some security features by default:
- **#2033**: Kubelet-in-userns, aka rootless mode, graduates to Beta with `Default: true`, allowing you to run the kubelet as a non-root user.
- **#5541**: Report last used time on a PVC, introducing a new condition type, Unused, in the PersistentVolumeClaim status conditions.

Review who has access to the API to ensure they are accessing only the data they need. 

For more details, [Read full article](https://webflow.sysdig.com/blog/kubernetes-1-37-new-security-features)