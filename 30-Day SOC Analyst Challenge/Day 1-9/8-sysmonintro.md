# Day 8: Intro to Sysmon
## Introduction
In Windows, logging is enabled by default. However, this default is not enough. We use Sysmon to help us go above and beyond when it comes to logging events. Sysmon is a free Microsoft tool and can monitor lots of different types of events, such as:

- Process creations
- Network connections
- File creations
- etc!

According to the [website](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon), Sysmon has the capability to:

- Log process creations along with the command line for both current and parent processes.
- Records the hash of process image files so we can use OSINT to find if anything similar has already been documented!
- Capture network connections, including source IP, destination IP, ports, and process!

As a side note, logging network connections is disabled by default, and we must enable it.

In the current version of Sysmon, v15.5, there are **30** different event IDs. Here are a few that Steven (the guy I'm following) mentioned:

- Event ID 1, Process creation
- Event ID 3, Network connection
- Event ID 6/7/8, Driver/Image Load and CreateRemoteThread
- Event ID 10, ProcessAccess
- Event ID 22: DNSEvent (DNS query)

We can create rules in an `.xml` file to whitelist or exclude some events so that we don't get overwhelmed. SIEMs are also expensive and targeting only what we want is valuable.

On day 9, we'll install Sysmon using a popular configuration. See you there!

