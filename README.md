# Kafka Connect for Azure Cosmos DB

## Introduction

This project provides connectors for [Kafka Connect](http://kafka.apache.org/documentation.html#connect) to read from and write data to [Azure Cosmos DB](https://azure.microsoft.com/databases/cosmos-db).

## Development

### Building the connectors

### Running Integration Tests

### Debugging with Trace Logging


## Supported Data Formats
The sink & source connectors are configurable in order to support
* **JSON plain** (offers JSON record structure without any attached schema)
* **RAW JSON** (string only - JSON structure not managed by Kafka connect)

Since key and value settings can be independently configured, it is possible to work with different data formats for records' keys and values respectively.

_NOTE: Even when using RAW JSON mode i.e. with [StringConverter](https://kafka.apache.org/21/javadoc/index.html?org/apache/kafka/connect/storage/StringConverter.html) the expected Strings have to be valid and parsable JSON._

#### Configuration example for JSON plain
```properties
key.converter=org.apache.kafka.connect.json.JsonConverter
key.converter.schemas.enable=false

value.converter=org.apache.kafka.connect.json.JsonConverter
value.converter.schemas.enable=false
```

#### Configuration example for RAW JSON
```properties
key.converter=org.apache.kafka.connect.storage.StringConverter
value.converter=org.apache.kafka.connect.storage.StringConverter
```

## Configuration Properties
The Sink and Source connectors share the following common configuration properties - 
* 
* 
* 

For Sink connector specific configuration please refer to [Sink Connector Documentation](./doc/README_Sink.md)

For Source connector specific configuration please refer to [Source Connector Documentation](.doc/README_Source.md)

## Limitations

### Supported Data Formats
The Sink & Source connectors do not currently support the following data formats
* **AVRO** (makes use of Confluent's Kafka Schema Registry)
* **JSON with Schema** (offers JSON record structure with explicit schema information)

## Quickstart

## Resources
[Kafka Connect](http://kafka.apache.org/documentation.html#connect)

[Kafka Connect Deep Dive – Converters and Serialization Explained](https://www.confluent.io/blog/kafka-connect-deep-dive-converters-serialization-explained/#json-topics)

