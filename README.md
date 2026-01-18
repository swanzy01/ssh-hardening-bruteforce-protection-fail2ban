# SSH Hardening Against Brute-Force Attacks Using Fail2Ban

## Overview
This project demonstrates how to harden SSH access on a Linux server by mitigating brute-force authentication attacks using Fail2Ban. The solution detects repeated failed SSH login attempts through log analysis and automatically blocks offending IP addresses.

## Security Objective
- Protect SSH services from brute-force and credential-stuffing attacks
- Reduce unauthorized access attempts
- Enforce automated incident response for repeated authentication failures

## Threat Description
SSH brute-force attacks involve repeated login attempts using automated tools to guess valid credentials. If successful, attackers can gain unauthorized access, escalate privileges, and compromise the system.

## Defensive Control
Fail2Ban is configured to monitor SSH authentication logs and enforce temporary IP bans after a defined number of failed login attempts.

## Tools & Technologies
- Linux (Ubuntu/Debian)
- OpenSSH
- Fail2Ban
- systemd
- Log-based intrusion detection

## Configuration Summary

| Parameter | Value |
|--------|------|
| maxretry | 3 |
| findtime | 10 minutes |
| bantime | 10 seconds (testing environment) |

## How It Works
1. SSH authentication failures are logged in `/var/log/auth.log`
2. Fail2Ban parses log entries in real time
3. After 3 failed attempts within 10 minutes:
   - The source IP is automatically banned
4. The ban is lifted after the configured ban time

## Validation & Evidence
- Fail2Ban logs confirm detection of failed login attempts
- Automatic IP banning and unbanning verified through testing

## Security Impact
- Blocks brute-force login attempts
- Limits attack surface on SSH services
- Demonstrates automated threat detection and response

## Future Improvements
- Enforce SSH key-only authentication
- Implement progressive ban durations
- Integrate with UFW firewall rules
- Enable email alerts for security events
