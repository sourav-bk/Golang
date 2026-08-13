## RabbitMQ?

RabbitMQ is an open-source message-broker.

### message-broker?

Message-broker is intermediary software that enables., different applications, systems, and services to communicate and exchange data, even if they run on different platforms or use different languages. 

Acts as a "middleman / middleware" that receives Data/messages from producers and routes them to consumers, storing Data/messages in a queue, until they are processed, that ensuring reliable delivery and asynchronous communication.

RabbitMQ is a message-broker that uses message-queues, as part of its core functionality. 
It contains message-queues, where messages are stored (buffered), before being processed by the consumer.., and message-queues follow FIFO order.

In Core application layer, RabbitMQ primarily uses AMQP 0-9-1 (Advanced Message Queuing Protocol) for messaging. It also natively supports AMQP 1.0, MQTT (for IoT), STOMP (for interoperability), and HTTP/REST API (for management). These protocols operate over TCP/IP connections on transport layer.

It acts as a central hub, allowing producers to send data and consumers to receive it, decoupling services to increase scalability and reliability.


RabbitMQ Architecture component
- producer 

- Broker
  - Exchange
    - Direct (exact key match),
    - Fanout (broadcast to all),
    - Topic (pattern matching),
    - Headers (based on header attributes)
  - Binding
  - Queues
- Consumer




## Data Flow Process

## type of exchanges 

## RabbitMQ use for



RabbitMQ is a message broker that acts as a middleware between applications. It works as an intermediary that receives messages from producers and routes them to the appropriate consumers.

RabbitMQ follows a message queuing architecture, enabling asynchronous communication between applications, services, or microservices. It allows messages to be sent, stored, and processed independently, reducing direct dependencies between systems.

Important: RabbitMQ itself neither produces nor consumes messages. Its primary role is to receive, store, route, and deliver messages from producers to consumers through exchanges and queues.

on High-Level that communication have   Architecture have 3 major component -----------------

1. producer:
   producer is a user application, service, or program that creates and sends messages to a RabbitMQ message broker server.
before send messages/data 1st step to producer is make connection to RabbitMQ or broker server using TCP protocol . on and on top of then create channel.(Channel is a lightweight, virtual connection multiplexed inside that single TCP connection) and  through channel send messages to the RabbitMQ server or thats called "Broker"

   
2. RabbitMQ itself (or called "Broker") :
RabbitMQ itself  have difarrent 

   
3. Consumer:
consumer is different application service or program that Registers a subscription to a queue and receives incoming messages, and send acknowledgement back to the RabbitMQ server or broker.

also before get the messages from RabbitMQ server or broker connect through using TCP protocol .and on top of then create channel. through that channel Consumers can get massage.
