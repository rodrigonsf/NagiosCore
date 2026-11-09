# AGENTS.md

## Project overview

This repository provides a shell script that automates the installation
and initial configuration of **Nagios Core 4.5.14** on **CentOS 7**.

It is an independent automation project. It is not the Nagios Core
source code and it is not an official Nagios installer.

Official Nagios Core project:

https://www.nagios.org/projects/nagios-core/

Official Nagios Core 4.5.14 download:

https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.5.14.tar.gz

Official Nagios Core versions page:

https://assets.nagios.com/downloads/nagioscore/versions.php

## Supported environment

| Component | Requirement |
|---|---|
| Operating system | CentOS 7 |
| Architecture | x86_64 |
| Nagios Core | 4.5.14 |
| Privileges | Root or `sudo` |
| Network | Internet access required |

Do not claim support for Ubuntu, Debian, RHEL, CentOS Stream or other
operating systems unless the script has been updated and tested for them.

## Repository layout

- `README.md`: human-facing documentation and quick start.
- `nagios_automatizado.sh`: main installation and configuration script.
- `LICENSE.md`: project license.
- `CONTRIBUTING.md`: contribution guidelines.
- `SECURITY.md`: security reporting policy.
- `docs/INSTALLATION.md`: detailed installation procedure.
- `docs/TROUBLESHOOTING.md`: troubleshooting guidance.
- `docs/SECURITY_CHECKLIST.md`: pre-execution security checklist.

## Main entry point

The primary executable is:

```bash
nagios_automatizado.sh
```

Typical execution:

```bash
wget -O nagios_automatizado.sh \
  [https://raw.githubusercontent.com/rodrigonsf/NagiosCore/master/nagios_automatizado.sh](https://raw.githubusercontent.com/rodrigonsf/NagiosCore/master/nagios_automatizado.sh)

chmod 755 nagios_automatizado.sh
sudo ./nagios_automatizado.sh
```

## Before making changes

1. Read the full script before proposing changes.
2. Identify every package, file, user, group, service, port and
   configuration file affected by the change.
3. Preserve CentOS 7 compatibility.
4. Do not change the Nagios Core version unless the README, docs and
   validation steps are updated.
5. Do not introduce credentials, private IP addresses, hostnames,
   tokens or secrets into the script, examples or documentation.
6. Prefer idempotent commands when possible.
7. Avoid destructive commands without explicit checks and warnings.
8. Update documentation whenever installation behavior changes.

## Validation

Before proposing a change, validate:

```bash
bash -n nagios_automatizado.sh
shellcheck nagios_automatizado.sh
```

If ShellCheck is not available, install it with:

```bash
sudo yum install -y ShellCheck
```

Also validate the resulting Nagios configuration after installation:

```bash
nagios -v /usr/local/nagios/etc/nagios.cfg
```

Adjust this path if the script uses a different Nagios configuration
location.

## Security considerations

This script requires administrative privileges and may modify system
packages, configuration files, users, groups, services and firewall rules.

- Do not run the installer automatically in production.
- Test changes in a disposable virtual machine first.
- Do not disable SELinux or security controls without a documented reason.
- Do not download binaries from unverified sources.
- Do not expose the Nagios web interface without reviewing access control,
  authentication and TLS configuration.
- Do not commit credentials, private keys, tokens or real infrastructure
  details.

## Commit and pull request guidelines

Use concise commit messages that describe the change and its impact.

Suggested format:

```text
[type]: short description

[optional body explaining motivation and impact]
```

Examples:

```text
docs: add Nagios Core 4.5.14 installation instructions
fix: validate Nagios configuration before starting service
security: restrict permissions on Nagios configuration files
```

For pull requests, include:

- What changed.
- Why it changed.
- How it was tested.
- Which CentOS 7 components were affected.
- Any security or compatibility impact.
