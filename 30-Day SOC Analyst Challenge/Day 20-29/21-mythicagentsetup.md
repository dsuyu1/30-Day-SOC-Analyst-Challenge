# Day 21: Mythic Agent Setup
## Objective
In this section, I will learn how to perform a brute force attack, generate a Mythic agent, and establish C2 (command & control).

## Steps
Firstly, if you can remember, we're going to extract passwords from a file on our Windows server called "passwords.txt." This is for demonstration purposes which is why it's referred to as a "fake" file in the attack diagram. Nonetheless, this will serve as data we will try to exfiltrate from the machine.

This time around, instead of going into the console via Vultr, I'm just going to RDP into the machine. I have no clue why I couldn't figure this out sooner, but here we are! I've learned a lot from this challenge, that's for sure.

<p align="center"><img src="https://i.imgur.com/WugLTVP.png"></p>
<p align="center"><i>Ref 1: Using RDP to connect to our Windows machine to create a file called "passwords.txt" that will serve as our target for the brute force attack we're going to perform!</i></p>
<br>

We're done with the Windows instance for now. Let's go to our Kali machine and start looking at the resources we have on hand.

Kali Linux comes with password dictionaries. We can find them using these commands:

<p align="center"><img src="https://i.imgur.com/mFWVBOH.png"></p>
<p align="center"><i>Ref 2: Preinsalled password dictionaries on Kali.</i></p>
<br>

We're going to be using `rockyou.txt`. As a proof of concept, I'm going to put my Windows machine's password into this text file. I know it's cheating, but since the purpose of this challenge is to learn how to brute force machines and how such attacks work, this is fine for now. As a note, I'm only going to use the top 50 passwords since the actual file is quite large. I used `head -50 rockyou.txt > /home/dsuyu/dsuyu-wordlist.txt` to save those top 50 (+ my Windows password) into the wordlist we'll use for the attack.

We'll be using Crowbar to perform an RDP brute force attack over to our Windows machine. To do this, I used the `crowbar -b rdp -u Administrator -C dsuyu-wordlist.txt -s 155.138.242.206/32` command. `-b` specifies the RDP service, `-u` is the user account, `-C` is the source of our passwords that we want to try to authenticate with, and `-s` specifies the specific IP address I want to use. `/32` means we're only interested in this specific IP address. I won't show the password for now, since somebody seeing the password while I'm still trying to complete the challenge would be problematic, to say the least.

<p align="center"><img src="https://i.imgur.com/M9g2wgK.png"></p>
<p align="center"><i>Ref 3: Crowbar successfully brute-forced the machine.</i></p>
<br>

Now that we have our credentials, we can RDP from our Kali machine by using `xfreerdp`. Running the command `xfreerdp /u:Administrator /p: [password] /v: 155.138.242.206:3389`, we can RDP into the machine.

<p align="center"><img src="https://i.imgur.com/8iFtNp0.png"></p>
<p align="center"><i>Ref 4: I've successfully RDP'd into the machine!</i></p>
<br>

Looking at our attack diagram, once we've established a connection, the next step is to do some recon. For example, we can run the command `net user Administrator` to learn more about our privileges. In a real scenario, an attack might compromise an account, say, for example, "Steven," and they would have to run a command like `net user` to figure out what privileges they have or to what group they belong to. 

Once we've done reconnaissance, we can move to Phase 3: Defense Evasion. I'll turn off Windows Defender via the command line. We could also do this the BORING way by going into Settings and turning everything off.

<p align="center"><img src="https://i.imgur.com/ulBvkwF.png"></p>
<p align="center"><i>Ref 5: Disabling real-time monitoring from the command line.</i></p>
<br>

After Phase 3 follows Phase 4: Execution. In Phase 4, we need to create our Mythic agent and payloads. Any configuration needs to be done within the Mythic CLI.

We're going to be using the Apollo agent for our purposes. We can install it using the command `./mythic-cli install github https://github.com/MythicAgents/Apollo.git`. You can find Apollo's documentation [here](https://github.com/MythicAgents/Apollo).

<p align="center"><img src="https://i.imgur.com/MDsXRQa.png"></p>
<p align="center"><i>Ref 6: Apollo now appears within our web GUI under "C2 profiles and payload types."</i></p>
<br>




