# Mooc

## Explain How Test Automation is Leveraged within Different Environments

### Screen

> **How Test Automation is Leveraged in Different Environments**
>
> - Understanding test environment is crucial for designing effective automation strategies.
> - "Environments" refer to the different setups or configurations where tests run.
> - These are stages in the software pipeline with specific purposes.
> - Examples include containers, virtual machines, and cloud platforms.

---

> **What Are Test Environments?**
>
> - Different environments exists to verify software before it reaches users.
> - Can vary by project and methodology.
> - Examples of technical setups:
>   - Containers (Dockers)
>   - Virtualization software (VMware, VirtualBox)
>   - Cloud platforms (AWS, Azure, Google Cloud)
> - Real-world example: 5 serpate environments (dev>QA>UAT>Staging>Prod) helped improve our automation.

---

> **Local Development Environment**
>
> - Where developers create and test on their own machines.
> - Ideal for early testing:
>   - Component testing
>   - GUI testing
>   - API testing
> - Enables **white box testing** using IDEs (e.g., Visual Studio, Intellij).
> - Developers step through code and run unit tests (e.g., validating discounts)

---

> **Build Environment**
>
> - Used to build software and run automated tests.
> - Part of DevOps pipeline
> - Can be local or part of CI/CD (e.g., Jenkins Bitbucket).
> - Run low-level tests:
>   - Component tests
>   - Integration tests
>   - Static analysis (analysing code without execution)
> - Example: Bitbucket auto-builds code and runs unit tests on every push.

---

> **Integration Environment**
>
> - Runs fully integrated release candidate of the SUT.
> - Executes UI and API tests as a user would.
> - Focus on **black-box testing** only.
> - **intoduces monitoring for tests investigation:**
>   - Logs
>   - API calls
>   - DB queries
> - Example; Logs help identify test failures or real bugs.

---

> **Preproduction (Staging) Environment**
>
> - Resembles production as closely as possible
> - Focuses on **non-functional testing**:
>   - Performance
>   - Load
>   - Security
>   - Usuability
> - Stakeholders perform user acceptance testing here.
> - Automated test suites may be reused here.
> - Monitoring is critical for analysis.

---

> **Production/Operational Environment**
>
> - Where real users interact with the system.
> - Testing in production still happens!
> - Real-=time functional and non-functional checks.
> - **Techniques include:**
>   - Canary releases
>   - Blue/green deployment
>   - A/B testing
> - Example: Deploy search feature to 5% of users and monitor feedback.

---

> **Real-World Testing Example E-commerce**
>
> - **Local** -- Dev writes and tests recommendation code.
> - **Build** -- CI build and runs unit tests
> - **Integration** -- Automated tests check UI/API
> - **Prepoduction** -- Performance and business checks.
> - **Production** -- Feature rolled out to 10% then 100%.

---

> **Conclusion**
>
> 1. Test Automation is used across multiple environments
> 2. Each environment has a specific purpose
> 3. Strategy helps catch defects early and save time
> 4. Common mistake: No clear plan for where tests should run
>
> Environment purposes:
>
> - **Local**: Early testing
> - **Build**: Code validation
> - **Integration**: Full system tests
> - **Preproduction**: Final non-functional checks
> - **Production**: Real-world validation

### Transcript

"Explain how test automation is leveraged within different environments.

Now let's dive into how test automation is leveraged within different environments.

This is a really important topic because understanding the various environments will you'll run your

automated tests helps you design more effective test automation strategies.

So let's get started by talking about what we mean by environments in the context of test automation.

When we talk about test environments, we're essentially referring to the different setups or configurations.

Will we run our tests?

Think of these as different stages in your software development pipeline, each with its own purpose

in the real world.

Most projects have one or more environments to utilize for testing.

These environments can differ quite a bit between projects and methodologies, but they all serve the

common purpose of giving us places to verify our software works correctly before it reaches actual users.

From a technical perspective, these environments can be created using different approaches containers

such as Docker, virtualization software like VMware or VirtualBox, cloud platforms like AWS, Azure

or Google Cloud, and other approaches specific to your organization.

Let me share a quick personal example.

In one of my last projects, we had five different environments, each serving a specific purpose Managing

tests across all of these environments was challenging at first, but once we understood the role of

each environment, our test automation became much more effective.

Now, let's look at the different types of environments commonly used in software development, and

how test automation fits into each one.

Local development environment.

The local development environment is, well, exactly what it sounds like.

It's where developers initially create the software on their own machines.

This is where the first line of defense against bugs happens.

In this environment, developers can run automated tests to verify that the components they're working

on function correctly before sharing their code with the team.

Several test types can occur here.

Component testing will be testing the individual pieces of code.

Old guy testing where we're testing the user interface.

API testing, where we're testing the application programming interfaces.

One really important point about the local development environment is that it allows for white box testing.

Now, if you're not familiar with this term, white box testing is when you have knowledge of and access

to the internal structures of the application.

This is different from black box testing, where you only test from the user's perspective without looking

at the code.

Using an integrated development environment like Visual Studio, IntelliJ, or eclipse, developers

can perform white box testing to identify poor coding practices and quality problems as early as possible.

For example, a developer might write a unit test that directly calls a method to validate that it correctly

calculates a discount for online orders.

The developer can step through the code line by line, watching how variables change and making sure

the logic works correctly.

Build environment.

Moving up the pipeline we have the build environment.

The main purpose of this environment is to build the software and execute tests that check the correctness

of the resulting build.

In the DevOps ecosystem.

Now, if you're not familiar with the term DevOps, it's essentially a set of practices that combines

software development dev and IT operations ops to shorten the development life cycle and provide continuous

delivery of high quality software.

This environment can be either a local development environment or a continuous integration continuous

delivery agent.

In this environment, low level tests like component tests and component integration tests are performed

along with static analysis.

Static analysis is when we analyze code without actually executing it.

Think of it as spell checking for code.

For instance, in my previous company we used Bitbucket as our ci CD tool.

Every time a developer pushed code to our repository, Bitbucket would automatically build the application

and run all the unit tests.

If any tests failed, the developer would receive an email notification allowing them to fix the issue

immediately before it affected anyone else.

Integration environment.

After the build environment, we moved to the integration environment.

This is where things get more interesting from a testing perspective.

In this environment, we have a release candidate of the Sut that is fully integrated with other systems.

Here we can execute fully automated test suites like UI tests and API tests.

The key difference between the build environment and the integration environment is that in the integration

environment we're doing black box testing only.

We're testing the system from the outside as the user would experience it.

An important note about this environment is that it's the first place where monitoring should be present.

Monitoring lets us see what happens in the background during the use of the Sut, which is crucial for

efficiently investigating defects and failures.

For example, we might have logging set up to track all database queries, API calls, or error messages

that occur occurred during testing.

This gives us valuable context when a test fails.

Helping us determine if the issue is with the tests or with the application itself.

Pre-production environment.

Moving closer to production, we have the pre-production environment.

Some teams may call this the staging environment.

This environment is primarily used to assess non-functional quality characteristics such as performance

efficiency.

Now when I say non-functional testing, I'm referring to testing aspects of the software that aren't

about specific features, but rather how well the system performs overall.

This includes things like performance testing or how fast does it run load testing.

Meaning, can it handle many users?

Security testing.

Is it vulnerable to attacks and usability testing?

Meaning, is it easy to use?

While these non-functional tests can be performed in any environment?

There's extra focus on pre-production because it resembles production as closely as possible.

This is your last chance to catch issues before they affect real users.

Often, business stakeholders will perform user acceptance testing in this environment to verify the

final product.

And yes, you can execute your existing automated test suite here as well if necessary.

Like the integration environment, the pre-production environment is also monitored to help with troubleshooting

and analysis.

Production.

Operational environment.

Finally, we reached the production environment where real users interact with your application.

You might be surprised to learn that testing doesn't stop here.

The production environment can be used to assess both functional and non-functional quality characteristics

in real time, while users interact with the deployed system.

This approach is sometimes called testing in production, and includes practices like Canary releases,

where we gradually roll out a new feature to a small percentage of users before making it available

to everyone.

Blue green deployment.

This is running two identical production environments, only one of which is live at any time a b testing.

Here we show different versions of a feature to different users to see which performs better.

For example, a company might deploy a new search algorithm to 5% of their users as a canary release

and monitor metrics like search, success rate and user satisfaction before rolling it out to everyone.

Bringing it all together.

So we've covered a lot of different environments, each with its own purpose in the testing lifecycle.

Let me try to tie this all together with a real world example.

Imagine you're developing a new feature for an e-commerce website.

Let's say a recommended products section.

Here's how testing might flow through these environments.

In the local development environment, a developer writes code for the recommendation algorithm and

creates unit tests to verify that it returns the expected products based on the user's purchase history.

Moving on to the build environment When the code is pushed to the repository.

The CI CD system builds the application and runs all unit tests, ensuring the new code doesn't break

existing functionality.

Then, to the integration environment, the feature is deployed there where automated tests verify that

the recommendations appear correctly on the product page.

Clicking on a recommended product takes the user to the correct page in the API that serves recommendations.

Returns the correct data format.

Then moving on to the pre-production environment.

In this environment, performance tests verify that loading recommendations don't slow down the page.

Business stakeholders also check that the recommendations make sense from a.

Business stakeholders also check that the recommendations make sense from a business perspective?

And finally, the production environment.

The feature is initially rolled out to 10% of users, and metrics are collected to compare user engagement

with and without the new recommendations based on positive results.

It's gradually rolled out to all users.

To wrap up what we've learned.

Test automation can be leveraged in multiple environments through the software development lifecycle.

Each environment serves a specific purpose.

Local development environment is where we do early testing by the developers.

The build environment is where automated tests are run during the build process.

In the integration environment, we test this fully integrated system.

In the pre-production environment, we do final verification and non-functional testing.

And in the production environment, we do real world validation and continuous monitoring.

Understanding these environments helps you design a more effective test automation strategy that catches

issues at the right stage of development.

In my experience, one of the biggest mistakes teams make is not having a clear strategy for which tests

run in which environments.

By understanding the purpose of each environment, you can make better decisions about where to invest

your test automation efforts.

In the next video, we'll dive into the evaluation process for selecting the right tools and strategies

for test automation."
