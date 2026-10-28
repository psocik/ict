---
title: In a pickle Why every pickle defense in machine learning is bypassed the same way
date: 2026-10-27
categories: [MACHINE LEARNING]
tags: [MACHINE LEARNING,SECURITY,PYTHON,CVE,PICKLE]
---

## In a pickle: Why every pickle defense in machine learning is bypassed the same way

The machine learning (ML) ecosystem recently shipped a series of defenses against malicious model files. PyTorch restricted what its loader will deserialize, Keras added a safe mode, and vendors built scanners. But none of them held up to six documented CVE bypasses. These bypasses, often called "pickles," let a malicious Python data file slip past security scanners undetected. The Sysdig Threat Research Team (TRT) pulled apart every public pickle bypass on record, and a pattern emerged.

Pickle is a built-in Python capability for saving something in memory to file so you can load it back later exactly as it was. Many teams may be pickling and they don't even realize it; `torch.save()` or `joblib` are both pickle. Unlike data formats, `pickle.load()` doesn't parse, it executes. A .pkl file is a sequence of instructions for a small stack-based virtual machine built into CPython, and loading the file means running them. This is not an implementation flaw or a parser bug, but the inherent design. The `__reduce__` method, which allows an object to tell pickle how to reconstruct itself, names a callable and its arguments for pickle to invoke on load. Attacks use pickle exactly as specified, for instance, nominating `os.system` as the callable.

A pickle solves the problem of general object serialization, which requires the precise capability that makes it dangerous. Arbitrary code execution is not a bug in pickle, but a feature. Python's module documentation explicitly warns that the default unpickling behavior "is unacceptable as it permits the unpickler to import and invoke arbitrary code." `torch.save` serializes with pickle, producing .pt, .pth, or .bin files that do not visibly appear as pickles. More than half the models you might download execute code the moment you load them. A survey of 705,991 models on a Hugging Face mirror found PyTorch's .pt, .pth, and .bin accounted for 51.0% of models, with explicit pickle variants adding another 4.1%.

You can't make `pickle.load` both general and safe. Both major frameworks attempted to restrict their loaders, but were bypassed. PyTorch made `torch.load`'s `weights_only` argument default to True in version 2.6 for security. However, in 2.5.1 and earlier, `weights_only=True` was bypassable via CVE-2025-32434, where `_legacy_load` failed to enforce the restricted unpickler. Subsequently, CVE-2026-24747 (Jan 2026, CVSS 8.8) defeats validation with crafted opcodes, leading to code execution, affecting all PyTorch versions before 2.10.0. Keras also faced bypasses; `Lambda` layers execute marshalled Python on load (CVE-2024-3660). Even with `safe_mode=True` as default from 2.13, CVE-2025-9905 demonstrated that loading a legacy .h5 file ignores `safe_mode` without warning.

To read the complete article see: [Read full article](https://webflow.sysdig.com/blog/in-a-pickle-why-every-pickle-defense-in-machine-learning-is-bypassed-the-same-way) 
