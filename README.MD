
## About 
This repo contains demo clusters for testing the Kafka Sonar Docker Desktop Extension. 
With Docker Desktop running, run one of the demo clusters by using the scripts in `package.json` to spin up a 1-, 3-, or 5-broker cluster.
When that cluster is up and running, you can connect to it via Kafka Sonar. Once your demo cluster is up, you can then run the producer, consumer, and mass-producer scripts to simulate a live pub-sub environment.
When connecting Kafka Sonar to a given demo cluster, make sure to enter the following on the Add New Connection:

## Example
If you mean to connect to the 3-broker demo cluster:

- Client ID: (this can be anything)
- Hostname: localhost
- Port: 9091
- Authentication Mechanism: N/A

- Docker network name: 3broker
- Broker 1 Hostname: kafka1
- Broker 1 port: 8081
- Broker 2 Hostname: kafka2
- Broker 2 port: 8081
- Broker 3 Hostname: kafka3
- Broker 3 port: 8081

**If any of the above information is not entered correctly, Kafka Sonar cannot connect to your cluster.**

Client ID is the name Kafka Sonar uses to refer to your cluster. 
Hostname/Port should be the host/port of a seed broker. See [KafkaJS docs](https://kafka.js.org/docs/configuration#broker-discovery).

Docker network name should be the name of the Docker bridge network that you cluster is running on. Kafka Sonar needs this in order to spin up a Prometheus container connected to that network in order to scrape metrics from your cluster.
Broker N Hostname should be the host name of a given broker; Broker N Port should be the port on that broker that is exposing JMX data. In the demo cluster, it is 8081.
