---
title: Refactoring Week 1
description: Refactoring
author: Cheongu Kim
date: 2026-07-13 18:00:00 +0900
categories: [Refactoring]
tags: [Refactoring]
pin: true
math: true
mermaid: true

---

# The History of the OSI 7-Layer Model

## Definition of the OSI Model

The **Open Systems Interconnection (OSI)** model is a standard reference model developed by the **International Organization for Standardization (ISO)**.

It was introduced to standardize network communication among different vendors and resolve interoperability issues between heterogeneous network systems.

---

## Why a Layered Architecture?

### Problems with a Monolithic Architecture

* All networking functions are tightly coupled within a single system.
* Adding or modifying functionality is difficult because changes affect the entire system.
* Troubleshooting and maintenance become more complex.
* Reusing individual components is difficult due to the lack of modularity.

### Benefits of a Layered Architecture

* Each layer has a well-defined responsibility.
* A problem in one layer can be isolated and resolved without affecting the other layers.
* Individual layers can be developed, maintained, or upgraded independently.
* Standardized interfaces improve interoperability between different systems and vendors.

---

## Features of Each Layer

### 1. Application Layer

* Provides network services directly to end-user applications.
* Main protocols and services:

  * HTTP / HTTPS
  * FTP
  * SMTP
  * DNS

---

### 2. Presentation Layer

* Translates data into a standardized format for communication.
* Main functions:

  * Data encoding
  * Data compression
  * Data encryption and decryption

---

### 3. Session Layer

* Establishes, manages, synchronizes, and terminates communication sessions.
* Main functions:

  * Session establishment
  * Session maintenance
  * Synchronization
  * Session termination

---

### 4. Transport Layer

* Provides reliable end-to-end communication between applications using port numbers.
* Main functions:

  * Connection establishment (TCP handshake)
  * Data segmentation and reassembly
  * Flow control
  * Error detection and recovery

---

### 5. Network Layer

* Determines the optimal path for data transmission using IP addresses.
* Main functions:

  * Routing
  * Logical addressing
  * Packet forwarding

---

### 6. Data Link Layer

* Transfers data between devices on the same local network using MAC addresses.
* Main functions:

  * Ethernet
  * VLAN
  * Error detection
  * Frame transmission

---

### 7. Physical Layer

* Converts digital bits into electrical, optical, or radio signals for physical transmission.
* Main functions:

  * Signal encoding
  * Signal transmission
  * Physical media communication

---

# Protocol Data Units (PDUs)

A **Protocol Data Unit (PDU)** is the data format used at each layer of the OSI model.

As data moves down the OSI layers, each layer adds its own header through a process called **encapsulation**. At the receiving end, each layer removes its corresponding header through **decapsulation**.

| OSI Layer                            | Protocol Data Unit (PDU)       |
| ------------------------------------ | ------------------------------ |
| Application / Presentation / Session | Data                           |
| Transport                            | Segment (TCP) / Datagram (UDP) |
| Network                              | Packet                         |
| Data Link                            | Frame                          |
| Physical                             | Bit                            |

