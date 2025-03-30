# Kafka Cluster Docker Compose Setup

![Docker](https://img.shields.io/badge/Docker-27.2.0-orange)
![Docker Compose](https://img.shields.io/badge/Docker%20Compose-v1.29.2--desktop.2-orange)
![Kafka](https://img.shields.io/badge/Kafka-red)

## Overview
This setup provides a Kafka cluster using KRaft mode (ZooKeeper-free) with 3 brokers. Each broker is configured as both a broker and a controller, using plaintext communication and supporting automatic topic replication.

## Checking Out the Repository
To clone the repository, use the following command:
```bash
git clone git@github.com:luismr/kafka-cluster-docker-compose.git
```

## Configuration
- **KAFKA_KRAFT_CLUSTER_ID**: Unique identifier for the Kafka cluster.
- **KAFKA_NODE_ID**: Unique ID for each broker.
- **KAFKA_PROCESS_ROLES**: Configures the broker to act as both a broker and a controller.
- **KAFKA_LISTENERS**: Defines the internal and external listeners for each broker.
- **KAFKA_LISTENER_SECURITY_PROTOCOL_MAP**: Specifies the security protocol for each listener (plaintext).
- **KAFKA_INTER_BROKER_LISTENER_NAME**: Specifies the listener used for inter-broker communication.
- **KAFKA_CONTROLLER_LISTENER_NAMES**: Specifies the listener used for controller communication.
- **KAFKA_ADVERTISED_LISTENERS**: Advertises the listener addresses for client connections.
- **KAFKA_LOG_DIRS**: Directory where Kafka logs are stored.
- **KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR**: Sets the replication factor for the offsets topic.
- **KAFKA_TRANSACTION_STATE_LOG_REPLICATION_FACTOR**: Sets the replication factor for the transaction state log.
- **KAFKA_TRANSACTION_STATE_LOG_MIN_ISR**: Minimum in-sync replicas for the transaction state log.

## Running the Kafka Cluster
To start the Kafka cluster, use the following command:
```bash
docker-compose up -d
```
This command will start all the services defined in the `docker-compose.yml` file in detached mode.

## Stopping the Kafka Cluster
To stop the Kafka cluster, use the following command:
```bash
docker-compose down
```
This command will stop and remove all the containers defined in the `docker-compose.yml` file.

## Removing the Kafka Cluster
To remove the Kafka cluster and its associated volumes, use the following command:
```bash
docker-compose down -v
```
This command will stop the containers and remove the volumes, ensuring that all data is deleted.

## Adding New Nodes
To add a new broker node:
1. Copy the configuration of an existing broker in the `docker-compose.yml` file.
2. Update the `KAFKA_NODE_ID` and listener ports to unique values.
3. Add the new broker service to the `docker-compose.yml`.

## Contributing
To contribute to this project:
1. Fork the repository on GitHub.
2. Create a new branch for your feature or bug fix.
3. Commit your changes and push them to your fork.
4. Submit a pull request to the main repository.

We welcome contributions and improvements to this setup! 