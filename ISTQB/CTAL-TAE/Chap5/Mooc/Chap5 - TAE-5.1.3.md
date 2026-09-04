# Mooc

## Explain Test Automation Dependencies for an API Infrastructure

### Screen

> **Introduction to API Test Automation Dependencies**
>
> - API testing is super important in modern software development.
> - API testing is sometimes easier to automate than UI testing.

---

> **What is an API**
>
> - API stands for **A**pplication **P**rogramming **I**nterface.
> - Think of it like a waiter in a restaurant.
> - Most APIs are RESTful or GraphQL, communicating over HTTP

---

> **API Dependencies for Test Automation**
>
> 1. **API Connections**
>
> - The business logic and relationships between different APIs.
> - Example: User Service > Authentication > Product Catalog > Payment
>
> ```mermaid
> graph LR
>     subgraph Left[" "]
>         direction TB
>         USA["[User Service API]"]
>         PCA["[Product Catalog API]"]
>         SCA["[Shopping Cart API]"]
>     end
>     subgraph Right[" "]
>         direction TB
>         AA["[Authentication API]"]
>         IA["[Inventory API]"]
>         PA["[Payment API]"]
>     end
>     USA <--> PCA
>     USA --> AA
>     PCA <--> SCA
>     PCA --> IA
>     SCA --> PA
>
>     style Left fill:none,stroke:none
>     style Right fill:none,stroke:none
> ```
>
> Understanding those connections tells you:
>
> - What APIs depend on other APIs
> - What order you need to test things in
> - What mock services you might need to create

---

> **API Dependencies for Test Automation**
>
> 2. **API Documentation**
>
> Includes:
>
> - All the endpoints (URLs)
> - What HTTP methods to use (GET, POST, PUT, DELETE, etc.)
> - Required request parameters and headers
> - Expected response formats
> - Authentication requirements
> - Error codes and messages
>
> Example:
>
> ```http
> GET /api/users/{id}
> Description: Retrieves a user by their ID
>
> Path Parameters:
>   - id (integer, required): The unique identifier for the user
>
> Headers:
>   - Authorization: Bearer {token}
>
> Response:
>   200 OK:
>   {
>     "id": 123,
>     "username": "johndoe",
>     "email": "john@example.com",
>     "createdAt": "2023-05-10T14:30:00Z"
>   }
>
>   404 Not Found:
>   {
>     "error": "User not found"
>   }
> ```
>
> The documentation tells us exactly what the endpoint is, what parameters it needs, what headers to include and what responses to expect.
>
> This is gold for test automation because it tells us:
>
> - How to form our requests
> - What to validate in the responses
> - What error conditions to test for.

---

> **Integrated Automated API Testing**
>
> - API testing can be done by either developers or Test Automation Engineer, but with the shift left movement, it's often a shared responsibility
> - "Shift left" means moving testing earlier in the development process to catch issues sooner when they're cheaper and easier to fix
> - ISTQB Foundation level mentions component integration testing and system integration testing as levels where API testing fits in.
> - "Contract testing" is a best practice particularly useful for APIs

---

> **Contract Testing**
>
> Type of integration testing verifying that services can communicate with each other, by following a set of rules known as contract
>
> Example:
>
> - Two teams working on microservices
> - Team A building shopping cart service
> - Team B building payment service
>
> ```mermaid
> %%{init: {'flowchart': {'nodeSpacing': 16, 'rankSpacing': 10}}}%%
> graph TB
>     subgraph without ["Without Contract Testing"]
>         direction LR
>         TA1["Team A"] ~~~ TB1["Team B"]
>         CS1["[Cart Service]"] -->|"???"| PS1["[Payment Service]"]
>         HW["(Hoping it works)"] ~~~ SPACER1[" "]
>     end
>
>     subgraph with_ct ["With Contract Testing"]
>         direction LR
>         TA2["Team A"] ~~~ CT_LABEL["Contract"] ~~~ TB2["Team B"]
>         CS2["[Cart Service]"] --> AC["[Agreed Format]"] --> PS2["[Payment Service]"]
>         VL["(Verified against<br/>the contract)"] ~~~ DE["(Documented<br/>expectations)"] ~~~ VR["(Verified against<br/>the contract)"]
>     end
>
>     without ~~~ with_ct
>
>     style without fill:none,color:#ff4444
>     style with_ct fill:none,color:#22aa22
>
>     style TA1 fill:none,stroke:none
>     style TB1 fill:none,stroke:none
>     style HW fill:none,stroke:none,color:#ccaa00
>     style SPACER1 fill:none,stroke:none
>
>     style TA2 fill:none,stroke:none
>     style CT_LABEL fill:none,stroke:none
>     style TB2 fill:none,stroke:none
>     style VL fill:none,stroke:none,color:#22aa22
>     style DE fill:none,stroke:none,color:#22aa22
>     style VR fill:none,stroke:none,color:#22aa22
>
>     style AC fill:none,stroke:#22aa22,color:#22aa22
>
>     linkStyle 1 stroke:#ff4444,color:#ff4444
>     linkStyle 5 stroke:#22aa22
>     linkStyle 6 stroke:#22aa22
> ```
>
> - The contract serves as a formal agreement between the two services
> - Both services are tested against this contract independently, which means teams can work in parallel without constant integration.
> - Without using a contract, teams would have to "hope or guess" that the communication will work as expected.

---

> **Consumer-Driven vs. Provider-Driven Contract Testing**
>
> 2 approaches:
>
> - **Consumer-driven contract testing** -- The consumer (like our cart service) sets expectations for how the provider (payment service) should respond.
> - **Provider-driven contract testing** -- The provider creates the contract, showing how its services operate, and consumers must adapt to it.
>
> Real-World example:
>
> - The hotel booking service needed specific information from the user profile service, like:
>   - User's name (for reservation)
>   - Payment methods (for billing)
>   - Loyalty program status (for benefits)
> - This approach had several benefits:
>   - The user profile team knew exactly what the hotel team needed
>   - We could test the hotel service in isolation using mock data that matched the contract
>   - When the real services were integrated, they worked together smoothly.

---

> **Advantages of Contract Testing**
>
> - Defects from underlying services can be found earlier in the Software Development LifeCycle.
> - The source of defects can be more easily identified
> - If a test fails, you know exactly which contract was violated and which service is responsible
> - Debugging is much faster compared to end-to-end testing.
> - An API change like a field name from userName to username could break multiple services; Contract tests catch this immediately before reaching a shared environment.
>
> Tools for implementing contract testing:
>
> - **Pact**: Lets consumer team define their expectations.
> - **Spring Cloud Contract**: works in Spring Boot ecosystems.
> - **Postman**: Used for simple contract testing scenarios.
>
> Example (Pact contract):
>
> ```json
> {
>   "provider": {
>     "name": "PaymentService"
>   },
>   "consumer": {
>     "name": "CartService"
>   },
>   "interactions": [
>     {
>       "description": "a request to process payment",
>       "request": {
>         "method": "POST",
>         "path": "/api/payments",
>         "headers": {
>           "Content-Type": "application/json"
>         },
>         "body": {
>           "orderId": "123",
>           "amount": 99.99,
>           "currency": "USD"
>         }
>       },
>       "response": {
>         "status": 200,
>         "headers": {
>           "Content-Type": "application/json"
>         },
>         "body": {
>           "paymentId": "456",
>           "status": "successful",
>           "transactionReference": "MATCHING(REGEX, '\\w{8}-\\w{4}-\\w{4}-\\w{4}-\\w{12}')"
>         }
>       }
>     }
>   ]
> }
> ```
>
> - The contract specifies exactly what the request should look like and what response is expected.
> - It uses pattern matching (e.g., MATCHING(REGEX,...)) for fields that might have dynamic values but still need to follow a specific format.

---

> **Real-World Implementation**
>
> 1. Identify all the API interactions between services
> 2. Define contracts for each interaction
> 3. Write tests that verify each service adheres to its contracts
> 4. Run these tests as part of your CI/CD pipeline (which we talked about in the previous lesson)
> 5. Block deployments if contract tests fail

---

> **Conclusion**
>
> 1. Understand API connections, documentation, and implement contract testing
> 2. Tools: Pact, Spring Cloud Contract, Postman.

---

### Transcript

"Explain test automation dependencies for an API infrastructure.

Let's dive into a topic that's super important in modern software development: API testing and the dependencies you need to understand when automating these tests.

When I first started working with APIs, I was like, what are all these endpoints? Where's my nice user interface to test? But once I got the hang of it, I realized that API testing is actually really powerful. And honestly, sometimes easier to automate than UI testing.

What is an API?

Let's back up a second. In case you're new to this concept, API stands for Application Programming Interface. Basically, it's how different software systems talk to each other.

Think of it like a waiter in a restaurant. You, the customer, don't go directly into the kitchen to get your food. You give your order to the waiter, who takes it to the kitchen and then brings back your meal. Similarly, an API takes requests from one system, delivers them to another system, and returns the response.

These days, most APIs are what we call RESTful APIs or GraphQL APIs, which communicate over HTTP, the same protocol your web browser uses to talk to websites.

API dependencies for test automation.

So when we're setting up automated testing for APIs, what dependencies do we need to understand? There are two critical ones.

API connections.

First, we need to understand the API connections. Basically, the business logic that can be tested automatically and the relationships between different APIs.

Let me show you a simple diagram of what this might look like. As we can see in this diagram, there's a whole flow between different API services. The User Service API talks to the Authentication API to verify users. Once authenticated, users can access the Product Catalog API, which checks the Inventory API to see what's available. Then users can add items to the Shopping Cart API, which eventually talks to the Payment API for checkout.

Understanding these connections is crucial because they tell you what APIs depend on other APIs, what order you need to test things in, and what mock services you might need to create.

For example, I once worked on an e-commerce system where we couldn't properly test the checkout process without first calling the Product API, then the Cart API, then finally the Payment API, in that exact order, with the right data flowing between them. If you don't map out these connections first, you'll end up with tests that fail for reasons that aren't obvious.

API documentation.

The second dependency is API documentation, which serves as a baseline for your test automation. Good API documentation includes all the endpoints or URLs you can call, what HTTP methods to use like GET, POST, DELETE, PUT, etc., required request parameters and headers, expected response formats, authentication requirements, and error codes and messages.

Here's an example of what API documentation might look like for a simple user service. As we can see in this example, the documentation tells us exactly what the endpoint is, what parameters it needs, what headers to include, and what responses to expect.

This is gold for test automation because it tells us how to form our requests, what to validate in the responses, and what error conditions to test for.

I've worked on projects where the API documentation wasn't the greatest. We had to reverse engineer how the API worked by looking at network traffic and browser dev tools. It wasn't a fun experience. Good documentation saves you a ton of time and frustration.

Integrated automated API testing.

Now let's talk about who does the API testing. It can be done by either developers or test automation engineers. But with the shift-left movement in testing, it's often a shared responsibility.

In case you've never heard of shift left, it's the practice of moving testing earlier in the development process. The idea is to catch issues sooner when they're cheaper and easier to fix.

In the ISTQB Foundation level syllabus, component integration testing and system integration testing are mentioned as levels where API testing fits in. But there's also a best practice called contract testing that's particularly useful for APIs.

Contract testing.

Contract testing is a type of integration testing that verifies that services can communicate with each other correctly, and that the data they share follows a specified set of rules known as the contract.

Imagine you have two teams working on different microservices. Team A builds a shopping cart service while Team B builds a payment service. The cart service needs to call the payment service to complete a purchase. Contract testing ensures that when the cart service makes that call, the payment service understands the request and responds in a way the cart service can understand.

Here's a visual representation of how contract testing works. As we can see in this diagram, the contract serves as a formal agreement between the two services. Both services are tested against this contract independently, which means teams can work in parallel without constant integration. Without using a contract, teams would have to hope or guess that the communication will work as expected when they attempt to communicate with each other.

Consumer-driven versus provider-driven contract testing.

There are two main approaches to contract testing.

Consumer-driven contract testing: the consumer, like our cart service, sets expectations for how the provider (the payment service) should respond. The consumer team creates the contract based on what they need.

Provider-driven contract testing: the provider creates the contract showing how its services operate and consumers must adapt to it.

Let me share a real world example. I worked on a travel booking system where we had separate services for flights, hotels, and car rentals. We used consumer-driven contract testing because each service had specific needs from the others.

For instance, the hotel booking service needed specific information from the user profile service like user's name for reservation, payment methods for billing, and loyalty program status for benefits. But it didn't care about other user data like password history or communication preferences. So the hotel service defined a contract saying "when I ask for user data, I expect these specific fields in this format."

This approach had several benefits. The user profile team knew exactly what the hotel team needed. We could test the hotel service in isolation using mock data that matched the contract. When the real services were integrated, they worked together smoothly.

Advantages of contract testing.

One of the main advantages of this approach is that defects occurring from underlying services can be found earlier in the software development life cycle, and the source of these defects can be more easily identified.

For example, if a test fails, you know exactly which contract was violated and which service is responsible. This makes debugging much faster compared to end-to-end testing, where the failure could be anywhere in the chain.

I've been in situations where an API changed silently, maybe a field name change from camelCase `userName` to all lowercase `username`, and it broke multiple services that depended on it. With contract tests, this kind of change would be caught immediately before it even made it to a shared environment.

Tools for contract testing.

There are several popular tools for implementing contract testing. Pact: a consumer-driven contract testing tool that lets consumer teams define their expectations. Spring Cloud Contract: a tool that works well in Spring Boot ecosystems. Postman: another tool that can be used for simple contract testing scenarios.

Here's what a simple Pact contract might look like. As we can see in this example, the contract specifies exactly what the request should look like and what response is expected. Notice that it even uses pattern matching for fields that might have dynamic values, but still need to follow a specific format.

Real world implementation.

In practice, when implementing contract testing into your API test automation strategy, you typically: identify all the API interactions between your services, define contracts for each interaction, write tests that verify each service adheres to its contracts, run these tests as part of your CI/CD pipeline (which we talked about in the previous lesson), and block deployments if contract tests fail.

I've seen this approach dramatically reduce integration issues in distributed systems. In one project, we were able to identify 80% of integration problems before services were even deployed to a shared environment.

So to wrap up, when implementing API test automation, you need to understand API connections (the business logic and relationships between different APIs) and API documentation (the complete specifications for working with each API). And remember, while developers or test automation engineers can handle API testing, a best practice is to implement contract testing, which verifies that services can communicate correctly, catches integration issues early, makes it easier to identify the source of defects, and supports both consumer-driven and provider-driven approaches.

In my experience, properly implementing these practices can save your team countless hours of debugging and frustration.

In the next video, we'll explore how to collect, analyze, and report test automation data to better understand your test results and improve your test automation solution over time."
