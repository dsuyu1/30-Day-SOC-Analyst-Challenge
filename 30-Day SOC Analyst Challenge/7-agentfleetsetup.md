# Day 7: Elastic Agent and Fleet Server Setup
## Steps
The objective for today is to install an Elastic Agent on the Windows server and enroll the Windows server into a Fleet.

Like we've done many times already, I'm going to create a new Ubuntu server on Vultr. This server will be our Fleet server. After creating the server, it's time to pay a visit to our web GUI (our elastic/kibana server) and add the Fleet. 

<p align="center"><img src="https://i.imgur.com/76TZbJD.png">
<i>Ref 1: Our servers so far.</i></p>
<br>

Before I do anything in Elastic, I think it's worth noting that I ran into some trouble. I wasn't able to access the web GUI via my web browser, and I started thinking about all the different ways something might've gone wrong. First, I poked around the .yml configuration files and changed some settings here and there to see what would happen. I visited forums online to see if anybody had been running into the same problems. I restarted the services regularly with `systemctl restart` to no avail.

As always, however, the simplest fix was the correct one. My IP address had changed and it wasn't being whitelisted by Vultr's firewall. After whitelisting it, I was able to connect to the web GUI. Lesson learned: start with the simple fixes before poking around what you aren't sure about!

I also made some changes to Elastic (i.e. configured dark mode so it looks cooler).

Anyways, troubleshooting done with, it's time to start making our Fleet. To begin, now within the web GUI, we navigate under Management and select Fleet.

<p align="center"><img src="https://i.imgur.com/L6hdMmU.png"></p>
<p align="center"><i>Ref 2: Creating a Fleet within Elastic</i></p>
<br>

We're prompted for a Fleet name and URL. The URL will be our public IP address. After, we're asked to install the fleet server on a centralized host, aka, the Ubuntu server we just spun up specifically for the Fleet. We'll be connecting using PuTTY like last time.

After running the command, the connection between the Fleet server and our centralized host could not be established. This is because our Elastic server (called `elk` wasn't allowing connections from the Fleet server's public IP. This was causing the connection to never be established. In other words, the Fleet server has to be able to access Elasticsearch. I didn't mention it, but previously, I configured the ELK server's firewall to allow connections on port 9200, the port Elasticsearch listens on by default. I had to configure both the Vultr firewall and the ELK server's firewall for this connection to be established.

Now, our Fleet server is connected and we can continue enrolling our Elastic Agent.

<p align="center"><img src="https://i.imgur.com/nUuMmKy.png"></p>
<p align="center"><i>Ref 3: Adding an agent and creating an agent policy.</i></p>
<br>

This policy is for a Windows machine so we'll select Windows when it asks us to select the appropriate platform.

<p align="center"><img src="https://i.imgur.com/eLVQIKY.png"></p>
<p align="center"><i>Ref 4: Installing the Elastic Agent on our host (Windows Server 2022).</i></p>
<br>

Let's go to our Windows server to install the Elastic Agent. After running the command we were provided, we get an error. Among the error is this line:
`fail to execure request to fleet-server: dial tcp 149.28.246.152:443`. It looks like something is preventing the connection between our Fleet server and Elasticsearch. 

Looking at the documentation from Elastic, the default port from our Elastic Agent towards our Fleet Server is `8220`. While we don't have a firewall on Vultr for our Fleet server, we do have to configure the firewall on the virtual machine itself.

<p align="center"><img src="https://i.imgur.com/w4HYtve.png"></p>
<p align="center"><i>Ref 5: Configuring the firewall for our Fleet server.</i></p>
<br>

Even after allowing connections on port `8220`, we're still getting an error. Let's try allowing connections on port `443` since that's where our Elastic Agent is trying to connect to.

