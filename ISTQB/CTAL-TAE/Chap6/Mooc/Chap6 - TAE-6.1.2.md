# Mooc

## Analyze Data from the Test Automation Solution and the System Under Test to Better Understand Result

### Screen

> **Introduction to Test Result Analysis**
>
> Two main things we're looking for:
>
> - Possible failure in the SUT (System Under Test)
> - Possible failure in our TAS (Test Automation Solution)
>
> The data from our TAS is usually our primary source of information, while data from the SUT gives us additional context.

---

> **Analyzing Test Environment Data**
>
> is super helpful for properly sizing our test automation resources, especially if you're running tests in the cloud.
>
> You might need to analyze:
>
> - Cluster and resource usage (CPU, RAM, etc.).
> - Whether to run single or multi-browser tets (cross-browser testing).
>
> Example: banking application, test randomly timing out, analysis shows test environment experienced CPU spike. solution was to increase the virtual machine size in the cloud when running more than 10 parallel test sessions.
>
> ```mermaid
> xychart-beta
>     title "CPU Usage vs 80% Threshold"
>     x-axis ["08h00", "08h15", "08h30", "08h45", "09h00", "09h15", "09h30", "09h45", "10h00", "10h15", "10h30", "10h45", "11h00", "11h15", "11h30", "11h45", "12h00", "12h15", "12h30", "12h45", "13h00", "13h15", "13h30", "13h45", "14h00"]
>     y-axis "%" 0 --> 100
>     line "80% Threshold" [80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80, 80]
>     line "CPU usage" [35, 45, 60, 75, 88, 78, 62, 55, 50, 52, 62, 75, 85, 76, 60, 52, 48, 50, 60, 72, 82, 72, 58, 48, 40]
> ```
>
> Peak at 09:00, 11:00 and 13:00 coincides with a test failure (CPU above threshold).

---

> **Comparing Test Results with Previous Executions**
>
> Helps us identify trends and patterns.
>
> You might notice that:
>
> - A test that passed yesterday is failing today (potential regression.).
> - A test that's been failing for weeks suddenly passes (potential fix).
> - A test that fails intermittently (a potential flaky test).
>
> Example: subtle feature breakages across builds; historical comparison linked failures to one developer's changes on the authentication module.

---

> **The Process of Analyzing Test Execution Failures**
>
> 1. Check if the same failure happened in the previous test executions.
> 2. If it's not a known issue, identify the test case and what it's testing.
> 3. Find which test step of the test case failed.
> 4. Analyze the test logs to understand the state of the SUT when the failure occurred.
> 5. Log if in your defect management system, including all the necessary information and logs.
>
> ```text
> [2025-04-15 09:32:14] INFO: Test case 'CheckoutProcessTest' started
> [2025-04-15 09:32:16] DEBUG: Adding product 'Smartphone XS' to cart
> [2025-04-15 09:32:18] DEBUG: Navigating to checkout page
> [2025-04-15 09:32:20] DEBUG: Entering shipping information
> [2025-04-15 09:32:22] ERROR: Element not found: 'payment-method-selector'
> [2025-04-15 09:32:22] ERROR: Screenshot saved: checkout_failure_20250415_093222.png
> [2025-04-15 09:32:22] INFO: Test case 'CheckoutProcessTest' failed
> ```

---

> **Using SUT Audit Logs with Correlation IDs**
>
> ```mermaid
> ---
> title: Correlation ID Flow Through System Components
> ---
> sequenceDiagram
>     participant WB as Web Browser<br/>(User Checkout)
>     participant WS as Web Server<br/>(API Gateway)
>     participant AS as Auth Service<br/>(Validation)
>     participant Pd as Product<br/>(Inventory Check)
>     participant Pm as Payment<br/>(Processing)
>
>     Note over WB,Pm: Correlation ID a7c9be1-f2d4
>     WB->>WS: request
>     WS->>AS: request
>     AS-->>WS: response
>     WS->>Pd: request
>     Pd-->>WS: response
>     WS->>Pm: request
>     Pm-->>WS: response
>     WS-->>WB: response
> ```
>
> Correlation ID (`a7c9be1-f2d4`) follows the request through each system component.
>
> **TAS log**
>
> ```text
> [2025-04-15 10:45:23] DEBUG: Submitting payment with correlation ID: a7c9b3e1-f2d4-4c18-8f09-6e21d35abc89
> [2025-04-15 10:45:24] ERROR: Payment failed
> ```
>
> **SUT log**
>
> ```text
> [2025-04-15 10:45:23.145] INFO [a7c9b3e1-f2d4-4c18-8f09-6e21d35abc89] - Payment-Service: Received payment request for order #12345
> [2025-04-15 10:45:23.278] INFO [a7c9b3e1-f2d4-4c18-8f09-6e21d35abc89] - Payment-Service: Contacting external payment gateway
> [2025-04-15 10:45:23.892] ERROR [a7c9b3e1-f2d4-4c18-8f09-6e21d35abc89] - Payment-Service: External gateway timeout after 500ms
> [2025-04-15 10:45:23.945] INFO [a7c9b3e1-f2d4-4c18-8f09-6e21d35abc89] - Payment-Service: Returning error response to API Gateway
> ```

---

> **Special Consideration: Test Environment Availability**
>
> - Sometimes, all your tests might fail at once, either with the same error or with what appear to be unrelated errors
> - One of hte first thing to check is whether your test environment was fully available
> - The root cause was a single environment issue.

---

> **Real-World Example: Debugging a Complex Registration Flow**
>
> Here's how we analyzed it:
>
> - The test had a 15% failure rate.
> - We looked at the specific test step where it was failing
> - In the failing cases, the test was timing out while waiting for the confirmation email.
> - During peak test execution times, the email service was experiencing higher latency.
> - The email service was resource-constrained.

---

> **Quick Tip — Visualization Best Practices**
>
> - Create dashboards with multiple metrics to spot patterns quickly.
> - Include: test execution trends over time, failure rates by component and environment, performance metrics.
> - Use a single view to make correlations between factors easier to see.
> - Visualization supports analysis — it is not just reporting for stakeholders.
>
> **Test Execution Trends (Last 7 Days)**
>
> ```mermaid
> %%{init: {'xyChart': {'showLegend': true}, 'themeVariables': {'plotColorPalette': '#2e7d32, #f9a825, #c62828'}}}%%
> xychart-beta
>     title "Test Execution Trends (Last 7 Days)"
>     x-axis ["Apr 17", "Apr 18", "Apr 19", "Apr 20", "Apr 21", "Apr 22", "Apr 23"]
>     y-axis "Tests" 0 --> 200
>     line "Passed tests" [175, 155, 130, 125, 128, 150, 170]
>     line "Stopped tests" [10, 20, 30, 32, 30, 20, 12]
>     line "Failed tests" [15, 25, 40, 43, 42, 30, 18]
> ```
>
> **Environment Performance Metrics**
>
> ```mermaid
> %%{init: {'xyChart': {'showLegend': true}, 'themeVariables': {'plotColorPalette': '#1565c0, #6a1b9a, #ef6c00'}}}%%
> xychart-beta
>     title "Environment Performance Metrics"
>     x-axis ["Apr 17", "Apr 18", "Apr 19", "Apr 20", "Apr 21", "Apr 22", "Apr 23"]
>     y-axis "%" 0 --> 100
>     line "CPU Usage" [45, 52, 48, 70, 65, 55, 50]
>     line "Memory Usage" [60, 62, 58, 75, 72, 68, 64]
>     line "Response Time" [25, 28, 30, 55, 48, 35, 32]
> ```
>
> Response Time shown on the same 0–100 scale for dashboard comparison (relative latency index).
>
> **Failure Rate by Component**
>
> ```mermaid
> %%{init: {'xyChart': {'showLegend': true}, 'themeVariables': {'plotColorPalette': '#c62828'}}}%%
> xychart-beta
>     title "Failure Rate by Component"
>     x-axis ["Authentication", "Dashboard", "Payment", "User Profile", "Settings"]
>     y-axis "%" 0 --> 25
>     bar "Failure rate" [18, 8, 22, 12, 5]
> ```
>
> **Test Summary** (Total: 450)
>
> ```mermaid
> %%{init: {'themeVariables': {'pie1': '#2e7d32', 'pie2': '#c62828', 'pie3': '#757575', 'pie4': '#ef6c00', 'pie5': '#1565c0', 'pieStrokeWidth': '0px', 'pieOuterStrokeWidth': '0px', 'pieOuterStrokeColor': 'transparent'}}}%%
> pie showData
>     title Test Summary
>     "Passed" : 360
>     "Failed" : 40
>     "Skipped" : 25
>     "Blocked" : 15
>     "Not run" : 10
> ```

> **Conclusion**
>
> 1. Examine both TAS and SUT data
> 2. Compare historical results
> 3. Follow systematic failure analysis
> 4. Leverage correlation IDs
> 5. Visualize for pattern recognition

---

### Transcript

"Analyze data from the test automation solution and the system under test to better understand test results.

Now let's focus on how to analyze all that data we've collected to gain deeper insights into our test results. This is honestly one of my favorite parts of test automation, because it's like being a detective. You're looking for clues and piecing together what happened during test execution.

The purpose of test result analysis.

After we run our automated tests, we need to analyze the results to understand what's happening. And there are really two main things we're looking for here: possible failures in the system under test and possible failures in our test automation solution. A lot of people focus only on finding bugs in the SUT. But honestly, our test automation code can have bugs too. So we need to look at both.

When analyzing test results, the data from our test automation solution is usually our primary source of information, while data from the system under test gives us additional context.

Analyzing test environment data.

Let's start by looking at how we can analyze test environment data. This is super helpful for properly sizing our test automation resources, especially if you're running tests in the cloud.

Let's say you're setting up automated tests for a large e-commerce website. You might need to analyze cluster and resource usage, which is CPU, RAM, etc. Whether to run single or multi-browser tests, which is cross-browser testing.

Here's a real example I encountered. We were running automated tests for a banking application and our tests were randomly timing out. When we analyzed the CPU usage data, we found that our test environment was experiencing significant CPU spikes whenever we ran more than ten parallel test sessions. The solution was to increase our virtual machine size in the cloud. But we wouldn't have known that without analyzing the environment data.

Here's a graph that illustrates the issue. As we can see in this graph, the blue line represents CPU usage percentage over time from 8 a.m. to 2 p.m. The horizontal red dashed line at 80% marks our CPU threshold. This is the point where we observe that the system becomes unstable for testing. The red X marks indicate test failures, and you can see they align perfectly with the three major CPU spikes that exceed our 80% threshold. The first failure happened a little after 9 a.m., when CPU usage spiked to nearly 90%. The second failure, a little after 11 a.m. during another spike above 90%. And the third failure, around 1:00 p.m., during the most severe spike that reached almost 95%. Notice how during periods where the CPU usage stays below our 80% threshold, we don't see any test failures. Once we upgraded our testing environment resources, those failures disappeared.

Comparing test results with previous executions.

Another key aspect of analysis is comparing current test results with previous runs. This helps us identify trends and patterns. For example, let's say you run a nightly regression test suite by comparing today's results with yesterday's. You might notice that a test that passed yesterday is failing today, which might be a potential regression. A test that's been failing for weeks suddenly passes, indicating a potential fix. Or a test that fails intermittently could be a potential flaky test.

I once worked on a project where we had a particularly troublesome feature that would break in subtle ways. By comparing test results across multiple builds, we noticed that failures would occur anytime a specific developer made changes to the authentication module. This pattern wasn't obvious from looking at a single test run, but became clear when we analyzed historical data.

The process of analyzing test execution failures.

Now let's talk about the process of analyzing test failures. When a test fails, we need a systematic approach to understand what went wrong. Here's the process I typically follow.

First, check if the same failure happened in previous test executions. This might be a known defect either in the SUT or the TAS. If it's not a known issue, identify the test case and what it's testing. Sometimes the test name is self-explanatory, or you might need to look it up in your test management system. Find which test step of the test case failed. Your test automation solution should log this information. Analyze the test logs to understand the state of the SUT when the failure occurred. Look at screenshots, API responses, network logs, or anything else that shows the state of the SUT in the last step. If the state of the SUT doesn't match what was expected, you've likely found a defect in the SUT. Log it in your defect management system, including all necessary information and logs.

Let me show you a real example. Here's a snippet from a test log. As we can see in this log snippet, the test failed because it couldn't find the payment method selector element. This is the kind of specific information that helps us pinpoint the issue quickly.

Now, it's important to note that there are situations where the test might fail, even though the SUT is working correctly. For example, the test could be expecting one thing, but the SUT is correctly doing something else, meaning the test is wrong. There could be an invisible mismatch like whitespace differences in test comparisons, or the test environment might not be fully available. To identify these kinds of issues, we can analyze the SUT logs to see if there were any environment outages or unexpected conditions at the time of the test run.

Use SUT audit logs with correlation IDs.

Okay, here's a really powerful technique I want to share with you. If your SUT implements audit logs for user interactions like UI sessions or API calls, these can be incredibly helpful for analyzing test results. Many modern systems use what's called a correlation ID or trace ID. This is a unique identifier that's added to each interaction, and follows that interaction through all subsequent calls and integrations in the system.

Here's how it works. As we can see in this diagram, the request starts at the web browser — the yellow box where a user initiates a checkout process. Then it flows to the web server API gateway — the blue box, which coordinates the overall process. The server then communicates with multiple backend services. We have the auth service — the green box — to validate the user. We have the product service — the purple box — to check inventory. And then we have the payment service — the red box — to process the payment. The orange boxes show the same correlation ID traveling with the requests through each system component. This ID remains consistent across all services, allowing developers and testers to trace the entire transaction path.

By logging this correlation ID in our test automation, we can trace exactly what happened to a particular request as it moved through the system. This is absolutely invaluable for debugging complex issues in microservice architectures.

Let me give you an example. In a team I work with, we had a test that was failing when trying to complete a purchase. The UI was showing a generic payment failed message. By looking at our test logs, we found a correlation ID for that request. And as you can see in this diagram, the correlation ID is on the first line after the submitting payment with correlation ID text. Then we search for that correlation ID in the logs. And as you can see in these logs, the issue wasn't with our SUT or the tests. The external payment gateway was timing out. This kind of insight would be much harder to gain without correlation IDs to connect the dots between different parts of the system.

Special consideration: test environment availability.

There's another situation we should discuss. Sometimes all your tests might fail at once, either with the same error or with what appears to be unrelated errors. When this happens, one of the first things to check is whether your test environment was fully available. I ran into this situation once when 95% of our tests suddenly started failing one morning. After spending an hour investigating individual test failures, we finally checked the database server logs and found that the database had been restarted for maintenance during our test run. The system was partially working, which is why each test was failing in different ways, but the root cause was a single environment issue.

Real-world example: debugging a complex registration flow.

I'll share a real-world example that brings together several of the techniques we've discussed. I was on a team where we were working on automated tests for a user registration flow that was failing intermittently. Here's how we analyzed it.

First, we compared the current failure with historical data and found that the tests had a 15% failure rate, which was definitely a pattern. We looked at the specific test step where it was failing: the confirmation email validation step. We examined the logs and found that in the failing cases, the test was timing out while waiting for the confirmation email. We traced the correlation ID through the system logs and discovered that during peak test execution times, the email service was experiencing higher latency. By analyzing the environment data, we found that the email service was resource-constrained.

The solution was twofold. We increased the resources for the email service, but we also made our test more resilient by implementing a dynamic wait mechanism instead of a fixed timeout.

Quick tip.

Visualize test results for analysis. Before we wrap up, I want to share a quick tip about visualizing test results to make analysis easier. Creating dashboards that show various metrics can help you spot patterns quickly. As we can see in this dashboard, we've got test execution trends over time, failure rates by component and environment, and performance metrics all in one view. This kind of visualization makes it much easier to spot correlations between different factors.

So to wrap up this lesson on analyzing data from test automation, we need to analyze data from both the test automation solution and the system under test to get a complete picture. We should compare current test results with previous runs to identify patterns and trends. When analyzing test failures, we follow a systematic process to determine if the issue is with the SUT, the TAS, or the test environment. Correlation IDs are incredibly valuable for tracing requests through complex systems. Visualizing test results can help us spot patterns and correlations more easily.

Remember, the goal of all this analysis isn't just to find bugs, it's to understand your system better, make your tests more reliable, and ultimately deliver higher quality software. In the next video, we'll talk about how to construct and publish effective test progress reports based on the analysis we've done."
