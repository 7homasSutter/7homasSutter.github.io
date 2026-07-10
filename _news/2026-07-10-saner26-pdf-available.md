---
title: "Paper available: Relocate and Emulate"
date: 2026-07-10
layout: post
categories: news
tags: [publication, SANER26, Android, dynamic-analysis, emulation]
---

{% include figure.liquid loading="eager" path="assets/img/news/2026_07_10/relocate_and_emulate.png" title="Re-Hosting Android's Application Layer" class="img-fluid rounded z-depth-1" %}


Testing vendor-customized Android software has historically required an extensive, expensive inventory of physical
smartphones, severely limiting the scalability and reproducibility of dynamic security analysis. To eliminate this
hardware dependency, my colleagues from the University of Bern, Cyber-Defence Campus, ZHAW, and I introduced our new framework
called Relocate and Emulate at the SANER 2026 conference. Our novel method successfully relocates the Android framework
and pre-installed software from real device firmware into a fully emulated environment, allowing us to run proprietary
binaries device-independently.

The core innovation relies on an automated pipeline we designed to extract application-layer
components directly from real-world ARM firmware and systematically map them into the Android Open Source Project (AOSP)
build system. By leveraging tailored pre-build and post-build injection strategies, the framework handles notoriously
difficult technical hurdles like Android Runtime dependencies, intricate permission whitelisting, and dual-signed APEX
packages. The pipeline then generates "vendor-flavoured" emulator images that fully preserve system integrity and runtime
compatibility. We are particularly proud that this complex injection process adds less than three minutes of computational
overhead to a standard AOSP build, making it highly practical for large-scale production pipelines.

To test the real-world viability of our research prototype, we evaluated a baseline injection strategy against a comprehensive dataset of 184 official firmware samples spanning Android SDK versions 31 to 33. Even in its current experimental stage, the system demonstrated robust performance, achieving consistently high build and boot success rates across multiple major device manufacturers. While we still encounter some residual service crashes—primarily triggered by strict device-protection checks or inherent emulator platform constraints—we intentionally designed the prototype's modular architecture to be highly flexible. This allows researchers and early adopters to easily tailor custom injection rules for stubbornly modified OEM firmware, paving the way for future community-driven improvements to the framework.

For all the technical details, please refer to our full publication: [SANER67736.2026.00053](https://ieeexplore.ieee.org/abstract/document/11576713).
The complete open infrastructure, replication artifacts, and study datasets are fully public and accessible at our official [Relocate
and Emulate Project Page](https://sites.google.com/view/relocate-and-emulate)
