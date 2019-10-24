### Zabbix script - Check Windows RDS host for drain mode

This script will check if an RDS host is set to drain mode

To make this work, do the following:

- Import the template
- Put the file "checkdrainmode.ps1" in your zabbix directory
- Add the following lines to your zabbix agent config:

EnableRemoteCommands=1

UnsafeUserParameters=1

UserParameter=drainmode,powershell -NoProfile -ExecutionPolicy Bypass -File "C:\Zabbix\checkdrainmode.ps1"

The script will check every minute if a host is set to drain and will raise an alert.

I've tested this on Zabbix 3.2 and up.
