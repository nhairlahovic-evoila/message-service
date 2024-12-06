# Message Service

A Spring Boot application showcasing integration with Apache Kafka for efficient message publishing and consumption.

## Features

- **Message Publishing**: Send messages to a Kafka topic using a REST endpoint.
- **Message Consumption**: Automatically listens and logs messages from a Kafka topic.
- **Topic Management**: Automatically creates Kafka topics using Spring configuration.
- **Custom Producer and Consumer Configurations**: Fine-tuned configurations for Kafka producers and consumers.

## Prerequisites

- Java 17 or higher
- Apache Kafka running on the default bootstrap server
- Maven for building the project

### Running Kafka with Docker

If you don't have Kafka installed locally, you can use the provided `docker-compose.yml` file to run Kafka and Zookeeper containers.

Start Kafka and Zookeeper:
```bash
docker-compose up -d
```

Verify Kafka is running by ensuring the broker is listening on `localhost:9092`. 
This address will be used as the `spring.kafka.bootstrap-servers` in your application configuration.

## Testing the Application

After starting the application, you can use tools like Postman or cURL to interact with the API.

### Publish a Message

**URL**: `/api/publish`

**Method**: `GET`

**Query Parameter**: `message` - The message to send to the Kafka topic.

Example:

```bash
"http://localhost:8080/api/publish?message=HelloKafka"
```

## Project Structure

- `MessageController`: REST controller for sending messages.
- `KafkaProducer`: Service for publishing messages to a Kafka topic.
- `KafkaConsumer`: Service for consuming messages from a Kafka topic.
- `KafkaTopicConfig`: Configuration for Kafka topic creation.
- `KafkaProducerConfig`: Configuration for Kafka producer.
- `KafkaConsumerConfig`: Configuration for Kafka consumer.