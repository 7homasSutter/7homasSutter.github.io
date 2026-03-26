---
layout: page
title: FirmwareDroid
description: Automating Android Pre-Installed App Analysis at Scale for Security Research.
img: assets/img/projects/SmartPhoneSky.jpg
importance: 1
category: work
related_publications: false
---

FirmwareDroid is a research project that develops novel methods and tooling to analyze Android firmware at scale. The 
project focuses on automating the end-to-end process of extracting pre-installed (vendor / system) Android applications 
and framework artifacts from device firmware images, preparing them for static and dynamic security analysis, and providing
reproducible pipelines and artifacts for researchers.

### Project goals

- Automate extraction of Android firmware components (system apps, framework libraries, vendor blobs) across many devices and OEM firmware formats.
- Produce normalized artifacts that can be consumed by static-analysis tools (e.g., APK/Suite scanners) and dynamic-analysis environments (e.g., vendor-flavoured emulators).
- Provide robust heuristics and configurable extraction strategies to handle vendor-specific packaging and obfuscation.
- Make datasets and tooling available to the research community to enable reproducible experiments and large-scale studies.

### Publication: FirmwareDroid: Towards Automated Static Analysis of Pre-Installed Android Apps

**Abstract:**
Supply chain attacks are an evolving threat to the IoT and mobile landscape. Recent malware findings have shown that 
even sizeable mobile phone vendors cannot defend their operating systems fully against pre-installed malware. Detecting 
and mitigating malware and software vulnerabilities on Android firmware is a challenging task requiring expertise in 
Android internals, such as customised firmware formats. Moreover, as users cannot choose what software is pre-installed 
on their devices, there is a fundamental lack of transparency and control. To make Android firmware analysis more 
accessible and regain some transparency, we present FirmwareDroid, a novel open-source security framework for Android 
firmware analysis that automates the extraction and analysis of pre-installed software.FirmwareDroid streamlines the
process of software extraction from Android firmware for static security and privacy assessments. With FirmwareDroid, 
we lay the groundwork for researchers to automate the security assessment of Android firmware at scale, and we demonstrated
the capabilities of FirmwareDroid by analysing 5,728 Android firmware samples from various vendors. We analysed 75,141 unique 
pre-installed Android applications to study how common advertising tracker libraries (a piece of software that collects 
user usage data) are used and which permissions pre-installed Android apps inherit. We conclude that 20.53% of all apps 
in our dataset include advertising trackers and that 88.14% of all used permissions are signature-based.

Paper: [https://ieeexplore.ieee.org/document/10172951](https://ieeexplore.ieee.org/document/10172951)

### Personal Notes

FirmwareDroid matters because it addresses a fundamental gap in how we study and defend the Android ecosystem: visibility and 
scale. For years, researchers and practitioners have relied on labor-intensive, ad-hoc methods to inspect firmware and 
pre-installed applications, which limited studies to small, non-representative samples and made replication difficult. FirmwareDroid 
provides a reproducible, automatable pipeline that turns opaque firmware images into analyzable artifacts, enabling systematic 
measurement studies and comparative analyses across vendors, regions, and time.

From a research perspective, this capability unlocks questions that were previously infeasible: How prevalent are certain 
categories of trackers or risky permissions across device families? How do vendor customizations alter attack surfaces? Which 
behaviors are introduced by pre-installed apps that do not appear in Play-distributed apps? By standardising extraction and 
provenance metadata, FirmwareDroid helps ensure results are comparable and reproducible — a crucial property for 
credible empirical security research.

From an engineering and tooling point of view, FirmwareDroid reduces the entry barrier for dynamic and static analyses that 
require real system artifacts. By producing normalized outputs and provenance manifests, it allows downstream tools (scanners, 
emulators, taint analyzers) to operate on realistic inputs without manual pre-processing. This both accelerates experiments and 
helps uncover issues that only manifest in vendor-flavoured environments (e.g., proprietary binaries, vendor services, or OEM-specific permission models).

