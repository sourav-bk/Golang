## RabbitMQ?

RabbitMQ is an open-source message broker.

### message broker?

Message broker is intermediary software that enables different applications, systems, and services to communicate and exchange data, even if they run on different platforms or use different languages. 

It acts as a "middleman / middleware" that receives messages from producers and routes them to consumers, storing messages in a queue until they are processed, ensuring reliable delivery and asynchronous communication.

RabbitMQ is a message broker that uses message queues as part of its core functionality. 
It contains message queues where messages are stored (buffered) before being processed by the consumer and message queues follow FIFO order.

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




Data Flow Process

type of exchanges 

RabbitMQ use for
