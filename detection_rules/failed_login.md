# Windows Failed Login Detection

## Objective
Detect multiple failed Windows authentication attempts.

## Detection
Monitor Windows Security Event ID 4625.

## Logic
If multiple Event ID 4625 events originate from the same source IP within a short period, flag the activity as a potential brute-force attack.

## Severity
High

## Example
Source IP: 192.168.1.105
Event ID: 4625
Multiple failed attempts detected.
