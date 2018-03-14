# zabbix Netgear ReadyNAS SNMP template

## Zabbix template for monitoring Netgear ReadyNAS devices with firmware 6.9.x

Written by andre@schild.ws


## Known Problems
- The ReadyNAS firmware has a know bug which results in -1 temperature values
  for the disks.
  In the template we fixed this to only allow unsigned values, so negative values
  are ignored.
  The sideeffect of this, is that the disk termperature items can get
  disabled for a monitoring cycle, until zabbix retrys the item