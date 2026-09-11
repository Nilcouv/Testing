# Mooc

## Apply Data Collection Methods from the Test Automation Solution and the System Under Test

### Screen

> **Introduction to Test Data Collection**
> 
> - Test automation generates valuable execution data;
> - Data helps understand both test and system behavior
> - Multiple collection sources provide different perspectives

---

> **Data Collection Sources**
>
> **SUT Logs**
>
> Can come from several places:
>
> - Web or mobile user interfaces.
> - APIs.
> - Applications.
> - Web servers.
> - Database servers.
>
> **Example:** E-commerce project - transaction randomly failing. Discovered root cause was the timeout configurations, which were different between test and production environment, by examining database server logs.

---

> **Data Collection Sources**
>
> **TAF Logs**
>
> Provide what we call an "audit trail" - basically a record of everything that happened during test execution.

---

> **Data Collection Sources**
>
> **Build Logs**
>
> - The process of converting your source code into an executable program.
> - Build logs tell us if the compilation was successful and if any issues occurred during the build process

---

> **Data Collection Sources**
>
> **Deployment Logs**
> 
> Give us information about what happened when we deployed our software to a test or production environment.

---

> **Data Collection Sources**
>
> **Production Logs**
>
> - Helps us monitor data in production environment
>
> We can use this for:
>
> - Performance monitoring to analyze trends over time.
> - Performance efficiency test logs in dedicated test environment.

---

> **Data Collection Sources**
>
> **Screenshot and screen-recordings**
>
> These can be native to our automation tool or from third-party applications.

---

> **Test Automation Data Source**
>
> ```mermaid
> flowchart LR
>     subgraph Left[" "]
>         direction TB
>         SL["**SUT Logs**<br/>Web/Mobile UI, APIs, Application"]
>         TL["**TAF Logs**<br/>Audit trail"]
>         BL["**Build Logs**<br/>Compilation info"]
>     end
>
>     DCH(("**Data Collection Hub**"))
>
>     subgraph Right[" "]
>         direction TB
>         DL["**Deployment Logs**<br/>Environment setup"]
>         PL["**Production Logs**<br/>Performance monitoring"]
>         S["**Screenshots**<br/>Visual records"]
>     end
>
>     Left ~~~ DCH ~~~ Right
>
>     SL --> DCH
>     TL --> DCH
>     BL --> DCH
>     DL --> DCH
>     PL --> DCH
>     S --> DCH
>
>     style Left fill:none,stroke:none
>     style Right fill:none,stroke:none
> ```

---

> **Enhancing Testware for Data Collection**
>
> - instrument testware to record execution metadata.
> - Example: Track test start/end times automatically.
> - Foundation improvement benefits all tests.
>
> ```java
> // Before enhancement
> public void runTest() {
>     loginToApplication();
>     navigateToUserPage();
>     verifyUserDetails();
>     logout();
> }
>
> // After enhancement
> public void runTest() {
>     logger.info("Test started at: " + getCurrentTime());
>
>     loginToApplication();
>     navigateToUserPage();
>     verifyUserDetails();
>     logout();
>
>     logger.info("Test completed at: " + getCurrentTime());
>     logger.info("Total execution time: " + calculateExecutionTime() + " seconds");
> }
> ```

---

> **Feature Supporting Measurement and Reporting**
>
> - Good test reporting also needs to analyze results across multiple test runs
> - Spot trends, like changes in the test success rate over time.
> - The pass rate had gradually declined from 98%

---

> **Test Verification & Assertions**
>
> - Assertions compare actual vs expected results.
> - Example: Displaying calculated vs expected totals.
> - Failure context is critical (values, screenshots).
>
> Example:
>
> ```javascript
> // Simple assertion
> assert.equals(actualValue, expectedValue, "Values should match");
>
> // More detailed assertion with context
> function verifyOrderTotal(orderPage) {
>     const itemPrices = orderPage.getAllItemPrices();
>     const calculatedTotal = itemPrices.reduce((sum, price) => sum + price, 0);
>     const displayedTotal = orderPage.getOrderTotal();
>
>     assert.equals(
>         displayedTotal,
>         calculatedTotal,
>         `Order total ${displayedTotal} doesn't match sum of items ${calculatedTotal}. Items: ${itemPrices.join(', ')}`
>     );
> }
> ```

---

> **TAS Logging Essential**
>
> - Must log: Test case ID, status, timings.
> - Include severity levels (INFO/DEBUG/ERROR).
> - Capture failure artifacts: screenshots, crash dumps.
>
> Example:
>
> ```text
> [2025-04-15 10:15:32] INFO: Starting test case 'VerifyUserRegistration'
> [2025-04-15 10:15:32] DEBUG: Navigating to registration page
> [2025-04-15 10:15:34] DEBUG: Filling out registration form with username: testUser123
> [2025-04-15 10:15:36] WARN: Form submission took 2.5 seconds, exceeding threshold of 2 seconds
> [2025-04-15 10:15:36] DEBUG: Verifying welcome message
> [2025-04-15 10:15:37] ERROR: Test failed! Expected welcome message 'Welcome, testUser123!' but found 'Welcome!'
> [2025-04-15 10:15:37] INFO: Test case 'VerifyUserRegistration' completed with status: FAILED
> [2025-04-15 10:15:37] INFO: Total execution time: 5 seconds
> ```

---

> **SUT Log Correlation**
>
> - Log configuration data at startup (version, OS)
> - Timestamp synchronization enables root cause analysis
>
> Example:
>
> ```text
> [2025-04-15 10:15:35.823] Server: User registration successful for user 'testUser123'
> [2025-04-15 10:15:35.945] Server: Error retrieving user profile: Database timeout
> [2025-04-15 10:15:36.012] Server: Falling back to default welcome message
> ```

---

> **Visualization of Test Results**
>
> Traffic-light style status and charts for stakeholders; drill-down when needed.
>
> **Test Status Distribution**
>
> ```mermaid
> %%{init: {'themeVariables': {'pie1': '#2e7d32', 'pie2': '#c62828', 'pieStrokeWidth': '0px', 'pieOuterStrokeWidth': '0px', 'pieOuterStrokeColor': 'transparent'}}}%%
> pie showData
>     title Test Status Distribution
>     "Pass" : 85
>     "Fail" : 15
> ```
>
> **Test Execution Times by Module**
>
> ```mermaid
> xychart-beta
>     title "Test Execution Times by Module"
>     x-axis [Auth, Profile, Payment, Checkout]
>     y-axis "Seconds" 0 --> 10
>     bar [5, 8, 10, 4]
> ```
>
> **Pass Rate Trends (Last 30 Days)**
>
> ```mermaid
> xychart-beta
>     title "Pass Rate Trends (Last 30 Days)"
>     x-axis ["Apr 1", "Apr 3", "Apr 5", "Apr 7", "Apr 9", "Apr 11", "Apr 13", "Apr 15", "Apr 17", "Apr 19", "Apr 21", "Apr 23", "Apr 25", "Apr 27", "Today"]
>     y-axis "%" 70 --> 90
>     line [80, 78, 79, 80, 81, 80, 80, 84, 85, 86, 86, 88, 88, 89, 89]
> ```

---

> **Real-World Example: Financial Application**
>
> - Payment test failures correlated with batch jobs.
> - Grafana visualization revealed timing patterns.
> - Solution: Adjusted timeouts and test scheduling.

---

> **Conclusion**
>
> 1. Leverage multiple data sources
> 2. Enhance testware instrumentation
> 3. Implement Comprehensive logging
> 4. Visualize for decision-making
> 5. Correlate TAS/SUT events

### Transcript

"Apply data collection methods from the test automation solution and the system under test.

One of the most valuable aspects of test automation isn't just running the test, it's all the data we can collect during the process. This data helps us understand what's happening with our tests and our system under test, which we'll often refer to as the SUT.

So, we're going to talk about where we can collect data from, how to enhance our testware to record information, and the different types of logging that could help us make sense of our test results.

Data collection sources.

Let's start by looking at the different data sources we can collect data from. Think of these sources as different windows into what's happening with our testing and our software. First off, we've got SUT logs.

These logs can come from several places: web or mobile user interfaces, APIs — like we talked about in a previous lesson, the interfaces that allow different software systems to talk to each other — applications, web servers, and database servers.

I remember working on this e-commerce project where we were testing the checkout process. The web UI looked fine, but transactions were randomly failing. By examining the database server logs, we discovered that our test environment had timeouts configured differently than production. Without those database logs, we might never have found the root cause.

Next, we have TAF logs. These logs provide what we call an audit trail: basically a record of everything that happened during test execution. We also collect data from build logs.

If you're not familiar with builds, they're the process of converting your source code into an executable program. Build logs tell us if the compilation was successful and if any issues occurred during the build process. Similarly, deployment logs give us information about what happened when we deployed our software to a test or production environment.

Then, we have production logs, which help us monitor data in production environments. This is super valuable because it lets us see how our software behaves in the real world with real users. We can use this for performance monitoring to analyze trends over time, and for performance efficiency test logs in dedicated test environments like load, stress, and spike testing.

Finally, we can collect screenshots and screen recordings. These can be native to our automation tool or from third-party applications. Pictures are worth a thousand words, especially when trying to debug a UI issue. Take a look at this diagram showing how data sources flow into a central collection hub.

As we can see in this diagram, data flows from multiple sources into our collection system. Each source provides a different perspective on how our system is performing.

Enhancing testware for data collection.

Now, since our test automation solution has automated testware at its core, we can enhance this testware to record information about its use. This is really powerful.

For example, let's say we enhance our underlying testware to record the start and end time of test execution. This enhancement can then be used by all our higher-level automated test scripts. It's kind of like improving the foundation of a house: everything built on top gets the benefit. Let me show you a simple example.

As we can see in this code snippet, we've enhanced a simple test method to log the start time, end time, and total execution time. This small change gives us valuable performance data for every test that uses this method.

Features supporting measurement and reporting.

Many test tools have built-in features that support measurement and reporting. These features let us record and log information before, during, and after test execution, both for individual tests and entire test suites.

Good test reporting also needs to analyze results across multiple test runs. This helps us spot trends like changes in the test success rate over time. I once worked on a project where our tests were passing 95% of the time, which seemed great, but when we looked at the trend over several weeks, we noticed that the pass rate had gradually declined from 98%. This early warning helped us identify and fix a memory leak before it became a major issue.

Test verification through assertions.

Test automation typically requires automating both the test execution and the test verification. Verification is usually done by comparing actual results with expected results using what we call assertions. An assertion is basically saying, "I expect this condition to be true, and if it's not, the test should fail." The level of information reported when an assertion fails is really important.

At minimum, we need to know if the test passed or failed, but for a failed test, we usually need more information to diagnose the problem, like screenshots of what the application looked like when it failed. Let me show you a quick example of assertions.

As we can see in this code snippet, the second assertion provides much more context about what was being tested and what went wrong by including the displayed total and calculated total information. This additional context can save hours of debugging time.

Test logging.

Test logging is a super important source of information for analyzing potential issues in both our test automation solution and our system under test. Let's take a look at TAS and SUT logging.

TAS logging.

In TAS logging, depending on the context, either the test automation framework or the test execution engine is responsible for logging information, which should include: which test case is currently being executed, including start and end times; the status of test execution — passed, failed, or TAS failure; low-level details of the test log, including timing information; dynamic information about the SUT that the test case identified; and for reliability or stress testing with multiple cycles, a counter to track how many times test cases have been executed.

Let's visualize this with an example log.

As we can see in this log snippet, we have different severity levels — info, debug, warn, and error — and detailed information about what happened during the test. The log clearly shows which test was running, what it was doing, and why it failed. When a test fails, it's crucial that our TAS saves all information needed to analyze the defect: screenshots at the time of failure, associated crash dumps and stack traces, and any logs that might be overwritten later. As a pro tip, using color in your test logs can really help distinguish different types of information. For example, you might have defects in red and progress information in green.

SUT logging.

Correlating test automation results with SUT logs helps identify the root cause of defects in both the system under test and the test automation solution. When a defect is found in the SUT, all necessary information for analysis should be logged: date and timestamps, source location of the defect, and error messages. Configuration information should also be logged at system startup, with things like the software or firmware versions, SUT configuration, and operating system configuration.

Using test automation, SUT logs can be easily searched and analyzed. Synchronizing various logs with timestamps makes it easier to correlate events when a failure occurs.

For example, imagine we have a test that fails at 10:15:36 when checking a welcome message. We can look at the SUT logs at the exact time to see if any errors or warnings were recorded on the server side.

As we can see in these synchronized logs, we now know that the test failed because of a database timeout on the server side, which caused it to fall back to a default welcome message. This correlation between test logs and SUT logs is incredibly valuable for troubleshooting.

Integration with third-party tools.

The information from our test automation can be used in other tools for tracking and reporting. For example, we might want to update traceability information in a test management tool or create reports in a specific format.

Many test tools offer export formats for reporting, or we can create custom reporting that outputs data in formats compatible with other tools like spreadsheets (Excel or Google Sheets), XML files, documents, databases, and specialized reporting tools.

I remember working on a project where management wanted test results in a very specific PowerPoint format. We set up our automation to export XML data, then used a script to generate the PowerPoint slides automatically. This saved hours of manual work each week.

Visualization of test results.

Finally, let's talk about visualizing test results. As we've said before, a picture is worth a thousand words, especially when communicating with management or other stakeholders.

Test results can be made visible using charts and graphs. Traffic light indicators like red, yellow, and green are particularly effective for showing the overall status of test execution. Management typically prefers visual summaries that help with decision-making, with the ability to drill down into details if needed.

As we can see in this dashboard, we have multiple visualizations that quickly communicate the health of our testing efforts. The pie chart shows that 85% of tests are passing. The bar chart identifies which modules have the longest-running tests. And the trend line shows our pass rate has been slowly improving over the past month.

Real-world example.

Let me share a real-world example to tie all of this together. On one of my last projects, we were building a financial application and we noticed inconsistent failures in our payment processing tests.

We set up comprehensive logging in both our test automation framework and the payment processing service. We also integrated with a tool called Grafana for visualization and set up alerts for unusual patterns.

After collecting data for a week, our dashboard showed that failures were clustered around specific times of day. By correlating our test logs with the system logs, we discovered that the payment processor was running batch jobs at those times, causing increased response times that exceeded our test timeout thresholds. The solution was simple: we adjusted our timeouts to be more realistic and scheduled our most critical tests to avoid the batch processing windows. Our test reliability improved from 75% to 99%, and we gained valuable insights into the system's behavior under different conditions.

So to wrap up this video: we can collect data from multiple sources such as SUT logs, TAF logs, build logs, deployment logs, production logs, and visual records like screenshots. Our testware can be enhanced to record information that's valuable for analysis and reporting. Good test logging is crucial for both the test automation solution and the system under test. Integration with third-party tools and visualization of results helps communicate findings effectively. Remember, the goal of all this data collection isn't just to gather data; it's to gain insights to help us improve both our testing and the quality of our software.

In the next video, we'll look at how to analyze all this collected data to better understand our test results."
