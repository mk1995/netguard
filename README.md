# NetGuard AI - Android Security, Network Discovery & IR Diagnostic Lab

NetGuard AI is a high-performance, edge-computing network security and hardware diagnostic utility built for Android. Designed using modern Android development practices (MVVM, Kotlin Coroutines, Jetpack Compose, and Material Design 3), NetGuard AI acts as a Swiss-army knife for cybersecurity students, network administrators, and IoT device auditors.

This document serves as both a development guide and a **Play Store Publication Kit** containing required disclosures, Store Listing assets, and metadata to guarantee a successful and policy-compliant release on Google Play.

---

`Audit IoT security, discover network devices, analyze Wi-Fi & replay IR signals.`

NetGuard AI is a comprehensive local network discovery, IoT vulnerability auditor, and hardware signal diagnostic laboratory designed for security enthusiasts, sysadmins, and smart home specialists. 

Perform deeply informative subnet scans, parse wireless environments, evaluate IP camera streams, audit IoT firmware endpoints, and diagnose Consumer Infrared (IR) signals—all securely from your Android device.

⚠️ This application is strictly an educational tool and diagnostic aid. It requires explicit user consent before performing any active diagnostics or transmission, does not exploit systems, and serves is to identify vulnerabilities to help protect your home network.

=== KEY DIAGNOSTIC POWERHOUSES ===

1. ADVANCED LOCAL SUBNET DISCOVERY
• Employs high-speed ARP sweeps, SSDP, and mDNS multicast service lookups.
• Lists all active nodes: IP addresses, physical MAC addresses, OUI manufacturer footprints, and hostname identities.

2. IOT & IP CAMERA AUDIT LAB (Lab 7)
• Evaluates unauthenticated legacy streams and common RTSP exposure risks (Port 554).
• Scans common CGI configuration exposure paths (e.g., /cgi-bin/snapshot.cgi, /tmpfs/auto.jpg) for major surveillance vendors.
• Educational context references for known old vulnerabilities (CVE-2017-15222, CVE-2021-33044, CVE-2018-9995) with comprehensive remediation guides.
• Requires explicit active confirmation dialogs before diagnostic sweeps.

3. SMART TV & IPTV AUDITOR (Lab 6)
• Analyzes local DLNA/UPnP rendering endpoints, Chromecast setup metadata leaks, and IPTV playlist integrity exposures.
• Explains raw TV commands protocol issues in depth.

4. INFRARED (IR) DIAGNOSTIC LAB
• Interfaces directly with internal ConsumerIrManager infrared blaster hardware.
• Learn, edit, organize, and inspect raw infrared command packets (TV, Air Conditioners, Garage receivers).
• Built-in database of universal raw pulses and custom carrier signal editors to debug legacy appliances.

5. WI-FI QUALITY & CHANNEL OVERVIEW
• Graphs overlapping channels, analyzes SSIDs, metrics signal strength, and diagnoses dead zones.

6. SECURE LOCAL DEEP VPN AUDITOR
• Leverages an internal Android VpnService loopback interface (does not connect to external servers) block to intercept local outbound packets.
• Diagnoses raw plaintext streams (HTTP, RTSP) leaking your credentials in real-time.

7. COMPREHENSIVE COMPLIANCE & SCORING
• Computes your overall Subnet Defensibility Rating.
• Generates high-fidelity HTML and PDF audit sheets to export and hard-harden your configuration interfaces.


## 📐 Technical Architecture Stack

NetGuard AI is written fully in **100% Kotlin** and adheres strictly to robust professional standards:

- **UI & Layout:** Declarative Jetpack Compose (Material Design 3 with an immersive dark theme).
- **Architecture Model:** Model-View-ViewModel (MVVM) driving UI state securely with cold and hot Kotlin flows (`StateFlow` and `SharedFlow`).
- **Local Persistence:** Room SQL Database preserving device fingerprints, captured IR command arrays, and historized diagnostic runs.
- **Multitasking Concurrency:** Structured Kotlin Coroutines (`Dispatchers.IO` for socket sweeps and `Dispatchers.Default` for OUI calculation arrays).
- **Built-in Security:** Active rate-limiting policies, passive-only discovery mode selectors, and secure state handling.

---

## 🔒 Crucial Android Permissions & Play Store Disclosures

To pass Google Play Policy reviews successfully, your console listing must declare the following permissions and show interactive safety dialogs to users inside the app (which NetGuard AI has fully implemented):

### 1. `ACCESS_FINE_LOCATION` & `ACCESS_COARSE_LOCATION`
*   **Why it's needed:** Android operating system rules bundle SSID and BSSID scanning under location permissions. The app does NOT track your physical location; it only queries wireless environment parameters.
*   **Play Store Disclosure:** *“NetGuard AI accesses Wi-Fi state and location parameters solely to discover local wireless SSID channel grids and analyze network interference in your general environment.”*

### 2. `TRANSMIT_IR` / `android.permission.TRANSMIT_IR`
*   **Why it's needed:** Needed to interface with Android's system `ConsumerIrManager` chip to emit diagnostic TV/AC control commands during infrared blaster audits.

### 3. Loopback `VpnService` Disclosure
*   **Why it's needed:** Powers the locally hosted non-root packet sniffer console. It creates an on-device isolated loopback adapter to parse network layer headers.
*   **Play Store Disclosure:** *“NetGuard AI utilizes a local Android VpnService interface to analyze raw local network packets for dangerous unencrypted traffic (such as HTTP and plain text password exposures). All traffic calculations occur strictly on your physical device. No external connection, server dispatch, or visual data collection occurs.”*

---

## 🛡️ Educational Code of Conduct & Legal Notice
This project is made open-source purely for diagnostic research, network optimization, and smart devices threat auditing. It must never be used to initiate attacks, target third-party networks without written permission, or attempt unauthorized entry. 
The developer assumes no responsibility or liability for how users employ these diagnostic resources.
