# Day 20: Mythic Server Setup
## Objective
In this section, I'll learn how to set up a Mythic C2 (command & control) server and how Mythic works.

## Steps
Like many times before, we'll make the server in Vultr, this time using Ubuntu 22.04. I didn't know how to SSH into machines before, but now I do (lol)! I'm going to start SSHing through PowerShell instead of PuTTY. Honestly, I have no idea how I didn't figure it out before, it's so easy. Moving on, we'll update the Ubuntu server and whatnot. 

We'll start by downloading some Mythic dependencies (Docker compose and Make) with `apt install docker-compose` and `apt install make`. Then, we'll install Mythic with `git clone https://github.com/its-a-feature/Mythic --depth 1`. These instructions can all be found [here](https://docs.mythic-c2.net/installation). Then, I'll run `./install_docker_ubuntu.sh`, make sure the service is running with `systemctl status docker.service` and `systemctl restart docker.service`. After, we can run `make` and get Mythic started with `./mythic-cli start`. 

Let's tighten up the firewall a little bit to only allow our computer and the other Agents (target machines) to communicate with Mythic. We can do this by only allowing incoming TCP connections from the IP addresses of our target machines. That way, only the agents can communicate with us.

After, we can access our Mythic web GUI using our server's IP address using port 7443 over HTTPS.

<p align="center"><img src="https://i.imgur.com/HUEbqdL.png"></p>
<p align="center"><i>Ref 1: Our Mythic web GUI.</i></p>
<br>

Honestly, this website looks pretty sketchy haha 😆 I'm excited to get started!

## Summary
In the next few sections, I'll be using Kali Linux to attack our target machines, generate a payload, and generate our Mythic Agents. See you then!
