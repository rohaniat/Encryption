# TLS Handshake Encryption Analysis

This repository provides an in-depth analysis of the TLS handshake for an HTTPS connection to https://www.google.com, captured using Wireshark on a Kali Linux virtual machine. The report details each stage of the handshake, packet information, and verification of encryption.

## Files in this Repository

- **EncryptionReport.pdf**: This document provides the complete analysis of the TLS handshake, including timestamps, IP addresses, port numbers, and encrypted packet verification after the handshake.

## Project Overview

### 1. Introduction
The report analyzes the TLS handshake, focusing on the ClientHello, ServerHello, and Key Exchange messages. It explains the significance of each message and verifies encryption status after the handshake is complete.

### 2. Methodology
**Tools**: Wireshark on a Kali Linux VM  
**Procedure**:
- **Setup**: Ensuring Wireshark and Kali Linux are configured to capture traffic on the correct network interface.
- **Capture**: Filtering the capture to TLS packets to isolate the handshake process.
- **Analysis**: Reviewing ClientHello, ServerHello, and Application Data packets for handshake details and encryption status.

### 3. TLS Handshake Analysis
**Key Messages**:
- **ClientHello**:
  - **Timestamp**: 2024/216 17:38:35
  - **Purpose**: Initiates the handshake and proposes encryption settings to the server.
  - **Source IP/Port**: 10.0.2.15:49640, **Destination IP/Port**: 142.251.41.36:443
- **ServerHello**:
  - **Timestamp**: 2024/216 17:38:35
  - **Purpose**: The server agrees on the encryption settings and sends back its selection.
  - **Source IP/Port**: 142.251.41.36:443, **Destination IP/Port**: 10.0.2.15:49640
- **Key Exchange**:
  - In TLS 1.3, key exchange data is included in the ServerHello via extensions, establishing a shared secret for encryption.

### 4. Packet Information
Each packet provides source and destination IP addresses, port numbers, and the encrypted status of data post-handshake.

### 5. Encryption Verification
After the handshake, packets are encrypted, as confirmed by the "Application Data" packets in the capture. Screenshots included in `EncryptionReport.pdf` demonstrate encrypted packet status.

---

This repository serves as a guide for capturing and analyzing the TLS handshake, providing insights into secure communication using Wireshark and encryption fundamentals.
