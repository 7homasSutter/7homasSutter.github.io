---
title: "Publication presented at SANER 2026: Relocate and Emulate"
date: 2026-03-25
layout: post
categories: news
tags: [publication, SANER26, Android, dynamic-analysis, emulation]
---

Dynamic analysis of Android’s application layer typically relies on physical devices, limiting scalability and reproducibility. To compensate, we introduce a systematic re-hosting method that relocates the Android framework and pre-installed software from real device firmware into a fully emulated environment. Our approach integrates vendor-specific components into the Android Open Source Project (AOSP) build system using tailored extraction and injection strategies, producing vendor-flavoured emulator images that preserve system integrity and runtime compatibility. This enables dynamic execution of real-world framework and application-layer components, including proprietary binaries and pre-installed apps, across multiple SDK versions.

We evaluate our method on a collection of firmware samples from SDK 31–33. It achieves high build and boot success rates, with residual failures primarily occurring during core-service initialization due to baseline strategy limitations, missing dependencies, device-protection checks, or emulator constraints. However, the modular design allows injection strategies to be extended for specific firmware, supporting broader compatibility and future research on automated, adaptive re-hosting. Though we identified potential for optimization through engineering vendor-specific solutions, our research demonstrates the feasibility of vendor-flavoured emulators for scalable, reproducible dynamic analysis.

More details and supplementary artifacts are available at https://sites.google.com/view/relocate-and-emulate
