# Day 6: Elastic Agent and Fleet Server Introduction
## Introduction
Elastic Agents collect all forms of data from the endpoint they're installed on with a single unified agent per host. They provide convenience as you can then use a Fleet server to onboard data faster and more easily through centralized management.

Moving data across systems in different formats from different sources is a challenge. With Elastic Agents, we can collect logs, metrics, traces, availability, security, and other forms of data from each host in a single unified way. They can either be standalone or Fleet-managed; we'll be using the latter. Fleets let us update Agent policies easily.

Fleet provides a web-based UI to add and manage agents and integrations providing a secure and easy setup that is centrally managed at scale. 

<p align="center"><img src="https://static-www.elastic.co/v3/assets/bltefdd0b53724fa2ce/bltc4aaa61a860fae21/60fee7d0429fb95880e59fd4/screenshot-central-management-with-fleet.png">
<i>Ref 1: A Fleet server managing different Elastic Agents.</i></p>
<br>

If you remember, previously, I mentioned Beats. Beats are more granular in that you can mix and match the different kinds of Beats based on the type of data you want to collect. Selecting which one to use depends on your use case. You can click [here](https://www.elastic.co/guide/en/fleet/current/beats-agent-comparison.html#additional-capabilities-beats-and-agent) to learn more about the differences and similarities between Beats and Agents.
