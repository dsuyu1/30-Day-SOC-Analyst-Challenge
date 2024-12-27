# Day 25: osTicket + ELK Integration
## Objective
This section aims to integrate osTicket with ELK and send a test alert into osTicket.

## Steps

<p align="center"><img src="https://i.imgur.com/R0lVZQP.png"></p>
<p align="center"><i>Ref 1: Creating an API key within osTicket.</i></p>
<br>

The first step is to navigate to the osTicket Admin Panel so we can manage our API keys. Because we want to integrate osTicket with our ELK server, we'll be needing an API key from our osTicket server to serve as a connector within our ELK instance.

<p align="center">
  <img src="https://i.imgur.com/M6613kJ.png">
  <img src="https://i.imgur.com/83xlIOI.png">
</p>
<p align="center"><i>Ref 2 & 3: Creating an connector within Elastic.</i></p>
<br>


Once we have that API key, we can create a new connector. Because our servers are within the same VPC 2.0 network, we should be able to communicate between them via private IP addressing. I made some configurations within our ELK server so that would be possible. Once the IP address for the ELK server has been configured, the ELK server and osTicket instance can now communicate.

<p align="center"><img src="https://i.imgur.com/zgZy83m.png"></p>
<p align="center"><i>Ref 4: The connection has been made!</i></p>
<br>

## Summary
<p align="center"><img src="https://i.imgur.com/wJw4ZSM.png"></p>
<br>

Once the connector has been created and the connection has been successfully established, we now have a fully functioning mock SOC environment. 
