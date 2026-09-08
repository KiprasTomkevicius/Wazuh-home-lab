This is a personal home-lab set up using OracleVM and virtual machines. The current machines used are Windows 11 and Wazuh version 4.14.7.
This lab is for personal learning use, trying to learn how to use SIEM, security tools and log analysis. 



## Experiments

Part 1

- **01-local-account-creation** — Creating an account on a local Windows 11 machine and observing generated logs. **Completed**
- **02-failed-logon** — Generating failed logon attempts using an incorrect password on a local Windows machine. **Completed**
- **03-account-lockout** — Repeated failed login attempts until the account is locked out. **Completed**
- **04-permission-privilege-change** — Generating log events by changing the privileges of an existing local account. **Completed**
- **05-denied-vs-allowed-file-access** — Generating log events by having an account try to access files without having the access to do so. **Half Completed**
- **06-standard-user-elevation** — Attempting to run a process with elevated privileges from a standard user account and observing generated logs. **Completed**
- **07-admin-user-elevation** — Running a process with elevated privileges from an administrator account and observing generated logs. **Planned**



Part 2
**Add linux device to the system and test connection based logs**
-ICMP connection
-maybe ftp?
-maybe ssh?
-firewall rules allow
-firewall rules block
-remote access



Part 3
**Add Windows server and test server based logs**
-shared resources/files
-authentication
-access fail/success
-remote access