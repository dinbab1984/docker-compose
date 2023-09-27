# Pre-requisite
Install docker on your machine
# Kafka

Run the following command to start the kafka
````docker-compose -f kafka.yml up -d````

Run the following command to test the zookeeper connection via Powershell
````tnc localhost -port 2181````

Run the following command to test the kafka broker connection via Powershell
````tnc localhost -port 29092````

Testing producer and consumer with test topic
create test topic : ````docker exec kafka kafka-topics --create --topic kafkaTest --partitions 1 --replication-factor 1 --bootstrap-server kafka:9092````

publish messages to test topic : ````docker exec -it kafka kafka-console-producer --topic kafkaTest --broker-list kafka:9092````

consume messages from test topic : ````docker exec -it kafka kafka-console-consumer --topic kafkaTest --from-beginning --bootstrap-server kafka:9092````
list all topics : ````docker exec kafka kafka-topics --list --bootstrap-server kafka:9092````

Run the following command to shutdown the kafka
````docker-compose -f kafka.yml down````

# Flink

Run the following command to start the flink on session mode
````docker-compose -f flink.yml up -d````

Run the following command to test the connection via Powershell
````tnc localhost -port 8081````

Once you’ve started Flink on Docker, you can access the Flink Web UI on http://localhost:8081

Run the following command to shutdown the flink
````docker-compose -f flink.yml down````

# Postgres

Run the following command to start the flink on session mode
````docker-compose -f postgres.yml up -d````

Run the following command to test the connection via Powershell
````tnc localhost -port 5432````

Run the following command to shutdown the flink
````docker-compose -f postgres.yml down````
