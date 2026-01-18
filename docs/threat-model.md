# Threat Model

## Identified Threat
- SSH brute-force authentication attacks
- Credential stuffing attempts

## Attack Vector
- Automated scripts attempting repeated SSH logins

## Potential Impact
- Unauthorized system access
- Privilege escalation
- Data compromise

## Mitigation Strategy
- Detection of repeated authentication failures
- Automated IP banning using Fail2Ban
- Reduced attack window
