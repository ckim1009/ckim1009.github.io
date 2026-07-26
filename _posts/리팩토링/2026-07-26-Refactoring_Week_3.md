---
title: Refactoring Week 3
description: Refactoring
author: Cheongu Kim
date: 2026-07-26 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---

## 1. Firewall

#### Definition
- A security device that monitors and controls incoming and outgoing network traffic based on predefined security rules.

#### Features
- Controls inbound and outbound traffic based on IP addresses, ports, and protocols.
- Typically deployed at the boundary between internal and external networks.
- Serves as the first line of defense against unauthorized access.

#### Limitations
- Cannot detect malicious content within allowed traffic.
- Cannot prevent attacks originating from inside the network.
- Cannot effectively defend against unknown attacks.

## 2. DoS and DDoS

### Denial of Service (DoS)

#### Definition
- An attack that overwhelms a target server with excessive requests, preventing it from processing legitimate user requests.
- Typically launched from a single attacker or device.

#### Features
- Uses a Botnet, a network of compromised devices controlled by an attacker.
- Consumes server resources such as CPU, memory, or network bandwidth.

### Distributed Denial of Service (DDoS)

#### Definition
- An attack in which multiple compromised devices simultaneously send massive amounts of traffic to overwhelm a target service.

#### Features
- Uses a Botnet, a network of compromised devices controlled by an attacker.
- Generates significantly larger traffic than a DoS attack.
- Much more difficult to detect, trace, and mitigate.

### Types of DDoS Attacks

#### SYN Flood
- Exploits the TCP three-way handshake.
- Sends a large number of SYN packets without completing the handshake.
- Exhausts the server's connection table, preventing legitimate users from establishing connections.

#### UDP Flood
- Sends a massive number of UDP packets to consume network bandwidth and server resources.
- Frequently targets DNS, VoIP, and online gaming servers.

#### DNS Amplification
- Uses IP spoofing and open DNS resolvers to amplify attack traffic.
- A small DNS request generates a much larger response, which is redirected to the victim.

## Concept of IDS and IPS

### Intrusion Detection System (IDS)

#### Definition
- A security system that continuously monitors network traffic to detect suspicious activities and alerts administrators.

#### Features
- Analyzes mirrored network packets without interrupting normal traffic.
- Operates in Out-of-Band mode, so it has little impact on network performance.
- Generates alerts and logs when suspicious activities are detected.
- Many companies typically deploy firewalls and IPSs, while IDSs are optional.

### Types of IDS

#### Signature-based IDS
- Detects attacks by comparing traffic against predefined attack signatures (e.g., SQL Injection, Buffer Overflow).
- Provides high detection accuracy for known attacks.
- Cannot effectively detect previously unknown attacks.

#### Anomaly-based IDS
- Learns normal network behavior and detects deviations from the baseline.
- Capable of detecting previously unknown attacks.
- May generate false positives by identifying legitimate traffic as malicious.


### Intrusion Prevention System (IPS)

#### Definition
- A security system that continuously monitors network traffic, detects attacks, and automatically blocks malicious traffic in real time.

#### Features
- Operates Inline, inspecting every packet before it reaches its destination.
- Automatically blocks malicious packets and terminates suspicious sessions.
- Provides real-time protection against network attacks.

### Comparison between IDS and IPS

| | IDS | IPS |
|---|---|---|
| Objective | Detect attacks | Detect and block attacks |
| Deployment | Out-of-Band | Inline |
| Pros | Provides detailed visibility into network activities | Automatically blocks attacks in real time |
| Cons | Cannot stop attacks automatically | False positives may block legitimate traffic |


