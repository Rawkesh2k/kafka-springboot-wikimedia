Project Overview:
=================
This repository contains a multi-module project for real-time data streaming using Apache Kafka. The project is divided into two main modules:
Kafka Producer
Kafka Consumer

Kafka Producer:
---------------
The Kafka Producer module is responsible for producing real-time stream data from Wikimedia and publishing it to a Kafka topic. This module implements the necessary Kafka producer functionalities to handle data ingestion from the Wikimedia API.

Kafka Consumer:
---------------
The Kafka Consumer module consumes real-time stream data from the Kafka topic and writes it to a MySQL database. This module implements the Kafka consumer functionalities required to process and store the incoming data into the database.

Summary:
--------
Kafka Producer: Reads real-time data from Wikimedia and sends it to a Kafka topic.
Kafka Consumer: Reads data from the Kafka topic and writes it to a MySQL database.
