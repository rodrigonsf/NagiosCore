# Security Policy

## Supported versions

This project targets CentOS 7, which reached end of life on June 30, 2024.
There is no guarantee of security updates for the operating system or for
dependencies used by the installer.

| Project version | Status |
|---|---|
| Current version | Experimental support |
| CentOS 7 | Legacy environment |

## Reporting a vulnerability

Do not report security vulnerabilities in public issues.

To report a vulnerability, contact the maintainer privately through GitHub
or use GitHub private vulnerability reporting when available.

Include:

- A description of the vulnerability.
- Steps to reproduce it.
- The script version and operating system version.
- Relevant logs, with sensitive information removed.
- The estimated impact.
- Any suggested mitigation, if applicable.

## Scope

This policy applies to the automation script and files in this repository.

Vulnerabilities in Nagios Core, CentOS, Apache, PHP, system packages or
third-party dependencies should be reported to the respective upstream
maintainers.

## Safe usage

Before running the installer:

- Review the entire script.
- Test it in a disposable virtual machine.
- Back up relevant configuration and data.
- Do not run it automatically in production.
- Do not expose the Nagios web interface without access controls and TLS.
- Do not add real credentials to examples or configuration templates.
