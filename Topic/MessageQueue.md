## RabbitMQ?

RabbitMQ is an open-source message broker.

### message broker?

A message broker is intermediary software that enables different applications, systems, and services to communicate and exchange data, even if they run on different platforms or use different languages. It acts as a "middleman" that receives messages from producers and routes them to consumers, storing messages in a queue until they are processed, ensuring reliable delivery and asynchronous communication.

It contains message queues where messages are stored (buffered) before being processed by the consumer.

RabbitMQ is a message broker that uses message queues as part of its core functionality. and message queues follow FIFO order.

RabbitMQ primarily uses AMQP 0-9-1 (Advanced Message Queuing Protocol) as its core application layer protocol for messaging. It also natively supports AMQP 1.0, MQTT (for IoT), STOMP (for interoperability), and HTTP/REST API (for management). These protocols operate over TCP/IP connections on transport layer.


What is RabbitMQ?

RabbitMQ Architecture


Data Flow Process

type of exchanges 

RabbitMQ use for
