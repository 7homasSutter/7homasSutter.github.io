---
title: "Good News: I Passed the OSWE Exam!"
date: 2026-11-04
layout: post
categories: news
tags: [offsec, oswe, exam, certification]
img: assets/img/news/2026_11_04/OSEW-Badge.png
img_fit: contain
description: "Passed the OffSec Web Expert (OSWE) certification exam after a 48-hour white-box web application security assessment—sharing my course preparation, AI study wiki experiments, and exam takeaways."
---

# My OffSec Web Expert Experience

{% include figure.liquid loading="eager" path="assets/img/news/2026_11_04/OSEW-Badge.png" title="OffSec OSWE Certification Badge" alt="OffSec OSWE Certification Badge" class="img-fluid rounded" max-height="280px" %}

So I finally took the time to take the **OffSec Web Expert (OSWE)** exam, and I'm happy to say that I passed! So let's talk about my experience with the OSWE exam and the preparation for it, but first, what is the OSWE exam?

> ##### What is the OSWE?
>
> The **OffSec Web Expert (OSWE)** is an advanced web application security certification by OffSec. Unlike traditional black-box penetration testing, OSWE focuses on white-box security assessments. Candidates audit web application source code across different languages and frameworks to identify complex vulnerabilities, chain them together, and write custom scripts that achieve authentication bypass and remote code execution (RCE) during a proctored 48-hour hands-on exam (followed by 24 hours for reporting).
> {: .block-tip style="font-size: 0.95rem;" }

## Course Preparation

To be honest, I didn't prepare for the OSWE exam as much as I should have. I was busy with work and other commitments, and I didn't have as much time to study as I would have liked.
However, I did manage to go through the course material. Usually, I read the course material every day during my train ride to work, but I never watched any of the videos or did any of the exercises. Except, I did one challenge lab one week before the exam, just to know how to use their remote debugger.
I kind of completed the course material within four weeks, but I had already covered most of the topics years ago. Since I had done most of the PortSwigger Web Academy labs quite some time ago during my master's, I was already familiar with the topics covered in the OSWE course.
However, I did go through the course material, and I found it to be very helpful in refreshing my memory and filling in some gaps in my knowledge. I learned one or two new tricks, but overall it was more of a refresher for me. More surprising for me was that I found out that PortSwigger added some new labs to their Web Academy platform, definitely worth checking out, and I have to say that the labs are very well designed and challenging.
I still have some of the labs that I haven't completed yet, so I hope I will find the time to complete them at some point.

{% include figure.liquid loading="eager" path="assets/img/news/2026_11_04/portswiggerLab.png" title="PortSwigger Web Security Academy Lab Progress" alt="PortSwigger Web Security Academy lab progress showing 85% completion across Apprentice, Practitioner, and Expert levels" caption="My current PortSwigger Web Security Academy lab progress (85% overall)." class="img-fluid rounded z-depth-1" max-height="400px" zoomable=true %}

In preparation for the exam, I wanted to test out if I could use AI to create a local wiki for me, where I could store all my payloads and links to external resources. During the exam, I was not allowed to use AI, but I thought it would be a good idea to have a
local wiki with all the information I needed and some case studies to look for known payloads and how to script them. So I tested Codex (ChatGPT) out and was disappointed by how it would not help me prepare
some Python templates for exploit development; even with DayBreak Blue, it did not work out. I then switched to Antigravity (Google Gemini) and was surprised that the Pro model would kind of create the wiki, but
fill it only with garbage information. I then switched to the
Flash 3.8 model, which is the weaker one, and was surprised that it would create a wiki with some useful payloads and Python script templates. However, it would refuse to create payloads frequently, but I was surprised that I could
often just ask the model to continue to work on it and it just did. Turned out that Google did not like that in the long run, and I got a notification after like months that my account might get suspended because of the content I created with the model.

{% include figure.liquid loading="eager" path="assets/img/news/2026_11_04/GeminiWiki.png" title="Generating a local study wiki with Antigravity (Gemini)" alt="Screenshot of using Antigravity to expand a local XXE wiki page" caption="Using Antigravity (Google Gemini) to generate a local study wiki for XXE payloads and filter bypasses." class="img-fluid rounded z-depth-1" max-height="550px" zoomable=true %}

I guess I will have to find another model for my daily work, because I don't want to risk my account being suspended. But I'm really not a big fan of censoring the capabilities of these AI models when it comes to security use cases.

## Exam Experience

Obviously, I can't go into details of the exam, but I can say that the exam is more or less what you expect from a white-box assessment and that the machines are fair.
The exam was challenging as expected, but for this exam I felt rather confident and relaxed. Maybe it was because this was not my first OffSec exam,
and that I felt the OSED exam was much more challenging than the OSWE exam. I think the OSWE exam is a good balance between being challenging and being fair. The exam is not easy, but it is not impossible either.

The first day went by quickly, and I was able to identify the correct vulnerabilities for the first full compromise, but man, the exploit for the PE took me so much time to develop because I made a ("stupid") mistake in my Python code. I guess
that happens if you work through the exam for like 14 hours with only some small 30-minute breaks. My bad, I guess I should have read more carefully through the course material and copied some of the code snippets from the course material. In a normal engagement, my
exploit script would have taken me like 10 minutes, but since the exam restricts every automated tool, I had to write the exploit from scratch, and I made a mistake in my code that cost me a lot of time.

On the second day, I started with the second machine and found it to be much easier than the first one. I found the PE vector within like 2 hours, and I was able to develop the exploit within the next 1 hour. After that, I went back to my
Python exploit script for the first machine and tried to figure out why it did not work correctly, and after some coffee and double espressos, I finally figured out that I had to add like one line of code to fix the issue. After that, I was able to complete the first machine and submit both flags.

So all that was left was to code the Python exploit for the second machine and to submit the flags. After having the necessary flags, I just started documenting my findings and writing the report. Usually, I write the report findings directly whenever I find a vulnerability, but documenting in a white-box assessment meant that I also had to kind of report my reasoning, which took me more time than in a black-box assessment.

## WEB-404 course not found?

I still think, while the OSWE course is great, there is a huge gap in the content. The OSWE course is focused on web application security, but it doesn't
cover all the topics that are relevant for a web application penetration tester. For instance, nowadays, most enterprise web applications are hosted in the cloud, and the OSWE course doesn't cover cloud security at all.
I think it would be great if OffSec could create a new course that focuses on cloud security for web applications, and then have a new exam for that course. In addition, the OSWE course doesn't cover
some of the more advanced topics in web application security, such as content security policy (CSP), subresource integrity (SRI), and other modern web security features. I think it would be great if Offensive Security
could create a new course that covers these topics, and then have a new exam for that course.

In the meantime, I will continue to study these topics on my own, and I will try to apply them in my work. I think it is important for me to
stay up-to-date with the latest web security trends and techniques, and I will continue to do so even after passing the [OSWE exam]({{ 'assets/pdf/offsec/oswe.pdf' | relative_url }}). Thus, I guess
the next step would be to take the Burp Suite Certified Practitioner (BSCP) exam, which is a great way to validate my skills in web application security, and I'm a big fan of their Web Academy platform. Also, I bought the exam
voucher some years ago during a Black Friday sale, so I guess it's time to take the exam.
