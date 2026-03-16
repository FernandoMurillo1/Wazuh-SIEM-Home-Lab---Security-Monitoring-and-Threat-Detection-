# Wazuh-SIEM-Home-Lab---Security-Monitoring-and-Threat-Detection-
# Wazuh SIEM Security Monitoring Lab

## Overview

This project demonstrates the deployment and configuration of a Security Information and Event Management (SIEM) platform using Wazuh. The lab simulates a Security Operations Center (SOC) environment where endpoint activity and system logs are monitored to detect potential security threats.

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

## Technologies Used

- Wazuh SIEM
- Ubuntu Linux
- Windows Endpoint Monitoring
- PowerShell
- Virtualization (Parallels / VM Environment)
- Syslog
- Windows Event Logs

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

Several security scenarios were simulated to test SIEM detection capabilities.

### Authentication Failure Detection

Failed login attempts were generated on the Windows endpoint.

Example event:

Event ID: 4625  
Description: Failed login attempt

These alerts can indicate:

- brute force attacks
- credential stuffing
- unauthorized access attempts

---

### PowerShell Monitoring

Suspicious PowerShell commands were executed to simulate fileless malware activity.

Example command:

powershell -ExecutionPolicy Bypass -Command "Get-Process"

Wazuh analyzes these events and generates alerts when suspicious command execution is detected.

---

### File Integrity Monitoring

Wazuh was configured to detect file system changes.

Example alert:

Rule: File added to the system  
Rule ID: 554  
Severity Level: 5

This helps identify unauthorized file changes or malware installation.

---

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

## Screenshots

## Screenshots

### Wazuh Dashboard
![Wazuh Dashboard](screenshots/wazuh-dashboard.png)

### Endpoint Agent Connected
![Agent Connected](screenshots/agent-connected.png)

### Failed Login Alert
![Failed Login](https://github.com/FernandoMurillo1/Wazuh-SIEM-Home-Lab---Security-Monitoring-and-Threat-Detection-/blob/1f3ec10bfb150e3155a1beda9d2d41afb9c7f0d2/authentication%20failure.png)

### PowerShell Alert
![PowerShell Alert](https://github.com/FernandoMurillo1/Wazuh-SIEM-Home-Lab---Security-Monitoring-and-Threat-Detection-/blob/6914d28424a9f379af0a3f27a55b75b2545946bb/Powershell%20Alert%20User%20created.png)
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

## Author

Luis Fernando Murillo  
Cybersecurity / IT Enthusiast  

LinkedIn: https://www.linkedin.com/in/luis-murillo-748474217/

Conclusion 

This project provided hands-on experience deploying and operating and SIEM platform to monitor system activity and detect security threats. By simulating real-worl attack scenarious and analyzing the resulting alerts, this lab demostrates practical skills relevant to roles in: 

- Security Operations (SOC)
- Cybersecurity Analysis
- Incident Response
- Threat Detection



  
