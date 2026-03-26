---
layout: page
title: "Uninstallable by Design"
date: 2025-02-19
location: "OWASP Switzerland Chapter Meeting"
permalink: /talks/uninstallable-by-design/
excerpt: "The role of pre-installed apps in Android's security landscape and why some apps cannot be removed easily."
link: "https://www.meetup.com/owaspswitzerland/"
slides: "https://github.com/7homasSutter/public-slides/tree/main"
---

{% include figure.liquid loading="eager" path="../assets/img/projects/OWASP_Flyer.avif" title="OWASP Chapter Meeting" class="img-fluid rounded z-depth-1" %}


**Resources:**
- [Slides](../../assets/pdf/presentations/2025_02_19_OWASP_ChapterSwitzerland.pdf)
- [ERCIM News](https://ercim-news.ercim.eu/en139/special/uninstallable-by-design-the-role-of-pre-installed-apps-in-androids-security-landscape)

I presented our work on the security of pre-installed apps at the OWASP Switzerland Chapter Meeting in February 2025. The 
talk focused on the role of pre-installed apps in Android's security landscape and why some apps cannot be removed easily. 
I discussed the challenges of analysing pre-installed apps, the security implications of bloatware, and 
our framework, FirmwareDroid, which allows for the extraction and analysis of these apps at scale. The talk 
also highlighted our future plans to expand FirmwareDroid's capabilities to include dynamic analysis of pre-installed 
apps without the need for physical devices.

We also published an article in [ERCIM News](https://ercim-news.ercim.eu/en139/special/uninstallable-by-design-the-role-of-pre-installed-apps-in-androids-security-landscape)
that provides an overview of our research on the security of pre-installed apps 
and the development of FirmwareDroid. The article discusses the importance of understanding what data is collected 
on smartphones, the security implications of bloatware, and how FirmwareDroid can help researchers and practitioners 
analyse pre-installed apps to improve mobile security. The article also emphasizes the need for transparency in the 
smartphone industry and how our work contributes to that goal.


## Abstract
The competitive smartphone market is keen to prevent its intellectual property from being analysed by competitors and 
the public. As a result, most smartphones are locked when distributed, and anti-reversing techniques are widely used. 
Consequently, millions of users use smartphones daily without a clear understanding of the software’s functionality 
and purpose. We developed a novel framework, FirmwareDroid, to analyse the security of mobile device firmware.

Nowadays, most smartphones come with a large number of pre-installed mobile apps. For instance, on Android, it is 
normal to find between 150 and 1,000 pre-installed apps for various purposes. Some of these apps are essential for 
the system to operate correctly, while others aim solely to enhance the user experience. Android allows the inclusion 
of third-party apps. Thus, many devices come shipped with apps that some users don’t want or need on their devices, such 
as social media and news apps. These apps are often referred to as “bloatware,” as they unnecessarily bloat the device’s 
operating system and cannot be simply uninstalled by users. The main reason why bloatware on Android cannot be uninstalled 
is a security feature that prevents attackers from modifying system apps on the device.

On Android, the file system where pre-installed apps are stored is read-only, to prevent any modifications to the 
system. This security feature is fundamental and complements other security mechanisms (e.g. Android Verified Boot) to 
prevent Man-At-The-End (MATE) attacks. As most Android devices are effectively locked, users cannot remove pre-installed 
apps from the filesystem without unlocking the bootloader of the device (e.g. by rooting or jailbreaking).

Moreover, the open-source nature of Android allows vendors to modify existing system apps by adding or removing 
functions. As these modifications are mainly closed-source changes, they might introduce bugs that affect the security 
of the device. Recent studies have found several security issues in pre-installed apps and identified privacy 
concerns but could only provide limited insights in terms of analysis methods applied. This demonstrates the need 
for better testing and verification of pre-installed apps on mobile devices.

Undoubtedly, there is a high level of public interest in knowing what data is collected on smartphones and which vendors 
follow good software development and security practices. As a result, in an attempt to restore some transparency, we 
developed a framework called FirmwareDroid that allows the extraction of pre-installed apps from Android firmware. 
FirmwareDroid’s purpose is to automate the security analysis of pre-installed apps for various purposes, such as detecting 
vulnerabilities, identifying malware, or privacy issues. In addition, the project makes the analysis more applicable for 
practitioners and allows researchers to integrate their own testing tools.

With FirmwareDroid, we demonstrated that many pre-installed apps utilise advertising trackers and have a concerning 
number of dangerous privileges. Currently, FirmwareDroid includes several state-of-the-art static analysis tools, and 
the framework allows for the extraction and analysis of apps at scale with its multi-core scanning engine. However, the 
dynamic analysis of pre-installed apps has not been well studied and primarily relies on physical devices for testing, which 
is cost-intensive, does not scale well, and is challenging due to vendors implementing anti-reversing techniques.

As we continue to improve FirmwareDroid, our next critical objective is to expand its capabilities to include dynamic 
analysis of pre-installed apps. This enhancement will significantly strengthen the tools available to researchers, enabling 
them to conduct more comprehensive and detailed studies.

Given the highly fragmented nature of Android, each vendor’s custom modifications to the operating system present unique challenges. 
To address this, we recognise the need for innovative solutions that allow us to test these modifications in real time. 
Understanding what changes have been made and the reasons behind them is not only valuable for advancing research but also 
essential for safeguarding the public’s digital security.

To achieve this, we are developing a solution that facilitates the dynamic testing of Android pre-installed apps without 
the need for physical devices. By leveraging advanced emulation technologies, we aim to create a scalable, cost-effective method 
for analysing these apps in a controlled environment. This development will open new avenues for research and provide greater 
transparency, ultimately contributing to a safer and more secure mobile ecosystem for everyone. Through this project, we hope to 
help both the research community and the public regain some transparency and further strengthen the security of mobile devices. 
FirmwareDroid is open-source and will be continuously developed over the coming years. Contributions to the framework or our research are welcome.

