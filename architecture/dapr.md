# What is Dapr?

- Dapr is a portable, event driven runtime that makes it easy for developers to build resilient, microservice stateless and stateful applications that run on the cloud and edge and embraces the diversity of languages and developer frameworks.

- From the Microsoft article, "To enable all developers using any language and any framework to easily build portable microservices applications, whether writing new code or migrating existing code, we are exicted to announce Distributed Application Runtime."

- Dapor consists of a set of building blocks accessed by standard HTTP or gRPC APIs that can be called from any programming language. These building blocks empower all developers with poroven, industry practices and each building block is indepenpendent.

- Dapr is completely platform agnostic, meaning you can run your applications locally, on any Kubernetes cluster, and other hosting environments that Dapr integrates with. This enavbles developers to build microservice applications that run on boht the clouyd and edge with no code changes.

- Dapr makes it extremely simple to consume other microservices running in the same host, internal or external data services, and messaging services based on the pub/sub pattern. Actors, event-driven resource binding, and distributed tracing are the other building blocks available in the initial release. Dapr building blocks decouple internal consumers from external services. For example, without changing a line of code, you can switch from using Amazon DyanamoDB to Azure ComosDB. Building blocks are exposed via standard REST or gRPC endpoints.



# Dapr Building Blocks

- Service Incovation - Resilient service-to-service invocation enables method calls, including retires on remote services whethere they are running in the supported hosting environment.
- State Management - With state management for key/value pairs, long running, highly available, stateful services can be easily written, alongside statless services in the same application. The state store is pluggable and can include Azure Cosmos or Redis, with others such as AWS DynamoDB on the component roadmap.
- Publish and subscribe messaging between services: Publishing events and subscribing to topics between services enables event driven architecutres to simplify horizontal scalability.


# How it works

- Say for example, you are using the Azure Functions runtime in a microservice application that you have deployed into a Kubernetes cluster and you would like to take advantage of the pub sub pattern to send messages between services. Today, the Azure Functions runtime does not have this capability ubilt in, however by using Dapr pub/sub building block over http, you can easily add this new capability.

- THe Dapr pub/sub building bl;ock has a pluggable component model, meqaning that you can dynamicallyt choose different implementations for how the messages are sent, without changing any code.For example, you can choose the Redis, Kafka, or Azure Service Bus pub/sub Dapr component depending on your preferences. And in both cases the code remains the same, including being portable across different supported infrastructures, by using a standard API.

- To enable both portability and ease of integration with existing code, Dapr provides standard APIs over http or gRPC.


