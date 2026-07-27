# Mooc

##  Explain the Major Capabilities in a Test Automation Architecture

### Screen

> **Generic Test Automation Architecture (gTAA)**
>
> - Understanding the big picture of test automation architecture
> - Core capabilities that make automation effective
> - Introduction to Generic Test Automation Architecture (gTAA)

---

> **Generic Test Automation Architecture (gTAA)**
>
> The fTAA is a high-level design concept that gives us an abstract view of how our test automation communicates with other systems.
>
> It shows us the big picture of how everything connects together.

---

> **Key connections in gTAA**
>
> Test Automation Framework
> - includes the layers "Test Generation", "Test Definition", "Test Execution" and "Test Adaptations"
> - Connects to "The SUT (System Under Test)", "Project Management", "Test management" and "Configuration management"

---

> **The interface of gTAA**
>
> - SUT interface -- Connects framework to the system being tested (e.g., web elements, APIs). Example: Banking project handled UI and API interactions
> - Project Management Interface -- Track automation progress (e.g., Jira integration)
> - Test Management Interface - Maps manual test cases to automated tests
> - Configuration Management Interface -- Manages CI/CD pipelines, environments, and versioning

---

> **Capabilities Provided by Test Automation Tools and Libraries**
>
> - The core capabilities that our test automation architecture should provide.
> - These are the essential functions that allow us to build and maintain effective test automation.

---

> **Capabilities Provided by Test Automation Tools and Libraries**
> 
> **Test Generation**
> 
> Automatically design test cases from models (e.g., model-based testing)
>
> Example: Telecom call routing system saved weeks of work.

---

> **Capabilities Provided by Test Automation Tools and Libraries**
> 
> **Test Definition**
>
> Separates test logic from SUT/tools (e.g., keyword-driven Excel sheets)

---

> **Capabilities Provided by Test Automation Tools and Libraries**
> 
> **Test Execution**
>
> Runs, tests, logs results, handles parallel execution
>
> Example: E-commerce project ran 500+ nightly in 2 hours

---

> **Capabilities Provided by Test Automation Tools and Libraries**
>
> **Test Adaptation**
>
> Adapts tests for different SUT components (e.g., web, mobile, APIs)

---

> **Healthcare Project**
>
> We built a test adaptation layer that abstracted away the details of how we interacted with the system.
>
> When the UI was completely redesigned, we only had to update our adaptation layer while the test definition remained unchanged.

---

> **Real-World Example - Online Banking App**
>
> - Test Generation -- Model-based tests for funds transfer workflows
> - Test Definition -- Keyword-driven test cases
> - Test Execution -- Nightly runs with automated reports
> - Test Adaptations -- Adapters for web, mobile and APIs

---

> **Conclusion**
>
> 1. gTAA provides abstract view of automation communication
> 2. Four key interfaces: SUT, Project/test/configuration management
> 4. Core capabilities: Test generation, Test definition, Test execution, Test adaptation

### Transcript

"Explained the major capabilities in a test automation architecture.

Generic test automation architecture.

When we talk about building test automation, we need to understand the big picture of how everything

fits together.

Kind of like understanding the blueprint before building a house.

So let's break down what we mean by test automation architecture and explore its core capabilities,

which are basically the fundamental functions that make our automation work effectively.

First, let's talk about what we call the Generic Test Automation Architecture, or GTA for short.

The GTA is basically a high level design concept that gives us an abstract view of how our test automation

communicates with other systems.

Think of it as the 30,000 foot view of your automation ecosystem.

It shows us the big picture of how everything connects together.

Let me give you an example from my own experience.

A few years ago, I was working on a banking application where we had to design a test automation architecture

from scratch.

We needed to understand how our automation would interact with not just the banking application itself,

but also with our test management system, the CI CD pipeline, and our configuration management system.

The GT-R helped us visualize these connections and plan accordingly.

Now, if we look at this diagram of the GT-R, we can see that it shows connections between test automation

Animation and several other systems.

The system under test.

Project management.

Test management and configuration management.

These connections aren't just lines on a diagram.

They represent real interfaces that determine how our automation solution will communicate with each

of these systems.

Let's explore these interfaces a bit more.

The interfaces of G.t.r.

So what are these interfaces actually about?

Well, they're basically the communication channels between our test automation and other systems.

The Sut interface.

This describes how our test automation framework connects to the system we're testing.

For example, if we're testing a web application, this interface might define how our automation interacts

with the web elements or if we're testing an API.

How our automation makes API calls.

In the banking project I mentioned earlier.

Our interface had to handle both UI elements for the customer facing portal and API calls for the back

end services.

We needed to ensure our framework could interact with both seamlessly.

The project management interface.

This describes how we track the development progress of our test automation.

It might connect to tools like Jira where we manage our user stories and tasks.

The test management interface.

This shows how we map our manual test case definitions to the automated test cases.

You know how sometimes we start with manual test cases and then we automate them?

This interface helps us maintain that relationship.

Configuration management interface.

This describes our CI, CD pipelines, environments and test where it helps us manage versioning and

deployment of our automation code.

I once worked on a project where we didn't properly define our test management interface.

And let me tell you, it was a nightmare trying to trace which automated tests corresponded to which

manual test cases.

We spent weeks reconciling that information, so trust me, these interfaces are important to define

up front.

Capabilities provided by test automation tools and libraries.

Now let's get into the meat of our topic, the core capabilities that our test automation architecture

should provide.

These are the essential functions that allow us to build and maintain effective test automation.

Test generation.

Test iteration is about automatically designing test cases based on a test model.

This is an optional capability, but it can be super powerful when implemented properly.

Have you ever heard of model based testing?

It's an approach where you create a model of your system's behavior, and then tools automatically generate

test cases from that model.

It's like giving the computer a map and saying, find all the possible paths through this map.

For example, I worked on a telecommunications project where we use a model based testing tool to generate

test cases for a complex call routing system.

Instead of manually writing hundreds of test cases, we created a state model of how calls should be

routed and the tool generated all possible test scenarios.

It saved us weeks of work.

Test generation is optional because not all projects need this level of sophistication.

But when you're dealing with complex systems with many possible paths, it can be a game changer.

Test definition.

Test definition supports the definition and implementation of test cases and or test suites.

This capability separates the test definition from the Sut and or test tools.

In simpler terms, it's where we define what we want to test.

It contains the means to define high level tests like verify user can log in, and low level tests like

enter username, enter password.

Click login button.

Verify.

Dashboard appears.

Test definition is crucial because it creates the blueprint for our automation.

It's like the recipe we follow to create our automated tests.

For instance, in a healthcare project I worked on, we had a comprehensive test definition layer that

allowed business analysts to define tests in Excel using a keyword driven approach, which are automation

framework then translated into executable code.

This separation allowed non-technical team members to contribute to the test definition process.

Test execution.

Test execution is pretty straightforward.

It supports running the tests and logging the results.

It provides a test execution tool to run the selected tests automatically and components for logging

and reporting.

But it's not just about clicking run.

A good test execution capability includes features like scheduling tests to run at specific times,

running tests in parallel to save time, handling test dependencies like when one test needs another

test to run first managing test data.

Or reporting test results in a meaningful way.

I remember working on an e-commerce project where our test execution capability allowed us to run over

500 test cases every night in less than two hours by executing them in parallel across multiple browsers

and environments.

Without this capability, the same tests would have taken days to run sequentially.

Tests.

Adaptation.

Last but definitely not least, test adaptation provides the necessary functionality to adapt our automated

tests for various components or interfaces of the Sut.

Think of it as the layer that allows our tests to communicate with different parts of the system.

It provides different adapters for connecting to the Sut via APIs, protocols, and services.

For example, if you're testing a system that has both a web interface and a mobile app, your test

adaptation layer will provide the components needed to interact with both interfaces, possibly using

different tools or libraries for each.

In my experience, a well-designed test adaptation layer can be the difference between a brittle automation

solution that breaks with every UI change, and a robust solution that can withstand frequent changes

to the Sut.

On a healthcare project I worked on, we built a test adaptation layer that abstracted away the details

of how we interacted with the system.

When the UI was completely redesigned, we only had to update our adaptation layer while the test definitions

remained unchanged.

This saved us from having to rewrite hundreds of test cases.

Real world example.

Let me share a real world example that ties all these capabilities together.

So imagine we're building an automation solution for an online banking application.

Test generation.

We might use a model based testing tool to generate test cases for complex workflows, like funds transfers

between accounts.

Test definition.

We define our test cases in a structured way, perhaps using a keyword driven or data driven approach

specifying what needs to be tested.

Test execution.

We'd set up our framework to execute these tests automatically, perhaps as part of our nightly build

process and generate reports.

Test.

Adaptation.

We create adapters that allow our tests to interact with the web interface, mobile app, and APIs of

the banking application by implementing all these capabilities in our architecture.

We'd have a comprehensive test automation solution that could effectively test all aspects of the banking

application.

So to wrap up, the major capabilities in the test automation architecture include a generic test automation

architecture that provides an abstract view of communication between test automation and connected systems.

Well-defined interfaces for connecting with the Sut.

Project management.

Test management and configuration management.

Core capabilities including test generation.

Test definition, test execution, and test adaptation.

Understanding these capabilities is crucial for designing an effective test automation solution that

can scale with your project and adapt to changes in the Sut.

In the next video, we'll dive deeper into how to design a test automation solution that incorporates

these capabilities."