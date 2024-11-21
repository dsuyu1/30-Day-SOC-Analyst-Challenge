# Day 17: Creating Alerts and Dashboards in Kibana
## Objective
The objective for this section is to create a dashboard for the RDP activity generated from our vulnerable Ubuntu server.

## Steps
If you remember, last time, to create a dashboard, I went to Maps and made a new map to add to my dashboard. The process is simple, and I repeated the same thing here.

<p align="center"><img src="https://i.imgur.com/5YVrtgN.png"></p>
<p align="center"><i>Ref 1: Saving a map from the Maps tab.</i></p>
<br>

I used the query `agent.name: windows2022 and event.code: 4624 and (winlog.event_data.LogonType: 10 or winlog.event_data.LogonType: 7)` to filter for successful RDP connections, and `agent.name: windows2022 and event.code: 4625` to filter for unsuccessful RDP attempts. 

- Event ID [4625](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/auditing/event-4625) represents an unsuccessful login.
- Event ID [4624](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-10/security/threat-protection/auditing/event-4624) represents a successful login.

When it comes to event ID 4624, there are specific logon types we're looking for:

- Logon type 3 `Network`: Network connection.
- Logon type 7 `Unlock`: The workstation was unlocked.
- Logon type 10 `RemoteInteractive`: A user logged on to this computer remotely using Terminal Services or Remote Desktop.

<p align="center"><img src="https://i.imgur.com/PwuDEWj.png"></p>
<p align="center"><i>Ref 2: Our dashboard as of now.</i></p>
<br>
