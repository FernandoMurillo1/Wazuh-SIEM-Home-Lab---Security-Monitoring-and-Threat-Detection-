# Wazuh SIEM Home Lab — Security Monitoring & Threat Detection

## Overview
Deployed a fully functional Security Information and Event Management (SIEM) 
platform using Wazuh to simulate a SOC monitoring environment. The lab monitors 
a Windows endpoint for real-world attack patterns including brute force attempts, 
fileless malware execution, and unauthorized file system changes.

** Tools Used:** Wazuh SIEM · Ubuntu Server · Windows 10 · PowerShell · 
VirtualBox/Parallels · Syslog · Windows Event Logs

---

## Lab Architecture

The objective of this project was to gain hands-on experience with:

- SIEM deployment
- Endpoint monitoring
- Log analysis
- Threat detection
- Security alert investigation

---

## Lab Architecture

The environment was built using virtual machines to simulate a small enterprise network.

Mac Host
│
├── Ubuntu Server
│   └── Wazuh SIEM
│        • Wazuh Manager
│        • Wazuh Indexer
│        • Wazuh Dashboard
│
└── Windows Endpoint
    └── Wazuh Agent
        • Windows Event Logs
        • PowerShell Monitoring
        • File Integrity Monitoring

---


## Deployment Process

The SIEM lab was deployed using an Ubuntu server as the Wazuh manager.

Steps included:

1. Installing Wazuh manager, indexer, and dashboard
2. Configuring networking between virtual machines
3. Installing the Wazuh agent on the Windows endpoint
4. Registering the agent with the Wazuh server
5. Verifying log ingestion in the Wazuh dashboard

---

## Detection Scenarios

### 1. Authentication Failure Detection (Event ID 4625)
Simulated repeated failed login attempts to trigger brute force detection rules.

**What Wazuh detected:** Multiple Event ID 4625 failures from the same source,
triggering a high-severity alert indicating a potential brute force or 
credential stuffing attack.

![File Integrity Monitoring](https://github.com/FernandoMurillo1/Wazuh-SIEM-Home-Lab---Security-Monitoring-and-Threat-Detection-/blob/33fd1b517a655921d35a08bc58fc9cfbd8263f64/File%20Integrity%20monitoring%20alert.png)

---

### 2. PowerShell Execution Monitoring
Executed suspicious PowerShell commands to simulate fileless malware behavior.

**Command used:**
```powershell
powershell -ExecutionPolicy Bypass -Command "Get-Process"
```

**What Wazuh detected:** Script block logging captured the execution and 
generated an alert. A second alert fired when a new user account was created 
via PowerShell, simulating privilege escalation activity.

![PowerShell Alert](Powershell%20Alert%20User%20created.png)


---

### 3. File Integrity Monitoring (FIM)
Configured Wazuh FIM to monitor critical system directories for unauthorized 
file changes.

**What Wazuh detected:** Rule 554 triggered when a new file was added to a 
monitored directory, simulating malware installation or unauthorized data staging.

![File Integrity Monitoring](https://github.com/FernandoMurillo1/Wazuh-SIEM-Home-Lab---Security-Monitoring-and-Threat-Detection-/blob/33fd1b517a655921d35a08bc58fc9cfbd8263f64/File%20Integrity%20monitoring%20alert.png)

---

### 4. Malware Detection
Simulated malware activity and observed detection on the Wazuh dashboard.

![Malware Detection on Dashboard](https://github.com/FernandoMurillo1/Wazuh-SIEM-Home-Lab---Security-Monitoring-and-Threat-Detection-/blob/09e2d5325beb6cacbcb82374b14379d403760fbe/%20malware%20detection%20on%20the%20Dashboard%20of%20Wazuh.png)


---

## Detection Pipeline

## Detection Workflow

The SIEM processes security events through the following pipeline:

Endpoint Activity  
↓  
Wazuh Agent  
↓  
Wazuh Manager  
↓  
Wazuh Indexer  
↓  
Wazuh Dashboard

Security alerts are generated when events match detection rules.

---

## Skills Demonstrated

This project demonstrates hands-on experience with:

- SIEM deployment
- Endpoint security monitoring
- Log analysis
- Security event correlation
- Threat detection
- SOC alert investigation
- Linux system administration
- Windows event log analysis

## Future Improvements

Planned improvements for this lab include:

- Active Directory attack monitoring
- Malware detection alerts
- Brute force attack simulation
- Threat intelligence integration

---

## Skills Demonstrated
- Wazuh SIEM deployment and agent configuration on Ubuntu and Windows
- Windows Security Event Log analysis (Event IDs 4624, 4625, 4732)
- PowerShell script block logging and fileless malware detection
- File Integrity Monitoring (FIM) rule configuration
- Alert triage and security incident documentation
- Linux server administration and VM network configuration

---

## Author
**Luis Fernando Murillo**  
CompTIA Security+ | CySA+ | Network+ | A+  
[LinkedIn](https://www.linkedin.com/in/luis-murillo1) · 
[GitHub](https://github.com/FernandoMurillo1)

  
