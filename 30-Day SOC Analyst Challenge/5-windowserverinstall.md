# Day 5: Windows Server 2022 Installation
## Steps
The objective of this section is to have a Windows Server with RDP exposed to the Internet. We'll follow the same process as before to create a server, except this time, we will not include this server within our VPC (virtual private cloud). When the computer is compromised, we want it to be isolated from our private network. 

I'm going to call it **windows2022**.

<p align="center"><img src="https://i.imgur.com/NQyfpYA.png">
<i>Ref 1: Our servers so far.</i></p>
<br>

<p align="center"><img src="https://i.imgur.com/NF2Q2AR.png">
<i>Ref 2: Our Windows server has finished setting up!</i></p>
<br>

## Summary
Today, I got my Windows 2022 server up and running. Notice how I did not assign it to our firewall group like our Ubuntu server. This is because we want it to be vulnerable, specifically to RDP attacks. Right now, our Windows machine is being attacked from the Internet over RDP. Later, we'll investigate these logs, but for now, let's move on to day 6! 🥓
