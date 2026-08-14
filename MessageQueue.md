## RabbitMQ?

RabbitMQ is an open-source message-broker.

### message-broker?

Message-broker is intermediary software that enables., different applications, systems, and services to communicate and exchange data, even if they run on different platforms or use different languages. 

Acts as a "middleman / middleware" that receives Data/messages from producers and routes them to consumers, storing Data/messages in a queue, until they are processed, that ensuring reliable delivery and asynchronous communication.

RabbitMQ is a message-broker that uses message-queues, as part of its core functionality. 
It contains message-queues, where messages are stored (buffered), before being processed by the consumer.., and message-queues follow FIFO order.

In Core application layer, RabbitMQ primarily uses AMQP 0-9-1 (Advanced Message Queuing Protocol) for messaging. It also natively supports AMQP 1.0, MQTT (for IoT), STOMP (for interoperability), and HTTP/REST API (for management). These protocols operate over TCP/IP connections on transport layer.

It acts as a central hub, allowing producers to send data and consumers to receive it, decoupling services to increase scalability and reliability.


RabbitMQ Architecture component --

<img width="600" alt="image" src="https://github.com/user-attachments/assets/3847c227-c51d-4e46-90e3-8a136a3bf25b" />

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

## RabbitMQ use for ::

RabbitMQ is a message broker that acts as middleware between applications. It works as an intermediary that receives messages from producers and routes them to the appropriate consumers.

RabbitMQ follows a message queuing architecture, enabling asynchronous communication between applications, services, or microservices. It allows messages to be sent, stored, and processed independently, reducing direct dependencies between systems.

Important: RabbitMQ itself neither produces nor consumes messages. Its primary role is to receive, store, route, and deliver messages from producers to consumers through exchanges and queues.

At a high level, the RabbitMQ communication architecture consists of 3 major components: **1.Producer** , **2.RabbitMQ Broker** , **3.Consumer**


- **Producer ::**
  
  A Producer is an application, service, or program that creates and sends messages to a RabbitMQ server (broker).

  Before sending messages, the producer must first establish a connection to the RabbitMQ server using the TCP protocol. After the connection is established, the producer creates a channel on top of that connection.

  A channel is a lightweight virtual connection that operates within a single TCP connection. Producers use channels to publish messages to RabbitMQ efficiently without creating multiple TCP connections.

- **RabbitMQ Broker ::**
  
 
  
  - **Exchange :**
    - Direct (exact key match),
    - Fanout (broadcast to all),
    - Topic (pattern matching),
    - Headers (based on header attributes)
  - **Binding :**
  - **Queues :**
    
- **Consumer ::**

  A Consumer is an application, service, or program that subscribes to a queue and receives messages from RabbitMQ for processing.

  Like producers, consumers must first establish a TCP connection to the RabbitMQ server and then create a channel on top of that connection.

  Through the channel, consumers receive messages from the queue. After successfully processing a message, the consumer sends an acknowledgment (ACK) back to RabbitMQ. This acknowledgment informs RabbitMQ that the message has been processed successfully and can be removed from the queue.






