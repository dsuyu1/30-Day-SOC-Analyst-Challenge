# Day 17: Creating Alerts and Dashboards in Kibana
## Objective
The objective for this section is to create a dashboard for the RDP activity generated from our vulnerable Ubuntu server.

## Steps
I used the query `agent.name: windows2022 and event.code: 4624 and (winlog.event_data.LogonType: 10 or winlog.event_data.LogonType: 7)` to filter for successful RDP connections, and `agent.name: windows2022 and event.code: 4625` to filter for unsuccessful RDP attempts. 

- Event ID 4625 represents an unsuccessful login.
