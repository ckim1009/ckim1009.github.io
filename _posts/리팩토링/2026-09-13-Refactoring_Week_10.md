---
title: Refactoring Week 10
description: Refactoring
author: Cheongu Kim
date: 2026-09-13 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---

# Malware Analysis: `bton02setup.exe`

## Basic Analysis

### VirusTotal Analysis
![VirusTotal Result](/assets/img/Week_10/virustotal_result.png)

More than 50 vendors flagged the sample as suspicious for Trojan or Adware behavior.

![VirusTotal Network Communication](/assets/img/Week_10/virustotal_network_communication.png)
![VirusTotal Activity Summary](/assets/img/Week_10/virustotal_activitysummary.png)

The sample appeared to communicate with `a-ton.co.kr` and attempt to install `DelUS.bat` and `nskSetup.exe`.

---

## Static Analysis

### Exeinfo PE

![Exeinfo PE Result](/assets/img/Week_10/exeinfope_result.png)

The sample was confirmed to be unpacked.

### BinText
![BinText Result](/assets/img/Week_10/bintext_result.png)

`a-ton.co.kr` appeared repeatedly in the extracted strings.

Based on the strings, it was suspected that the sample would install `nskSetup.exe`.

It was also suspected that the sample repeatedly performed file installation and deletion.

---

## Dynamic Analysis

### Analysis Environment

The following dynamic analysis tools were prepared:

- CurrPorts
- Wireshark
- Process Monitor
- Process Explorer
- Autoruns

The analysis was performed five times using VMware snapshots.

For Process Monitor, the following executable files were used as filters:

- `bton02setup.exe`
- `DelUS.bat`
- `nskSetup.exe`

For Wireshark, traffic related to the following domain was filtered:

- `a-ton.co.kr`

### Malware Execution Results

#### 1. Executable File Deletion

The executable file was deleted immediately after execution.

#### 2. Process Monitor Results

`bton02setup.exe`

- Started at 10:09:27
- Terminated at 10:11:17
- No additional activity was observed after termination.

No activity related to `DelUS.bat` or `nskSetup.exe` was detected.

#### 3. Wireshark Results

The sample attempted to communicate with `a-ton.co.kr`, but the DNS query failed. Therefore, the sample was unable to establish communication with the domain.

#### 4. CurrPorts and Autoruns Results

- No changes in startup processes were observed before or after execution.
- No additional network connections were observed before or after execution.

---

## Final Analysis

The sample appeared to attempt to download and execute additional executable files from an external source.

Although it attempted to communicate with the external domain, the communication failed during the DNS query.

As a result, the sample was determined to have failed to perform its intended malicious behavior during the analysis.
