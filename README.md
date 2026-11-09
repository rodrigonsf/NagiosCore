# Nagios Core Installer - CentOS 7

Automated installation and configuration of **Nagios Core 4.5.14**
on **CentOS 7**.

This repository provides a shell script that automates the installation
and initial configuration of Nagios Core on CentOS 7.

> **Important:** CentOS Linux 7 reached end of life on June 30, 2024.
> Use this project for learning, reference, isolated test environments,
> or legacy-system assessment. It is not recommended for new production
> deployments.

## About this project

This is an independent automation project.

- It is **not** the Nagios Core source code.
- It is **not** an official Nagios installer.
- It automates the installation and initial configuration of Nagios Core.
- It targets CentOS 7 and Nagios Core 4.5.14.

## What this script does

- Installs the dependencies required to build and run Nagios Core.
- Downloads Nagios Core 4.5.14 from the official Nagios download server.
- Compiles and installs Nagios Core.
- Creates the required Nagios user and groups.
- Installs and configures the Nagios web interface.
- Enables and starts the required services.
- Applies basic security and permission settings.

Review the script before running it. The exact packages, files,
services and configuration changes depend on the current version
of `nagios_automatizado.sh`.

## Requirements

- CentOS 7.
- Root access or `sudo` privileges.
- Internet access.
- Sufficient disk space for packages, source code and compilation.
- Network access to the official Nagios download server.

## Quick start

### 1. Download the installer

```bash
wget -O nagios_automatizado.sh \
  [https://raw.githubusercontent.com/rodrigonsf/NagiosCore/master/nagios_automatizado.sh](https://raw.githubusercontent.com/rodrigonsf/NagiosCore/master/nagios_automatizado.sh)
```

### 2. Review the script

```bash
less nagios_automatizado.sh
```

### 3. Run the installer

```bash
chmod 755 nagios_automatizado.sh
sudo ./nagios_automatizado.sh
```

If you are already authenticated as root:

```bash
./nagios_automatizado.sh
```

### 4. Optional cleanup

After the installation finishes, remove the local copy of the installer:

```bash
rm nagios_automatizado.sh
```

This removes only the downloaded script. It does not uninstall Nagios.

## Nagios Core download

The installer downloads Nagios Core 4.5.14 from the official Nagios
download server:

https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.5.14.tar.gz

The official list of Nagios Core versions is available at:

https://assets.nagios.com/downloads/nagioscore/versions.php

The official Nagios Core project page is:

https://www.nagios.org/projects/nagios-core/

## Validation

After installation, verify that the services are running:

```bash
systemctl status nagios
systemctl status httpd
```

Validate the Nagios configuration:

```bash
nagios -v /usr/local/nagios/etc/nagios.cfg
```

Access the web interface using the server IP address:

```text
http://SERVER_IP/nagios/
```

Review the logs if the installation or service fails:

```bash
journalctl -u nagios
tail -f /var/log/httpd/error_log
```

## Security

Before exposing Nagios to a network:

- Configure HTTPS with a valid certificate.
- Restrict access to the web interface.
- Review firewall rules.
- Change any default credentials.
- Keep the operating system, Apache, PHP and Nagios updated.
- Do not disable SELinux or security controls without understanding the impact.

This installer targets a legacy operating system. Perform a security
review before using it in any environment.

## Re-running the installer

Document whether the script can be safely executed again.

If it can, explain which steps are repeated and which files may be
overwritten. If it cannot, state that clearly.

## Uninstallation

This project [does not include / includes] an uninstallation procedure.

If it does not, explain which packages, files, users, services and
configuration changes must be manually reverted.

## Limitations

- Targets CentOS 7 only.
- CentOS 7 is end-of-life.
- Dependencies and download URLs may require adjustment over time.
- Review the script before running it in any environment.

## Português

Este repositório automatiza a instalação e a configuração do
**Nagios Core 4.5.14** no **CentOS 7**.

Leia o script completo antes de executá-lo com privilégios
administrativos. Teste-o primeiro em uma máquina virtual isolada.

O CentOS Linux 7 está fora de suporte. Este projeto deve ser
avaliado como automação para ambientes legados, não como
recomendação para novas implantações em produção.

## Disclaimer

This software is provided “as is”, without warranty of any kind.
Review the script and assess its suitability before use. <i>¡La garantia soy io!</i>
<br> <i>(It´s automatic ♪♫)</i> <b>(<i>atcho tcho meri ♪♫</i>) ;-)</b>
## License

See [LICENSE.md](LICENSE.md).

## Author

Rodrigo N. S. Fernandes
