# Day 12: SSH Server Installation
## Steps
Our objective today is to set up a new server that will act as our vulnerable SSH server. As always, I'll be making the server through Vultr.

Once we're done updating and upgrading Ubuntu, we'll change to the directory where authentication logs are stored: `/var/log`. In `auth.log` we can see authentication logs. What we're looking for are failed log in attempts. We can search for them using `grep -i failed auth.log`.

## Summary
In this section, I created my vulnerable Ubuntu machine. On Day 13, I will install an Elastic Agent onto this server. ☄️
