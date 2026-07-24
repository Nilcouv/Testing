# Mooc

## Describe the Configuration Needs of an Infrastructure that Enable Implementation

### Screen

> **Understanding Testability in the SUT**
>
> * Testability = availability of software interfaces that support testing.
> * Provides control and observability of the SUT
> * Should be designed alongside system features, not added later.
> * Responsibility of software architect, with input from Test Automation Engineer (TAE).

---

> **Solution for Better Testability**
>
> **Accessibility identifiers**
>
> * Unique IDs for UI elements.
> * Generated automatically or manually set.
>
> **System Variables**
>
> * Parameters changed through administration.
> * Example: enable "test mode"
>
> **Deployment Variables**
>
> * Set before deployment
> * Example: use test DB instead of production.

---

> **Key Aspects of designing for Testability**
>
> * Observability
>   * Interfaces give insight into internal behavior.
>   * Helps determine actual vs expected results.
> * Controllability
>   * Interfaces used to perform actions.
>   * Includes UI interactions, function calls, communication protocols
> * Transparency
>   * Clear documentation of components and interfaces.
>   * Supports testing at all levels

---

> **Why Testability matters**
>
> * Without Testability
>   * Automated tests are fragile, unreliable, and hard to maintain
>   * Tests may break frequently as the application changes
> * With Testability
>   * Good testability = reliable tests + meaningful results + less manual work
>   * Investing in testability early saves time later.

---

> **Conclusion**
>
> 1. Testability should be designed and implemented alongside other features
> 2. Solutions include: Accessibility identifiers, System environment variables, and Deployment variables
> 3. Key aspects: Observability, Controllability, and Architecture Transparency

### Transcript

"Describe the configuration needs of an infrastructure that enables implementation of test automation.

Understanding testability in the Sut.

Let's talk about the configuration needs that enable effective test automation implementation.

Starting with a key concept testability.

When we talk about testability of the system under test or Sut, we're really talking about the availability

of software interfaces that support testing.

These interfaces give us control and observability of the Sut, which is essential for effective automation.

Now here's something important to note.

Testability isn't something we add after the fact.

It should be designed and implemented right alongside the other features of the Sut.

This is typically the responsibility of a software architect, since testability is actually a non-functional

requirement of the system.

However, a test automation engineer or two is often involved to identify specific areas where improvements

can be made.

Solutions for better testability.

So what kinds of solutions can be used to improve the testability of our Sut?

Well, there are several options, each with different configuration needs.

Accessibility identifiers.

These are basically unique IDs for UI elements that make them easily findable by automated tests.

You know, I once worked on a project where we had no accessibility identifiers at all, and we had

to rely on XPath selectors that broke constantly.

It was a nightmare.

After we implemented proper IDs, our testability improved dramatically.

These identifiers can be generated automatically by development frameworks or set manually by developers,

which is often more reliable.

System environment variables.

These are parameters that can be changed through administration to enable easier testing.

For example, you might set an environment variable to put the application in a test mode that makes

certain features more accessible or predictable.

Deployment variables.

These are similar to system variables but can be set before starting deployment.

For instance, you might configure your application to use a test database instead of the production

one during automated test runs.

Key aspects of designing for testability.

When we're designing for testability, there are three main aspects we need to consider.

Observability.

The Sut needs to provide interfaces that give insight into what's happening inside.

Think of it like putting windows in a black box.

You need to be able to see what's going on inside.

Test cases can then use these interfaces to determine whether the actual results match the expected

results.

Let me give you a real world example.

I once worked on a banking application where we added login endpoints that would tell us exactly what

was happening with transactions behind the scenes.

This made it so much easier to verify that our tests were working correctly.

Controllability.

The Sut needs to provide interfaces that can be used to perform actions.

These might include UI elements that can be clicked or interacted with.

Function calls that can be made directly, communication elements like Tcpip or USB protocols.

Electronic signals for physical or logical switches.

Without controllability, you can observe the system, but can't actually test it properly.

Architecture.

Transparency.

The documentation of an architecture needs to be clear and understandable.

It should outline components and interfaces that provide observability and controllability at all test

levels.

This fosters quality throughout the testing process.

I've seen many projects where poor documentation led to confusion about how to test certain features

when the architecture is transparent.

Everyone understands how the system works and how to test it effectively.

Why this matters.

You might be wondering, why should I care about all this?

Well, configuring your infrastructure for testability isn't just a nice to have is essential for effective

test automation.

Without proper testability built into your Sut, your automated tests will be fragile, unreliable,

and difficult to maintain.

They'll break frequently when the application changes, and you'll spend more time fixing tests than

actually finding defects.

On the other hand, when testability is designed from the beginning, your automated tests become powerful

tools for assuring quality they run reliably, provide meaningful results, and save your team countless

hours of manual testing.

In my experience, teams that invest in testability configuration early in the project save exponentially

more time later on.

It's really one of those pay now or pay much more later.

Type of situations.

So to summarize, we've learned that testability should be designed and implemented alongside other

features.

Solutions for better testability.

Include accessibility identifiers, system environment variables, and deployment variables.

The three key aspects of designing for testability are observability, controllability, and architecture

transparency.

In the next lesson, we'll explore how test automation is leveraged within different environments.

This will build on what we've learned in this video about configuring your infrastructure for testability."
