# Cargo Tracker

This sample Spring Boot project is used to illustrate the patterns of Domain-Driven Design. 
It is based on the source code<sup id="a1">[1](#f1)</sup> in
Chapter 4 of the book _Practical Domain-Driven Design in Enterprise Java_ with modification.

This Spring Boot project uses Apache Kafka as a messaging platform. 
To run this project, you need to set up Kafka first.

_Note. This project may be updated constantly._

## A Short Guide to Set Up Apache Kafka
### Linux and MacOS
Download a **binary package** of Apache Kafka (e.g., `kafka_2.13-2.8.0.tgz`) from 
[https://kafka.apache.org/downloads](https://kafka.apache.org/downloads)
and upzip it.
In the Terminal, `cd` to the unzip folder, and start Kakfa with the following commands (each in a separate Terminal session):
```bash
./bin/zookeeper-server-start.sh
```
```bash
./bin/kafka-server-start.sh
```

### Windows
Download a **binary package** of Apache Kafka (e.g., `kafka_2.13-2.8.0.tgz`) from 
[https://kafka.apache.org/downloads](https://kafka.apache.org/downloads) 
and unzip it to a directory, e.g., `C:\kafka`&mdash;Windows does not like a complex path name (!).

<!--
In the configuration file `C:\kafka\config\zookeeper.properties`, comment out the line `"dataDir=/tmp/zookeeper"`. In `C:\kafka\config\server.properties`, change the line `"log.dirs=/tmp/kafka-logs"` to `"log.dirs=.kafka-logs"`.
-->

Use the following two commands in the Windows CMD (one in each window) to start Kafka:
```bash
C:\kafka\bin\windows\zookeeper-server-start.bat C:\kafka\config\zookeeper.properties
```
```bash
C:\kafka\bin\windows\kafka-server-start.bat C:\kafka\config\server.properties
```

## View Kafka Topics
After running the `bookingms`'s main class, check the Kafka topics with the following command:

(Linux/MacOS)
```shell
./bin/kafka-topics.sh --bootstrap-server=localhost:9092 --list
```
(Windows)
```shell
.\bin\windows\kafka-topics.bat --bootstrap-server=localhost:9092 --list
```
You should see two topic names `cargobookings` and `cargoroutings`.

### Trouble Shooting
If you cannot start Kafka, try to clean up data in the Kafka topics to start over. 
For this purpose, in Linux/MacOS, delete the folders `/tmp/zookeeper`, `/tmp/kafka-logs` and `/tmp/kafka-streams`. In Windows, delete the folders `C:\kafka\.dataDirzookeeper` and `C:\kafka\.kafka-logs`.


---
<a id="f1">1.</a> GitHub link: 
[https://github.com/practicalddd/practicaldddbook/tree/master/Chapter5](https://github.com/practicalddd/practicaldddbook/tree/master/Chapter5) [↩](#a1)



