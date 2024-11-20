# Day 10: Ingesting Data into Elasticsearch
## Objective
The objective for today is to learn how to ingest Sysmon and Windows Defender logs into Elasticsearch.

## Steps
First, we'll go to our Elastic web GUI and click on the button that says "Add Integrations." From here, we can select all kinds of integrations, but for now, we're only interested in Sysmon and Windows Defender. 

<p align="center"><img src="https://i.imgur.com/wtMFFaB.png"></p>
<p align="center"><i>Ref 1: This custom Windows event log package allows us to ingest events from any Windows event log channel!</i></p>
<br>

We're asked to enter a channel name. To find this, we have to enter into Event Viewer on our Windows machine. We're going to find "Operational" and go into its "Properties." Here, we can find the "Full name," which is the channel name in our case.

<p align="center"><img src="https://i.imgur.com/dpIzfHt.png"></p>
<p align="center"><i>Ref 2: Under "Full Name" is the channel name we're looking for.</i></p>
<br>

We could figure this out thanks to the example Elastic gave us right under where it says "Channel name."

<p align="center"><img src="https://i.imgur.com/OU0JvMo.png"></p>
<p align="center"><i>Ref 3: The integration has been added to our policy!</i></p>
<br>

Now that the integration has been added, let's do the same for Windows Defender. By using Event Viewer and navigating to Operational, we can see our Windows Defender logs as well as the channel name we're looking for. However, we do not want to ingest all the logs. Some of them are informational, such as a healthy system check-up. This information is nice to know, but we don't want to ingest it into our SIEM. Remember, ingestion costs money (in a production environment), and we do not want to incur extra costs that could be avoided.

For our purposes, we will only want to ingest event IDs 1116 (MALWARE_DETECTED), 1117 (ACTION_TAKEN), and 5001 (RTP_DISABLED). 

<p align="center"><img src="https://i.imgur.com/Q4wDI0l.png"></p>
<p align="center"><i>Ref 4: After disabling Real-Time Protection (RTP), event ID 5001 is produced (please ignore the Grammarly icon haha).</i></p>
<br>

Similar to the previous integration, we're going to provide the channel ID, which in this case is `Microsoft-Windows-Windows Defender/Operational`. However, heading under Advanced Options, we can specify which event IDs in particular we are interested in.

<p align="center"><img src="https://i.imgur.com/gDv3xjY.png"></p>
<p align="center"><i>Ref 5: Configuring our integration so that it only looks for certain event IDs.</i></p>
<br>

<p align="center"><img src="https://i.imgur.com/JXSpm6t.png"></p>
<p align="center"><i>Ref 6: Now we have two integrations connected to our policy!</i></p>
<br>

Let's go over to our Discover tab to see if we're ingesting logs! Spoiler alert: we do!

<p align="center"><img src="https://i.imgur.com/C7mNdVL.png"></p>
<p align="center"><i>Ref 7: We are now ingesting logs from our Windows server into Elastic!</i></p>
<br>

The reference above is for event ID 1 from Sysmon (process creation), but we can also search for Windows Defender logs!

<p align="center"><img src="https://i.imgur.com/3rO3XQD.png"></p>
<p align="center"><i>Ref 8: Ingesting event ID 5001 logs from Windows Defender.</i></p>
<br>

## Summary
In this section, I successfully ingested Sysmon and Windows Defender logs into Elasticsearch. I learned how to add integrations and create policies. See you on Day 11!
