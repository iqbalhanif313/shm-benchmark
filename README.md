# This is a forked version from The OpenMessaging Benchmark Framework

This repository houses user-friendly, cloud-ready benchmarking suites for the following messaging platforms:

* [Apache Kafka](https://kafka.apache.org)
* [Apache RocketMQ](https://rocketmq.apache.org)
* [RabbitMQ](https://www.rabbitmq.com/)
* [Apache Pulsar](https://pulsar.apache.org)
* [NATS Streaming](https://nats.io/)

> More details could be found at the [official documentation](http://openmessaging.cloud/docs/benchmarks/).

## Prerequisites:
- Java version: 22
- Apache Kafka Cluster ([implementation](https://github.com/iqbalhanif313/shm-blueprint/blob/main/deployment/docker/docker-compose.yaml))
- RabbitMQ Cluster ([implementation](./rabbit-cluster/docker-compose.yml))

## How to Use:

### Install maven packages
```shell
mvn clean verify -DskipTests
## install all of the packages while skipping test
```

### How to run:

```shell
bin/benchmark --drivers {driver}  {workloads file} --output {output files}
```
example:
```shell
bin/benchmark --drivers driver-kafka/kafka-sync-group-all-throughput.yaml  workloads/1-topic-100-partitions-1kb-4-producers-75k-rate.yaml --output output.json
```

### Notes:
* Kafka drivers are on the /driver-kafka folder
* RabbitMQ drivers are on the /rabbit-mq folder
* The workloads are on the /workloads folder
* The previous result are on /result folder
