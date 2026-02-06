# eCPPTv3 Review: Survival Guide & Methodology

**Author:** Omar Haouari  
**Certification:** eLearnSecurity Certified Professional Penetration Tester (v3)  
**Date:** February 2026

---

## 🎯 Introduction

After earning the **eJPTv2**, I wanted to tackle a certification that accurately simulates a real-world corporate engagement. I chose the **eCPPTv3** because it is a 100% practical, black-box exam that requires deep network pivoting and professional-grade reporting, rather than just capturing flags.

## 📚 The Preparation Path

Rather than relying solely on the provided learning path, I curated a targeted training regimen to bridge the gap between theory and advanced practical application.

### 1. Foundation (INE)
I started by completing the official **eCPPTv3 Learning Path** and the accompanying CTFs on the INE platform. This gave me the baseline methodology for the exam's specific Rules of Engagement.

### 2. Specialization: Active Directory (HTB Academy)
Since v3 is heavy on AD, I paused my general prep to complete the **Active Directory Enumeration & Attacks** module on Hack The Box Academy. This was crucial for understanding:
* LLMNR/NBT-NS Poisoning
* Kerberoasting & AS-REP Roasting
* Domain Privilege Escalation

### 3. Simulated Engagements
I targeted specific labs that mirrored the exam's complexity (multi-step pivoting, AD chains, and web-to-shell exploitation).

| Platform | Lab/Machine | OS | Focus Area |
| :--- | :--- | :--- | :--- |
| **TryHackMe** | **Internal** | Linux | Pivoting & Jenkins Exploitation |
| **TryHackMe** | **Relevant** | Windows | SMB & Client-side Attacks |
| **TryHackMe** | **VulnNet: Roasted** | Windows | Active Directory (Kerberoasting) |
| **TryHackMe** | **VulnNet: Active** | Windows | Full AD Chain (GPO & Lateral Movement) |
| **HackTheBox** | **Overwatch** | Windows | Service Exploitation & AD |
| **HackTheBox** | **Conversor** | Linux | Web & File Processing Exploits |

---

## 🧰 The Toolkit

A carpenter is only as good as his tools. These were the drivers of my exam success:

| Category | Tools Used |
| :--- | :--- |
| **Web Enumeration** | **WPScan**, **OWASP ZAP**, **Gobuster**. I used these to map out the attack surface and identify vulnerable plugins on CMS targets. |
| **AD & Network Enum** | **BloodHound.py**, **Ldapsearch**, **Enum4linux**, **CrackMapExec**. For Kerberos attacks, I relied on **GetUserSPNs.py** and **GetNPUsers.py**. |
| **Lateral Movement** | **Evil-WinRM**, **WMIexec**, **PsExec**, **SMBClient**, **RDPClient**. These were critical for moving between machines once credentials were compromised. |
| **Exploitation & Shells** | **Netcat (nc)**, **Web_Delivery** (Metasploit), **Mshta**. I used living-off-the-land binaries (LOLBins) like mshta for initial access. |
| **PrivEsc & Cracking** | **PowerUp**, **KeePass2John**, **Hashcat**, **John the Ripper**, **Hydra**. |

---

## 💀 The Exam Experience

**The Environment**
The v3 environment is massive. It simulates a realistic enterprise forest, not just a single domain.
* **Complex AD Topology:** Dealing with a **Parent-Child Domain** architecture meant I had to understand trust relationships and enterprise admin privileges, not just local domain admin.
* **Web-Heavy Entry:** The initial footholds relied heavily on Web Application Penetration Testing, specifically targeting **WordPress** servers and custom CMS misconfigurations.
* **Service Exploitation:** I had to exploit specific vulnerable services and hunt for sensitive files left on targets to move laterally.

---
---

## 💡 3 Tips for Future Candidates

1.  **Deep-Dive Active Directory:** Don't just learn the basics. You must master Directory Enumeration (LDAP, SMB) and modern attacks like Kerberoasting/AS-REP Roasting. Understanding the Parent-Child trust relationship is critical.
2.  **Web App Enumeration is Key:** A huge part of the initial access relies on web apps. Focus heavily on WordPress enumeration and identifying vulnerable plugins—standard scans might miss custom vectors.
3.  **Post-Exploitation is Where You Win:** Getting a shell is just step one. You need to be thorough in local file enumeration to find credentials in config files. Extracting hashes and performing privilege escalation (Local to System to Domain Admin) is the core loop of this exam.

---
*Connect with me on [LinkedIn](https://www.linkedin.com/in/omar-haouari-b81628236/)*
