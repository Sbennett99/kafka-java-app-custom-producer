# kafka-java-app-custom-producer
## What it's for
In this project I created a producer Api for kafka
The producer api is name SethBennettProducer and can be used to look up algorithms for different rubiks cube puzzles

## All commands used

- Start Kafka and ZooKeeper
```powershell
.\bin\windows\kafka-server-start.bat .\config\server.properties
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
- Create a topic 
```powershell
.\bin\windows\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic Rubiks_Cube_Algorithms
```

- clean compile and assemble java classes into fat jar file
```powershell
mvn clean compile assembly:single
```

- Start Producer and Consumer from jar file
```powershell
java -cp target/kafka-java-app-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.bigdataingersoll.Consumer Rubiks_Cube_Algorithms group1
java -cp target/kafka-java-app-1.0-SNAPSHOT-jar-with-dependencies.jar edu.nwmissouri.bigdataingersoll.SethBennettProducer Rubiks_Cube_Algorithms
```
