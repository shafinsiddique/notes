# What is Kubernetes?

- Previously, we looked at docker and docker containers. COntainers are a good way to bundle and run your applications. In a production environment, you need to manage the container that run the applications and ensure that therre is no downtimew. For example, if a container goes down, another container needs to start. 

- Kubernetes is a tool that handles these issues.

- Kubernetes provides you with a framework to run distributed systems resiliently. It takes care of scaling and failover for your application, provides deployment patterns and more.

- It essentially automates many of the manual processes invovled in deploying, managing and scaling containerized applications.

- You can cluster together groups of hosts runnng Linux containers, and kubernees helps you easily and efficienly manage those clusters.

- If we have an application that we know is containerized and we know that it is going to be using servers, we can use Kubernetes to help deploy that application to the server. Kubernetes will keep track of the container in the servers and then handle issues such as the container crashing and what not. It will also handle scaling if you increase the number of your containers.

# Features

- Kubernetes can expose a container using a DNS name or use their own IP address. If traffic to a container is high, Kubernetes is able to load balance and distribute the network traffic so that the deployment is stable.

- Kubernetes allows you to automatically mount a storage system of your choice such as local storate, cloud and such.


- The primary advantage of using Kubernetes in your environment, especially if you are optimizing app dev for the cloud, is that it gives you the platform to schedule and run containers on clusters of physical or virtual machines (VMs).

# Scalability with Kubernetes

- Think of the scenario of your web application getting more traffic than usual. THe naive approach to scaling would be to deploy one container per server. 
- THe way scaling works in Kubernetes is by changing the number of replicas in a deployment.

- Scaling out a deployment will ensure new pods are created and schedules to nodes with avaialbel resources. Scaling will increase the number of pods to the new desired state.

- Kubernetes also supports autoscaling of pods.

- Running multiple instances of an application will require a way to distribute the traffic to all of them. Services have an integrated load-balancer that will distribute network traffic to all Pods of an exposed Deployment. Services will monitor continuously the running Pods using endpoints, to ensure the traffic is sent only to available Pods.


# Terminology

- Pod: A kubernetes pod is a group of containers that are deployed otgether on the same host. A group of containers with shared storage/network, and a specification for how to run the containers. A pod's contents are alwyas co-located and co-scheduled, and run in a shared context.

- Containers within a Pod share an IP address and port space, and can find each other via localhost. They can also communicate with each other using standard inter-process communications like SystemV semaphores or POSIX shared memory. Containers in different Pods have distinct IP addresses and can not communicate by IPC without special configuration. These containers usually communicate with each other via Pod IP addresses.

# How Kubernetes works

- Kubernetes coordinates a highly available cluster of computers that are connected to work as a single unit. The abstractions in Kubernetes allow you to deploy containerized applications to a cluster without tying them specifically to individual machines. To make use of this new model of deployment, applications need to be packaged in a way that decouples them from individual hosts: they need to be containerized. Containerized applications are more flexible and available than in past deployment models, where applications were installed directly onto specific machines as packages deeply integrated into the host. Kubernetes automates the distribution and scheduling of application containers across a cluster in a more efficient way. Kubernetes is an open-source platform and is production-ready.

- Once you have a running Kubernetes cluster, you can deploy your containerized applications on top of it. To do so, you create a Kubernetes Deployment configuration. The Deployment instructs Kubernetes how to create and update instances of your application. Once you've created a Deployment, the Kubernetes master schedules the application instances included in that Deployment to run on individual Nodes in the cluster.

- Once the application instances are created, a Kubernetes Deployment Controller continuously monitors those instances. If the Node hosting an instance goes down or is deleted, the Deployment controller replaces the instance with an instance on another Node in the cluster. This provides a self-healing mechanism to address machine failure or maintenance.











