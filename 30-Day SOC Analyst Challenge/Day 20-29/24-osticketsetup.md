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




