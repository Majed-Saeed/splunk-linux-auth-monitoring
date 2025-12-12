# Splunk Linux Authentication Monitoring

## Overview
This project demonstrates how to build a practical SIEM detection using **Splunk Enterprise** to monitor **Linux authentication logs** and detect **failed SSH login attempts** in real time.

The lab uses real system logs generated from an Ubuntu machine and simulates authentication failures to validate detection logic and alerting behavior.

This project reflects a real-world SOC analyst workflow: log ingestion, detection engineering, alert creation, and validation.

---

## Objectives
- Ingest Linux authentication logs into Splunk
- Detect failed SSH login attempts
- Create a real-time Splunk alert
- Validate detection using simulated attack activity
- Review alert trigger history

---

## Lab Environment
- **Operating System:** Ubuntu Linux 24.04
- **SIEM Platform:** Splunk Enterprise 10.x
- **Services:** OpenSSH Server
- **Virtualization:** VMware Workstation

---

## Data Source
- **Log File:** `/var/log/auth.log`
- **Log Type:** Linux authentication events
- **Events Monitored:**
  - Failed SSH password attempts
  - PAM authentication failures
  - SSH daemon activity

---

## Detection Logic

### Splunk Search (SPL)
```spl
index=main "Failed password"
