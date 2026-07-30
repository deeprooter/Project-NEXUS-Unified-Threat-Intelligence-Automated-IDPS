# Project-NEXUS: Unified-Threat-Intelligence-Automated-IDPS
An ISO/SAE 21434-aligned SIEM/SOAR infrastructure using Wazuh, Splunk, and ChatOps automation.

# SecOps Automated Detection & Mitigation Pipeline

## Project Overview
This project documents the design and implementation of a centralized Security Operations (SecOps) pipeline built to monitor, detect, and mitigate active threats against a self-hosted web application. By pairing Wazuh (Endpoint Detection & Response / SIEM) with Splunk (Advanced Log Analytics) and Slack (ChatOps / Notification Layer), this architecture establishes a resilient defense loop capable of executing automated, active responses against real-world attack vectors.



*   **Telemetry Generation:** Wazuh agents deployed on the web application host collect log data, file integrity metrics, and system telemetry.
*   **Detection & Active Mitigation:** The Wazuh Manager processes events against security rulesets. When malicious activity triggers a critical rule, Wazuh executes an Active Response script locally to block the threat instantly.
*   **Deep Analytics:** Filtered, high-fidelity security alerts are forwarded from Wazuh to Splunk for long-term retention, complex correlation, and visual dashboarding.
*   **ChatOps Notification:** Splunk passes live, critical events directly to a dedicated Slack channel via incoming webhooks, keeping the administrator informed in real time.

# Use Case 1: Brute Force Detection
## Attack Scenario 
An external or internal threat actor attempt to gain unauthorized access to your web hosted resources such as self hosted ```Jellyfin - Home Media Server``` using dictionary attack.

## Detection Mechanism
1. Wazuh agent monitors /var/log/auth.log.
2. Repeated failed login attempts trigger Wazuh Rule 5712 (SSHD brute force).
3. Wazuh generates an alert event.
4. Event is forwarded to Splunk in real-time.

Wazuh Search Query (WSR)




Splunk Search Query (SPL)

index=wazuh rule.id=5712 
| stats count by srcip, user, agent.name 
| where count > 5
