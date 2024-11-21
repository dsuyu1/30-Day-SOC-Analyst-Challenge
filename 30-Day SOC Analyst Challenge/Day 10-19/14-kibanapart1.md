# Day 14: Creating Alerts and Dashboards in Kibana
## Objective
The objective of this section is to create SSH brute force alerts and a dashboard to visualize where the attacks are sourcing from.

## Steps
To start, we want to query for the specific events we're interested in. That is:

- Failed attempts
- User
- Source IP

For now, we're only interested in our SSH server (the Ubuntu server we just set up). We're going to filter for these logs. When it comes to a brute force attack, the first thing we're looking for are failed authentications. Let's look at these events first.

<p align="center"><img src="https://i.imgur.com/7UCZ4Mi.png"></p>
<p align="center"><i>Ref 1: Searching only for failed authentication attempts.</i></p>
<br>

On the left-hand side under the Discover tab, there are lots of different field names we can query for. We can first sort for only events coming from the Ubuntu server, and then start adding the field names as columns in our table. These columns provide the data we want. These available fields are what we are going to be working with specifically.

The field `system.auth.ssh.event` gives authentication events related to SSH - this is what we want.
The field `user.name` gives us the username that was entered in the SSH session.
The field `source.ip` gives us the source IP address.
For fun, we can add `source.geo.country_name` to give us the source IP's country.

Within our table, we can sort for a specific value within a field by hovering over the value we want and selecting the plus (+) icon.

Now that we have the query ready, we should save it.

To create an alert, we select the Alerts tab at the top right. Under here, our rule has already been filled out since we made a new alert while our query was up. We can change the rule's setting if we want to.

Next, we want to create a dashboard so that we can visualize where the attacks are sourcing from. First, we navigate to Map since I'll be created a heat map of sorts for accepted and failed SSH activity. Under Maps, select the blue button that says Add Layer. Since we want a heatmap, I'll select the Choropleth option. I had some trouble making a data view, but it's important not to overthink things when it comes to these labs and to just trial and error. After all, the purpose of this challenge is to learn!

I made a new data view called SSH Brute Force Activity. We can think of this as where the data is being pulled from. Under Join field, what we want is the country for this map. So, we'll select the field `source.geo.country_iso_code`. And we're done! It's as simple as that. We can go ahead and save this map out and add it to a dashboard.

We can rinse and repeat this process for "Accepted" authentication attempts.

<p align="center"><img src="https://i.imgur.com/gGcJIHx.png"></p>
<p align="center"><i>Ref 2: Our dashboard that monitors SSH activity.</i></p>
<br>
