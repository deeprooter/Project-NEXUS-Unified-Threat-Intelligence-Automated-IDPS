# Project-NEXUS: Unified Threat Intelligence & Automated IDPS
An ISO/SAE 21434-aligned SIEM/SOAR infrastructure deploying automated detection, deep data analytics, and real-time ChatOps mitigation loops using Wazuh, Splunk, and Slack automation.

# SecOps Automated Detection & Mitigation Pipeline

## Project Overview
This project documents the design and implementation of a centralized Security Operations (SecOps) pipeline built to monitor, detect, and mitigate active threats against a self-hosted web application. By pairing Wazuh (Endpoint Detection & Response / SIEM) with Splunk (Advanced Log Analytics) and Slack (ChatOps / Notification Layer), this architecture establishes a resilient defense loop capable of executing automated, active responses against real-world attack vectors.

---

## Introduction
Modern enterprise networks and self-hosted environments face an expanding perimeter of web-facing exposures. Automated brute-force arrays, vulnerability scanning engines, and dictionary-based exploit frameworks constantly search for perimeter vulnerabilities. Traditional passive logging infrastructures lack the agility required to counter these immediate, high-frequency intrusion threats.

Project-NEXUS bridges this operational gap by deploying a resilient, multi-tiered Intrusion Detection and Prevention System (IDPS). By integrating endpoint detection tools with big-data analytics and collaborative workspace triggers, Project-NEXUS transitions a standard network architecture from a defensive posture into an active, self-healing defensive ecosystem.

### Core Objectives
*   **Real-Time Telemetry Processing:** Continuously monitor systems to capture indicators of compromise (IoCs) and application failure streams.
*   **Automated Edge Mitigation:** Execute sub-second local active responses to block source attackers at the network firewall layer.
*   **Centralized Security Analytics:** Aggregate high-fidelity security data for deep search analytics, multi-vector correlation, and visual dashboard metrics.
*   **ChatOps Operational Visibility:** Stream security alarms to administrators over messaging channels to streamline incident assessment and response workflows.

---

## Project Structure & Architecture
This repository is organized into distinct functional phases to simplify deployment, verification, and engineering audits. Use the links below to navigate deeper technical implementations:

```text
├── README.md                           # Master Project Introduction & Architecture Overview
├── CONFIGURATION-AND-SETUP.md           # Part 1: Architecture, Installation, & Network Topology
└── DETECTION-AND-RESPONSE.md           # Part 2: Use Cases, Decoders, Validation, & SIEM Analytics
```

### 1. Project Implementation Framework
*   **System Architecture:** High-level blueprint mapping data streams from localized bare-metal servers, hypervisors, and Docker nodes to a dedicated ingestion pipeline.
*   **Technology Stack:** Core infrastructure specifications highlighting platform deployments on Ubuntu Server, Wazuh XDR managers, Splunk Enterprise indices, and secure Cloudflare reverse-proxy tunnels.
*   **Homelab Network Topology:** A comprehensive network diagram illustrating boundaries between demilitarized zones (DMZ), internal VLAN nodes, and the security management plane.

### 2. Detection & Response Playbooks
*   **Custom Parsing Rulesets:** Production XML decoders engineered to capture and tokenize application authentication faults in real time.
*   **Automated Security Workflows:** Mermaid sequence diagrams outlining the lifecycle of an alert—from initial edge log ingestion to state-engine correlation and Active Response firewall remediation.
*   **SIEM Analytics Integration:** Advanced Splunk Search Processing Language (SPL) threat hunting queries designed for behavioral tracing and statistical attacker profiling.
*   **ChatOps Orchestration Layer:** Native webhook structures funneling high-priority threat alerts directly into dedicated Slack and GitHub channels.


[![Your GitHub stats](https://vercel.app)](https://github.com/deeprooter/Project-NEXUS-Unified-Threat-Intelligence-Automated-IDPS/tree/main)

<!-- Replace 'your-username' with your actual GitHub profile name -->

<!-- [![Your GitHub stats](https://vercel.app)](https://github.com/deeprooter/) -->
