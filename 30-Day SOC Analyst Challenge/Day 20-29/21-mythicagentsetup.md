# Day 21: Mythic Agent Setup
## Objective
In this section, I will learn how to perform a brute force attack, generate a Mythic agent, and establish C2 (command & control).

## Steps
Firstly, if you can remember, we're going to extract passwords from a file on our Windows server called "passwords.txt." This is for demonstration purposes which is why it's referred to as a "fake" file in the attack diagram. Nonetheless, this will serve as data we will try to exfiltrate from the machine.

This time around, instead of going into the console via Vultr, I'm just going to RDP into the machine. I have no clue why I couldn't figure this out sooner, but here we are! I've learned a lot this challenge, that's for sure.

<p align="center"><img src="https://i.imgur.com/WugLTVP.png"></p>
<p align="center"><i>Ref 1: Using RDP to connect to our Windows machine to create a file called "passwords.txt" that will serve as our target for the brute force attack we're going to perform!</i></p>
<br>
