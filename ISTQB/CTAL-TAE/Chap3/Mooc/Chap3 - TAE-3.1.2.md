# Mooc

## Explain  How to Design a Test Automation Solution

### Screen

> **What is a TAS (Test Automation Solution)**
>
> TAS : *The complete package for automating testing activities (beyond just tools/scripts)*
>
> Must account for existing/new tools.
>
> Defined by three requirement types:
> 
> 1. Functional requirements of the SUT
> 2. Non-functional requirements of the SUT
> 3. Technical requirements of the SUT

---

> **Implementing a TAS - Tool Options**
>
> Implementation options:
>
> - Commercial tools (paid)
> - Open-source tools (free)
> - Combination of both (most common)
>
> Healthcare project used Tricentis Tosca (UI) + JMeter (performance)
> Custom components/adapters are almost always needed

---

> **The Role of Test Automation Architecture**
>
> TAA defines the technical design for the automation solution
>
> **Key aspects to address:**
>
> - Selecting tools/libraries
> - Developing plugins/components
> - Identify connectivity/interface requirements
> - Connecting to test/defect management tools
> - Utilizing version control

---

> **The Role of Test Automation Architecture**
>
> **Selecting Test Automation Tools and Libraries**
>
> Critical decision - consider:
>
> - Application type (web/mobile/desktop)
> - Testing needs (UI/API/performance)
> - Team Skills
> - Budget
> - Integration capabilities
>
> **Example:** React frontend + REST
> - API --> Selenium + RestAssured
> (Java) or Cypress + Postman (JavaScript)

---

> **The Role of Test Automation Architecture**
>
> **Developing Custom Plugins/Components**
>
> Extend tool functionality for unique SUT needs
>
> **Example:** E-commerce project required custom checkout page component

---

> **The Role of Test Automation Architecture**
>
> **Identifying Connectivity and Interface Requirements**
>
> **Often overlooked** - includes:
>
> - Firewall configurations
> - Database connections
> - URL/endpoint
> - Mocks/stubs
> - Message queues
> - Protocols
>
> **Example:** Firewall blocked automation connections --> redesign required

---

> **The Role of Test Automation Architecture**
>
> **Connecting to Test Management and Defect Management Tools**
>
> Connect automation to tools like Jira (defects) and TestRail (Test cases)
>
> **Example**: Auto-create Jira tickets with screenshots/logs on test failure

---

> **The Role of Test Automation Architecture**
>
> **Utilizing Version Control and Repositories**
>
> **Manage automation code like software development:**
>
> - Git for version control
> - Organized repositories (e.g., by test level)
> - Code reviews/merge
>
> **Example:** Monolithic repository --> painful refactor into modular repos

---

> **A Real-World Example: E-commerce Website Automation**
>
> **Requirements:**
>
> _Functional:_ Browse product, checkout
> _Non-functional_: Holiday traffic, <2s load time
> _Technical:_ Chrome/Firefox/Safari + mobile
>
> **Tools**
>
> Selenium, Jmeter, RestAssured, BrowserStack
>
> **Custom Components**
>
> Shopping cart wrapper, Custom reporting
>
> **Connectivity**
>
> DB access, mock payment, gateway, API endpoint
>
> **Integration**
>
> Jira, TestRail
>
> **Version Control**
>
> Git + Jenkins + Docker

---

> **Common Pitfalls to Avoid**
>
> 1. **Tool-first approach** : Starting with a tool and then figuring out how to make it work for your needs, rather than starting with your needs and finding the right tool.
> 2. **Ignoring maintainability** : Creating an automation solution that works now but will be a nightmare to maintain as the application evolves.
> 3. **Insufficient abstraction** : Coupling your test too tightly to the implementation details of the SUT, so they break with every UI change.
> 4. **Neglecting reporting** : Not investing enough in good reporting capabilities, making it hard to interpret test result
> 5. **Siloed approach** : Designing the automation solution in isolation from the development process, rather than integrating it with your overall SDLC.

---

> **Conclusion**
>
> 1. TAS design requires: Understanding SUT requirements, Right mix of tools + custom components, Comprehensive connectivity planning, Integration with testing/dev ecosystem, proper code management
> 2. Automation is a journey - evolves with the application

---

### Transcript

"Explaining how to design a test automation solution.

What is a test automation solution?

So what exactly do we mean by a test automation solution or Tas?

Well, a Tas is basically the complete package of everything you need to automate your testing activities.

It's not just about picking a tool and writing some scripts.

It's much more comprehensive than that.

A test automation solution is defined by understanding three key types of requirements functional requirements

of the system under test, non-functional requirements of the system under test and technical requirements.

Plus you'll need to know about existing tools or tools you'll need to implement your solution.

Let me give you a real world example.

I once worked on a project for a healthcare application that needed to be thoroughly tested.

The functional requirements included things like users must be able to schedule appointments, and doctors

must be able to view patient records.

The non-functional requirements included security it needed to be HIPAA compliant, and performance.

It needed to handle 10,000 concurrent users, and the technical requirements included compatibility

with specific browsers and operating systems.

All of these requirements influence how we designed our test automation solution.

We couldn't just pick any tool off the shelf.

We needed something that could handle these specific requirements.

Implementing a test automation solution.

Now, when you're implementing a Tas, you have a couple of options.

You can either use commercial tools.

You know, the ones that you pay for.

Use open source tools, the free ones, or as is often the case, use a combination of both.

Let me tell you, in almost every project I've worked on, we've ended up using a mix of commercial

and open source tools because no single tool can do everything we need.

For example, on that healthcare project, we used a commercial tool called Tricentis Tosca for our

UI testing because it has strong support for healthcare industry regulations.

But we also used an open source tool, Jmeter, for performance testing because it was really good at

simulating heavy user loads.

And here's something important to keep in mind.

You'll almost always need to develop some custom components or adapters specific to your system under

test.

That's just the nature of the beast in test automation.

Every application has its unique characteristics that off the shelf tools won't perfectly address.

The role of test automation architecture.

Now, the test automation architecture is what defines the technical design for your overall solution.

Think of it as the blueprint or the master plan for your automation efforts.

Your TAA should address several key aspects, and I'll walk through each one with some examples from

my own experience.

Selecting test automation tools and libraries.

First up, you need to select the right tools and libraries for your specific needs.

This is probably one of the most critical decisions you'll make.

I remember a project where we initially chose a tool because it was what the team was familiar with,

but it turned out to be a nightmare for API testing, which was a major part of our testing effort.

We ended up having to switch tools mid project, which cost us a lot of time and effort.

So when selecting tools, consider factors like the type of application you're testing like web, mobile

or desktop.

The testing needs, UI testing, API testing, performance testing, the skills of your team, budget

constraints, and integration capabilities with your existing toolset.

For instance, if you're testing a web application with a react front end and a rest API backend.

You might use selenium webdriver for UI testing and rest assured for API testing.

If your team is comfortable with the Java language, or you might go with Cypress and Postman if they

prefer JavaScript.

Developing plugins and components.

Next, you'll likely need to develop custom plugins or components to extend the functionality of your

chosen tools.

I worked on an e-commerce project where the application had a unique checkout process that none of our

standard tools could properly interact with.

We had to develop a custom component that understood the specific DOM structure of the checkout page,

and could reliably interact with it.

This is pretty common.

No matter how comprehensive your tools are, there will almost always be some aspect of your SUT

that requires custom handling, identifying connectivity and interface requirements.

This is a big one that often gets overlooked until it's too late.

You need to identify all the connectivity and interface requirements for your automation solution.

These might include firewall configurations.

Do your tests need to access systems across firewalls?

Database connections?

Does your automation need to verify data in databases?

URL connections.

What endpoints does your automation need to access mocks and stubs?

Do you need to simulate components that aren't available?

Message queues?

Is your system using asynchronous messaging protocols?

What communication protocols does your SUT use?

Let me share a painful lesson from my own experience.

We once set up a beautiful test automation framework for a client, but when we deployed it to their

environment, we discovered that their corporate firewall blocked some of the connections our automation

relied on.

We had to redesign parts of our solution to work within their security constraints.

So make sure you understand all these requirements up front to avoid surprises later.

Connecting to test management and defect management tools.

Your test automation doesn't exist in isolation.

It needs to connect to your test management and defect management tools.

For example, when a test fails, you might want it to automatically create a defect in your bug tracking

system like Jira.

Or you might want to update the status of test cases in your test management tool like TestRail based

on the results of your automated test.

I worked on a project where we integrated our automation framework with Jira and Testrail.

When the tests failed, it would create a JIRA ticket with all the relevant details, screenshots,

logs, etc. and update the test case status in Testrail.

This saved our testers a ton of time and ensured nothing fell through the cracks.

Utilizing version control and repositories.

Last but definitely not least, you need to think about how you manage the code for your test automation.

This means choosing a version control system like git.

Setting up repositories for your automation code.

Establishing branching strategies and defining processes for code reviews and merges.

This might seem like standard software development practice, and it is.

But test automation is also software development and the same practices apply.

On one project, we didn't properly plan our repository structure, and we ended up with a monolithic

repository that became unwieldy as the project grew.

We had to refactor it into multiple repositories organized by test level unit, API and UI.

And it was a painful process.

A real world example.

E-commerce.

Website automation.

Let me tie this together with a comprehensive example.

Imagine we're designing a test automation solution for an e-commerce website.

Understanding requirements.

Functional requirements.

Users can browse products add to cart checkout.

Non-functional requirements.

Site must handle holiday shopping traffic.

Pages must load in under two seconds.

Technical requirements.

Compatible with Chrome, Firefox and Safari.

Responsive design for mobile.

Tool selection.

Selenium WebDriver for UI testing.

Jmeter for performance testing.

Rest assured for API testing and Browserstack for cross-browser testing.

Custom components.

A wrapper for the shopping cart functionality.

Custom reporting that aggregates results across different test types.

Connectivity requirements.

Database access to verify order placement.

Mock payment gateway for checkout.

Testing API endpoints for product catalog testing.

tool integration.

Connect with JIRA for defect management.

Integrate with Testrail for test case management.

Version control.

Git repositories organized by test type Jenkins for continuous integration.

Docker containers for consistent test environments.

With this comprehensive approach, we've designed a test automation solution that addresses all aspects

of testing the e-commerce website.

Common pitfalls to avoid.

Before we wrap up, let me share some common pitfalls I've seen teams fall into when designing their

test automation solution.

Tool first approach, starting with a tool and then figuring out how to make it work for your needs.

Rather than starting with your needs and finding the right tool.

Ignoring maintainability.

Creating an automation solution that works now, but will be a nightmare to maintain as the application

evolves.

Insufficient abstraction coupling your tests too tightly to the implementation details of the SUT so

they break with every UI change.

Neglecting reporting.

Not investing enough in good reporting capabilities.

Making it hard to interpret test results.

Siloed approach.

Designing the automation solution in isolation from the development process rather than integrating

it with your overall SDLC.

So, to wrap things up, designing the test automation solution is about much more than just picking

a tool and writing some scripts.

It requires a thoughtful approach that considers the specific requirements of your SUT, the right mix

of tools and custom components.

All the connectivity and interface requirements, integration with your broader testing and development

ecosystem, and proper code management practices.

By taking this comprehensive approach, you'll create a test automation solution that not only meets

your current needs, but can evolve with your application over time.

Test automation is a journey, not a destination.

Your solution will continuously evolve as your application changes and as new tools and techniques emerge.

In the next video, we'll dive deeper into how to implement layering into your test automation framework,

which is a crucial aspect of creating maintainable automation."