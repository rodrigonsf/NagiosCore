# Security Checklist

Complete this checklist before running the installer.

## Before execution

- [ ] I reviewed the entire `nagios_automatizado.sh` script.
- [ ] I understand which packages will be installed.
- [ ] I understand which files will be created or modified.
- [ ] I understand which users and groups will be created.
- [ ] I understand which services will be enabled or restarted.
- [ ] I understand whether firewall rules will be changed.
- [ ] I understand whether SELinux settings will be changed.
- [ ] I confirmed that the script does not contain credentials or secrets.
- [ ] I made a backup of relevant configuration and data.
- [ ] I will test the installer in a disposable virtual machine first.
- [ ] I understand that CentOS 7 is end-of-life.
- [ ] I understand that this project is not the official Nagios installer.
- [ ] I understand that this project does not replace a security review.

## After installation

- [ ] The Nagios service is running.
- [ ] Apache is running.
- [ ] The Nagios configuration passes validation.
- [ ] The web interface is accessible only through an approved network.
- [ ] HTTPS is configured before public exposure.
- [ ] Default credentials were changed, if applicable.
- [ ] Firewall rules allow only required access.
- [ ] SELinux remains enabled unless there is a documented reason to change it.
- [ ] Logs are available and monitored.
- [ ] The system and dependencies are kept updated where possible.

## Never do this

- Do not run the installer automatically on production servers.
- Do not expose the web interface without authentication and TLS.
- Do not disable security controls without a documented reason.
- Do not commit credentials, private keys, tokens or sensitive logs.
- Do not download binaries from unverified sources.
