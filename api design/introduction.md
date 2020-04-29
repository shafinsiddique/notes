# What is an API?

An API is the interface that a software program presents to other programs, to humans, and in the case of web APIs, to the world via the internet. An APIs design bellies much about the porgram behind it - business mode, product features, the occasional bug.

Although APIs are intended to work with other programs, they are intended to be understood and used by humans writing those other programs aka developers.

APIs are the building blocks that allow interoperability for major business platforms on the web. Think of legos. APIs are the lego blocks for your program. 

# Why do we need APIs?

APIs have emerged out of a need to exchange information with providers of data who are equipped to solve specific problems. Often times, you will face problems when building your software that other developers has already built solutions to. Using an API, you can integrate those solutions without implementing your own.

You might want to embed a google maps without reinventing google maps or have a login feature without reinventing facebook login. These are what API's are for.

# Who are the users?

When desigining an API, it is important to identify exactly who will be using our API. It is important that we understand who our developers are, what their needs are, and why they are using our API. Focusing on developers prevents us from building APIs that no one wants to use or that do not fit the usage requirements of developers.

Changing an API's design is extremely difficult. It is important that we specify our APIand validate it long before we begin implementing it.

# Approaches to APIs design:

### APIs for Internal Developers First, External Developers Second.

Some companies build their APIs for internal developers first and then release them to external developers. There could be a number of motivations for this. One reason might be that the company sees potential value in adding an external API. This could create a developer ecosystem, drive new demand for the company's product, or enable other companies to build products that the company itself does not want to build.

Slack initially created its API for its internal developers, something else happened as the company grew; a handful of integrations with important business software became a key piece of the puzzle for Slack's growth and developemnt as a communication software.


### APIs for External Developers First, Internal Developers Second.

Some companies create APIs for external stakeholders first and then release them to the internal stakeholders. in the beginning, Github's API audience was primary external developers who wanted to gain programmatic access to their own data. Shortly after the initial release, small businesses began to form around Github's API. These businesses were creating developer tools and seeling them to Github users.

### APIs as the product

For some companies, APIs is the product. Think of Stripe or Twillio. Stripe provides APIS for payment processing and Twillio provides APIs for communixacation via SMS and voice. 

# What makes an API great?

Usability, Scalability and Performance are some of the aspects that make a good API. 

Documentation and developer resources are also important to setting users up for success. 

Another important thing is how well the API will stand the test of time. APIs are flexible platforms that connect businesses, and the rate of change is variable. We must design APIs that will stand the test of time.
