---
title: Refactoring Week 4
description: Refactoring
author: Cheongu Kim
date: 2026-08-01 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---

# Classification of Detection Outcomes

## Event

### Definition

- A security event in which malicious or abnormal activity is detected on a system or network.

---

## Correct Detection (True Detection)

### Definition

- A security event is correctly identified and handled by the security analyst.

---

## False Detection (False Positive)

### Definition

- Normal activity is incorrectly classified as malicious, resulting in an unnecessary security alert.

### Impact

- Increases analysts' workload
- May interrupt legitimate services
- Causes alert fatigue

---

## Missed Detection (False Negative)

### Definition

- Malicious activity is incorrectly classified as normal or is not detected at all.

### Impact

- Allows attackers to continue operating undetected
- May lead to data breaches or system compromise
- Generally considered more dangerous than false positives

---

|                        | Detected as Normal  | Detected as Malicious |
| ---------------------- | ------------------- | --------------------- |
| --Actually Normal--    | True Negative (TN)  | False Positive (FP)   |
| --Actually Malicious-- | False Negative (FN) | True Positive (TP)    |

---

# Types of Malware

## 1. Virus

### Definition

- Malware that attaches itself to legitimate executable files and is activated when the user runs the infected file.

### Features

- Requires user interaction to execute
- Infects other executable files
- Cannot spread automatically through the network
- Often modifies or corrupts existing files

### Case: Sality (2003)

- A file-infecting virus
- Spread through P2P file sharing, pirated software, and infected USB drives
- Injected malicious code into legitimate executable files
- Disabled antivirus software and downloaded additional malware

### Countermeasures

- Use antivirus software with updated signatures
- Verify the integrity of executable files
- Keep the operating system and security software up to date
- Avoid downloading software from untrusted sources

---

## 2. Worm

### Definition

- Malware that automatically replicates and spreads across networks without user interaction.

### Features

- Exploits software vulnerabilities in network services
- Can rapidly infect multiple systems
- An infected host becomes a new source of infection
- Often generates massive network traffic

### Case: WannaCry (2017)

- Exploited the SMBv1 vulnerability (EternalBlue)
- Used a buffer overflow vulnerability to execute arbitrary code remotely
- Automatically spread to vulnerable systems
- Encrypted victims' files and demanded ransom payments

### Countermeasures

- Apply security patches promptly
- Disable unnecessary network services (e.g., SMBv1)
- Segment internal networks
- Detect abnormal network traffic using IDS/IPS
- Restrict unnecessary inbound connections

---

## 3. Trojan Horse

### Definition

- Malware disguised as legitimate software that tricks users into executing it.

### Features

- Relies on social engineering rather than self-replication
- Often installs a backdoor for remote access
- Downloads additional malware from a command-and-control (C&C) server
- Frequently serves as the initial stage of advanced cyberattacks

### Case: Emotet (2014)

- Delivered through phishing emails containing malicious Office documents
- Malicious macros executed PowerShell commands
- Downloaded and installed the Emotet payload
- Later installed additional malware such as TrickBot and ransomware

### Countermeasures

- Disable Office macros by default
- Deploy email filtering and sandboxing
- Use behavior-based detection (EDR/XDR)
- Enable Multi-Factor Authentication (MFA)
- Train users to recognize phishing emails

---

## 4. Ransomware

### Definition

- Malware that encrypts files or systems and demands a ransom for decryption.

### Features

- Uses strong encryption algorithms, making recovery extremely difficult without backups
- Modern ransomware often steals sensitive data before encryption (Double Extortion)
- Even if files are decrypted, their integrity cannot be fully guaranteed because attackers may have modified or copied the data
- Commonly targets enterprises, hospitals, and government organizations

### Case: LockBit (2019)

- Initial access through phishing emails, stolen credentials, or vulnerable VPN services
- Escalated privileges to obtain administrator access
- Moved laterally across the internal network
- Exfiltrated sensitive data before encrypting systems

### Countermeasures

- Maintain regular offline backups
- Apply security patches and enable MFA
- Deploy EDR/XDR solutions
- Implement the principle of least privilege
- Monitor lateral movement within the network

---

## 5. Adware

### Definition

- Software that displays unwanted advertisements, often without the user's consent.

### Features

- Displays pop-up advertisements
- Redirects web browsers to advertising websites
- May collect browsing history and user preferences
- Usually bundled with free software

### Case: Fireball (2017)

- Infected over 250 million computers worldwide
- Hijacked web browsers and changed default search engines
- Collected user browsing information for advertising purposes

### Countermeasures

- Install software only from trusted sources
- Keep browsers and extensions up to date
- Remove suspicious browser extensions
- Use reputable anti-malware software

---

## 6. Spyware

### Definition

- Malware that secretly collects sensitive information from a victim without their knowledge.

### Features

- Monitors user activities
- Steals credentials, messages, and browsing history
- May access the microphone, camera, GPS, or files
- Transmits collected information to a command-and-control (C&C) server

### Case: Pegasus (2016)

- Exploited zero-day vulnerabilities in iMessage and WhatsApp
- Installed itself through zero-click attacks without requiring any user interaction
- Escaped the application sandbox by chaining multiple vulnerabilities
- Monitored messages, calls, location, camera, and microphone in real time

### Countermeasures

- Keep the operating system updated
- Install security patches promptly
- Restrict unnecessary application permissions
- Enable Lockdown Mode on supported iOS devices
- Monitor unusual network connections and device behavior
