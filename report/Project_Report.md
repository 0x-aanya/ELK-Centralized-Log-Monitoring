# Centralized Log Monitoring and Threat Detection System using ELK Stack

## 1. Introduction

Modern enterprise environments generate large volumes of system and security logs. Monitoring these logs independently across different systems makes it difficult to identify unauthorized access, suspicious authentication attempts, and other malicious activities.

This project presents a centralized log monitoring and threat detection system using the ELK Stack consisting of Elasticsearch, Logstash, and Kibana. Logs from Windows and Linux endpoints are collected using Winlogbeat and Filebeat and are analyzed for security-related events.

The project demonstrates a simulated Security Operations Center (SOC) environment and focuses on centralized visibility, log analysis, threat detection, dashboards, and security monitoring.

## 2. Objectives

The primary objectives are:

- Understand centralized logging and SIEM concepts.
- Understand the architecture of the ELK Stack.
- Collect Windows and Linux security logs.
- Analyze authentication and system events.
- Detect suspicious login activity.
- Monitor SSH authentication attempts.
- Monitor sensitive file modifications.
- Design dashboards for security monitoring.
- Define alerts for suspicious activities.
- Understand basic SOC analyst workflows.

## 3. System Requirements

### Host Machine

- Minimum 16 GB RAM recommended.
- Intel/AMD processor with virtualization support.
- Virtualization software such as VirtualBox or VMware.

### Virtual Machines

| VM | Operating System | Purpose |
|---|---|---|
| VM 1 | Ubuntu Server | ELK Server |
| VM 2 | Windows | Windows Endpoint |
| VM 3 | Ubuntu/Kali Linux | Linux Endpoint |

## 4. Project Architecture

The centralized monitoring architecture consists of Windows and Linux endpoints forwarding logs through Beats to Logstash. Logstash processes the events and forwards them to Elasticsearch for storage and search. Kibana provides visualization, querying, dashboards, and alert monitoring.

### Log Flow

Windows/Linux Endpoint → Winlogbeat/Filebeat → Logstash → Elasticsearch → Kibana

## 5. Implementation

### Phase 1: ELK Stack

The ELK Stack consists of:

- Elasticsearch — centralized storage and search.
- Logstash — log collection and processing.
- Kibana — visualization and monitoring.

Configuration examples for the ELK components are included in the `configs` directory.

### Phase 2: Endpoint Log Collection

#### Windows Endpoint

Winlogbeat is configured to collect:

- Security logs
- System logs
- Application logs

#### Linux Endpoint

Filebeat is configured to collect:

- Authentication logs
- System logs

Sample security events are included in the `sample_logs` directory for demonstration and testing.

## 6. Security Use Cases

### Use Case 1: Windows Failed Login Detection

Windows Event ID 4625 represents a failed authentication attempt.

Multiple failed authentication events from the same source IP can indicate a potential brute-force attack.

Example:

Source IP: 192.168.1.105

Event ID: 4625

Status: Failed

### Use Case 2: Suspicious Successful Login

A successful authentication event following several failed authentication attempts can indicate a potentially compromised account.

The detection logic correlates failed authentication events with a subsequent successful login.

### Use Case 3: Linux SSH Login Monitoring

SSH authentication logs are monitored for repeated failed login attempts and unexpected successful logins.

Multiple failed SSH attempts from a single source IP may indicate an unauthorized access attempt.

### Use Case 4: File Integrity Monitoring

Sensitive Linux files such as:

- `/etc/passwd`
- `/etc/shadow`
- `/etc/ssh/sshd_config`

are considered important files for integrity monitoring.

Unexpected modifications should be investigated as potential security events.

### Use Case 5: Abnormal Activity Simulation

Suspicious activity can be simulated in a controlled environment and the resulting logs can be analyzed through the centralized monitoring pipeline.

## 7. Dashboards and Alerts

The proposed Kibana security dashboard includes:

- Login Attempts
- Failed Authentication Events
- Top Source IP Addresses
- Error Events
- SSH Login Attempts
- File Integrity Events

### Alerts

The monitoring system defines alerts for:

- Multiple failed login attempts
- Unauthorized access patterns
- Abnormal system activity

## 8. Results and Observations

The project demonstrates the concept of centralized security log monitoring.

Expected observations include:

- Centralized visibility of security events.
- Improved analysis of authentication activity.
- Identification of repeated failed login attempts.
- Monitoring of SSH authentication events.
- Detection of suspicious successful logins.
- Visibility into sensitive file modifications.
- Dashboard-based security monitoring.

## 9. Learning Outcomes

This project provides practical understanding of:

- SIEM architecture.
- ELK Stack components.
- Centralized logging.
- Log analysis.
- Authentication monitoring.
- Threat detection concepts.
- Dashboard-based monitoring.
- SOC analyst workflows.
- Blue Team security operations.

## 10. Evaluation Criteria

| Criteria | Weightage |
|---|---:|
| ELK Stack Installation & Configuration | 20% |
| Log Collection and Accuracy | 20% |
| Security Use-Case Implementation | 25% |
| Dashboards & Alerts | 20% |
| Documentation & Presentation | 15% |

## 11. Conclusion

The project demonstrates a centralized log monitoring and threat detection architecture using the ELK Stack.

By collecting and analyzing security events from Windows and Linux endpoints, the system provides centralized visibility into authentication attempts, SSH activity, file integrity events, and suspicious behavior.

The project provides a foundation for understanding SIEM-based monitoring and SOC operations and develops skills relevant to security monitoring, threat detection, and incident response.

## Project Structure

```text
ELK-Centralized-Log-Monitoring/
├── README.md
├── configs/
├── sample_logs/
├── detection_rules/
├── dashboards/
├── architecture/
└── report/


