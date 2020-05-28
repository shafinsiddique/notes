# Event Driven Architecture

Event Driven Architecture is a pattern used for developing systems with the microservice architecture. Instead of sending requests, services send an 'event' to the event bus. When the service sends an event, it is basically saying that 'something has happened.' The services who care about the certain event that just happened will be able to receive that event from the event bus.

Let's imagine you are building an e-commerce application store where customers have a credit limit. The application must ensure that a new order will not exceed the customer's credit limit. Since orders and customers are in different databases, the application simply cannot use a ACID transaction.

In a situation like this, the solution is to use an event driven approach. Each service publishes an evbent whenever it updates its data. Other service subscribe to evenets. When an event is received, a service updates its data.

# Example

An e-commerce application that uses this approach would work as follows: 

  - The Order Service creates an Order in a pending state and publishes an OrderCreated event.
  - The Customer Service receives the event and attempts to reserve credit for that order. It then publishes either a Credit Reserved EVent or a CreditLimitExcedded event.
  - The Order Service receives the event from the Customer Service and changes the state to either approved or cancelled.
  
# Advantages

  - It enables the application to maintain data consistency acorss multiple services without distributed transactions.
