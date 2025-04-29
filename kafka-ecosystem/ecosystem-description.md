# Docker Compose Services Explanation (Excluding Kafka, Zookeeper, and MongoDB)

## 1. Schema Registry (`schema-registry`)
- **Purpose**: Serves as a metadata layer for message schemas
- **Key Features**:
  - Uses Avro schema format by default
  - Stores schemas in Kafka
  - Provides REST API on port `8081`
- **Role**: Ensures data compatibility between producers and consumers

## 2. Kafka Connect (`connect`)
- **Purpose**: Framework for Kafka-external system integration
- **Configuration**:
  - REST API on port `8083`
  - Avro converters with schema registry integration
  - Includes kafka-connect-datagen plugin
- **Capabilities**:
  - Moves data between Kafka and other systems
  - Supports source and sink connectors

## 3. Control Center (`control-center`)
- **Purpose**: Web-based Kafka management GUI
- **Access**: Port `9021`
- **Features**:
  - Cluster monitoring and visualization
  - Topic management interface
  - Consumer lag tracking
  - KSQL integration
  - Stream processing visualization

## 4. KSQL Server (`ksql-server`)
- **Purpose**: Stream processing engine for Kafka
- **Interface**: REST API on port `8088`
- **Functionality**:
  - SQL-like syntax for stream processing
  - Creates streams and tables
  - Performs transformations and aggregations

## 5. KSQL CLI (`ksql-cli`)
- **Purpose**: Command-line interface for KSQL
- **Usage**:
  - Interactive shell environment
  - No exposed ports (internal use only)
  - Executes KSQL queries against KSQL Server

## 6. REST Proxy (`rest-proxy`)
- **Purpose**: RESTful interface to Kafka cluster
- **Access**: Port `8082`
- **Benefits**:
  - HTTP-based message production/consumption
  - Non-JVM client support
  - Rapid prototyping capability
  - Schema Registry integration for Avro

## 7. Kafka Topics UI (`kafka-topics-ui`)
- **Purpose**: Web UI for Kafka topic inspection
- **Access**: Port `8000`
- **Features**:
  - Lightweight topic browser
  - Message content viewer
  - Connects via REST Proxy (port `8082`)
  - Alternative to full Control Center

This environment provides a complete Confluent Platform implementation with monitoring, stream processing, and schema management capabilities.