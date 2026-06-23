---
title: FFmpeg Fixes PixelSmash Flaw in Widely Used Video Decoder
date: 2026-06-22
categories: [SECURITY]
tags: [FFMPEG,VULNERABILITY,SECURITY,VIDEO]
---

## FFmpeg Fixes PixelSmash Flaw in Widely Used Video Decoder 🚀

A newly disclosed FFmpeg flaw dubbed **'PixelSmash'** could be exploited for remote code execution on Jellyfin servers under certain conditions. It can also trigger a denial-of-service condition in applications like Kodi, Emby, Nextcloud, PhotoPrism, and OBS Studio. The vulnerability is tracked as **CVE-2026-8461** and is a heap out-of-bounds write in the MagicYUV decoder, receiving a high-severity score of **8.8**. This flaw can be leveraged via a malicious video file in **AVI**, **MKV**, or **MOV** format.

### How It Works

Any application that uses **libavcodec**, FFmpeg's core library for video decoding and encoding, is considered vulnerable. However, exploitation for remote code execution (RCE) is possible if the **Address Space Layout Randomization (ASLR)** defense is disabled or by chaining another vulnerability to defeat the protection.

Researchers at software supply-chain security company **JFrog** explain that PixelSmash stems from the way MagicYUV processes slices, independent regions of a video frame that can be decoded separately. The vulnerability is a one-row heap buffer overflow in the MagicYUV decoder's slice handling, caused by an inconsistency between how the frame allocator and the decoder compute chroma plane heights.

### Real-World Impact

JFrog demonstrated that PixelSmash can be used for remote code execution on Jellyfin and Nextcloud instances. They achieved full remote code execution against a Jellyfin media server through its normal media library scan pipeline. The attack path involves downloading a crafted MagicYUV AVI into the media library, which triggers ffprobe for metadata extraction, leading to the exploit firing.

Even when RCE is prevented, the CVE-2026-8461 vulnerability should be sufficient to reliably achieve a denial-of-service (DoS) condition on vulnerable targets.

JFrog discovered PixelSmash and the developer addressed the issue in version **8.1.2**. They warn that PixelSmash has a huge attack surface because the MagicYUV decoder is present in hundreds of projects that trust FFmpeg to handle untrusted input safely, turning the vulnerability into a supply-chain problem.

For more details, [Read full article](https://www.bleepingcomputer.com/news/security/ffmpeg-fixes-pixelsmash-flaw-in-widely-used-video-decoder/)