# IT Support Home Lab Portfolio

Home lab simulating a small Windows domain: Server 2022 DC running AD DS, DNS, and DHCP, a domain-joined Windows 10 client, and a Linux VM. Each scenario is documented in ticket format- symptom, diagnosis, root cause, resolution- with screenshots.

## Lab Environment
- **DC01-server** - Windows server 2022, AD DS /DNS /DHCP
- **WIN10-CLIENT** - Windows 10., domain-joined to lab.local
- **Kali Linux** - Linux troubleshooting
- **Ubuntu-Wazuh** - Wazuh agent installed and configured
## Scenarios
- [Password Reset - Domain Account](01-active-directory/password-reset.md)
- [New User provisioning - Darcy Smith](01-active-directory/new-user-provisioning.md)
- [Account Lockout / Unlock](01-active-directory/account-lockout-unlock.md)
- [User Offboarding - disable first then delete](01-active-directory/offboarding.md)
- [GPO - Control Panel Restriction](02-group-policy/gpo-controlpanel-restriction.md)
- [GPO - Mapped Network Drive](02-group-policy/mapped-drive-gpo.md)
- [GPO - Password Policy](02-group-policy/password-policy-gpo.md)
- [Remote Desktop (RDP) Session](04-remote-support/rdp-session.md)
