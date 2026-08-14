## RabbitMQ?

RabbitMQ is an open-source message-broker.

### message-broker?

Message-broker is intermediary software that enables., different applications, systems, and services to communicate and exchange data, even if they run on different platforms or use different languages. 

Acts as a "middleman / middleware" that receives Data/messages from producers and routes them to consumers, storing Data/messages in a queue, until they are processed, that ensuring reliable delivery and asynchronous communication.

RabbitMQ is a message-broker that uses message-queues, as part of its core functionality. 
It contains message-queues, where messages are stored (buffered), before being processed by the consumer.., and message-queues follow FIFO order.

In Core application layer, RabbitMQ primarily uses AMQP 0-9-1 (Advanced Message Queuing Protocol) for messaging. It also natively supports AMQP 1.0, MQTT (for IoT), STOMP (for interoperability), and HTTP/REST API (for management). These protocols operate over TCP/IP connections on transport layer.

It acts as a central hub, allowing producers to send data and consumers to receive it, decoupling services to increase scalability and reliability.


## RabbitMQ Architecture component

<img width="600" alt="image" src="https://github.com/user-attachments/assets/3847c227-c51d-4e46-90e3-8a136a3bf25b" />

RabbitMQ is a message broker or tools that acts as middleware between applications. It works as an intermediary that receives messages from producers and routes them to the appropriate consumers.

RabbitMQ follows a message queuing architecture, enabling asynchronous communication between applications, services, or microservices. It allows messages to be sent, stored, and processed independently, reducing direct dependencies between systems.

Important: RabbitMQ itself neither produces nor consumes messages. Its primary role is to receive, store, route, and deliver messages from producers to consumers through exchanges and queues.

At a high level, the RabbitMQ communication architecture consists of 3 major components: **1.Producer** , **2.RabbitMQ Broker** , **3.Consumer**


- **Producer ::**
  
  A Producer is an application, service, or program that creates and sends messages to a RabbitMQ server (broker).

  Before sending messages, the producer must first establish a connection to the RabbitMQ server using the TCP protocol. After the connection is established, the producer creates a channel on top of that connection.

  A channel is a lightweight virtual connection that operates within a single TCP connection. Producers use channels to publish messages to RabbitMQ efficiently without creating multiple TCP connections.

  > Connection : Connection is a physical TCP connection established between a client application (Producer/Consumer) and the RabbitMQ broker.
  
  > Channel : Channel is a lightweight virtual connection that exists inside a TCP connection. Created on top of an existing TCP connection. Multiple channels can share a single TCP connection.

- **RabbitMQ Broker ::**
  
  
  - **Exchange :**
    
    Exchange is a message routing agent in RabbitMQ. It receives messages from producers and decides where to route using internal rules.

    Exchange does not store messages itself. Instead, it uses routing rules to forward messages to one or more queues.

    Messages are always sent to exchange first from Producer, not directly to a queue.
    
    RabbitMQ provides 4 types of Exchanges:
    
    - Direct (exact key match)::
      Routes messages to a queue based on an exact routing key match.
    - Fanout (broadcast to all)::
      Broadcasts messages to all bound queues, ignoring routing keys.
    - Topic (pattern matching)::
      Routes messages using pattern matching on routing keys. ( * matches exactly one word and # matches zero or more words )
    - Headers (based on header attributes) ::
      Routes messages based on message header attributes instead of routing keys.
      
  - **Binding :**

    Binding is a link or routing rule that connects an exchange to a queue. It defines how messages should be routed from the exchange to the queue.

    Based on the binding configuration and routing criteria, the exchange determines which queue(s) should receive a particular message.
    
  - **Queues :**

    A Queue is a buffer that stores messages until they are processed by consumers. It receives messages from an exchange, holds them safely, and delivers them to one or more consumers.

    Messages remain in the queue until they are successfully consumed and acknowledged.
    
- **Consumer ::**

  A Consumer is an application, service, or program that subscribes to a queue and receives messages from RabbitMQ for processing.

  Like producers, consumers must first establish a TCP connection to the RabbitMQ server and then create a channel on top of that connection.

  Through the channel, consumers receive messages from the queue. After successfully processing a message, the consumer sends an acknowledgment (ACK) back to RabbitMQ. This acknowledgment informs RabbitMQ that the message has been processed successfully and can be removed from the queue.


## Data Flow Diagram

<img width="268" height="355" alt="image" src="https://github.com/user-attachments/assets/bfe26896-0fc5-442b-b5a0-e53ee43eee87" />




## RabbitMQ use for ::





