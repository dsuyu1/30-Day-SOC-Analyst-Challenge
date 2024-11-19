# Day 10: Ingesting Data into Elasticsearch
## Steps
The objective for today is to learn how to ingest Sysmon and Windows Defender logs into Elasticsearch.

First, we'll go to our Elastic web GUI and click on the button that says "Add Integrations." From here, we can select all kinds of integrations, but for now, we're only interested in Sysmon and Windows Defender. 

<p align="center"><img src="https://i.imgur.com/wtMFFaB.png"></p>
<p align="center"><i>Ref 1: This custom Windows event log package allows us to ingest events from any Windows event log channel!</i></p>
<br>

We're asked to enter a channel name. To find this, we have to enter into Event Viewer on our Windows machine. We're going to find "Operational" and go into its "Properties." Here, we can find the "Full name," which is the channel name in our case.

<p align="center"><img src="https://i.imgur.com/dpIzfHt.png"></p>
<p align="center"><i>Ref 2: Under "Full Name" is the channel name we're looking for.</i></p>
<br>

We could figure this out thanks to the example Elastic gave us right under where it says "Channel name."
