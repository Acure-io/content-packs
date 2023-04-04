# Acure Content Packs

## CMDB Autobuild

Examples of CMDB Autobuild Scenarios

| Name                                            | Section                                |
|-------------------------------------------------|----------------------------------------|
| Zabbix groups and hosts autobuild scenarios     | [Zabbix](./CMDB%20Autobuild/Zabbix/)   |
| VCenter topology autobuild scenario             | [vCenter](./CMDB%20Autobuild/vCenter/) |


## Signals

Examples of Event Deduplication & Correlation Scenarios

| Monitoring Syste   | Scenario                                                                                                     |
|--------------------|----------------------------------------|
| Zabbix             | [Scenario for Data Stream using Zabbix default template](./Signals/Zabbix%20Default%20Signal%20Processor.txt)|
| Zabbix             | [Scenario for Data Stream using Default Template](./Signals/Zabbix%20Webhook%20Signal%20Processor.txt)       |


### Zabbix

Processing scenarios for events from Zabbix

#### Scenario for Data Stream using Zabbix default template

[Zabbix Default Processor](./Signals/Zabbix%20Default%20Signal%20Processor.txt)

#### Scenario for Data Stream using Default Template

> Zabbix should be configured to send events as [WebHook](https://docs.acure.io/current/en/solutions/integrations/#example-of-zabbix-integration-via-webhook)

[Zabbix Webhook Processor](./Signals/Zabbix%20Webhook%20Signal%20Processor.txt)

### SCOM

Event processing scenario for events from SCOM (System Center Operations Manager)

[SCOM Signal Processor](./Signals/SCOM%20Signals%20processor.txt)
