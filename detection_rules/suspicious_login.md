# Suspicious Successful Login

## Objective
Identify successful authentication following multiple failed attempts.

## Detection Logic
Monitor Event ID 4624 after repeated Event ID 4625 events from the same source IP.

## Severity
High

## Interpretation
This pattern may indicate a compromised account or successful brute-force attempt.
