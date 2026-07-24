# Mooc

## Analyze System Under Test to Determine the Appropriate Test Automation Solution

### Screen

> **Understanding the Uniqueness of Systems**
>
> - Every system is different -- this must guide tests automation decisions.
> - Analyze system factors and characteristics.
> - Gather requirements considering scope and capabilities.

---

> **Real World Example: Different systems, Different Tools**
>
> - **Web Service Backend** -- API-focused tools.
> - **Mobile Banking App** -- Tools for touchscreen and mobile features.

---

> **Collaboritive Analysis Is Crucial**
>
> - Don't work alone -- Collaborate with: 
>   - Manual testers, 
>   - Business stakeholders,
>   - Business analysts.
> - Collaboration helps identify risks and improve solutions.

---

> **Requirements to Consider**
>
> **Test Process Activities**
> 
> - **Test management** -- Tracking what tests exists and their results.
> - **Test Design** -- Creating the test cases.
> - **Test Generation** -- Automatically creating test cases based on models or other inputs.
> - **Test Execution** -- Running the tests and collecting results.

---

> **Requirements to Consider**
>
> **Test Levels**
>
> - **Component Testing** -- Testing individual pieces of code
> - **Integration Testing** -- Testing how components work together
> - **System Testing** -- Testing the entire system
> - **Acceptance Testing** -- Testing whether the system meets business requirements

---

> **Requirements to Consider**
>
> **Test Types**
>
> - **Functional Testing** -- Does it work as expected?
> - **Performance Testing** -- Is it fast enough?
> - **Security Testing** -- Is it secure?
> - **Usability Testing** -- Is it easy to use?

---

> **Requirements to Consider**
>
> **Test Roles and Skill Sets**
>
> - Who will be creating and maintaining the automated tests?
> - What programming skills do they have?
> - How familiar are they with test automation concepts?

---

> **Requirements to Consider**
>
> **Product Considerations**
>
> - Which software products, product lines, and families should be supported?
> - What's the expected lifespan of the implemented TAS?
> - Will it need to support multiple versions of the software?

---

> **Requirements to Consider**
>
> **SUT Compatibility**
>
> - Is it a web application, mobile app, desktop application, or something else?
> - Does it have a graphical user interface (GUI), application programming interfaces (APIs), or both?
> - What technologies is it built with?

---

> **Requirements to Consider**
>
> **Test Data Availability**
>
> - Is it readily available?
> - What's the quality of that data?
> - Can you generate test data as needed?
> - Are there privacy or security concerns with the test data?

---

> **Requirements to Consider**
>
> **Edge Cases and Third-Party Applications**
>
> - How will you emulate unreachable cases?
> - How will you handle third-party applications that you can't control?
> - What about external systems that might not be available in a test environment?

---

> **A Practical Approach**
>
> 1. **Document the system architecture** -- Get a clear understanding of all components, interfaces, and technologies used in the SUT.
> 2. **Map out user journeys** -- Identify the key workflows that users will follow through the system.
> 3. **Identify high-risk areas** -- Which parts of the system would cause the biggest problems if they failed
> 4. **Assess technical feasibility** -- For each part of the system, determine how easily it can be automated
> 5. **Consider resource constraints** -- What budget, time, and expertise do you have available?
> 6. **Create a prioritized automation roadmap** -- Based on risk, feasibility, and constraints, decide what to automate first.

---

> **A Practival Approach**
>
> **A Real-World Example**
>
> - The payment processing had the highest business risk but was complex to automate.
> - The inventory management had APIs that were straightforward to test.
> - The touchscreen UI used a custom framework with limited automation support.
>
> **Based on this analysis, we decided to:**
>
> - Start with API automation for the inventory system (easy wins).
> - Build simulations for the payment processing (addressing high risk).
> - Create a limited set of UI tests for critical paths only (managing the technical challenge).

---

> **Conclusion**
>
> 1. Understanding that each system is unique and requires careful analysis.
> 2. Collaborating with various stakeholders to identify risks and requirements.
> 3. Considering multiple factors
> 4. Creating a prioritized approach based on risk, feasibility, and constraints 
>
> multiple factors including :
>
> - Test process activities to automate
> - Test levels to support
> - Test types to include
> - test roles and skill sets available
> - Product considerations and lifespan
> - SUT compatibility requirements
> - Test data availability and quality
> - Strategies for handling edge cases and third-party applications.

### Transcript

"Analyze the system under test to determine the appropriate test automation solution.

Understanding the uniqueness of systems.

Now let's talk about how to analyze the system under test to identify the appropriate test automation

solution.

First things first every system is different.

I mean, that sounds obvious, right?

But it's really important to remember this when you're thinking about test automation.

Even though there are systems that can be different from one another, there are still certain factors

and characteristics that we can analyze to help us build a successful test automation solution.

During your investigation of an Sut as a test automation engineer, you need to gather requirements

considering its scope and capabilities.

Let me give you a real world example.

A few years ago, I worked on two projects simultaneously.

One was a web service back end system with no UI, and the other was a mobile banking application.

The approaches we needed for automating these two systems were completely different.

The web service required API focused testing tools, while the mobile app needed tools that could interact

with touch screens and mobile device features.

Collaborative analysis.

Now, here's something really important that I want to emphasize.

This investigation shouldn't be done in isolation.

In fact, it's highly recommended to collaborate with other stakeholders like manual testers who may

know the testing challenges, business stakeholders who understand the business risk, and business

analysts who know the requirements inside and out.

By working together, you can identify as many risks and potential mitigations as possible to create

a more beneficial test automation solution for the future.

I remember on one project, we initially missed some critical business logic because we didn't involve

the business analyst in our automation planning.

We ended up having to redo a significant portion of our framework later, which was a waste of time

and resources.

So trust me on this one.

Collaboration is key.

Requirements to consider.

So what exactly should you be looking for when analyzing the system for test automation?

Let's break down the requirements you should consider.

Test process activities.

First, you need to think about which test process Activities should be automated.

These might include test management, tracking what tests exist in the results.

Test design.

Creating the test cases.

Test generation automatically creating test cases based on models or other inputs.

Test execution.

Running the tests and collecting results.

For example, in a regulated industry like healthcare, you might need robust test management automation

to provide compliance while in a fast moving startup, automated test execution might be a priority.

Test levels.

Next, consider which test levels need to be supported by your automation component.

Testing.

Testing individual pieces of code.

Integration.

Testing.

Testing how components work together.

System testing.

Testing the entire system.

Acceptance testing.

Testing whether the system meets business requirements.

I've worked on projects where we focus almost exclusively on system level automation, because that's

where we had the most regression issues.

On other projects, we automated primarily at the component level because that gave us the fastest feedback.

Test types.

You'll also need to consider which test types should be supported.

Functional testing.

Does it work as expected?

Performance testing.

Is it fast enough?

Security testing.

Is it secure?

Usability testing.

Is it easy to use?

And many others.

Remember that different test types might require different automation approaches or even different tools

entirely.

Test roles and skill sets.

This is a big one that's often overlooked.

Your automation solution needs to be usable by the people who will actually be working with it.

Consider who will be creating and maintaining the automated tests.

What programming skills do they have?

How familiar are they with test automation concepts?

I once joined a team that had invested in a complex code automation framework, but most of their testers

had limited programming experience.

The framework was technically impressive, but practically useless because no one could maintain it.

Product considerations.

You also need to think about the software products themselves.

Which software products, product lines, and families should be supported?

What's the expected lifespan of the implemented TOS?

Us.

Will it need to support multiple versions of the software?

For instance, if you're automating tests for a product family with multiple variations, you'll need

a framework that allows for easy adaptation to different configurations.

Sut compatibility.

What kind of Suts need to be compatible with your test automation solution?

Consider is it a web application, mobile app, desktop application, or something else?

Does it have a graphical user interface, application programming interfaces, or both?

What technologies is it built with?

Each type of application requires different automation approaches.

For example, web applications might be automated using tools like playwright, while APIs might use

tools like karate DSL.

Test data availability.

This is a huge factor that can make or break your automation efforts.

Is test data readily available?

What's the quality of that data?

Can you generate test data as needed?

Are there privacy or security concerns with the test data?

On one healthcare project I worked on, we had to spend almost as much time creating realistic but anonymized

test data as we did on the automation itself.

Edge cases and third party applications.

Finally, consider how you'll handle special situations.

How will you emulate unreachable cases?

How would you handle third party applications that you can't control?

What about external systems that might not be available in a test environment.

For example, if your system integrates with a payment processor, you probably won't want to run real

credit card transactions during automated tests.

You'll need to figure out how to simulate or mock these interactions.

A practical approach.

Let me walk you through a practical approach I've used for analyzing systems.

Document the system architecture.

Get a clear understanding of all components, interfaces, and technologies used in the Sut.

Map out user journeys.

Identify the key workflows that users will follow through the system.

Identify high risk areas.

Which parts of the system would cause the biggest problems if they failed?

Assess technical feasibility For each part of the system, determine how easily it can be automated.

Consider resource constraints.

What budget, time, and expertise do you have available?

Create a prioritized automation roadmap based on risk, feasibility and constraints.

Decide what to automate first.

Let me share a real example.

We were automating a retail point of sale system that had a touch screen interface connected to inventory

systems and process payments.

Our analysis revealed the payment processing had the highest business risk, but was complex to automate.

The inventory management had APIs that were straightforward to test.

The touch screen UI used a custom framework with limited automation support.

Based on this analysis, we decided to start with API automation for the inventory system for easy wins.

Build simulations for the payment processing to address the high risk.

Create a limited set of UI tests for critical paths only, which helped us manage the technical challenge.

This prioritized approach gave us the best return on our automation investment.

To wrap up, analyzing a system under test to determine the appropriate test automation solution involves

understanding that each system is unique and requires careful analysis, collaborating with various

stakeholders to identify risks and requirements.

Considering multiple factors, including test process activities to automate test levels to support.

Test types to include test roles and skill sets available.

Product considerations and lifespan Sut compatibility requirements.

Test data availability and quality.

Strategies for handling edge cases and third party applications.

Creating a prioritized approach based on risk, feasibility and constraints.

Remember, the goal isn't to automate everything, it's to automate the right things and the right way

to provide the most value.

A well thought out analysis is the foundation of successful test automation.

In the next video, we'll look at how to illustrate the technical findings of your tool evaluation,

which builds directly on this analysis."