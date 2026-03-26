---
layout: page
title: Android Application Layer Re-Hoster
description: A tool to re-host Android applications in a controlled environment for dynamic analysis and testing.
img: assets/img/projects/SmartphoneData.jpg
importance: 1
category: work
related_publications: false
---

{% include figure.liquid loading="eager" path="assets/img/projects/SmartphoneAtoB.jpg" title="Re-Hosting Android's Application Layer" class="img-fluid rounded z-depth-1" %}

Dynamic analysis on Android has long been stuck between a rock and a hard place. On one hand, physical devices 
offer the most authentic environment but are a nightmare to scale and reset. On the other, standard emulators (AOSP) 
are scalable but lack the proprietary vendor components—the "secret sauce" from manufacturers—that real-world apps often rely on.

Today, we are bridging that gap. We’re excited to introduce our research on Systematic Android Re-hosting alongside 
[FMD Re-Hoster](https://github.com/FirmwareDroid/FMD-AECS), a toolkit designed to turn "vendor-flavored" emulators into a scalable, cloud-ready infrastructure.

### The Problem: The "Vendor Gap" in Emulation
Most dynamic analysis relies on the Android Open Source Project (AOSP). However, a real phone isn't just AOSP; 
it’s packed with vendor-specific frameworks, pre-installed services, and proprietary binaries. When you try to 
analyze an app that expects these components in a generic emulator, it often crashes or behaves unexpectedly.

Our work introduces a systematic method to re-host these components. Instead of just running an app, we relocate 
the entire framework and preinstalled software from real device firmware into a fully emulated environment.


**Our Research Highlights**
- Systematic Extraction: We pull proprietary binaries and configurations directly from physical firmware.
- Injection Strategies: We seamlessly integrate those pieces into the AOSP build system.
- High Success Rates: Evaluated on firmware samples from SDK 31–33, our method achieves high boot success, allowing 
for the execution of real-world framework components and proprietary apps.

### Enter FMD-AECS: Scaling the Research
Research is only as good as its utility. To make these re-hosted environments accessible, we built FMD-AECS—a 
comprehensive toolkit for building, deploying, and managing these Android emulators within Docker containers.

**The Architecture:** FMD-AECS isn't just a wrapper; it’s a full-stack infrastructure for Android orchestration:

- Containerized Runtimes: Every emulator runs in a lightweight Docker container.
- Envoy Reverse Proxy: Provides a robust gRPC API to manage multiple instances.
- Interactive Access: Integrated via WebRTC (Coturn), allowing you to interact with the emulator through a browser with low latency.
- Vendor Integration: Directly implements our research by building vendor-flavored images at scale.