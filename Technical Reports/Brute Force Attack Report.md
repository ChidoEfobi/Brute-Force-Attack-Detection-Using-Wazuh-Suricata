# SOC Lab Environment Overview   : Brute-Force Attack Detection Using Wazuh & Suricata (SOC Simulation)
---
Open-Source SIEM / IDR / XDR-Oriented Detection Scenario
---
Security Monitoring & Testing Tools Used: Hydra, Suricata, Wazuh

By Chido Efobi


---
<a href="https://www.linkedin.com/in/chido-efobi-95691143/"><img src="https://img.shields.io/badge/-LinkedIn-0072b1?&style=for-the-badge&logo=linkedin&logoColor=white" /></a>


# SOC Simulation Architecture & Configurations
<img width="1024" height="1536" alt="SOC Lab Overview" src="https://github.com/user-attachments/assets/35d4fa3e-5e7f-4ad7-a828-7c50f3064a83" />



---
Confirming the status of the wazuh-agent
---
<img width="696" height="376" alt="confirm wazuh agent is active  befor installing suricata 2" src="https://github.com/user-attachments/assets/6f46dc13-6afb-4c5c-91ef-75ce33507cb7" />


---
 Installing Suricata on this wazuh-agent
---
<img width="851" height="405" alt="suricata installation 1" src="https://github.com/user-attachments/assets/3aa19404-06ad-49c9-8fbd-1515ad0fe789" /> #
<img width="854" height="326" alt="suricata installation 2" src="https://github.com/user-attachments/assets/da5b23c9-b1cc-49e7-bd64-4da8d1e222a8" />
<img width="651" height="372" alt="suricata installation 3" src="https://github.com/user-attachments/assets/f78ac7d4-cd49-4971-b7b5-909e0044f49d" />

---
 Updating the yaml file with
 ---
<img width="527" height="32" alt="update suricata yaml file " src="https://github.com/user-attachments/assets/d9e5f8e6-42fa-4c33-90fe-374bcbd801df" />

---
<img width="280" height="152" alt="suricata yaml update 1" src="https://github.com/user-attachments/assets/1992d582-d7df-4050-bcb5-21bd0e47d480" />


---
<img width="373" height="45" alt="suricata yaml update 2" src="https://github.com/user-attachments/assets/45be8488-63fb-4719-8bda-7f5349efde8f" />


---
<img width="401" height="89" alt="suricata yaml update 3" src="https://github.com/user-attachments/assets/77f50ba8-3d70-45a2-8fc3-246ebd6dd90c" />



---
 Updating the ossec file with 
---
<img width="283" height="22" alt="ossec config 1" src="https://github.com/user-attachments/assets/d23a2b97-d6ae-42e3-9ba8-2a1b79f1a800" />

---
<img width="263" height="55" alt="ossec config 2" src="https://github.com/user-attachments/assets/247ae1bf-e865-435d-bbf1-f2b804d5a4cb" />

---
Confirm Suricata is active and running. 
---
<img width="618" height="190" alt="confirm status suricata is now enabled and running " src="https://github.com/user-attachments/assets/6c78a598-1536-46d5-bd7a-87ccdb93289b" />



---
# Attack Execution (Kali Linux Hydra Brute-Force Attack  in Progress)
---
See failed login attempts and one successful login
---
<img width="950" height="466" alt="kali hydra brute force on suricata wazuh agent showing successful username and password" src="https://github.com/user-attachments/assets/a2df4015-9786-434d-b30f-735c45a4620d" />


---

# Wazuh Alert Correlation (Centralized SOC Monitoring)
---
Correlated alerts provide actionable SOC insights
---
Visual: Wazuh dashboard mockup
Alerts table: Source IP, event type, severity, Highlight severity and affected services
Timeline graph: Attack attempts over time
 Add MITRE ATT&CK tag: T1110 – Brute Force screenshots

 ---
<img width="956" height="446" alt="wazuh server brute force output 2" src="https://github.com/user-attachments/assets/fab07ee5-63a1-4020-8ca7-2f63a16de373" />

---
<img width="944" height="470" alt="wazuh server brute force output 3" src="https://github.com/user-attachments/assets/0339cfed-b0ee-49e3-a637-4ef1c787e556" />

---
<img width="944" height="476" alt="wazuh server brute force output 4" src="https://github.com/user-attachments/assets/8210377f-52f8-4e20-8746-fbb9d5849288" />

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


## Custom Detection & Automation

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
## Conclusion
This project demonstrates practical SOC capabilities including detection, analysis, and response using Wazuh SIEM.
