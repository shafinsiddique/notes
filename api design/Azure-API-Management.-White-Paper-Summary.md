# Azure API Management Whitepaper

This is a summary of the Azure API Management White Paper. The paper can be found here : https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts

# Introduction

- As API's have evolved, it has become clear that there are basic responsibilities to be met when publishing an API in any form. A poorly designed API can expose confidential information to unintended parties.

- Good API design takes the following factors into consideration.
    - Reuse
    - Access without headaches
    - Security
    - Visibility

# Reasons for an API Management Platform

- Supprt multiple APIS by decoupling and presenting facades

  - Companies that publish APIs are responsible for systematically evovling the APIs. If the API changes in significatn ways, developers must rewrite their programs. Developers should not be forced to change their programs. This is why IT orgaizations present simpler facades that decouple the internal implementation and the API consumer experience. BY proving a simpler API tailored for a specific type o9f use, IT organizations can change the underlying implementation without impacting developers applications.

  - This is one of the ways a need for a central API management platform comes into play. Supporting all your APIS through an APi management platform creares a clearinghouise for all of the APIS in your organization, allowing developers to find the APIS they need and avoid reinventing the wheel.

  - THe API Management provides a single 'front door' with a single URL for all your APIS.

- Easy Access for Developers.

  - For developers using an API, access is the first step. Developers want to be productive as quickyu as possible. They need a developer portal with interaction docs, an API console, and code samples. Creating such a portal can be time consuiming and maintaining it is even more time consuming.
  - There is also the matter of security keys. When handled manually, the process of getting API keys is cunmbersome and time consuming. Customers partners and developers request access from someone in ht ebusiness, who typically rouytes the request toi IT, which then handles the provisioning of an API key. The IT department muyst keep track of who has access to which APIs so that, if necessary, it can succesfully revoke a particular partner or developers access to an API.
  - This calls for an API platform that automaically generates and updates content for the developer portal based on any changes to the API.
  
- Secure Access

    - IT departments need assurance that APIs are secure, throttled, scaled, monitored, optimized, and instrumented to get business and operational insights. Without these measures, APIs can be misused or overused. Because APis provide access, that access muyst be proeprly secured. IT organizations need a way to ensure that all APis comply with security policies and are able to connect with legacy apps and data.
    
 - Analytics and Metrics
 
 An API management platform can address the challenges and requires associated iwth publishing APIs/ At its simplest, an APi management platform is a proxy between the API and the customer, partner or developer using the API. Instead of connecting to the underlying services directly, developers connect to an API management later that provides all of the capabilities required for safe, successful and scalable use of an API.
 
# Azure API Management Platform

Microsoft's Azure API Managemnt is a compelling enterprise-grade API management service that runs on Azure. AAMP works with any backend service hosted anywhere. The turnkey solution includes everytjing IT organizations need to create, maintain, and manage its APIs.

The publisher portal is the control plane from which APIs are created, managed, and maintained. Only the API publisher has access to the publisher portal. It is here that the publisher can create APIs, ciew analytics, configure various sustem parameters.

API data can be entered manually or imported from an API definition language.

The developer portal consists of automatically generated documentation and an interactive console. Internal and External developers can use self service registration functionality and access API docs.




 
 
    
  
