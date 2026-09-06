---
title: Refactoring Week 9
description: Refactoring
author: Cheongu Kim
date: 2026-09-05 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---
# Using Static and Dynamic Analysis Tools

- It is important to clearly understand what each tool is used to identify, so that appropriate analysis results can be derived during the actual analysis process.

- Malware: A malware sample may initially perform behavior A, but over time it may perform behaviors B and C, or it may not perform A at all.

  - Using these tools, it is important to be able to identify changes in the malware's behavior over time.

---

## Static Analysis Tool Practice

### 1. Exeinfo PE

- Analyze whether the file is packed.

### 2. BinText

- Extract human-readable text from the file if it is stored as plain text.
- Check for:
  - IP addresses
  - Port numbers
  - URLs
  - Function calls
- During the dynamic analysis process, trace the collected IP addresses to determine whether the process communicates with those IP addresses.

### 3. PEview

- Used to cross-check the results obtained from the previous steps.
- In this course, we will not perform an in-depth analysis of the file.
- Import functions: Windows built-in functions that can be used to predict the malware's approximate behavior.
- Export functions: Functions customized by the attacker, whose behavior cannot be predicted from the function name alone.

---

## Dynamic Analysis Tool Practice

### Analysis Targets

- Changes to files/registry
- Changes to processes
- Changes to network connections

### 1. Cports

- Provides a user-friendly interface instead of using the `netstat` command.
- Check currently active network connections.

### 2. Process Monitor / Process Explorer / System Explorer

- Can be used to analyze processes themselves, even when the target is not malware.
- Use PID-based filtering to focus only on processes related to the malware.

### 3. Autoruns

- Mainly used to analyze changes in registry-related areas.

### 4. SmartSniff / Wireshark

- Analyze network traffic and packets.
- Track when the malware connects to a malicious intermediary, what it does, and when the connection is terminated.
- Check the flag bits of TCP/UDP packets to determine the connection state.
- Since there can be a large number of packets, filter the traffic to focus only on packets related to the malware.

  - At this point, filter packets related to the IP addresses identified using BinText.
