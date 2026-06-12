---
title: How to Defend ARM64 Cloud Infrastructure from ITScape
date: 2026-06-11
categories: [CYBERSECURITY]
tags: [ARM64,CLOUD,VULNERABILITY,SECURITY]
---

## How to Defend ARM64 Cloud Infrastructure from ITScape

ITScape (CVE-2026-46316) is a guest-to-host escape vulnerability in the vGIC-ITS (Interrupt Translation Service) emulation within KVM/arm64, disclosed by researcher Hyunwoo Kim (V4bel) via oss-security on June 10. The root cause is a race condition in the `vgic_its_invalidate_cache()` function that produces a double-put use-after-free, ultimately enabling host kernel code execution. Because the bug lives entirely within in-kernel KVM rather than QEMU user-space, successful exploitation yields host kernel privilege rather than user-process compromise, making it a direct threat to multi-tenant arm64 cloud environments that accept untrusted guests. 🚀

In scenarios where the attacker lacks guest root, ITScape can be chained with a local privilege escalation. The vulnerability affects kernels from commit `8201d1026caa` (2024-04-25) through `13031fb6b835` (2026-06-05), at which point the patch landed in mainline.

### Detection Rules

Two YARA rules have been developed to detect this threat:
- **ITScape_ExploitConstants_1** targets nine hardcoded 64-bit constants present in the PoC source: kernel symbol addresses (ORDERLY_POWEROFF, POWEROFF_CMD, NEIGH_GC_WORK_FUNC, PMU_FN_LINKED, gadget_rt), an anti-leak sentinel (LEAKLEAD), and the three packed u64 values that compose the `/bin/touch /ITScape` host command string. All constants are encoded little-endian as they appear in a compiled ARM64 ELF.
- **ITScape_KVM_PrivDrop_1** takes a behavioral approach, targeting a semantically unique instruction sequence in the compiled binary: a `stat(2)` group permission check (`st_mode & 0x6 == 0x6`) on `/dev/kvm` followed immediately by `setgroups(0, NULL)` / `setgid(1000)` / `setuid(1000)` with error-checked `cbnz` branches after each call. Branch offsets and stack frame offsets are wildcarded at the byte and nibble level using ARM64 instruction encoding semantics, making the pattern robust to recompilation while keeping all semantically meaningful immediates as exact matches.

### Recommendations

Defenders running arm64 KVM hosts should prioritize applying the mainline patch at commit `13031fb6b835` and the two companion fixes for CVE-2026-46316. Organizations operating multi-tenant arm64 infrastructure, particularly public cloud providers, should closely evaluate this issue given that exploitation requires only guest kernel privilege and yields host root. Since this represents a new vulnerability class, additional variants and follow-up vulnerabilities are expected, so continued monitoring of the vgic-its code path is warranted even after patching.

[Read full article](https://www.reversinglabs.com/blog/defend-cloud-infrastructure-itscape)