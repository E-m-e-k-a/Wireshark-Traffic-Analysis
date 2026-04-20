# Wireshark Traffic Analysis

## 📊 Project Overview

Network traffic analysis exercises demonstrating practical understanding of TCP/IP protocols, packet inspection, and network communication patterns using Wireshark. This project documents hands-on packet capture and analysis sessions focusing on protocol behavior, connection establishment, and traffic filtering techniques.

---

## 🎯 Learning Objectives

- Understand TCP three-way handshake mechanism
- Analyze network traffic at packet level
- Apply display filters for targeted analysis
- Identify normal vs suspicious network patterns
- Document network forensics methodology

---

## 🛠️ Tools & Environment

**Analysis Tool:**
- Wireshark (latest version)

**Lab Environment:**
- Kali Linux 2024
- VirtualBox networking (NAT/Bridged)
- Command-line utilities (curl, ping)

---

## 📚 Sessions Completed

### Session 1: TCP Three-Way Handshake Analysis

**Date:** April 11, 2026

**Objective:** Capture and identify TCP connection establishment process

**Methodology:**

1. **Traffic Generation**
   - Used `curl http://example.com` to generate simple HTTP request
   - Single connection for clean packet capture

2. **Packet Capture**
   - Interface: eth1 (internet-connected adapter)
   - Filter: `tcp` (display TCP packets only)
   - Result: 12 TCP packets captured

3. **Analysis**
   - Located TCP three-way handshake sequence
   - Examined TCP flags in packet details
   - Verified SYN → SYN-ACK → ACK pattern

**Key Findings:**

**Packet 1 (SYN):**
- Source Port: 51950
- Destination Port: 80
- Flags: 0x002 (SYN)
- Purpose: Client initiates connection

**Packet 2 (SYN-ACK):**
- Source Port: 80
- Destination Port: 51950
- Flags: 0x012 (SYN, ACK)
- Purpose: Server acknowledges and responds

**Packet 3 (ACK):**
- Source Port: 51950
- Destination Port: 80
- Flags: 0x010 (ACK)
- Purpose: Client confirms connection established


## 🔍 Technical Concepts Demonstrated

### TCP Three-Way Handshake

**Purpose:** Establishes reliable connection before data transmission

**Process:**
1. **SYN (Synchronize)** - Client requests connection
2. **SYN-ACK (Synchronize-Acknowledge)** - Server accepts and acknowledges
3. **ACK (Acknowledge)** - Client confirms receipt

**Security Relevance:**
- Port scanning detection (SYN without completion)
- Connection tracking for firewall rules
- Identifying half-open connections (potential attacks)
- Network troubleshooting (failed handshakes indicate connectivity issues)

---

---

## 🎓 Skills Developed

**Technical Skills:**
- Wireshark interface navigation
- Display filter syntax (`tcp`, `http`, `ip.addr`)
- TCP/IP protocol analysis
- Packet inspection and interpretation
- Network troubleshooting methodology

**Security Analysis:**
- Normal vs anomalous traffic patterns
- Connection establishment verification
- Protocol behavior understanding
- Network forensics fundamentals

---
---

### Session 2: HTTP Traffic Analysis

**Date:** April 20, 2026

**Objective:** Analyze HTTP request and response cycle to understand web traffic communication

**Methodology:**

1. **Traffic Generation**
   - Used `curl http://example.com` to generate HTTP request
   - Single HTTP transaction for clean analysis

2. **Packet Capture**
   - Interface: eth1 (internet-connected adapter)
   - Filter: `http` (display HTTP packets only)
   - Result: Captured HTTP request/response packets

3. **Analysis**
   - Examined HTTP GET request structure
   - Analyzed HTTP 200 OK response
   - Identified request/response headers

**Key Findings:**

**HTTP Request (GET):**
- Method: GET
- Host: example.com
- User-Agent: curl/8.14.1
- Purpose: Client requests webpage from server

**HTTP Response (200 OK):**
- Status Code: 200 (Success)
- Content-Type: text/html
- Purpose: Server delivers requested webpage

**Complete Communication Flow:**
1. TCP Three-Way Handshake (Session 1 concept)
2. HTTP GET Request → Client asks for resource
3. HTTP 200 OK Response → Server delivers resource
4. TCP Connection Termination

**Security Relevance:**
- HTTP traffic is unencrypted (visible in plaintext)
- Can see exactly what's being requested and sent
- Useful for detecting data exfiltration
- Identifying malicious web requests (C2 communication)
- Analyzing suspicious user activity



---
## 📈 Next Steps

**Planned Sessions:**
- Session 3: Advanced filtering techniques
- Session 4: Suspicious traffic identification
- Session 5: Network forensics case study

---

## 🔒 Ethical Notice

All network traffic analysis conducted on:
- Personal lab environment only
- Authorized systems and networks
- Educational purposes
- No unauthorized packet capture

---

## 📞 Contact

**GitHub:** [@E-m-e-k-a](https://github.com/E-m-e-k-a)

**Date:** April 2026

---

**⭐ Building practical network analysis skills for SOC Analyst career path**
