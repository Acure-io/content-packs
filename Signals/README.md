# Acure Event Processing Scenarios (deduplication)

[Processing scenario](Zabbix%20Webhook%20Signal%20Processor.txt) for events from Zabbix, recieved via Zabbix Webhook.

[Processing scenario](Zabbix%20Default%20Signal%20Processor.txt) for events from Zabbix for standard Data Stream using Zabbix Default Template.

[Processing scenario](SCOM%20Signals%20processor.txt) for events from SCOM:

* Filtration of the events in the scenario is executed by the name of the stream (e.g. SCOM).
* Before creating a signal scenario tries to find a CI with the ScomObjectPath label (ObjectPath field in the primary event). 
* If a CI with such a label is not found, the signal will be created without binding the CI.
