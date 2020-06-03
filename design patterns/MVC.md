# Model View Controller

The Model-View-Controller(MVC) architectural pattern seperates an application into three main groups of components: Models, Views, and Controllers. This pattern helps to achieve seperation of concerns. Usiong thi spattern, user requests are routed to a Cotnroller which is responsible for working with the Model to perform user actions and/or retruece results of queries. The controller chooses the view to display to the user, and provides it any Model data it requires.

This delineation of responsibilities helps you scale the application in terms of complexity becasue its easier to code, debug and test something that has a single job.


# View Responsibilities

Views are responsible for presenting content through the user interface. THe use the Razor View Engine to embed .NET code in HTML markup. THere should be minimal logic within views, and any logic in them should relate to presenting content. 

# Model Responsibilities

The Model in an MVC application represents the state of the application and any business logic or operations that should be performed by it. Business logic should be encapsulated in the model, along with any implementatin logic for presisting the state of the application.

# Controller Responsibilities

Controllers are the components that handle user interaction, work with the model and ultimately self a view to render. In an MVC application, the view only displays information, the controller handles and responds to user input and interaction. In the MVC pattern, the controller is the initil entry point, and is responsible for selecting which model types to work with and which view to render (hence its name - it controls how the app responds to a given request)

# Model View Controller in ASP.NET.

ASP.NET Core MVC includes the following:
  - Routing
  - Model Binding
  - Model Validation
  - Depedency Injection
  - Filters
  - Areas
  - Web APIs
  - Testability 
  - Razor View Engine
  
  
# Routing in ASP.NET Core

Routing is responsible for matching incoming HTTP requests and dispatching those requests to the app
s executable standpoints. 

ASP.NET Core Controllers use the Routing middleware to amtch the URLs of incoming requests and map them to actions. Routes templates:
  - Are defined in startup code or attributes.
  - Describe how URL paths are matched to actions.
  - Are used to generate URls for links. The generated links are typically returned in responses.
  
 Actions are either conventionally routed or attribute routed. Placing a route on the controller 




