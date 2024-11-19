# Day 9: Sysmon Setup
## Steps
The objective for today is to install Sysmon onto our Windows server and confirm that the server is generating telemetry (Sysmon logs).

To start, let's go into our Windows server and download Sysmon. First, let's download the configuration file we'll be using which can be found [here](https://github.com/olafhartong/sysmon-modular/blob/master/sysmonconfig.xml). Next, after downloading Sysmon and extracting the binaries from the .zip file, we'll run the command `.\Sysmon64.exe -i sysmonconfig.xml`. This installs Sysmon using the configuration file we downloaded.

<p align="center"><img src="https://i.imgur.com/GkNk7DT.png"></p>
<p align="center"><i>Ref 1: Sysmon successfully installed.</i></p>
<br>

We can check Services to verify that Sysmon is running and Event Viewer to start viewing our telemetry.

