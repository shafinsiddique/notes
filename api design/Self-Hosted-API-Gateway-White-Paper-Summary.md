# Self Hosted API Gateways

This is a summary of the 'API Management in a Hybrid and Multi-Cloud World' paper written by Micorosft that looks into self hosted API gateways using Azure API Management. The white paper can be found here: https://azure.microsoft.com/mediahandler/files/resourcefiles/api-management-in-a-hybrid-and-multi-cloud-world/API%20management%20in%20a%20hybrid%20and%20multi-cloud%20world.pdf

# API Management Today

- In today's cloud centric word, API Management platforms usually run on a cloud platform. Microsoft's Azure API Management runs on Microsoft Azure. 
- Yet the applications and data your APIs expose are probably spread across multiple on-premises and cloud environments. 
- Managing these APIs consistently throughout your organization is a key part of increasing productivity and maximizing business value.
- This is why we need a unified approach to API Management across an organizations hybrid and multi cloud world.

# Value of Self Hosted Gateways

- Today's most popular API Management solutions run in public clouds. 
- Purely cloud based solutions work for ALMOST all scenarios. Almost.
- However, there might be situations when its not ideal. Imagine organizations where certain parts of the data are on the cloud while other parts of the data are on premises. 
- What is client is accessing on premises applications and data within the same corporate environment, but none of the traffix is allowed to leave the environment? In scenarios like this, we can't use an API management service running on a public cloud, the service must run on premises. THis is the most significant problem with API management in many organizations.
- The solution is a self-hosted API Management gateway.

# Self Hosted API Gateways

- Even though API management typically runs in the cloud, this doesn't need to be the only option. A self-hosted API Management gateway doesn't replace the primary cloud-based API management service. Instead, it augments this service by providing the essential aspects of API management in software organizations can run wherever they choose. The 2 two most important scenarios for using this self hosted gateway are :
  - Running the self-hosted API management gateway in your own on-premises datacenter.
  - Running the self hosted API management gateway in another cloud: This lets clients access backend services in that cloud through API Management, but without forcing that traffic to go through the cloud that's running the primary API management service. Taking this approach eliminates both the delay and the extra cost of accessing two different clouds just to get API management.
  
- Self hosted means your organization will be responsible for installing and running self hosted API management gateways whereever you need them. You're also responsible for keeping them running, so they do require some extra effort.

# Azure API Management Self Hosted API Gateways

- Azure Arc enabled API management provides a self-hosted API management gateway.
- Using the self-hosted Azure API Management gateway lets you discover, use, and manage diverse APIs across your on-premises and multi-cloud enjvironment.
- The self hosted Azure API Management gateway includes only the gateway functionality of the full Azure API Management service.
- Wherever the self-hosted gateway is running, however, it must be federated with - connected to- the main cloud service.
- Each self hosted gateway is attached to and managed by a single Azure API Management cloud service.



  
  
