# zabbix Netgear ReadyNAS SNMP template

## Zabbix template for monitoring Netgear ReadyNAS devices with firmware 6.9.x

Written by andre@schild.ws

## Features
- LLD of disks, fans, temperature sensors, volumes, partitions, inetrfaces and processors
- Creation of graph and triggers
- No need to deploy MIB files to servers/agents, we work with direct OID's

## How to install
- If you don't have the default snmp templates installed, install them from here:
  https://www.zabbix.org/wiki/Zabbix_Templates/Official_Templates
- Import the template in Zabbix
- Assign it to your devices
- Enable SNMP on the device(s) and set a password
- Configure the password in the macro part of the device
- Make sure that your zabbix server or proxy hast SNMP agent enabled

## Known Problems
- The ReadyNAS firmware has a know bug which results in -1 temperature values
  for the disks.
  In the template we fixed this to only allow unsigned values, so negative values
  are ignored.
  The sideeffect of this, is that the disk termperature items can get
  disabled for a monitoring cycle, until zabbix retrys the item