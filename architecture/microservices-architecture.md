|
# Microservices Architecture

- Imagine buiulding a server-side application. It must support a variety of different clients including desktop browsers, mobile browsers and native mobile applications. THe application might also expose an API for 3rd parties to consume. It might also integrate with other applications.

- What we want to know is what will the architecture of the deployment be?

- WHatever it is, we want to keep the following in mind:
    - THere is a team of developers working on the application.
    - New team members must quickly become productive
    - The application must be easy to udnerstand and modify.
    - You want to practice continous deployment of the application.
    - You must run multiple instances of the application on multiple machines in order to satisfy scalability and availability requirements.
    - You want to take advantage of emerging technologies

- The answer to what architecture we should use is 'Microservices Architecture.'
- The MA defines an archtecture that strcutres the application as a set of loosely coupled, colloborating services. Each service is:
    - highly maintainable and testable - enables rapid and frequent development and deployment.
    - loosely coupled with other services - enables a team to work independently the majority of time on their service(s) without being impacted by their changes to other services and without affecting other services.
    - Independently depoyable.
    

- Services communicate using either synchronous protocols such as HTTP/REST or asynchronized protocols such as AMQP. Each service has its own database in order to be decoupled from other services.


# Drawbacks

- Developers must deal with the additional complexity of creating a distributed system.
- Deployment complexity.
- Increased memory consumption.

