# Architecture Overview

## Components
- SSH daemon (sshd)
- Fail2Ban service
- Authentication logs
- Firewall (iptables / nftables)

## Detection Flow
1. SSH receives authentication request
2. Failed login is logged
3. Fail2Ban filter parses log entry
4. Jail rules evaluate retry threshold
5. IP ban is enforced at firewall level

## Design Principles
- Log-based detection
- Automated response
- Minimal system overhead
