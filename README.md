# Project-NEXUS: Unified-Threat-Intelligence-Automated-IDPS
An ISO/SAE 21434-aligned SIEM/SOAR infrastructure using Wazuh, Splunk, and ChatOps automation.

# SecOps Automated Detection & Mitigation Pipeline

## Project Overview
This project documents the design and implementation of a centralized Security Operations (SecOps) pipeline built to monitor, detect, and mitigate active threats against a self-hosted web application. By pairing Wazuh (Endpoint Detection & Response / SIEM) with Splunk (Advanced Log Analytics) and Slack (ChatOps / Notification Layer), this architecture establishes a resilient defense loop capable of executing automated, active responses against real-world attack vectors.



*   **Telemetry Generation:** Wazuh agents deployed on the web application host collect log data, file integrity metrics, and system telemetry.
*   **Detection & Active Mitigation:** The Wazuh Manager processes events against security rulesets. When malicious activity triggers a critical rule, Wazuh executes an Active Response script locally to block the threat instantly.
*   **Deep Analytics:** Filtered, high-fidelity security alerts are forwarded from Wazuh to Splunk for long-term retention, complex correlation, and visual dashboarding.
*   **ChatOps Notification:** Splunk passes live, critical events directly to a dedicated Slack channel via incoming webhooks, keeping the administrator informed in real time.

## Technology Stack

*   **SIEM / EDR Engine:** ```Wazuh (Manager & Agents)```    https://documentation.wazuh.com/current/getting-started/index.html
*   **Log Aggregation & Analytics:** ```Splunk Enterprise / Splunk Universal Forwarder (activated accounted arequired with Splunk support team)```    https://www.splunk.com/ 
*   **Orchestration / Alerting Layer:** ```Webhooks (Slack ChatOps) (Github)```    https://github.com/wazuh
*   **Target Environment:** ```Linux-based Web Application Hosting Environment```    https://releases.ubuntu.com/jammy/


##  Intial Setup

  <img width="542" height="310" alt="image" src="https://github.com/user-attachments/assets/1fae6212-121e-4e2a-aa40-ebc433a8b990" />

##
*    **Hardware:** ```Intel(R) Core(TM) i7-6920HQ CPU @ 2.90GHz```
*    **Platform OS:** ```Ubuntu 22.04.5 LTS (Jammy Jellyfish)```
*    **Wazuh:** ```WAZUH_VERSION="v4.14.5", WAZUH_REVISION="rc1"```
*    **Wazuh agents a.k.a Telemetry Endpoint:** ```There were few devices in my home network identifed as good candidates for the endpoints```

<img width="596" height="164" alt="Screenshot from 2026-07-22 22-37-00" src="https://github.com/user-attachments/assets/3cb6f528-20cc-43b5-abe6-25437c222bfa" />

  
###  Wazuh Dashboard
<img width="925" height="453" alt="image" src="https://github.com/user-attachments/assets/935195c1-083c-4407-b880-549451166b1e" />

<img width="923" height="443" alt="Wazuh-1" src="https://github.com/user-attachments/assets/c2b18993-e4b9-4e93-ad94-1a10c39d7492" />


##  Extended Setup
Landing on the Wazuh Dashboard was flawless, thanks to the excellent documentation provided by Wazuh. I was able to see the telemetry projected in the Wazuh server, with the built-in, rule-based assessment consolidated under the Wazuh dashboard.

Now I wanted to take this setup to next level where more devices/ resources will be added to the endpoint telemetry with Integration with Splunk.

*    **Orchestration/ SOAR Platform:** ```Splunk Enterprise, Version: 10.4.1 (trial version)```
*    **Web Resources:** ```Self hosted websites with Cloudflared reverse proxy (SSL/TLS supported)```
*    **DMZ Server:** ```Exposing the home network to the Internet
*    **Alerting Layer:** ```Slack integration using webhooks``` https://slack.com/
*    **Telemetry Endponits:** ```Identified additonal endpoints for better log aggregation```

##    Network Topology for my homelab
<img width="1264" height="842" alt="image" src="https://github.com/user-attachments/assets/2f0212ec-97bc-4605-a5de-d1d1da173d5b" />

##    Incident Detection Workflow

```mermaid
graph LR
    A[Live Asset] -->|Telemetry & Logs| B(Wazuh Agent)
    B --> C{Wazuh Manager}
    C -->|Active Response: Intercept & Block Threat| A
    C -->|Webhook Trigger| E[Slack ChatOps Channel]

    subgraph F[Automated Response & Orchestration SOAR]
        D[Splunk Enterprise]
    end

    C -->|High-Fidelity Alerts| D
```






``Threat Mitigation Scenarios Demonstrated``

<!-- Replace 'your-username' with your actual GitHub profile name -->

[![Your GitHub stats](https://vercel.app)](https://github.com/deeprooter)
