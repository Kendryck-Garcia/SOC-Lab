
---

## 📦 Setup & Deployment

### Step 1: Architecting the SOC Environment

**Objective**: Establish a safe, isolated testing environment

- ✅ Deployed Wazuh OVA as the central SIEM manager
- ✅ Configured Windows 11 as the primary target (Victim)
- ✅ Verified network connectivity between all nodes using `ping` and `ip a`

![Network Architecture](https://github.com/user-attachments/assets/76f4abe9-0fd6-4757-bcec-4cf6e4c6b214)
![Network Verification](https://github.com/user-attachments/assets/1001d5a7-1abe-4401-80e9-aee0632a0b8e)

---

### Step 2: Telemetry & Agent Installation

**Objective**: Gain visibility into target system activity

- ✅ Executed PowerShell deployment script to install Wazuh Agent
- ✅ Linked agent to the central Wazuh manager
- ✅ Verified "Active" status in Wazuh Dashboard
- ✅ (Optional) Installed Windows Sysmon for deeper log visibility

![Agent Installation](https://github.com/user-attachments/assets/0c27fa7f-deab-498d-b859-a5bc3a407ed5)

---

### Step 3: Simulating Attacks (Offensive Operations)

**Objective**: Generate realistic security telemetry through controlled attack scenarios

#### 🔓 Brute Force Attack
- **Tactic**: Password spray attack against RDP using Hydra
- **Goal**: Test detection of credential compromise attempts

![Hydra Setup](https://github.com/user-attachments/assets/647e8cbb-edff-4735-8bc2-4dd8342d7b2a)
![Brute Force Execution](https://github.com/user-attachments/assets/52bcd6b6-e60c-48f6-acfe-3e6f97cf4076)

#### 🔐 Persistence Mechanism
- **Tactic**: Created unauthorized local user account via command line
- **Goal**: Test detection of suspicious account creation

![Unauthorized Account](https://github.com/user-attachments/assets/43449ee4-6e60-48fc-907c-16fca35cd642)
![Account Created](https://github.com/user-attachments/assets/73aaebe8-dd8f-4aeb-ac5c-b7b317001b67)

#### 🔎 Reconnaissance
- **Tactic**: Stealthy network scan to identify open ports
- **Goal**: Test detection of network enumeration activity

![Network Scan](https://github.com/user-attachments/assets/fba4e7ad-2aef-4ed8-9c8c-af2c0c646d62)
![Scan Results](https://github.com/user-attachments/assets/85577bce-2c1f-4bbc-840b-f6a839742556)

---

### Step 4: Incident Analysis & Detection (Defensive Operations)

**Objective**: Monitor, detect, and analyze security incidents

- ✅ Investigated Logon Failure alerts (Event 60122) to identify attacker source IP
- ✅ Documented timeline of unauthorized account creation
- ✅ Analyzed alert severity levels to prioritize incident response

![Wazuh Dashboard Alerts](https://github.com/user-attachments/assets/ed5f64ff-1e48-4b73-8bc8-7f8b254fc4bf)

---

## 🎓 Key Findings & Learnings

### Observations
This lab successfully demonstrated that **attackers leave a clear forensic footprint** through their activities:

- **Brute force attacks** generate distinctive patterns of failed authentication attempts
- **Unauthorized account creation** triggers system event logging
- **Network reconnaissance** can be detected through connection logs and port scanning activity

### Conclusions
The project reinforced critical SOC competencies:
- **Log Management**: Understanding what telemetry matters and why
- **Incident Detection**: Identifying anomalies within normal system noise
- **Threat Analysis**: Correlating multiple events to reconstruct the attack chain
- **Incident Response**: Prioritizing alerts based on severity and impact

---

**Created by**: Kendryck-Garcia  
**Last Updated**: April 2026
