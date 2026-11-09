# Troubleshooting

## Download failure

Check network connectivity and the script URL:

```bash
curl -I [https://raw.githubusercontent.com/rodrigonsf/NagiosCore/master/nagios_automatizado.sh](https://raw.githubusercontent.com/rodrigonsf/NagiosCore/master/nagios_automatizado.sh)
```

Verify that `wget` or `curl` is installed:

```bash
command -v wget
command -v curl
```

## Permission denied

Verify that you are running the script with root privileges:

```bash
whoami
sudo -v
```

Ensure the script is executable:

```bash
chmod 755 nagios_automatizado.sh
```

## Package installation failure

Check repository connectivity and available disk space:

```bash
yum repolist
df -h
```

Review the full output of the failed command. Do not paste credentials,
private IP addresses or sensitive server information into public issues.

## Nagios service does not start

Check the service status and logs:

```bash
systemctl status nagios
journalctl -u nagios --no-pager
```

Validate the configuration:

```bash
nagios -v /usr/local/nagios/etc/nagios.cfg
```

## Apache service does not start

Check the service status and logs:

```bash
systemctl status httpd
journalctl -u httpd --no-pager
tail -f /var/log/httpd/error_log
```

## Web interface is unavailable

Verify that Apache is running:

```bash
systemctl status httpd
```

Verify that the Nagios service is running:

```bash
systemctl status nagios
```

Check firewall rules and network access:

```bash
firewall-cmd --list-all
```

Do not disable SELinux or firewall controls without understanding the
security impact.

## Recovering from a failed installation

- Review the error output.
- Restore backups of modified configuration files.
- Revert package or service changes only if you understand their impact.
- Rebuild the test virtual machine if necessary.
- Do not run destructive cleanup commands without reviewing them first.
