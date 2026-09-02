# Mooc

## Analyze Deployment Risks and Plan Mitigation Strategies for Test Automation

### Screen

> **Introduction to Deployment Risks**
>
> - Deployment risks are often overlook until too late
> - Similar to planning a road trip without checking your car
> - Critical for ensuring smooth test automation implementation

---

> **TAF-SUT Interfacing**
>
> - Critical connection between Test Automation Framework and System Under Test
> - Web apps: Browser drivers (Selenium)
> - APIs: HTTP requests
> - example: developing an TAF, but Java applet incompatibility from legacy system

---

> **Packaging, Logging & Test Harness**
>
> - **Packaging** - JAR/NuGet/npm for consistent deployment
> - **Logging** - Critical for troubleshooting failures
> - **Test Harness** - JUnit (Java)/ NUnit (.Net)/ Jest (JavaScript)/ Pytest (Python) execution environments.

---

> **Deployment Risks: Firewall Openings**
>
> - Often overlook, catching team by surprise
> - Example : Tests tuning perfectly in development environment, but consistently failing in test environment due to corporate firewall. Easily solved by a firewall rule change.

---

> **Deployment Risks: Resource Utilization**
>
> You need to consider:
> 
> - CPU Usage
> - RAM requirements
> - Disk space for logs and reports
> - Network bandwidth

---

> **Technical Deployment Risks: Packaging**
>
> - Version control of test automation is crucial, just like for the SUT
> - Testware may need to be shared via a repository, either on-premises or in the cloud
> - Risk: inconsistent versioning leads to the "works on my machine!" issue.
> - Mitigation: use package managers like Maven, npm, or NuGet to lock dependencies.
> - Consider using docking for consistent environments.

---

> **Technical Deployment Risks: Logging**
> 
> Several logging levels : 
> 
> 1. **Fatal** - error causing execution to abort
> 2. **Error** - when test set fails, causing the test to fail
> 3. **Warning** - flag unexpected condition not breaking the test flow
> 4. **Info** - basic information (logging in as user, adding items to the cart, etc.)
> 5. **Debug** - defail execution information for investigation
> 6. **Trace** - blow by blow detail of the execution
>
> - Risk; Too much/too little logging
> - Example : Project where debug logging revealed race conditions, test trying to interact with unloaded element. problem solved by adding a wait condition.

---

> **Technical Deployment Risks: Test Structuring**
>
> - The test harness and fixtures are crucial for test automation solutions
> - Test fixtures control the test environment and test data
> - They define preconditions and post-conditions for test execution.
> - Fixtures group test cases into test suites for structured testing.
> - Risks: Poorly structured tests can lead to maintenance issues and flaky results.

---

> **Technical Deployment Risks: Test Structuring**
>
> **FIRST approach**:
> 
> - **F**ast - Test should run quickly
> - **i**ndependent - Test shouldn't depend on each other
> - **R**epeatable - Test should yield the same results every time
> - **S**elf-validating - Test should automatically determine if they pass of fail
> - **T**imely - Tests should be written at the right time

---

> **Technical Deployment Risks: Updating**
>
> - Automatic updates on test harnesses and devices can cause tests to break.
> - Technical risks include changes in version compatibility and UI updates.
> - To mitigate this risk, you need:
>   - Adequate power supplies, 
>   - Proper network connections
>   - Proper device configuration plan that control when and how updates happen.
> - Disabling automatic updates and implementing controlled processes avoids delays.

---

> **Real World Example: Mobile Testing Case Study**
>
> - **Real-World Challenges**
>   - Device availability/power
>   - Network connectivity
>   - OS updates
>   - App installation failures
> - **Mitigation strategies implemented**
>   - Set up charging stations and initial checks for battery and network.
>   - Added Wi-Fi access points.
>   - Disabled automatic updates, and created a controlled update process.
>   - Verified app installation before tests.

---

> **Risk Mitigation Framework**
>
> 1. **Identify** - List all deployment risks for your specific situation.
> 2. **Assess** - Rate each risk by likelihood and impact
> 3. **Prioritize** - Focus on high-impact risks first.
> 4. **Mitigate** - Develop specific strategies to address each prioritized risk.
> 5. **Monitor** - Keep an eye on how your mitigation strategies are working.

---

> **Risk Mitigation Framework**
>
> Risk Assessment Matrix
>
> | | Low Impact | Medium Impact | High impact | 
> |---|---|---|---|
> |High Likely| 3 | 4 | 5 |
> |Medium Likely| 2 | 3 | 4 |
> |Low Likely| 1 | 2 | 3 |
>
> (5) Critical Risk, (4) Major Risk, (3) Moderate Risk, (2) Minor Risk, (1) Low Risk

---

> **Conclusion**
>
> 1. Covered interfacing, packaging, logging, risk mitigation
> 2. Preparation is ley to successful deployment

---

### Transcript

"Analyze deployment risk and plan mitigation strategies for test automation.
Now we're going to dive into something that many teams overlook until it's too late.
Deployment risk.
The process is kind of like planning a road trip.
You spend all this time figuring out where you're going, what you'll do when you get there.
But sometimes you forget to check if your car is in good shape for the journey.
That's what deployment risk analysis is all about.
Making sure your test automation solution won't break down on the highway, so to speak.
Interfacing the Taff to the Sut.
So the first thing we need to think about is how your test automation framework connects to your system
under test.
This interfacing needs to be carefully considered as part of your architectural design.
What do I mean by interfacing?
Well, it's basically how your test framework talks to your application.
For example, if you're testing a web application, your framework might interface with it through the

browser using selenium WebDriver.

If you're testing an API, your framework might use HTTP requests to interact with the endpoints.

I once worked on a project where we spent weeks developing a beautiful test automation framework, only

to discover that our chosen approach couldn't properly interface with a legacy part of the system that

used an outdated Java applet.

We had to scramble to find a different solution, which wasted a lot of time and resources.

So getting this right early is super important.

Packaging.

Logging and test.

Harness selection.

During your pilot implementation, you need to think about how your package, your code handle test

logging and select the right test harness tools.

These factors are crucial for the pilot evaluation phase and can seriously impact your final decision.

Let's break these down.

Packaging.

Packaging is essentially how you bundle up your test automation code for distribution and execution.

You might package your code as Jar files in Java NuGet packages in.

Net or npm packages in JavaScript.

Why does this matter?

Well, imagine if every time you wanted to run your tests, you had to manually copy files to different

locations.

That would be a nightmare.

Proper packaging makes it easy to deploy your tests consistently across different environments.

Test logging.

Test logging is how your test automation solution records what happens during test execution.

Good logging is absolutely critical for troubleshooting failed tests.

Trust me on this one.

I've spent countless hours trying to figure out why a test failed because the logs didn't capture enough

information.

Test harness a test harness.

If you're not familiar with the term, is basically the software that runs your tests.

It provides the environment in which your tests execute and often includes functionality for setting

up preconditions, executing the tests, and cleaning up afterwards.

Popular test harnesses include JUnit for Java, N unit for.

Net jest for JavaScript and Pytest for Python.

Choosing the right one for your specific needs is important because it affects how you write, organize,

and execute your test.

Deployment risk.

Now let's talk about some specific deployment risks you need to watch out for.

Firewall openings.

This is a big one that often catches teams by surprise.

Your test automation might need specific network access to interact with the Sut or other systems.

If your corporate firewall blocks this access, your test will fail.

I remember a project where our test ran perfectly in the development environment, but failed consistently

in the test environment.

After a day of head scratching, we realized the test environment had a firewall blocking our database

connection.

A simple firewall rule change fixed it, but we could have avoided the delay if we'd identified the

risk earlier.

Resource utilization test automation can be resource intensive, especially if you're running many tests

in parallel.

You need to consider CPU usage, Ram requirements, disk space for logs and reports, and network bandwidth.

Here's a quick visualization of how resource utilization might look during test execution.

In the diagram, we can easily see how the CPU usage varies throughout the test run.

If your test consumed too many resources, they might slow down or even crash the test environment.

I've seen cases where a poorly optimized UI tests brought powerful servers to their knees, because

each browser instance was consuming massive amounts of memory.

Technical deployment risks.

Let's dig deeper into some technical deployment risks.

Packaging version.

Control of test automation is just as important for your Sut.

Your tests for may need to be uploaded into a repository to share across an organization, either on

premises or in the cloud.

A risk here is inconsistent versioning.

For example, if different team members use different versions of the same test libraries.

This can lead to the dreaded but it works on my machine problem.

To mitigate this, use a package manager like Maven, NPM, or NuGet to explicitly define and lock your

dependencies.

Also consider containerization technologies like Docker to ensure consistent environments.

Logging test logging is your window into what happened during test execution.

There are several logging levels and each serves a purpose.

Fatal.

These are catastrophic errors that cause the test execution to abort.

Like if your test framework can't even start up.

Error.

These occur when a test set fails, causing a test case to fail as well.

For instance, if your test expects a button to be clickable but it's disabled.

Warn these flag unexpected conditions that don't break the test flow.

Maybe a page load is slower than expected, but the test could still continue.

Info.

This gives you basic information about what the test is doing, logging in as a user.

Adding item to the cart, etc..

Debug.

This provides detailed execution information that's useful when investigating failures.

Trace.

This is even more detailed than debug, giving you a blow by blow details of the test execution.

The risk here is either too much or too little, logging too much, and you drown in data too little

and you can't diagnose failures.

I worked on a project where we initially only logged at the info level.

When tests started failing intermittently, we had no idea why.

Once we added debug logging, we discovered a race condition where our tests were trying to interact

with elements before they were fully loaded.

A simple wait condition fixed the issue, but we wasted days because our logging wasn't detailed enough.

Test structuring.

The most important part of your test automation solution is to test.

harness and the test fixtures included in it.

The fixtures are.

Everything that must be available for tests to run.

Test fixtures provide freedom and control in the test environment and test data.

They let you define preconditions and postconditions for test execution and group test cases into test

suites in several ways.

The risk here is poorly structured tests that are hard to maintain or that don't clean up after themselves.

This can lead to flaky tests or tests that fail inconsistently.

One approach I found helpful is to follow the first principles for test fixtures.

Fast, meaning tests should run quickly independent, so tests shouldn't depend on each other.

Repeatable Test should yield the same results every time.

Self-validating tests should automatically determine if they pass or fail.

And timely tests should be written at the right time, usually alongside the code they test.

Updating.

One of the most common technical risks involves automatic updates on test harnesses like CI agents,

and version changes on devices.

For example, imagine you have tests running on a form of mobile devices.

If those devices automatically update their operating systems overnight, your tests might break because

the UI has changed or because your test framework isn't compatible with the new OS.

To mitigate this risk, you need adequate power supplies, especially for mobile devices that can run

out of battery.

Proper network connections.

Proper device configuration plans that control when and how updates happen.

I once saw a team lose a whole day of testing because their test devices automatically updated to a

new iOS version overnight, and their tests weren't compatible with it.

After that, they configured the devices to disable automatic updates and implemented a controlled update

process.

Real world example.

Mobile testing challenges.

Let me share a real world example that combines several of these risks.

I was working with a team testing a mobile banking app across multiple devices.

We face several deployment challenges.

Device availability.

Our tests needed real devices to be powered on, have enough battery be connected to the network, and

have access to the Sut network connectivity.

The tests needed stable Wi-Fi, but the testing lab had dead spots for connectivity was weak.

OS updates.

As I mentioned earlier, unexpected OS updates for breakout tests.

App installation each test run needed a fresh install of the app.

But sometimes installation would fail silently.

Here's how we mitigate these risks.

We set up proper charging stations and implemented a check at the beginning of each test to verify battery

level and network connectivity.

We installed additional Wi-Fi access points to eliminate dead spots and added network checks to our

tests.

We disable automatic updates on all devices and created a controlled update process.

We added explicit verification after app installation to confirm it was successful before proceeding

with test.

The lesson here.

Identifying and addressing these risks early saved us countless hours of troubleshooting flaky tests

later.

A practical approach to risk mitigation.

So with all these potential risks, how do you approach mitigation in a practical way?

Here's a simple framework I like to use.

Identify list all potential deployment risks for your specific situation.

Assess.

Rate each risks by likelihood and impact.

For example, rating them by high, medium, or low.

Prioritize.

Focus on high likelihood high impact risks first mitigate.

Develop specific strategies to address each prioritized risk monitor.

Keep an eye on how your mitigation strategies are working.

Here's a simple risk assessment matrix you can use.

In this matrix.

The numbers represent priority, with five being the highest and one being the lowest.

For each risk plotted on this matrix and tackle them in priority order.

Conclusion.

So we've covered a lot of ground here.

We've looked at how the test automation framework interfaces with the system under test.

The importance of packaging, logging and test harness selection and a variety of deployment risks,

both general and technical.

Remember, the key takeaway here is that preparation is everything.

By identifying potential deployment risk early and developing mitigation strategies, you can save yourself

and your team a lot of headaches down the road.

In the next video, we'll discuss how to maintain your test automation solution over time, which is

just as important as setting it up correctly in the first place."