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



Dynamic analysis on Android has long been stuck between a rock and a hard place. On one hand, physical devices offer the most authentic testing environment, but they are an absolute nightmare to scale and reset for automated pipelines. On the other hand, standard Android Open Source Project (AOSP) emulators provide excellent scalability but completely lack the proprietary vendor components that real-world applications rely on. My colleagues at the University of Bern, ZHAW, and Armasuisse and I recognized that bridging this "vendor gap" was essential for the future of mobile security research. Today, we are excited to introduce our systematic Android re-hosting methodology alongside FMD Re-Hoster, a toolkit designed to turn vendor-flavored emulators into a scalable, cloud-ready infrastructure.  

The core motivation behind our research stems from the severe fragmentation of the Android ecosystem. Device manufacturers consistently modify core system components, such as the application framework and the central Zygote process, while integrating proprietary pre-installed applications. When security analysts attempt to run these vendor-specific applications inside a generic AOSP emulator, the apps typically crash or exhibit altered behavior due to missing dependencies and strict security policies. Historically, achieving deep dynamic analysis required rooting physical smartphones, a process that is costly, heterogeneous, and completely impractical for large-scale, high-throughput firmware analysis. We needed a way to conduct vendor-specific dynamic analysis without being tethered to physical hardware.  

To overcome these limitations, we developed a systematic re-hosting method that relocates the entire Android framework and pre-installed software from real device firmware directly into a fully emulated environment. Instead of merely attempting to run an isolated app, our approach extracts essential application-layer files, native libraries, and static assets from physical ARM firmware images. We then integrate these proprietary pieces directly into the AOSP build system using a combination of tailored pre-build and post-build injection strategies. This process required us to engineer solutions for several complex Android security mechanisms, including bypassing read-only partition restrictions, resolving deep native-library dependencies, and handling the dual-signing requirements of APEX modules. By dynamically generating AOSP-compatible build modules, we successfully produce vendor-flavored emulator images that preserve system integrity while running custom OEM code.  

We rigorously evaluated our baseline injection strategy on an extensive dataset of 184 distinct firmware samples spanning Android SDK versions 31 through 33. The results demonstrated exceptionally high build and boot success rates across multiple major device manufacturers. Our framework successfully re-hosted key application-layer components, allowing the modified Zygote process and vendor-specific Java frameworks to initialize correctly within an ARM-compatible emulator. While we documented some residual failures caused by aggressive device-protection checks or emulator platform constraints, our modular design ensures that researchers can extend injection strategies to support particularly stubborn firmware.  

While we are incredibly proud of the foundation we have built, it is important to emphasize that our re-hosting framework and the FMD-AECS toolkit remain research prototypes and are not yet ready for plug-and-play production use. Our primary goal was to prove the feasibility of vendor-agnostic re-hosting and to establish a reproducible baseline for the academic and mobile security communities. Because the Android ecosystem is vastly fragmented, users deploying this infrastructure in its current state may encounter rough edges, unresolved native dependencies, or unhandled edge cases when attempting to emulate heavily customized proprietary firmware. We view this release as a crucial first step toward closing the emulation gap, and we actively welcome contributions, bug reports, and pull requests from the community to help mature this experimental platform into a robust, production-grade tool.

Research methodologies are only as impactful as their practical utility. 

{% include figure.liquid loading="eager" path="assets/img/projects/ReHostingFun.png" title="Re-Hosting Android's Application Layer" class="img-fluid rounded z-depth-1" %}

To transform our re-hosting concept into an accessible reality, we built FMD-AECS, a comprehensive toolkit for building, deploying, and orchestrating these Android emulators within Docker containers. Rather than relying on simple wrapper scripts, FMD-AECS serves as a full-stack infrastructure tailored for heavy-duty system orchestration. Every emulator is isolated within a lightweight container to ensure clean, reproducible states for every single dynamic analysis run. To manage this infrastructure.

By successfully relocating the Android application layer into a device-independent environment, we are unlocking a scalable, reproducible foundation for dynamic analysis. 

We invite the community to read our full publication, [SANER67736.2026.00053](https://ieeexplore.ieee.org/abstract/document/11576713), and explore the [open-source infrastructure](https://github.com/FirmwareDroid).
