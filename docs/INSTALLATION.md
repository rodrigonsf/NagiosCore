# Installation Guide

This guide describes how to install and configure Nagios Core 4.5.14
on CentOS 7 using `nagios_automatizado.sh`.

## Requirements

- CentOS 7.
- Root access or `sudo` privileges.
- Internet access.
- Sufficient disk space for packages, source code and compilation.
- Access to the official Nagios Core download server.

## Download the installer

```bash
wget -O nagios_automatizado.sh \
  [https://raw.githubusercontent.com/rodrigonsf/NagiosCore/master/nagios_automatizado.sh](https://raw.githubusercontent.com/rodrigonsf/NagiosCore/master/nagios_automatizado.sh)
```

## Review the script

Before executing the installer, review its contents:

```bash
less nagios_automatizado.sh
```

Check which packages it installs, which files it modifies, which services
it restarts and whether it changes firewall or SELinux settings.

## Run the installer

```bash
chmod 755 nagios_automatizado.sh
sudo ./nagios_automatizado.sh
```

If you are already authenticated as root:

```bash
./nagios_automatizado.sh
```

## Validate the installation

Check the Nagios service:

```bash
systemctl status nagios
```

Check Apache:

```bash
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

## Logs

Check Nagios service logs:

```bash
journalctl -u nagios
```

Check Apache logs:

```bash
tail -f /var/log/httpd/error_log
```

## After installation

Before using the server in production:

- Configure HTTPS.
- Restrict access to the web interface.
- Review firewall rules.
- Change default credentials, if applicable.
- Review Nagios configuration files.
- Keep the system and dependencies updated.

## Cleanup

After installation, remove the local copy of the installer if desired:

```bash
rm nagios_automatizado.sh
```

This removes only the downloaded script. It does not uninstall Nagios.
