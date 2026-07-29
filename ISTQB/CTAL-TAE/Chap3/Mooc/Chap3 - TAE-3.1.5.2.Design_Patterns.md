# Mooc

## 

### Screen

> 

---

> 

---

> 

---

> 

---

> 

---

> 

---

> 

---

> 

---

> 

---

> 

---

> 

---

### Transcript

"Apply design principles and design patterns in test automation.

Design patterns.

Design patterns are proven solutions to common problems in software design.

They're like recipes or blueprints that have been tested by thousands of developers over many years.

Let's look at some key patterns that are particularly useful in test automation.

Fact pattern.

The fact pattern provides a simplified interface to a complex system or set of classes.

It's like the front desk at a hotel.

You don't need to interact with housekeeping, maintenance, and the restaurant separately.

You just talk to the front desk and they coordinate everything for you.

In test automation.

The fact pattern helps us hide the complexity of test libraries and expose only what testers need to

create test cases.

Here's a simple example of the fact pattern.

Notice how the user actions vacate presents a much simpler interface for the test code.

Instead of dealing with finding elements, waiting, and interacting separately, the test just calls

login.

I once worked at a company where we were trying to get manual testers to learn automation.

They were intimidated by the complexity of selenium WebDriver.

By creating a simple fact that wrapped the common actions, we were able to ease them into automation.

Gradually.

They could start with high level methods like login and search for product, and as they gain confidence,

they could learn the more complex underlying APIs.

Singleton pattern.

The singleton pattern ensures that a class has only one instance and provides a global point of access

to that instance.

It's like having only one principal at a school.

There's just one person in charge and everyone knows how to find them.

In test automation, the singleton pattern is often used for things like driver management, configuration,

and login.

Let's look at an example code snippet that uses the singleton pattern.

So as you can see, we have a single instance of the driver manager.

And we have a private constructor that prevents direct instantiation.

And there's a global access point with the synchronized method.

And then down at the bottom on line 43, we can see how it would be used in a test where we have our

WebDriver variable.

And that is an instance of the driver manager Getinstance dot get driver.

So this pattern ensures that all your tests use the same WebDriver instance, which prevents issues

like having multiple browser windows open at the same time and helps with resource management.

But be careful with singletons.

They can make testing more difficult since you can't easily swap out dependencies and create hidden

dependencies.

So use them judiciously.

As an example with more positive results using the pattern I once had a project where before we implemented

the singleton pattern, each test was creating its own browser instance.

When we ran tests in parallel, we'd have dozens of chrome windows open, which bog down the test machine.

After implementing the Singleton Driver Manager, we were able to control browser creation and re-use

instances when appropriate, which made our tests run much faster.

Page object model.

The page object model or palm.

As you may hear it called, is probably the most widely used design pattern in UI test automation.

It creates a separate class for each page of the application, which contains the page elements and

methods to interact with those elements.

The key benefit is that it separates the test logic from the page specific details, making tests more

maintainable.

Here's an example illustrating how it works.

Here we create a base page class that has all the common functionality for pages.

Next, we create a class for the login page that extends the base page and has its own page specific

methods.

Then we create another class for the dashboard page.

Finally, we write a test using the page objects by using the Page object model pattern.

If the login page changes, you only need to update the login page class, not all the tests that use

it.

For example, if the login button's ID changes from login button to submit login, you only need to

update it in one place.

the login button locator in the login page class.

Flow model pattern.

The flow model pattern is an expansion of the page object model.

It introduces an additional layer of abstraction over the page objects, which stores all the user flows

that interact with multiple page objects.

Think of it this way page objects represent the pages of your application, while flow models represent

the journeys users take through those pages.

Let's break this pattern down into its components with an example code snippet.

This first code snippet shows a login flow class that encapsulates login related user journeys.

Here's what's happening.

The class contains Instances of all the pages involved in login flows, login page and dashboard page.

It provides methods that represent complete user stories or journeys, not just individual page actions.

Each method handles the coordination between multiple pages to accomplish a business task.

For example, login and navigate to reports combines logging in and navigating to reports into a single

method call.

This abstracts away the details of which pages are involved and which methods need to be called.

This is powerful because it allows your test to focus on business scenarios rather than UI interactions.

Notice how the flow encapsulates the navigation between pages.

The test doesn't need to know that going to reports happens on the dashboard page after login.

This second snippet shows a more complex shopping flow class that manages e-commerce user journeys.

Here's what makes it valuable.

It manages a larger set of page objects home page, search results page, product page, cart page,

and checkout page.

It provides methods at different levels of granularity.

Small flows like search for product medium flows like add product to cart and complete flows like search

and buy product.

It handles the transitions between multiple pages automatically.

The search and buy product method is particularly impressive because it encapsulates an entire purchase

flow in a single method call.

Without the flow model, this would will require a test to directly interact with five different page

objects and manage all the transitions between them.

Another benefit is that the flow can handle data creation like the credit card and address objects internally.

This keeps tests cleaner and more focused on the business scenario rather than test data.

Setup.

This third snippet shows a test that uses the flow model.

Notice how incredibly concise and readable it is.

The test creates a shopping flow instance.

It calls a single method search and buy product to perform a complex operation.

Then it makes assertions on the result.

The flow model pattern is especially useful for complex applications where user flows often span multiple

pages.

It allows you to encapsulate entire business processes in a single method call, making your tests more

readable and maintainable.

On an e-commerce project I worked on, we had complicated checkout flows involving multiple pages and

different paths depending on the customer type, payment method, shipping options, etc. by implementing

flow models, we were able to encapsulate these complex flows into easy to use methods like complete

purchase with credit card or complete purchase with PayPal.

Our tests became much more focused on the business scenarios, rather than the mechanics of navigating

through the application.

The double layer of abstraction with Pageobjects plus the flow models gives you a clear separation between

In the hell of interacting with page elements, the page objects, the wad of completing business processes,

flow models, and the why of verifying application behavior.

The test.

This makes your code much more maintainable and easier to understand.

Common pitfalls and best practices.

Before we wrap up, let's talk about some common pitfalls and best practices when applying these principles

and patterns.

Some of the pitfalls are overengineering.

Don't create complex abstractions just for the sake of it.

Start simple and refactor as needed.

Rigid frameworks don't build frameworks that are so rigid that they can't adapt to changing requirements.

Forgetting the goal.

Remember, the goal is to test the application, not to build a perfect framework.

If your design makes tests harder to write or understand, reconsider it.

Ignoring context.

What works for a large enterprise application might be overkill for a simple website.

Choose patterns appropriate to your context.

In some of the best practices include.

Start with proven patterns.

Begin with established patterns like the Page Object model before experimenting with custom solutions.

Focus on readability tests should tell a story about how the application is used.

Not get lost in implementation details.

Refactor regularly as your understanding evolves.

False.

Refactor your framework to incorporate new insights.

Keep tests independent.

Each test should be able to run independently of others.

Avoid dependencies between tests.

Balance.

Abstraction and correctness.

Too much abstraction can make code hard to understand, while on the other hand, too little can make

it hard to maintain.

Conclusion.

We've covered a lot of ground covering design patterns.

Let's recap the key points.

Test automation is a software development activity, so software design principles apply.

The four key object oriented principles.

Encapsulation abstraction inheritance and polymorphism provide the foundation for good test automation

design.

The solid principles.

Single responsibility.

Open.

Close.

Liskov substitution.

Interface segregation and dependency inversion.

Help create more maintainable and flexible code.

Key design patterns for test automation include the fact pattern, singleton pattern, page object model,

and the flow model pattern.

Apply these principles and patterns isn't just theoretical, it makes a real difference in how maintainable,

scalable, and effective your test automation is.

In the next video, we'll talk about implementing test automation.

Building on these design concepts to create robust, maintainable test automation solutions."