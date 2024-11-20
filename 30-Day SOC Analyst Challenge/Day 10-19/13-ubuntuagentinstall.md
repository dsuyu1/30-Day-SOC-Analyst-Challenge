# Day 13: Installing an Elastic Agent on Ubuntu
## Steps
The objective of this section is to install an Elastic Agent onto the Ubuntu server we created in the last section (Day 12). This will grant us the capability to view logs generated in our Elasticsearch instance.

<p align="center"><img src="https://i.imgur.com/9kc4SIT.png"></p>
<p align="center"><i>Ref 1: Step 1 is to create a new agent policy for our Ubuntu server.</i></p>
<br>

Within this policy, we can check to see where the logs are going to be pulled from. By default, this is set to `/var/log/auth.log*` and `/var/log/secure*`. This works, as if you can remember from the previous section, we want to view authentication logs. To install the Elastic Agent, we'll go ahead and run the same command we did last time, but instead, the Linux version, making sure to use the flag `--insecure`. Once we've successfully installed the Elastic Agent, we can go to the Discover tab to view our collected logs. We can also view the logs manually within our server within `/var/log/auth.log`.

<p align="center"><img src="https://i.imgur.com/4V9ghKe.png"></p>
<p align="center"><i>Ref 2: Viewing failed authentication attempts from Ubuntu server.</i></p>
<br>

<p align="center"><img src="https://i.imgur.com/qACzLWH.png"></p>
<p align="center"><i>Ref 3: Viewing failed authentication logs from Elasticsearch.</i></p>
<br>

## Summary
In this section, I installed the Elastic Agent onto our Ubuntu server with SSH open and ingested telemetry into our Elasticsearch instance.
