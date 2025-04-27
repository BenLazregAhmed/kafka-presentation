

## Single Zookeeper / Single Kafka

This configuration fits most development requirements.

 - Zookeeper will be available at `$DOCKER_HOST_IP:2181`
 - Kafka will be available at `$DOCKER_HOST_IP:9092`
 - (experimental) JMX port at `$DOCKER_HOST_IP:9999`

Run with:
```
docker compose -f zk-single-kafka-single.yml up
docker compose -f zk-single-kafka-single.yml down
```

## Multiple Zookeeper / Multiple Kafka

If you want to have three zookeeper nodes and three Kafka brokers to experiment with production setup.

- Zookeeper will be available at `$DOCKER_HOST_IP:2181,$DOCKER_HOST_IP:2182,$DOCKER_HOST_IP:2183`
- Kafka will be available at `$DOCKER_HOST_IP:9092,$DOCKER_HOST_IP:9093,$DOCKER_HOST_IP:9094`

Run with:
```
docker compose -f zk-multiple-kafka-multiple.yml up
docker compose -f zk-multiple-kafka-multiple.yml down
```
## Source

[This README file and the docker-compose files were downloaded from this repository](https://github.com/conduktor/kafka-stack-docker-compose/blob/master/README.md)
