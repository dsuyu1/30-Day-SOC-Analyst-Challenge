# Day 2: Introduction to the ELK Stack
## Introduction
Elasticsearch, Logstash, and Kibana comprise the ELK stack.

### Elasticsearch
Elasticsearch is a database used to store logs, such as Wubdiws event logs, system logs, and firewall logs. It gives us the ability to effectively search across all our data. 

Elasticsearch uses a query languaged called ESQL, Elastic Search Query Langauge. It's beginner-friendly and easy-to-use.

Elasticsearch also uses RESTful APIs and json, which means that we can use various applications to iteract with our Elasticsearch database in a programmable way to retrieve information.

### Logstash
Logstash is a data processing pipeline that ingests data from a multitude of sources, transforms it, and then sends it to our favorite "stash." In other words, it can filter it into our Elasticsearch instance. 

When it comes to collecting telemetry, there are two popular ways to do it: **Beats** and **Elastic Agents**.

There are **six** differnet types of Beats:

- **File** Beats: logs
- **Metric** Beats: metrics
- **Packet** Beats: network data
- **Winlog** Beats: Windows events
- **Audit** Beats: audit data
- **Heartbeats**: uptime
