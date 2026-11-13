<div align="center">

# 🌍 Wikimedia Live Stream with Kafka & Spring Boot

### Stream real-time Wikimedia events through Apache Kafka into MySQL.

![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-Event_Streaming-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-Applications-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Wikimedia](https://img.shields.io/badge/Source-Wikimedia-000000?style=for-the-badge&logo=wikipedia&logoColor=white)
![MySQL](https://img.shields.io/badge/Storage-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

[✨ Overview](#-overview) · [🏗️ Data flow](#️-data-flow) · [🚀 Getting started](#-getting-started) · [🔧 Configuration](#-configuration)

</div>

---

## 🌟 Overview

This multi-module project demonstrates real-time data streaming with Apache Kafka. A producer module receives live stream data from Wikimedia and publishes it to a Kafka topic. A consumer module reads messages from that topic and stores them in a MySQL database.

## 🏗️ Data flow

```text
┌─────────────────────┐      ┌─────────────────┐      ┌─────────────────────┐
│ Wikimedia live data │ ───▶ │ Kafka Producer  │ ───▶ │    Kafka topic      │
└─────────────────────┘      └─────────────────┘      └──────────┬──────────┘
                                                                  │
                                                                  ▼
                                                       ┌─────────────────────┐
                                                       │  Kafka Consumer    │
                                                       └──────────┬──────────┘
                                                                  │
                                                                  ▼
                                                       ┌─────────────────────┐
                                                       │       MySQL         │
                                                       └─────────────────────┘
```

### 📤 Kafka Producer

Connects to Wikimedia's real-time stream and publishes incoming data to a Kafka topic.

### 📥 Kafka Consumer

Subscribes to the Kafka topic, processes the incoming messages, and writes the data to MySQL.

## ✨ What this project demonstrates

- 🌐 Consuming live event data from Wikimedia
- 📨 Publishing and consuming messages with Apache Kafka
- 🧩 Separating producer and consumer responsibilities into modules
- 🗄️ Persisting consumed stream data in MySQL
- 🔄 Building a simple real-time event pipeline

## ✅ Prerequisites

- A JDK compatible with the project's build configuration
- Apache Kafka and a running broker
- MySQL server
- Access to Wikimedia's live data stream
- The build tool specified in the project files

Check the module build files and application configuration for exact versions and requirements.

## 🚀 Getting started

### 1. 📥 Clone the repository

```bash
git clone https://github.com/Rawkesh2k/kafka-springboot-wikimedia.git
cd kafka-springboot-wikimedia
```

### 2. 📨 Start Kafka

Start a Kafka broker and ensure its address matches the producer and consumer configuration. Confirm that the configured topic exists, or that automatic topic creation is enabled in your local setup.

### 3. 🗄️ Prepare MySQL

Start MySQL and configure the consumer's datasource connection. Create the required database and schema if the project does not create them automatically; check the consumer module's configuration and source for the expected table structure.

### 4. ⚙️ Configure the modules

Review the producer and consumer configuration files. Set the Kafka bootstrap server, topic, and consumer settings, as well as the MySQL connection details. Keep credentials outside version control.

### 5. ▶️ Build and run

Build and start the producer and consumer using the commands and module names defined by the repository's build files. Run both modules while monitoring their logs: the producer should publish Wikimedia events, and the consumer should persist received data to MySQL.

> Exact module paths, build commands, topic names, and database schema are defined by the project files; inspect those before running the services.

## 🔧 Configuration checklist

- Kafka broker address and topic
- Producer connection to the Wikimedia stream
- Consumer group and deserialization settings
- MySQL URL, username, password, and schema
- Logging and retry behavior appropriate for local development

Use environment variables or local untracked configuration for secrets rather than committing credentials.

## 🧪 Verify the pipeline

1. Start Kafka and MySQL.
2. Start the consumer and confirm it connects to Kafka and the database.
3. Start the producer and confirm it receives and publishes live events.
4. Check consumer logs and query the configured MySQL table to verify that messages are being stored.

## 🔐 Security and reliability notes

- Never commit database passwords, API credentials, or other secrets.
- Restrict access to Kafka and MySQL to trusted services.
- Consider message validation, retries, and error handling when extending the pipeline.
- Be mindful of Wikimedia stream terms and the volume of data written to your database.

## 🤝 Contributing

1. Create a focused branch for your change.
2. Keep producer, broker, and consumer responsibilities clear.
3. Test changes with the services they affect.
4. Document any new configuration or setup requirements.

---

<div align="center">

⚡ **From Wikimedia's live stream to a Kafka-powered data pipeline.**

</div>
