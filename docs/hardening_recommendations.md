# Linux Hardening Recommendations
## Scope
This document summarizes safe recommendations based on the generated audit report. The goal is not to
blindly change the system, but to understand risk and document next actions.
## Recommended Review Areas
1. Listening ports: confirm every exposed port has a business reason.
2. Enabled services: disable services that are not needed.
3. Firewall: enable UFW only after confirming SSH/local access needs.
4. Updates: apply security updates regularly.
5. Sudo users: ensure only trusted users have sudo access.
6. Logs: review authentication errors and system errors.
7. File permissions: investigate world-writable files.
## Safe Commands to Review
```bash
sudo ufw status verbose
systemctl --type=service --state=running
ss -tulpen
apt list --upgradable
```
## Do Not Do Blindly
- Do not disable SSH on a remote server before confirming alternative access.
- Do not remove users without verifying ownership and purpose.
- Do not open firewall ports without a clear reason.
