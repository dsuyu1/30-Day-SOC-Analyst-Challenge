# Day 16: Creating Alerts and Dashboards in Kibana
## Objective
In this section, we'll observe the authentication logs from our Windows server and create a new alert. If you remember, we previously made a dashboard to visualize SSH brute force activity from our Ubuntu server. Now, we'll turn to our Windows server. If you remember, we set up Sysmon and Windows Defender integrations within Elasticsearch. We left it open to RDP brute force attacks. Now, we'll start to look into those logs more deeply.

## Steps
Going into the Discover tab, we'll look at events being generated from our Windows 2022 agent. Similar to how we sorted our table for specific fields, we'll do the same thing here.

<p align="center"><img src="https://i.imgur.com/hwiuaBn.png"></p>
<p align="center"><i>Ref 1: We're sorting for agent.name, source.ip, and user.name.</i></p>
<br>

In the reference above, you can observe that we've sorted our table to show `agent.name`, `source.ip`, and `user.name`. Using this query, let's make a new rule by going up to Alerts.

We'll follow the same process as before. Notably, making rules this way is kind of suboptimal. We should be making rules from the dedicated Rules tab. If we scroll down, under "Stack Management," we can find a tab that says "Rules." Here, we can make much more robust and advanced rules. This is what we'll do this time around.

<p align="center"><img src="https://i.imgur.com/XPWE6n0.png"></p>
<p align="center"><i>Ref 2: Under the Rules section, we can make more robust and advanced rules.</i></p>
<br>

As you can see, I've already made these rules. 

<p align="center"><img src="https://i.imgur.com/zBKJW7M.png"></p>
<p align="center"><i>Ref 3: A detailed view of our RDP brute force rule.</i></p>
<br>

## Summary
In this section, I created a new rule that detects unsuccessful RDP brute force attempts from our Windows 2022 server.
