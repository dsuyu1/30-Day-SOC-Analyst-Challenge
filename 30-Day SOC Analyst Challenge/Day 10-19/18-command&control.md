# Day 18: Introduction to Command and Control
## Objective
In this section, I am to learn more about a C2 (command and control), why it's important, what are some of the tools/frameworks, and what is Mythic and how it works.

## Introduction
When we download a malicious executable, what happens in the background? A series of commands might run to **discover** more about who we are. For example, `ipconfig`, `whoami`, `nslookup`, `net user`, and many more. **Persistence** might occur in the form of a service creation or scheduled task. However, there is one action that the majority of malware performs. That is: a **command and control** action.

## What is command and control?
According to the [MITRE ATT&CK](https://attack.mitre.org/tactics/TA0011/) framework:

> Command and Control is when an adversary is trying to communicate with compromised systems to control them. Command and Control consists of techniques that adversaries may use to communicate with systems under their control within a victim network. Adversaries commonly attempt to mimic normal, expected traffic to avoid detection. There are many ways an adversary can establish command and control with various levels of stealth depending on the victim’s network structure and defenses.

In other words, Command and Control is where a threat actor establishes control over the victim's computers. 

Establishing a C2 is important because it allows them access to further pursue their goal (credential access, execute ransomware, etc.). 

Based on the MITRE ATT&CK framework, there are a total of 18 different techniques a threat actor could use to establish a command and control session.

## Common tools and frameworks
For now, we'll just be going over four:

- Metasploit
- Cobalt Strike
- Sliver
- Mythic

In this challenge, we'll be looking at **Mythic**.
