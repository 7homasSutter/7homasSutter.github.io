---
title: "Paper Accepted at ACM CCS 2026 Doctoral Symposium"
date: 2026-09-21
layout: post
categories: news
tags: [publication, CCS26, Android, dynamic-analysis, emulation, doctoral-symposium]
---

My paper, "Systematic Security and Privacy Auditing of the Android Ecosystem via Automated System-Level Re-Hosting," has been accepted at the Doctoral Symposium 
of the [33rd ACM Conference on Computer and Communications Security](https://www.sigsac.org/ccs/CCS2026/index.html) (CCS 2026), held in The Hague, Netherlands.

## Overview
The multi-tiered Android supply chain introduces critical security and privacy challenges. Proprietary vendor firmware frequently carries undocumented data collection practices, over-privileged pre-installed applications, and unpatched vulnerabilities. Traditional dynamic analysis struggles to audit these downstream customizations at scale due to tight hardware coupling and emulator crashes.

This doctoral research proposes an automated system-level re-hosting pipeline designed to decouple proprietary vendor images from physical devices. By pairing semantic dependency resolution with bare-metal ARM64 hardware virtualization, the framework enables high-throughput, dynamic auditing of vendor firmware to uncover systemic supply-chain flaws and runtime data leaks.

This work is conducted by Thomas Sutter under the joint supervision of Prof. Dr. Timo Kehrer (University of Bern), Prof. Dr. Marc Rennhard (Zurich University of Applied Sciences - ZHAW), and Dr. Bernhard Tellenbach (Armasuisse W+T, Cyber-Defence Campus).