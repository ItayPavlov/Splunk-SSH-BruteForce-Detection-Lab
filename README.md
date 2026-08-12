#  Splunk SIEM: SSH Brute Force Attack Detection & Incident Analysis

##  Executive Summary
This project demonstrates an end-to-end SOC SIEM lab setup using **Splunk Enterprise** deployed in a Docker container on Kali Linux. The lab simulates an SSH Brute Force attack using **Hydra**, captures authentication logs (`auth.log`), and utilizes custom **SPL (Splunk Processing Language)** queries with Regular Expressions (`rex`) to detect, extract, and analyze attack metrics.

---

##  Lab Architecture & Setup
* **Host Environment:** Kali Linux
* **SIEM Platform:** Splunk Enterprise (Docker Container)
* **Attack Vector:** SSH Service (`port 22`)
* **Attack Tool:** Hydra
* **Data Source:** `/var/log/auth.log` (Linux Authentication Logs)

---

##  Attack Simulation (Hydra)
A dictionary attack was launched against the local SSH service using custom password lists:

```bash
hydra -l kali -P ~/passwords.txt ssh://127.0.0.1 -t 4

