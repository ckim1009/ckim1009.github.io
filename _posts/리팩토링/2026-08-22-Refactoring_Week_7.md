---
title: Refactoring Week 7
description: Refactoring
author: Cheongu Kim
date: 2026-08-22 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---

# Static / Dynamic Analysis

## 1. Static Analysis

- Analyze a file's header, strings, functions, and other internal information without executing the file.

### Precautions

- Although static analysis does not require executing the malicious file, the analysis should be performed in an isolated virtual environment for safety.
- Some malware uses packing, obfuscation, or encryption to hide its code and strings, which can limit the effectiveness of static analysis.

### Analysis Contents

#### Signature Information
- Check the file's digital signature, signer, and certificate information to determine whether the executable was signed by a trusted publisher.

#### Internal Strings
- Extract readable strings such as URLs, IP addresses, domains, file paths, commands, and Registry keys to identify clues about the file's potential functionality.

#### Imported Functions
- Examine functions imported from Windows system libraries and external DLLs to predict the functionality that the program may perform.

#### Exported Functions
- Examine functions exposed by the executable for use by other programs or modules to identify potential functionality defined by the file's creator.

### Related Tools

#### PE View
- Examine the internal structure of PE files.
- Analyze the PE Header, Sections, Entry Point, Import Table, Export Table, and other PE-related information.

#### BinText
- Extract readable ASCII and Unicode strings from executable and binary files.
- Useful for identifying URLs, IP addresses, commands, file paths, Registry keys, and other indicators.


## 2. Dynamic Analysis
- Execute the suspicious file or code in an isolated virtual environment and observe how it affects the system.
- Monitor changes in processes, files, Registry settings, and network communications during execution.

### Precautions

- The results obtained from a single analysis tool cannot guarantee that all malicious behaviors have been identified.
- Basic Windows processes and background activities can generate changes that are unrelated to the analyzed malware and may complicate the analysis.
- Malware may detect virtual machines or analysis environments and alter or hide its behavior.
- Therefore, analysis results should be interpreted by correlating multiple sources of evidence.

### Dynamic Analysis Process

1. Construct an isolated virtual environment
2. Set up analysis tools and record the initial state
3. Execute the suspicious file
4. Monitor system and network changes
5. Compare the system state before and after execution

### Analysis Targets

#### File / Registry Changes

- Identify files and Registry keys that were created, modified, or deleted during the execution of the suspicious file.

#### Process Changes

- Identify newly created or terminated processes and examine their parent-child relationships, command lines, and loaded DLLs.

#### Network Changes

- Identify DNS queries and network connections generated during execution and examine their destination IP addresses, domains, ports, and protocols.


### Related Tools

#### Process Explorer / Process Monitor

- Process Explorer: Monitor running processes, process relationships, loaded DLLs, handles, and command lines.
- Process Monitor: Monitor real-time file system, Registry, process, and other system activities.

#### Autoruns

- Examine programs and components that are automatically executed when Windows starts or a user logs in.
- Useful for identifying persistence mechanisms.

#### Wireshark

- Capture and analyze network packets generated during malware execution.
- Examine DNS queries, IP addresses, ports, protocols, and network communications to identify potential external or C2 connections.