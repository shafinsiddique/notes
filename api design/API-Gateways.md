# What is an API Gateway?

An API Gateway is an entry point for APIs. Requests from the client first go to the gateway. The gateway is responsible for processing the request which means the gateway handles authentication, authorization, the data from requests.
The gateway then routes the request to the appropriate microservice.

"An API Gateway is the conductor that organizes the requests being processing by the microservices architecture to create simplified experience for the user.
It's a translator taking a clients many requests and turning them into just one, to reduce the number of round trips between
the client and the application."

An API gateway is set up in front of the microservices and becomes the entry point fo rnew request being executed by the app. It simplifies both the
client implementation and the microservices app.

A backend of an application following the "MICROSERVICES ARCHITECTURE" probably has several APIs that communicate with different databases. Amazon might have a microservice for product information and then another one for product recommendation. Using an API gateway, we can take the load off the clients back by having them not worry about the different services and routes. They simply send one request and the API gateway processes everything to respond to the client.

# Advantages of using an API Gateway

- Insulates the clients from how the application is partitioned into microservices.
- INsulates the clients from the problem of determining the locations of service instances.
- Provides the optimal API for each client.
- Reduces the nmumber of requests. For example, the API gateway enables clients to retrieve data from multiple services with a single round-trip. Fewer requests also means less overhead and improves the user experience. An API gateway is essential for mobile applications.
- Translates from a standard public web friendly APIU to whatever protocols are used internally.

# Drawbacks

- Increased complexity in the architecture. The gateway is yet another thing to build, maintain and deploy.
- INcreased response time due to the additional network hop through the API GAteway.













