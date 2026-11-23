---
title: "Presenting at the ACM CCS 2026 Doctoral Symposium"
date: 2026-11-23
layout: post
categories: news
tags: [CCS26, doctoral-symposium, Android, re-hosting, dynamic-analysis, emulation]
img: assets/img/news/2026_11_23/ccs26_venue_sign.jpg
description: "Recap of presenting my PhD research on automated system-level Android re-hosting at the ACM CCS 2026 Doctoral Symposium in The Hague, with poster and presentation slides available for download."
---

Last week, I had the opportunity to attend the [33rd ACM Conference on Computer and Communications Security (CCS 2026)](https://www.sigsac.org/ccs/CCS2026/index.html) in The Hague, Netherlands, and present my PhD research at the **Doctoral Symposium**!

My presentation and poster focused on **"Systematic Security and Privacy Auditing of the Android Ecosystem via Automated System-Level Re-Hosting,"** conducted under the supervision of Prof. Dr. Timo Kehrer (University of Bern), Prof. Dr. Marc Rennhard (ZHAW), and Dr. Bernhard Tellenbach (Armasuisse W+T, Cyber-Defence Campus).

I received a tremendous amount of insightful feedback and thought-provoking questions during both the presentation and the poster session. Discussions around quality assurance for repair-based re-hosting, deterministic image modifications, peripheral simulation, and whether emulated systems behave differently from a security perspective gave me plenty of ideas to carry forward into the next phase of my PhD.

## Publication & Downloads

The extended abstract, **Presentation Slides**, and **Poster** from the symposium are available below:

- **Extended Abstract (ACM DL):** [10.1145/3830454.3846924](https://dl.acm.org/doi/abs/10.1145/3830454.3846924)
- **Presentation Slides (PDF):** [Download Presentation]({{ 'assets/pdf/presentations/2026_11_CCS26_Doctoral_Symposium_Presentation.pdf' | relative_url }})
- **Symposium Poster (PDF):** [Download Poster]({{ 'assets/pdf/presentations/2026_11_CCS26_Doctoral_Symposium_Poster.pdf' | relative_url }})

{% include figure.liquid loading="eager" path="assets/img/news/2026_11_23/ccs26_doctoral_symposium_poster.jpg" title="ACM CCS 2026 Doctoral Symposium Poster" alt="Poster: Systematic Security and Privacy Auditing of the Android Ecosystem via Automated System-Level Re-Hosting" caption="My poster presented at the ACM CCS 2026 Doctoral Symposium (click to zoom)." class="img-fluid rounded z-depth-1" max-height="650px" zoomable=true %}

## Key Takeaways & Research Overview

In my talk, I walked through the motivation, current prototype, and roadmap of my doctoral work:

- **The Supply-Chain Visibility Gap:** Before reaching users, the Android Open Source Project (AOSP) is sequentially modified by silicon vendors, OEMs, carriers, and third parties—resulting in ~27 to 1,000 pre-installed applications per device embedded in read-only partitions. Static analysis alone suffers from high false-positive rates and misses runtime behavior, while hardware-bound dynamic testing does not scale due to OEM-locked bootloaders, device costs, and limited reproducibility.
- **From Structural to Repair-Based Re-Hosting:** Building on our ~30 TB firmware dataset and the [FirmwareDroid](https://firmwaredroid.github.io/) extraction pipeline, I discussed our evolution from policy-based structural re-hosting (v1) toward **repair-based semantic re-hosting (v2)** using Cuttlefish hybrid vendor images. So far, we have successfully re-hosted application-layer partitions (`system.img`, `product.img`, `odm.img`) across devices from ASUS, Nothing, Fairphone, Xiaomi, OnePlus, and OPPO.
- **What's Next:** Looking ahead, I am focusing on advancing repair-based re-hosting, automated peripheral simulation (networking, Wi-Fi, Bluetooth, sensors), and extending the pipeline beyond smartphones to Android TV boxes, Android Automotive, and Android-based IoT devices.

## Conference Highlights & Photos

CCS 2026 in The Hague saw record participation, with over 1,400 in-person attendees and a sold-out conference. The Doctoral Symposium also experienced a record year with 82 submissions (+134% year over year) and 24 accepted papers (29.3% acceptance rate).

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/news/2026_11_23/ccs26_venue_sign.jpg" title="CCS 2026 Venue Sign" alt="Illuminated CCS 2026 letters at the conference venue in The Hague" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/news/2026_11_23/ccs26_participants.jpg" title="ACM CCS 2026 Participants" alt="Slide showing 1,400+ participants at ACM CCS 2026 across Europe, Asia, North America, Oceania, and South America" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/news/2026_11_23/ccs26_doctoral_symposium_stats.jpg" title="Doctoral Symposium Statistics" alt="Slide showing Doctoral Symposium statistics: 82 submissions, 24 accepted, 29.3% acceptance rate" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/news/2026_11_23/ccs26_track_stats.jpg" title="Submissions and Acceptance Rate per Track" alt="Bar and line chart of CCS 2026 submissions and acceptance rates per track (14.4% overall)" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
