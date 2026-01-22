# SOC Lab Environment Overview   : Brute-Force Attack Detection Using Wazuh & Suricata (SOC Simulation)
# Open-Source SIEM / IDR / XDR-Oriented Detection Scenario”

Security Monitoring & Testing Tools Used: Hydra, Suricata, Wazuh

By Chido Efobi
<a href="https://www.linkedin.com/in/chido-efobi-95691143/"><img src="https://img.shields.io/badge/-LinkedIn-0072b1?&style=for-the-badge&logo=linkedin&logoColor=white" /></a>


# SOC Simulation Architecture”
<img width="1024" height="1536" alt="SOC Lab Overview" src="https://github.com/user-attachments/assets/35d4fa3e-5e7f-4ad7-a828-7c50f3064a83" />



---
# Victim Endpoint Setup (Linux Endpoint: Wazuh Agent + Suricata)
- Network and host-based telemetry integrated for SOC visibility
Visual: Wazuh agent running (systemctl status wazuh-agent)
Suricata running with ET rules loaded (suricata -c /etc/suricata/suricata.yaml), “Active ET Rules”

# Wazuh Server Setup (Linux Endpoint: Wazuh manager + Wazuh indexer  + Wazuh dashboard)
- Network and host-based telemetry integrated for SOC visibility
Visual: Wazuh manager + Wazuh indexer  + Wazuh dashboard (systemctl status wazuh-manager, systemctl status wazuh-indexer, systemctl status wazuh-dashboard)
picture of the server with its agents (home page)
---
# Attacker Setup (Kali Linux Attacker Configuration)
- Hydra brute-force attack using common credentials
Visual: Terminal screenshot mockup hydra -l root -P common-passwords.txt ssh://192.168.x.x

---

# Attack Execution (Hydra Brute-Force in Progress)
Visual: Terminal on kali showing failed login attempts with one successful login
Callouts:

---

# Wazuh Alert Correlation (Centralized SOC Monitoring)
- Correlated alerts provide actionable SOC insights
Visual: Wazuh dashboard mockup
Alerts table: Source IP, event type, severity, Highlight severity and affected services
Timeline graph: Attack attempts over time
 Add MITRE ATT&CK tag: T1110 – Brute Force screenshots

---

# Suricata Detection (IDS Detection: Suricata Alerts)
Visual: Suricata alert log screenshot, Show timestamps and source IP

---

# Threat Intelligence & Rules (Rule-Based Detection & Threat Intelligence)
- Community-driven rules enable proactive detection
Heading: 
Visual: EMERGING THREATS rule snippet highlighted,Emphasize pattern recognition (SSH brute-force)

----

# Simulation Challenges (Lab Setup Observations)
Visual: VMware network settings screenshot (NAT vs Bridged), Suricata permissions warning screenshot


## 7.1 Custom Detection & Automation

In addition to Wazuh’s built-in detection rules, a custom Python script was developed to demonstrate
how SOC analysts can automate log analysis and alert generation.

The script analyzed the Linux authentication log (`/var/log/auth.log`) and identified repeated failed
SSH login attempts from the same source IP address. When the number of failed attempts exceeded a
defined threshold, the script generated an alert indicating a possible brute-force attack.

This automation helped to:
- Reduce manual log review
- Quickly identify suspicious behavior
- Correlate multiple failed login events into a single alert
- Support faster incident triage and investigation

The script acted as an additional detection layer, complementing Wazuh SIEM alerts and reinforcing
defense-in-depth within the SOC workflow.

![Python Detection Output](../screenshots/python_detection.png)

---

## Attack Summary & SOC Insights (Response & Mitigation)
- Layered detection improves SOC effectiveness and visibility”
The attacking IP was blocked and preventive controls were implemented.

![Mitigation](../screenshots/mitigation.png)


---
## 9. Conclusion
This project demonstrates practical SOC capabilities including detection, analysis, and response using Wazuh SIEM.
