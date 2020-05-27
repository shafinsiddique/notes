# Publisher-Subscriber Pattern

- In cloud based and distributed applications, components of the system often need to provide information to other components as events happen.

- Asynchronous messaging is an effective way to decouple senders from consumers and avoid blocking the sender to wait for a response. However, using a deidcated message queue for each consumer does not scale to many consumers. Also,m some of the consumers might be interested in only a subset of the information/ How can the sender announce events to all interested consumers without knowing their identities.

- The solution is to introduce an async messaging subsystem that incldues the following: 
    - AN input messaging channel used by the sender. The senbder packages events into messages, using a known message format, and sends these messages via the input channel. The sender is this pattern is the publisher.
    - One output messaging channel per consumer.
    A mechanism for copying each message from the inpout channel to the output challs fro all subscribers iterested in that message. This is handled by an intermediary such as a message broker or event bus.

    