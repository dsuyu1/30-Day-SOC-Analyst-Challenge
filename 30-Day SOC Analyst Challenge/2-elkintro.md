# Day 2: Introduction to the ELK Stack
## Introduction
Elasticsearch, Logstash, and Kibana comprise the ELK stack.

## Elasticsearch
**Elasticsearch** is a database used to store logs, such as Windows event logs, system logs, and firewall logs. It gives us the ability to effectively search across all our data. 

Elasticsearch uses a query language called ESQL, Elastic Search Query Language. It's beginner-friendly and easy to use.

Elasticsearch also uses RESTful APIs and json, which means that we can use various applications to iteract with our Elasticsearch database in a programmable way to retrieve information.

## Logstash
**Logstash** is a data processing pipeline that ingests data from a multitude of sources, transforms it, and then sends it to our favorite "stash." In other words, it can filter it into our Elasticsearch instance. 

When it comes to collecting telemetry, there are two popular ways to do it: **Beats** and **Elastic Agents**.

There are **six** different types of Beats:

- **File** Beats: logs
- **Metric** Beats: metrics
- **Packet** Beats: network data
- **Winlog** Beats: Windows events
- **Audit** Beats: audit data
- **Heartbeats**: uptime
Depending on the telemetry we want to connect, we would install the appropriate Beat.

Another way to collect telemetry is through Elastic Agents. Rather than multiple Beats, we can use one unified Agent. This is what we will be using for the 30-day challenge.

After configuring Logstash, our Windows machines would then be able to send telemetry using either a Winlog Beat or an Elastic Agent.

Logstash can filter logs that meet certain criteria. For example, if we have a specific event ID we're looking for, we can **only** send those through to Elasticsearch, reducing costs of ingestion and allowing us to ingest only the stuff we want, like source IP (srcip) and signature.

Logstash can also parse data, which means it can map a keyword within a log which will act as a field value to a field name.

## Kibana
Kibana gives us the luxury to query for our logs stored within our Elasticsearch instance. Kibana has lots of features, including Kibana Lens. Kibana Lens gives us visualization capabilities where we can drag and drop elements to build our dashboards.

### ELK Similarities to Splunk
**Elasticsearch** acts as our Indexer/Search Head.

**Logstash** is our Heavy Forwarder.

**Kibana** is our Web GUI.

**Beats/Agents** are our Universal Forwarders.

## Benefits of Using ELK
### 1. Centralized Logging
- Allow us to meet compliance requirements and sift through data if a security incident occurs

### 2. Flexibility
- We can customize our ingestion whether we use Beats or Elastic Agents. We can be flexible with what telemetry enters our Elasticsearch instance using Logstash.

### 3. Visualizations
- We can create visualizations that let us observe important information at a glance.

### 4. Scalability
- ELK is easy to configure to handle larger environments

### 5. Ecosystem
- If we can't find exactly what we're looking for, there are many integrations and a rich community.

Many of the SIEMs out there are built on the ELK stack. The more comfortable I am using ELK, the better I'll transition into using the other SIEMs.



