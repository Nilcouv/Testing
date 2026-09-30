# Mooc

## Identify where test automation produces unexpected results

### Screen

> **Root Cause Analysis Basics**
>
> - Dealing with unexpected test results happens to every automation engineer
> - Something fails that should pass, or something passes that you expected to fail
> - Identifying where unexpected results come from is an important skill
> - Test automation isn't always perfect
> - Knowing how to diagnose problems will save you tons of time and headaches
> - When a test script fails or passes unexpectedly perform root cause analysis
>   - Root cause analysis means finding the actual source of the problem, not just treating symptoms
>   - in test automation, we always want to address the root cause
>   - rerunning a failing tet without analysis doesn't solve anything
>   - collect evidence and analyze what's happening

---

> **Key Evidence to Collect**
>
> When performing root cause analysis, there are several key pieces of evidence you'll wan to gather:
>
> - **Test logs** -- show exactly what happened during test execution, step by step
> - **Performance data** -- Tests might fail du to timeouts or slow system performance.
> - **Setup and teardown information** -- Environment prep and cleanup issues can cause failures
> - **Screenshots or recordings** -- Visual evidence is invaluable for UI test failures.
>
> **Example**: E-commerce website
>
> - Test failed when adding items to the cart: button was clicked, but item count didn't increase
> - Performance data showed slower server response during peak hours
> - Test was checking for updated cart count before server processed the request
> - Root cause was a timing issue in the test, not a bug in the application
> - issue was fixed by adding a proper wait mechanism

---

> **Isolating the Problem**
>
> - Run just the failing test in isolation instead of the entire suite
> - Break down the test into smaller parts and run them individually if needed
>
> **Example**: If failing at step 8, create one test for steps 1-7 and another for step 8
>
> Intermittently failing tests can be broken into smaller components to isolate issues.
>
> **Test Isolation Process**
>
> ```mermaid
> flowchart TB
>     N1["**Full test (steps 1-10)**<br/>Intermittent failure"]
>     N2["**Setup (steps 1-7)**<br/>Passes consistently"]
>     N3["**Problem area (step 8)**<br/>Fails consistently"]
>
>     N1 --> N2
>     N1 --> N3
>
>     style N1 fill:#1565c0,color:#fff,stroke:#0d47a1
>     style N2 fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style N3 fill:#c62828,color:#fff,stroke:#b71c1c
> ```
>
> - Isolation helps pinpoint where the issue occurs, making debugging more efficient
> - Focus on the specific failing step and conditions causing the failure
> - Valuable for complex or intermittent failures that are hard to reproduce

---

> **Dealing with Intermittent Failures**
>
> Hypothetical causes:
> 
> 1. The test case itself
> 2. The System Under Test
> 3. The Test Automation Framework
> 4. The hardware or infrastructure
> 5. The network
>
> Running the test several times can help identify the cause. Example:
>
> ```javascript
> for (let i = 0; i < 50; i++) {
>   console.log(`Run #${i + 1}`);
>   try {
>     // Run the test
>     runTest('flakyTest');
>     console.log(' PASS');
>   } catch (error) {
>     console.log('X FAIL');
>     console.log(`Error: ${error.message}`);
>     // Capture additional diagnostic information
>     captureScreenshot(`failure-${i + 1}`);
>     logSystemResources();
>   }
>   // Small delay between runs
>   wait(2000);
> }
>
> // Analyze results
> analyzeTestRuns();
> ```
>
> - Run the test 50 times
> - Capture additional diagnostic information when a failure occurs
> - Helps spot patterns and gather clues about intermittent failures

---

> **Monitoring System Resources**
>
> Another extremely helpful technique is monitoring system resources during test execution.
> Test fail not because of bugs in the software logic, but because of resource constraints.
>
> - **CPU usage** - Is the processor being maxed out?
> - **Memory usage** - is the system running out of RAM?
> - **Disk I/O** - Are disk operations slowing things down?
> - **Network traffic** - Are network requests timing out of failing?
>
> **Example**:
>
> - Automate test suite on data processing
> - One test failing sometime on time out error
> - while monitoring system resource, discovered CPU usage spike to 100% during test, slowing everything down
> - root cause: processing a particular data set
> - solution: issue was fixed by optimizing how test process data

---

> **Log File Analysis**
>
> When analyzing log, look for clues like:
>
> 1. **Error messages** - These are the most obvious indicators of what went wong.
> 2. **Warning messages** - Sometimes these precede actual errors and can provide context.
> 3. **Timing information** - Look for delays or operations that took longer than expected.
> 4. **State changes** - Check if the application went through the expected states in the correct order.
>
> Logs comes from different sources:
>
> 1. **Test case logs** - What the test was trying to do
> 2. **SUT logs** - What the application was doing
> 3. **TAF logs** - What the test framework was doing
> 4. **System logs** - What was happening at the OS level

---

> **Checking Assertions**
>
> - Missing or incorrect assertions are a common cause of unexpected test results.
> - Assertions verify whether something is working as expected
> - Example: Check if the welcome message is displayed after login
> - Missing assertions can lead to false positives; Tests that pass but shouldn't
>
> **Example**: Test with/without proper assertions
>
> ```javascript
> function testLoginWithoutAssertions() {
>   navigateToLoginPage();
>   enterUsername("user123");
>   enterPassword("pass456");
>   clickLoginButton();
>   // Test will pass as long as no errors occur during these steps,
>   // even if the login actually failed!
> }
>
> function testLoginWithAssertions() {
>   navigateToLoginPage();
>   enterUsername("user123");
>   enterPassword("pass456");
>   clickLoginButton();
>
>   // Actually verify the login was successful
>   assert(isWelcomeMessageDisplayed(), "Welcome message should be displayed after login");
>   assert(getUsernameFromHeader() === "user123", "Username should appear in header after login");
> }
> ```
>
> - First test passes as long as steps complete without error, even if login failed
> - Second test verifies the login outcome with proper assertions
> - Always include appropriate assertions that verify the correct outcomes
> - Unexpected test passes might mean the test isn't actually checking the right thing

---

> **Getting Help from Others**
>
> Identifying some root cause may required specific expertise, so ask for help to other people, such as:
>
> - **Test Analysts** - Can help understand what the test is supposed to be checking
> - **Business Analysts** - Can clarify requirements
> - **Developers** - Can help with understanding the SUT's internals
> - **System engineers** - Can assist with infrastructure or environment issues.

---

> **Conclusion**
>
> 1. Perform root cause analysis by examining logs, performance data, and setup/teardown information
> 2. Isolate the problem by running tests individually or breaking them into smaller parts
> 3. Be especially methodical when dealing with intermittent failures
> 4. Monitor system resources to identify constraints and Analyze logs from multiple sources.
> 5. Check that all necessary assertions are in place and Don't hesitate to get help from others with complementary expertise.
>
> The goal is not to make the test pass, but to understand why the test was failing or passing unexpectedly.

### Transcript

"Identify where test automation produces unexpected results.

Root cause analysis basics.

Let's dive into something that happens to every automation engineer at some point: dealing with unexpected test results. You know those moments where you're running your automated tests and suddenly something fails that should pass? Or weirdly, something passes that you expect to fail. It can be pretty frustrating, right?

So let's explore how to identify where these unexpected results are coming from and how to troubleshoot them effectively. This is actually a really important skill because, let's face it, test automation isn't always perfect, and knowing how to diagnose problems will save you tons of time and headaches down the road.

So when a test script fails or passes unexpectedly, the first thing we need to do is perform what's called root cause analysis. Now, what exactly does that mean? Well, basically, it's the process of digging deeper to find the actual source of the problem, rather than just treating the symptoms.

Think of it like this. If your car makes a weird noise, you could just turn up the radio to mask it, which would be treating the symptom. Or you could figure out what's causing the noise and fix it, which is addressing the root cause. In test automation, we always want to do the latter.

So let's say you've got a failing test. Your first instinct might be to just rerun it and hope it passes, but that's not really solving anything. Instead, we need to collect evidence and analyze what's happening.

Key evidence to collect.

When performing root cause analysis, there are several key pieces of evidence you'll want to gather.

Test logs. These are probably the most important. They show you exactly what happened during test execution, step by step.

Performance data. Sometimes tests fail because of performance issues. For example, a test might time out because the system is running slowly.

Setup and teardown information. How is the test environment prepared? Was it cleaned up afterward? Problems here can cause unexpected test results.

Screenshots or recordings for UI tests. Having visual evidence of what the application looked like when the test failed can be invaluable.

Let me give you a real-world example. I was once working on an e-commerce website where we had a test that would sometimes fail when adding items to the cart. Our test logs showed that the add to cart button was being clicked, but the item count wasn't increasing. When we looked at the performance data, we noticed that during peak hours, the server response time was much slower. The test was failing because it was checking for the updated cart count before the server had time to process the request. So in this case, the root cause wasn't a bug in the application, but rather a timing issue in our test. We fixed it by adding a proper wait mechanism.

Isolating the problem.

A really helpful technique when dealing with unexpected test results is to isolate the problem. What do I mean by that? Well, instead of running your entire test suite, try running just the failing test in isolation. If that still doesn't give you enough information, you can even break down the test into smaller parts and run those individually.

For instance, if your test has ten steps and is failing at step eight, try creating a new test that just does steps one through seven to set up the environment, and then another that just does step eight.

Here's a simplified diagram of how you might approach this isolation process. As we can see in this diagram, when faced with an intermittently failing test — the blue box at the top of the diagram — we break it down into smaller components to isolate the issue. By dividing our original test into two parts, we can see that steps one through seven, the setup phase, consistently pass — which is the green box. Step eight, the problem area, consistently fails — which is the orange/red box. This isolation technique can help pinpoint exactly where the issue occurs, making debugging much more efficient. Instead of troubleshooting the entire test, you can focus specifically on step eight, examining what's happening at that precise moment and what conditions might be causing the failure. This approach is particularly valuable when dealing with complex test scenarios or intermittent failures that are difficult to reproduce consistently.

Dealing with intermittent failures.

Now, let's talk about one of the most challenging aspects of test automation: intermittent failures. These are tests that sometimes pass and sometimes fail without any apparent changes. They're often called flaky tests, and honestly, they can drive you a bit crazy.

Intermittent failures are particularly difficult to analyze because they're not consistently reproducible. The defect causing these failures could be in the test case itself, the system under test, the test automation framework, the hardware or infrastructure, or even the network.

When dealing with intermittent failures, it's often helpful to run the test multiple times and collect data about each run. Look for patterns. Does it fail more during certain times of the day? Does it fail after certain other tests have run? Is it related to system load?

One approach I've found useful is to create a small script that runs just the flaky test, say 50 times in a row, and logs all the results. This can help identify patterns that aren't obvious when running the test just once or twice. Here's an example of what such a script might look like.

As we can see in the code snippet, this script runs our flaky test 50 times, records each pass or fail, and captures additional diagnostic information when a failure occurs. This can help us spot patterns and gather more clues about what might be causing the intermittent failures.

Monitoring system resources.

Another extremely helpful technique is monitoring system resources during test execution. Sometimes tests fail not because of bugs in the software logic, but because of resource constraints. Things to monitor include: CPU usage — is the processor being maxed out? Memory usage — is the system running out of RAM? Disk I/O — are disk operations slowing things down? Network traffic — are network requests timing out or failing?

There was this one time I was working on an automated test suite for a data processing application. We had this one test that would sometimes fail with a timeout error. When we monitored the system resources, we discovered that during the test, the CPU usage would spike to 100%, causing everything to slow down. The root cause: the test was processing a particularly large data set that the system struggled with. By optimizing how the test handled the data, we were able to fix the issue.

Log file analysis.

Let's talk a bit more about log file analysis, because this is really where the rubber meets the road in finding the root cause of unexpected test results. When analyzing logs, you're looking for clues like:

Error messages. These are the most obvious indicators of what went wrong.

Warning messages. Sometimes these precede actual errors and can provide context.

Timing information. Look for delays or operations that took longer than expected.

State changes. Check if the application went through the expected states in the correct order.

It's important to analyze logs from multiple sources: test case logs — what the test was trying to do; SUT logs — what the application was doing; TAF logs — what the test framework was doing; system logs — what was happening at the OS level. By correlating information from all these sources, you can often pinpoint exactly what went wrong and when.

Checking assertions.

One really common source of unexpected test results is missing or incorrect assertions. Assertions are the checkpoints in your tests that verify whether something is working as expected. For example, if your test is supposed to verify that a user can log in successfully, you need an assertion that checks something like: is the welcome message displayed, or is the user's name shown in the header?

If these assertions are missing, your test might pass even when it shouldn't. This happens because the test just completes all its steps without error, but never actually verifies the outcome. We call these false positives: tests that pass, but shouldn't.

Here's an example of a test with and without proper assertions. As we can see in the code snippet, the first test will pass as long as all the steps complete without throwing an error, even if the login didn't actually work. The second test, however, actually verifies that the login was successful by checking for expected changes in the UI.

So always make sure your tests have appropriate assertions and that they're checking the right things. This is especially important when tests are passing unexpectedly. It could be that they're simply not verifying what they should be.

Getting help from others.

Finally, don't be afraid to ask for help. Identifying the root cause of unexpected test results can sometimes require expertise from different areas. Test analysts can help understand what the test is supposed to be checking. Business analysts can clarify requirements. Developers can help with understanding the SUT's internals, and system engineers can assist with infrastructure or environment issues.

I remember one particularly puzzling case where a test would only fail on Monday mornings. After much head-scratching, we consulted with a system engineer who pointed out that the system backups ran on Sunday nights, temporarily affecting database performance. Working together across teams was the key to solving that mystery.

All right, so let's wrap up this lesson. When your test automation produces unexpected results — whether tests are failing that should pass or passing when they should fail — you need to perform root cause analysis by examining logs, performance data, and setup/teardown information. Isolate the problem by running tests individually or breaking them into smaller parts. Be especially methodical when dealing with intermittent failures. Monitor system resources to identify constraints. Analyze logs from multiple sources. Check that all necessary assertions are in place. And finally, don't hesitate to get help from others with complementary expertise.

The goal isn't just to make the test pass, but to understand why it was failing or passing unexpectedly in the first place. This understanding helps improve both your tests and the system you're testing.

In the next video, we'll talk about how static analysis can aid test automation code quality."
