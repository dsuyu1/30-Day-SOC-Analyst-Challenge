# Day 24: osTicket Setup
## Objective
In today's section, I'll be learning how to set up osTicket, a popular open-source ticketing system. 

## Steps

<p align="center"><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Xampp_logo.svg/402px-Xampp_logo.svg.png"></p>
<br>

We're going to deploy a brand new Windows machine. To get started, we're going to host this ticketing system on a web server. Therefore, we're going to use XAMPP from Apache.

Once installed, I'll navigate to the Properties file under the XAMPP directory. Here, we can right-click the `properties` file to edit the settings. For example, first, I'll change the Apache domain name from `localhost` (127.0.0.1) to our public IP address.

I'll also make edits to the `phpMyAdmin` configuration file. The only change I'll make is also changing `localhost` to our virtual machine's IP ONLY AFTER allowing it once logging as Admin in via the XAMPP console.

We'll also create an endpoint firewall rule.

<p align="center"><img src="https://i.imgur.com/Lai4tFh.png"></p>
<p align="center"><i>Ref 1: Using Windows Firewall to create a new rule.</i></p>
<br>

<p align="center"><img src="https://i.imgur.com/cZYDoRe.png"></p>
<p align="center"><i>Ref 2: Our new firewall rule.</i></p>
<br>

Once that's all set up, we can start installing osTicket by navigating to the webiste and downloaded the correct version. Once extracted, I'll create a new directory within the `C:\xampp\htdocs` file path called `osTicket`. I'll paste the extracted files here.

<p align="center"><img src="https://i.imgur.com/VN6Csb3.png"></p>
<p align="center"><i>Ref 3: Created a new directory to host my osTicket files.</i></p>
<br>

Heading to `[ip]/osticket/upload` in our web browser, we are greeted with a page where we can start configuring our osTicket web server.

Before installing osTicket, we need to create a database via the phpMyAdmin control panel. I'll name this database `dsuyu-30-Day`. Once created, we can head back to the set up page for osTicket. Once created, we only have to run `icacls \ost-config.php /reset` in Powershell to change permissions. 

<p align="center"><img src="https://i.imgur.com/RE9V9DF.png"></p>
<p align="center"><i>Ref 4: We've successfully installed osTicket.</i></p>
<br>

Once installed, clients can now access the client page to submit tickets and we as agents can log in via the staff control panel. 

## Summary
In this section, I created an osTicket web server for clients to submit tickets and for agents (me) to review them. 
