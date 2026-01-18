# Testing and Validation

## Test Method
- Perform repeated failed SSH login attempts from a single IP
- Monitor Fail2Ban logs in real time

## Validation Commands
```bash
fail2ban-client status sshd
tail -f /var/log/fail2ban.log
sudo watch -n 1 fail2ban-client status sshd
