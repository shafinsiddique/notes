# What is Docker?

Docker is a tool designed to make it easier to create, deploy, and run applications by using containers. Containers allow a developer to package up an application with all of the parts it needs, such as libraries and other dependencies, and deploy is as one package. 

By doing so, the developer can be rest assured that the application will run on any other Linux machine regardless of any customized settings that machine might have that could differ from the machine used for writing and testing the code.

Developers can focus on writing code without worrying about hte system that it will be ultimately be runnning on . It also allows them to get a head start by using one of thousands of programs already designed to run in a Docker container as part of their application.


# Containers

Containers are a standerdized unit of software that allows developers to isolate thier app from its environment.

A docker file builds a Docker image.

THe docker image consists of all source code, node js installation, any dependencies.

Before when we used to host applications on servers, we would have to spend quite a bit of time installing all dependencies onto the server computer.

With docker, everything is held in a container and the server computer can simply run the container.

# Benefits

- Same environment
- Sandbox Projects
- Use software built by other developers.

# Terminology

- DockerFile: A file that Docker reads from top to bottom. This file is essentially a recipe for building a Docker image. 
- Docker Image: The component that Docker builds. It is a snapshot of your environment and application. Once youy build a Docker image, you can send it to other developers and as long as your image works on your machine, it will work on their machines.
- Docker Container: A container is an instance of a docker image. It is built when we run a docker image. If a docker image is the photograph, a container is the printout of that photograph. It is not meant to be shared within computers or people. Containers run individually.








