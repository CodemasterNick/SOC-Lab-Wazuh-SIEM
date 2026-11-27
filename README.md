# SOC Lab #03 — Wazuh SIEM: Monitoring and Threat Detection

## Project Overview

This project documents a hands-on Security Operations Center (SOC) lab using Wazuh SIEM to monitor a Windows 11 endpoint, collect security events, and investigate authentication-related activities.

The main goal was to configure a Windows endpoint, integrate it with Wazuh, and analyze security events generated during controlled tests.

## Environment

- **SIEM:** Wazuh 4.14.7
- **Endpoint:** Windows 11 Home
- **Server:** Ubuntu Linux running in VirtualBox
- **Agent name:** WIN11-LAB
- **Monitoring:** Windows Security Event Logs

## Lab Activities

### 1. Wazuh Agent Deployment
- Installed and configured the Wazuh agent on Windows 11.
- Connected the endpoint to the Wazuh manager.
- Verified successful communication and agent status.

### 2. Windows Security Event Investigation

The following events were generated and investigated:

| Event ID | Description | Result |
|---|---|---|
| 4720 | User account created | Detected |
| 4722 | User account enabled | Detected |
| 4625 | Failed logon attempt | Detected |

### 3. Detection Details

**Event ID 4720 — User Account Created**

A test account named `soclab_test` was created on the Windows endpoint. Wazuh collected the corresponding security event.

**Event ID 4722 — User Account Enabled**

The account activation event was also detected and correlated with the account creation activity.

**Event ID 4625 — Failed Logon Attempt**

An intentional incorrect password was used during a controlled authentication test. Wazuh detected the failed logon attempt.

- Target account: `soclab_test`
- Logon type: 2 (Interactive)
- Failure status: `0xC000006D`
- Substatus: `0xC000006A`
- Wazuh rule ID: `60122`
- Alert level: 5

## Evidence

Screenshots documenting the configuration and investigation will be available in the `evidencias/` directory.

## Skills Practiced

- SIEM deployment and configuration
- Windows endpoint monitoring
- Wazuh agent integration
- Windows Security Event Log analysis
- Authentication failure investigation
- Security event correlation
- Basic threat detection and investigation

## Disclaimer

All activities were performed in a controlled lab environment for educational purposes.

This project is part of my practical cybersecurity learning journey.
