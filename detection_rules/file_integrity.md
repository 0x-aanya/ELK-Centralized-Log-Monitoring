# File Integrity Monitoring

## Objective
Track changes to sensitive Linux system files.

## Monitored Files
- /etc/passwd
- /etc/shadow
- /etc/ssh/sshd_config

## Detection
Flag unexpected modification events.

## Severity
High

## Example
Modification of a sensitive system file should generate a security alert for investigation.
