Run Kafka Cluster with 1 node

```
docker-compose -f docker-compose.yml up -d 
```

Run Kafka Cluster with 3 nodes

```
docker-compose -f docker-compose-cluster.yml
```

Kill kafka cluster

```
docker-compose kill
```

Remove docker containers

```
docker-compose rm -f
```

See docker logs
```
docker-compose logs -f
```

Kafka Commands:

Create a topic

```
kafka-topics --zookeeper localhost:2181 --create --partitions 1 --replication-factor 1 --topic test
```

Produce messages to a topic

```
kafka-console-producer --broker-list localhost:9092 --topic test
```

Consume Topic

```
kafka-console-consumer --bootstrap-server localhost:9092  --topic test  --property print.key=true --from-beginning
```

Show all topics
```
kafka-topics --zookeeper=localhost:2181 --list
```

You can access to the docker kafka container
```
docker exec -it kafka-cluster_kafka_1 sh
```

You can found the data on the following path
```
cd /var/lib/kafka/data
```
