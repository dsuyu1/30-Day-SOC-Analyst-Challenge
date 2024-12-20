# Day 9: Sysmon Setup
## Objective
The objective for today is to install Sysmon onto our Windows server and confirm that the server is generating telemetry (Sysmon logs).

## Steps
To start, let's go into our Windows server and download Sysmon. First, let's download the configuration file we'll be using which can be found [here](https://github.com/olafhartong/sysmon-modular/blob/master/sysmonconfig.xml). Next, after downloading Sysmon and extracting the binaries from the .zip file, we'll run the command `.\Sysmon64.exe -i sysmonconfig.xml`. This installs Sysmon using the configuration file we downloaded.

<p align="center"><img src="https://i.imgur.com/GkNk7DT.png"></p>
<p align="center"><i>Ref 1: Sysmon successfully installed.</i></p>
<br>

We can check Services to verify that Sysmon is running and Event Viewer to start viewing our telemetry.

<p align="center"><img src="https://i.imgur.com/hMTuXYq.png"></p>
<p align="center"><i>Ref 2: Looking at Event Viewer, we can see that we are generating telemetry!</i></p>
<br>

## Summary
A short day today, all I did was install Sysmon using a popular configuration onto our Windows server.
