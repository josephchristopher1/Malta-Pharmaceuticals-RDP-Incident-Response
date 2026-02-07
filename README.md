#  Malta Pharmaceuticals – RDP Incident Response & Hardening

## Overview
This repository documents a **realistic enterprise-style incident response investigation** involving a **credential-based Remote Desktop Protocol (RDP) intrusion** against a Windows workstation within the *Malta Pharmaceuticals* internal network.

The project demonstrates **detection, investigation, containment, mitigation, and hardening actions** taken following confirmation of unauthorised RDP access.  
All actions align with **SOC Analyst (L2–L3) operational standards** and real-world incident handling practices.

---

## Incident Summary
- **Incident Type:** Credential-based RDP intrusion  
- **Affected Asset:** Windows 11 Workstation (Finance endpoint)  
- **Initial Access Vector:** Brute-force / credential abuse over RDP (TCP 3389)  
- **Environment:** Internal enterprise network (simulated)  
- **Detection Sources:** Windows Security Logs, Splunk, Firewall telemetry  

---

## Investigation Objectives
- Identify compromised account(s)
- Confirm successful or failed RDP authentication
- Assess post-authentication activity
- Contain the incident to prevent recurrence
- Apply endpoint and network-level hardening
- Preserve evidence suitable for executive and technical review

---

## Response & Containment Actions
Upon confirmation of credential-based RDP access, the following actions were executed:

- Immediate termination of validated RDP session  
- Identification of compromised local user account  
- Forced password reset for affected account  
- Enforced password change at next logon  
- Review of authentication telemetry for lateral movement  
- Continued monitoring during and after the incident window  
- No persistence mechanisms or follow-on activity observed  

---

## Mitigation & Hardening Measures

### Endpoint (Windows)
- Enforced **Network Level Authentication (NLA)** for RDP  
- Restricted RDP access to authorised users only  
- Implemented **account lockout policy** to prevent brute-force attempts  
- Strengthened **password policy** (length, complexity, history)  
- Reviewed and hardened Windows Defender Firewall RDP rules  

### Network (pfSense Firewall)
- Implemented temporary **RDP block rule (TCP 3389)** targeting the affected endpoint  
- Logged blocked traffic for investigation and audit purposes  
- Demonstrated rapid containment at firewall level following endpoint compromise  

> These actions reflect **real-world incident response hardening** while maintaining controlled access for continued security testing and validation.

---

## Evidence & Documentation Structure

├── Incident/
│ ├── Screenshots/
│ │ ├── Windows_Hardening/
│ │ ├── Firewall_Hardening/
│ └── Timeline/
├── Malta Project-Splunk/
│ ├── SPL_Queries/
│ └── Dashboards/
├── Wireshark/
│ └── Network_Capture_Evidence/
├── README.md
└── Malta_Pharmaceuticals_RDP_Incident_Report.pdf


- **Screenshots:** Portfolio-selected evidence only (no repetition or noise)  
- **SPL Queries:** Detection and validation searches  
- **PDF Report:** Full professional incident report suitable for offline review  
- **README:** Executive and technical summary for rapid assessment  

---

## Skills Demonstrated
- SOC Incident Response (L2–L3)  
- Windows Authentication & RDP Security  
- Credential Abuse Investigation  
- Endpoint Hardening  
- Firewall Rule Design & Validation  
- Splunk Threat Detection & Analysis  
- Evidence Handling & Professional Reporting  

---

## Framework Alignment
**MITRE ATT&CK**
- T1110 – Brute Force  
- T1078 – Valid Accounts  
- T1021.001 – Remote Services (RDP)  

**NIST Incident Response Lifecycle**
- Detection & Analysis  
- Containment  
- Eradication  
- Recovery  
- Lessons Learned  

---

## Disclaimer
This project was conducted in a **controlled, simulated environment** for the purpose of **defensive security training, incident response validation, and portfolio demonstration** only.

No production systems or real organisations were impacted.
