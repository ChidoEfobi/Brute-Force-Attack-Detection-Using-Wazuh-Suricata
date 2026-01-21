# Brute-Force Attack Detection Using Wazuh & Suricata (SOC Simulation)
Open-Source SOC | SIEM • IDS • IDR • XDR Simulation


This lab simulates a real-world brute-force attack where a Kali Linux attacker uses Hydra against a Linux host. Suricata detects it via Emerging Threats rules, and Wazuh SIEM correlates alerts, showing how an open-source SOC stack provides full visibility, rule-based detection, and centralized alerting (MITRE T1110).




        [ kalichido ]
      Kali Linux Attacker
       (Hydra Brute Force)
               |
               |  SSH Login Attempts
               v
 ┌─────────────────────────────┐
 |  wazuhagent-suricata        |
 |  Linux Victim Endpoint      |
 |  - Suricata (ET Rules)      |
 |  - Wazuh Agent              |
 └─────────────────────────────┘
               |
               |  Security Events / Alerts
               v
 ┌─────────────────────────────┐
 |  Ubuntuwazserver            |
 |  Wazuh Server (SIEM)        |
 |  - Log Correlation          |
 |  - Alerting & Dashboards   |
 └─────────────────────────────┘


📌 Project Overview
This project demonstrates a realistic SOC detection scenario where a Kali Linux attacker (kalichido) launches a credential brute-force attack using Hydra against a monitored Linux endpoint named wazuhagent-suricata.
The attack is successfully detected, logged, correlated, and visualized using a fully open-source SOC stack consisting of:
    • Wazuh (SIEM / HIDS / IDR)
    • Suricata (NIDS/NIPS)
    • Emerging Threats ruleset
All alerts are centralized and analyzed on the Wazuh SIEM server (Ubuntuwazserver), simulating real-world SOC operations.

🧠 Architecture & Components
🔴 Attacker
    • Hostname: kalichido
    • OS: Kali Linux
    • Tool: Hydra
    • Technique: Brute-force authentication
    • MITRE ATT&CK: T1110 – Brute Force
🔵 Victim
    • Hostname: wazuhagent-suricata
    • OS: Linux (Ubuntu)
    • Security Stack:
        ◦ Wazuh Agent (HIDS)
        ◦ Suricata (NIDS)
    • Role: Endpoint under attack and detection sensor
🟦 SOC / SIEM Server
    • Hostname: Ubuntuwazserver
    • OS: Ubuntu Server
    • Role:
        ◦ Centralized log collection
        ◦ Alert correlation
        ◦ SOC dashboards & visibility

⚔️ Attack Scenario
The attacker uses Hydra to attempt multiple username and password combinations against an exposed authentication service (e.g., SSH). The attack leverages common credential wordlists, mimicking real-world attacker behavior.
This type of activity is commonly observed during:
    • Initial access attempts
    • Password spraying campaigns
    • Automated bot-driven intrusions

🚨 Detection & Telemetry Flow
    1. Hydra generates repeated failed authentication attempts
    2. Suricata inspects live network traffic
    3. Emerging Threats rules detect brute-force behavior
    4. Suricata generates IDS alerts
    5. Wazuh Agent ingests Suricata logs
    6. Logs are forwarded to Ubuntuwazserver
    7. Wazuh correlates, enriches, and visualizes alerts
This provides end-to-end detection visibility, reducing Mean Time to Detect (MTTD).

🧩 What Makes Suricata Intelligent?
Suricata is an open-source Network Intrusion Detection and Prevention System (NIDS/NIPS).
Its intelligence comes from:
    • Signature-based detection
    • Protocol-aware inspection
    • Stateful traffic analysis
    • Threshold-based alerts
    • Emerging Threats rules
⚠️ Important:
Without readable rule files, Suricata cannot detect attacks.
Rules = Intelligence

📊 Role of Wazuh
Wazuh is an open-source SIEM, HIDS, and security analytics platform.
In this simulation, Wazuh:
    • Collects host and network logs
    • Correlates Suricata alerts
    • Applies detection rules
    • Generates SOC-ready alerts
    • Provides SIEM / IDR / XDR-style visibility

🧪 Lab Challenges Encountered (VMware Workstation)
    • ❌ A system cannot be both a Wazuh Server and Wazuh Agent
    • ⚠️ Suricata must be installed on the agent, not the server
    • 🔐 Incorrect rule file permissions prevent detection
    • 🌐 NAT vs Bridged networking impacts traffic visibility
    • ⏱️ Log ingestion timing affects correlation accuracy
These challenges closely reflect real-world SOC deployment constraints.

💥 Real-World Impact
If successful, brute-force attacks can result in:
    • Unauthorized system access
    • Privilege escalation
    • Lateral movement
    • Data exfiltration
    • Ransomware deployment
    • Full environment compromise
Brute force is often the first step in major breaches.

🛡️ Mitigation Strategies
    • Enforce strong password policies
    • Implement account lockout thresholds
    • Enable Multi-Factor Authentication (MFA)
    • Use rate limiting / fail2ban
    • Continuous monitoring with SIEM & IDS
    • Regular Suricata rule updates
    • Purple-team and attack simulations

✅ Key Takeaways
✔ Demonstrates real SOC detection workflow
✔ Combines host-based + network-based telemetry
✔ Uses 100% open-source tools
✔ Maps to MITRE ATT&CK
✔ Recruiter- and interview-ready project

📂 Repository Structure (Suggested)
.
├── README.md
├── diagrams/
│   └── Wazuh_Suricata_Simulation_Diagram.png
├── screenshots/
│   └── wazuh-alerts.png
└── notes/
    └── detection-analysis.md


Detailed step-by-step documentation is available here: 👉 <a href="https://github.com/ChidoEfobi/Brute-Force-Attack-Detection-Using-Wazuh-Suricata/blob/main/Technical%20Reports/Brute%20Force%20Attack%20Report.md">Brute Force Attack Report</a>  

👤 Author
Chido Efobi
Cybersecurity Analyst | SOC | SIEM | Threat Detection
📧 chynornor@yahoo.com
