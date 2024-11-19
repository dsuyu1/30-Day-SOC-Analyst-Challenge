# Day 4: Kibana Setup
## Steps
Using the same VM from last time (where we installed Elasticsearch). Similar to how we installed Elasticsearch, we'll use `wget https://artifacts.elastic.co/downloads/kibana/kibana-8.16.0-amd64.deb
` to download Kibana and `dpkg -i kibana-8.15.0-amd64.deb`.

We need to make sure we have made the necessary changes to the `kibana.yml` file (uncommenting the server port and host) so we can start the service similar to what we did with Elasticsearch.


<p align="center"><img src="https://i.imgur.com/xffeSIZ.png"></p>
<p align="center"><i>Ref 1: Starting the Kibana service.</i></p>
<br>

Before we move on, we need to create an Elasticsearch enrollment token for Kibana. We can do this by navigating to `/usr/share/elasticsearch/bin` and running the enrollment token creation program with `./elasticsearch-create-enrollment-token --scope kibana`. We'll copy and paste the generated token into Kibana.

Once we have that token, we can access our Kibana instance by going to `http://45.32.194.137:5601/` (our public IP address + the port on which the Kibana service is running). Just like this, we will not be able to access Kibana. First, we must configure our group firewall on Vultr to allow TCP connections on ports 1-65535 from my IP address. Secondly, we must configure the Ubuntu firewall to allow port connections on 5601. We can do this using the `ufw allow 5601` command. 

<p align="center"><img src="https://i.imgur.com/RCWrCS5.png"></p>
<p align="center"><i>Ref 2: Configuring our Vultr firewall.</i></p>
<br>

After configuring our firewalls, we can access Kibana. We are prompted for our enrollment token, and then we're prompted with a verification code—nothing too complicated.

<p align="center"><img src="https://i.imgur.com/m1EduPe.png"></p>
<p align="center"><i>Ref 3: Getting prompted for our enrollment token.</i></p>
<br>

<p align="center"><img src="https://i.imgur.com/kNuzG6G.png"></p>
<p align="center"><i>Ref 4: Login page.</i></p>
<br>

Now, we're prompted with a username and password. Remember those security details I mentioned earlier? Good thing we saved them because we'll be needing them now.

<p align="center"><img src="https://i.imgur.com/NiYTPNs.png"></p>
<p align="center"><i>Ref 5: Welcome page!</i></p>
<br>

<p align="center"><img src="https://i.imgur.com/dnYpdSc.png"></p>
<p align="center"><i>Ref 6: Homepage.</i></p>
<br>

After being greeted by the homepage, I'll navigate to **Alerts**. We're going to set some "persistent keys." I honestly do not know what these are exactly, but according to Elastic, "a new encryption key is generated for saved objects each time you start Kibana. Without a persistent key, you cannot modify rules after Kibana restarts." We can create our encryption keys by running a program within the `/user/share/kibana/bin` directory called `kibana-encryption-keys`. After, we'll want to store these keys within `kibana-keystore`. 

## Summary
In this section, I successfully installed Kibana. In the next section, I will be installing a 2022 Windows Server. See you there! ☄️
