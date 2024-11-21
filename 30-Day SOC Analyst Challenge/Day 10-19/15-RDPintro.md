# Day 15: Introduction to Remote Desktop Protocol (RDP)
## Introduction
The objective of this section is to learn about RDP, why it is used, how attackers abuse it, and how to find endpoints with exposed RDP.

### What is RDP?
Remote Desktop Protocol (RDP) is used for communication between the terminal server and the terminal client. Users can remotely connect to their endpoints without having to physically go to where their endpoints are located. It makes everything more accessiblee and convienent. However, 90%, of randomware breaches involved RDP abuse. 
One of the main ways an attacker can gain unauthrozied access into a network is by an exposed RDP service. Attackers can authenticate using a phished account or brute forcing their way into the server. They can then dump credentials or move laterally within the network.

### How to find exposed RDP servers
Shodan.io is a great tool for finding servers that have an exposed port 3389. We should disable the default RDP port (3389) if it's not needed or in use.
Just because port 3389 is open, that doesn't necessarily mean that RDP is running on that port. 

Censys is another tool that can let us find hosts with exposed RDP ports. 

### How to protect ourselves

1. Turn off RDP if it isn't needed.
2. Use MFA to provide an additional layer of security.
3. Restrict access. This can be done by implementing firewall rules to only allow certain IP addresses to connect.
4. Better passwords are always a plus.
5. Change default credentials! Change your username and passwords after spinning up a server!

## Summary
This section was simply an introduction to RDP. In the next section, we'll be looking at the RDP logs our server generated. See you there!
