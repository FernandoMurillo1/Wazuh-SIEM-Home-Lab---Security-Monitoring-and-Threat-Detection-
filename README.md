# Wazuh-SIEM-Home-Lab---Security-Monitoring-and-Threat-Detection-

Overview 

This project demonstrates the deployment and configuration of a Security Information and Event Management (SIEM) platform using Wazuh. This lab simulates a real-world security operations environment where system logs, endpoint telemntry and security events are collected, analyzed, and visualized to detect potential threats. 

The goal of this project was to gain hands-on experience with: 
- SIEM deployment and configuration
- Enpoint Monitoring
- Log ingestion and analysis
- Threat detection and investigation
- Security event correlation

This lab replicates a simplifies Security Operations Center (SOC) workflow where alerts are generated, investigated and documented. 

Lab Architecture 

The environment was built using virtual machines to simulate an enterprise network 

Host Machine (Mac / Parallels)

├── Ubuntu Server
│   └── Wazuh SIEM
│        • Wazuh Manager
│        • Wazuh Indexer
│        • Wazuh Dashboard

├── Windows Endpoint
│   └── Wazuh Agent
│        • Windows Security Logs
│        • PowerShell Monitoring
│        • File Integrity Monitoring

Components 

Wazuh Server (Ubuntu) 
Responsible for collecting logs, analyzing events, applying detection rules and sending alerts to the dashboard 

Wazuh Agent (Windows) 
Instlled on endpoints to forward logs and telementry data to the Wazuh server. 

Wazuh Dashboard 
Web-based interface used to visualize alerts, investigate security events, and monitor endpoints 


Technologies Used 

- Wazuh SIEM
- Linux (Ubuntu Server)
- Windows Endpoint Monitoring
- Powershell
- Virtualization (Parellels / VM environment)
- Syslog
- Windows Event Logs

Features impemented 

Endpoint Monitoring 

The Wazuh agents was installed on a Windows machine to collect system logs and send them to the Wazuh server. 

Data collected includes: 

- Windows authentication events
- PowerShell activity
- System changes
- File modification
- Network port changes

File Integrity Monitoring 

Wazu monitored file system changes on the host machine and generated alerts when files were created or modified. 

Example detection: 

Rule: File added to the system 
Rule ID: 554 
Severity Level: 5 

This demonstrates Wazuh's ability to dectect unauthorized file changes which may indicate malware activity or persistence mechanisms. 


Network Monitoring 

The SIEM monitored changes to listening network ports using netstat. 

Example alert: 

Rule: Listened ports status changed 
Rule ID: 533 
Severity Level: 7

This detection can help identify suspicious services or unauthorized processes opening network ports. 


Authentication Monitoring 

The Lab simulated failed login attempts on a Windows machine 

Example detection: 

Event ID: 4625 
Description: Failed login attempt 

These events are commonly used to detect: 
- Brute force attacks
- credential stuffing
- unauthoritzed access attempts

PowerShell Attack Simulation 

A suspicious PowerShell command was executed to simulate fileless malware behavior. 

Example command: 

powershell -ExecutionPolicy Bypass -Command "Get-Process" 

THis behavior mimics techniques used in real attacks where malicious scripts bypass security policies to execute commands. 

Wazuh analyzes these logs and can detect: 
- Suspicous PowerShell execution
- Policy bypass attempts
- Malicious scripting activity

Detection Workflow 

The SIEM pipeline processes events in the following order: 

Endpoint Activity
        ↓
Wazuh Agent
        ↓
Wazuh Manager
        ↓
Wazuh Indexer
        ↓
Wazuh Dashboard

Security alerts are generated when log events match predefined detection rules. 

Example Security Alerts 

Examples of alerts generated in the lab environment include: 

Alert Type                           Description 
File Integrity Monitoring            File Created or modified 
Network Monitoring                   New listening port detected 
Authentication Failure               Failed login attempt 
PowerShell Activity                  Suspicious PowerShell command 

These alerts are analyzed through the Wazuh dashboard for investigation 

Skills Demonstrated 

This project demonstrates hands-on experience with: 

- SIEM deployment 
- Endpoint security monitoring
- Security event analysis
- Threat detection techniques
- Log management
- Security incident investigation

Future Improvements 

Planned enhancements to this lab included: 

- Active Directory attack detection
- Malware detection monitoring
- Brute force attack simulation
- Network scanning detection
- Integration with threat intelligence feeds

Conclusion 

This project provided hands-on experience deploying and operating and SIEM platform to monitor system activity and detect security threats. By simulating real-worl attack scenarious and analyzing the resulting alerts, this lab demostrates practical skills relevant to roles in: 
- Security Operations (SOC)
- Cybersecurity Analysis
- Incident Response
- Threat Detection

  
