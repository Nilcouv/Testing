# Mooc

## Explain How a Test Progress Report is Constructed and Published

### Screen

> **The Need for Test Progress Report**
>
> - Test logs are super detailed, and they can be overwhelming if you're not the person who's actually going to debug the failing tests.
> - A good test progress report gives stakeholders a concise overview of the test results without drowning them in technical details they don't need.
>
> Example - raw test logs (hundreds of lines):
>
> ```text
> [2024-04-25 14:32:15] INFO - Starting test: LoginTest_ValidCredentials
> [2024-04-25 14:32:15] DEBUG - Opening browser: Chrome
> [2024-04-25 14:32:16] DEBUG - Navigating to: https://app.example.com
> [2024-04-25 14:32:17] DEBUG - Finding element: username_field
> [2024-04-25 14:32:17] DEBUG - Entering text: testuser123
> ...
> [2024-04-25 14:45:02] DEBUG - Finding element: submit_button
> [2024-04-25 14:45:03] INFO - Test completed: LoginTest_ValidCredentials - PASSED
> ```
>
> Useful for debugging, but overwhelming for stakeholders who only need a global view of progress and results.
>
> Example - a clean progress report:
>
> <clean-progress-report-widget></clean-progress-report-widget>

---

> **Core Report Components**
>
> - **Test Result Summary** - The highlight reel
> - **SUT Information** - Details about the system under test
> - **Test Environment Documentation** - Information about the environment in which the tests were run
>
> Example:
>
> - project running 2000 overnight.
> - reviewing all the test would be tedious.
> - create a test report showing
>   - Total tests
>   - Passed, failed and skipped tests
>   - Top failing tests suites
>   - Build version
>   - The Environment
>
> <daily-report-widget></daily-report-widget>

---

> **Failure Analysis Section**
>
> <test-failure-breakdown-widget></test-failure-breakdown-widget>

---

> **Publication Channels**
>
> - **Upload to a website** - This could be an internal website, Sharepoint, or some other document repository.
> - **Cloud storage** - Services like Google Drive, Dropbox, or OneDrive
> - **On-premises storage** - If you're working in a more traditional environment, you might save report to a network drive.
> - **Email distribution list** - Send the report to a mailing list of interested parties.
> - **Test management tool** - Upload to tools like Zephyr, TestRail, or similar systems.
> - **Chat notifications** - Some teams set up automated notifications to Slack or Microsoft Teams.
>
> Example - a chat notification:
>
> <chat-notification-widget></chat-notification-widget>

---

> **Stakeholder-Specific Views**
>
> - **Management Stakeholder** - High-level information like trends over time
> - **Operational Stakeholder** - Interested in metrics related to product usage and business impact.
> - **Technical Stakeholder** - Want the nitty-gritty details

---

> **Modern Dashboard Visualization**
>
> Modern report-ing tools provide options like interactive dashboards, colorful charts, detailed log collections, and even automated log analysis
>
> These tools can aggregate data from various sources like pipeline execution logs, project management tools, and code repositories.
>
> **For example, you might have a dashboard that shows:**
>
> - A trend graph of passing vs. failing tests over time
> - A heat map showing which modules have the most defects
> - A chart showing defect severity distribution
> - Metrics on how quickly defects are being fixed
>
> <test-dashboard-widget></test-dashboard-widget>

---

> **AI-Powered Analysis**
>
> Test automation tools have started incorporating machine learning algorithms to help analyze test logs.
>
> **Test automation engineers spend on tedious tasks like:**
>
> - Finding broken locators.
> - Analyzing whether a failure is due to a defect in the system under test or in the test automation framework itself.
> - Grouping common defects together for more efficient reporting.

---

> **Conclusion**
>
> 1. Bridge technical results and stakeholder needs.
> 2. Include failure context and history
> 3. Publish through multiple channels
> 4. Tailor to audience roles
> 5. Leverage modern visualization/AI

### Transcript

"Explain how a test progress report is constructed and published.

Now let's talk about how test progress reports are constructed and published. This is really important because all our automation efforts won't mean much if we can't effectively communicate what's happening with our test.

Why we need test progress reports.

So you've got all these automated tests running, and they're generating tons of test logs with detailed information about test steps, actions and expected responses. That's great. But honestly, if you just hand those raw logs to your project manager or product owner, they're going to look at you like you've just handed them a book in a foreign language. Test logs are super detailed and it can be overwhelming if you're not the person who's actually going to debug the failing tests. They don't really give you that bird's eye view of what's happening with your testing efforts. That's where test progress reports come in. A good test progress report gives stakeholders a concise overview of the test results without drowning them in technical details they don't need.

Let me show you what I mean. In this screenshot, we have raw test logs with hundreds of lines of technical details. As you can see, while these test logs are essential for debugging, they will be overwhelming for stakeholders who just need to know the overall status.

Now let's see a clean progress report. In this screenshot, the information is visual and straightforward. 98% of tests are passing, two tests failed, and it takes a little over five seconds for each test to run. This visual progress report gives stakeholders a concise overview of the test results, without giving them technical details they don't need or even understand.

What goes into a test progress report?

A well-structured test progress report typically includes a test result summary similar to the Clean Progress report we just looked at. This is like the highlight reel. How many tests pass, how many failed, how many were skipped, etc.

SUT information.

Details about the system under test. Like what version was tested, what build number, what environment, etc.

Test environment documentation.

Information about the environment in which the tests were run, like the operating system, browser versions, database versions, etc.

I was once working on a project where we had about 2000 automated tests running every night. You can imagine how tedious it would be to go through all those test logs manually. So we created a test progress report that showed total tests that passed, failed and skipped, top failing test suites, build version and the environment. It looks similar to this. With this information, our project manager could immediately see that we had some issues with the user authentication and payment processing modules, and they could prioritize getting those fixed.

Failures and troubleshooting information in your test progress report.

You definitely want to include information about which tests have failed and, if possible, the reasons for the failures. Here's an example. This makes troubleshooting much easier. It's also super helpful to include the test execution history and who reported the failure. Generally, this is the person who created or last updated the test. This person will often be responsible for investigating the cause of the failure, reporting the defect, following up on the fix, and then testing the fix to make sure it actually works.

I remember one project where we had this flaky test that would sometimes pass and sometimes fail. It was driving everyone crazy. But by looking at the test execution history in our test progress reports, we noticed that it only failed when it ran at the same time as another specific test. Turns out there was a resource conflict between the two tests. Without that history information in our reports, we might never have figured that out.

Test reporting isn't just about reporting on the system under test, though. It's also super useful for diagnosing any failures in the test automation framework itself. Maybe you've got a problem with your test data setup, or maybe your test environment isn't being properly reset between test runs. A good test progress report can help you spot these issues too.

Publishing the test reports.

Okay, so you've got this awesome test progress report. Now, what do you do with it? Well, you need to publish it to all the relevant stakeholders. There are several ways to publish test reports.

Upload to a website.

This could be an internal website, SharePoint or some other document repository.

Cloud storage services like Google Drive, Dropbox or OneDrive.

On-premises storage.

If you're working in a more traditional environment, you might save reports to a network drive.

Email distribution list send the report to a mailing list of interested parties.

Test management tool upload to tools like Zephyr, TestRail, or similar systems.

Chat notifications.

Some teams set up automated notifications to Slack or Microsoft Teams.

The goal here is to make sure the right people see the reports. Here's a quick example of a chat notification. If people are subscribed to receiving them by email or through chat notifications, they're more likely to actually review and analyze them. It's also a good idea to keep a history of your test reports. This allows you to gather statistics about test cases or test suites that frequently have issues, so you can do some trend analysis. For instance, if you notice that the same module keeps having regressions, that might indicate a deeper architectural issue that needs to be addressed.

Stakeholders and their needs.

Different stakeholders have different information needs when it comes to test reports. It's important to tailor your reports or create different views of the same report for different audiences.

Management stakeholders.

These folks include solution architects, project managers, program managers, test managers, and test directors. They typically want high level information like trends over time. How many test cases have been added since the last run, changes in the pass fail ratio, and the overall reliability of both the test automation solution and the system under test.

Operational stakeholders.

This group includes product owners, product managers, business representatives, and business analysts. They're usually more interested in metrics related to product usage and business impact.

Technical stakeholders.

This includes team leaders, scrum masters, web administrators, database administrators, test leaders, test automation engineers, testers, and developers. These folks often want the nitty gritty details which specific tests failed, what the error messages were, stack traces, etc.

In my experience, it's best to create a report that has different sections for different audiences. Start with a high level executive summary for the management stakeholders. Then have more detailed sections that the technical stakeholders can dive into if they need to.

Monitoring dashboards and visualization.

These days there are some really cool tools available for visualizing test results. Monitoring reporting tools provide options like interactive dashboards, colorful charts, detailed log collections, and even automated log analysis. These tools can aggregate data from various sources like pipeline execution logs, project management tools, and code repositories. The visualization helps stakeholders quickly spot trends and make decisions. For example, you might have a dashboard that shows a trend graph of passing versus failing tests over time. A heat map showing which modules have the most defects, a chart showing defect severity distribution, and metrics on how quickly defects are being fixed. Here is how a dashboard might actually look. Visualizations like these can help identify patterns like defect clusters, changes in how defects propagate to different environments, performance degradation in a system under test, and build reliability issues.

I worked on a project once where we set up a dashboard using Grafana that displayed real time test results on a big screen in our team area. It was amazing how much more engaged everyone became with the test results when they could see them at a glance.

AI and Machine Learning for test log analysis.

And now for something really cutting edge. In recent years, some test automation tools have started incorporating machine learning algorithms to help analyze test logs. This is super cool because it can help reduce the time that test automation engineers spend on tedious tasks like finding broken locators. Like when a web element ID changes and breaks your test. Analyzing whether a failure is due to a defect in the system under test or in a test automation framework itself. Grouping common defects together for more efficient reporting.

For example, I've seen tools that could automatically classify test failures into categories like network error, database timeout, UI element not found, etc. this kind of classification can save hours of manual analysis. Some tools can even predict which tests are likely to fail based on code changes, allowing you to run those tests first and get faster feedback.

So, to wrap up, test progress reports are crucial for communicating the results of your automated testing efforts to stakeholders. They provide a concise overview of test results, system information, and environment details. A good report includes information about failures and troubleshooting. And it's published in a way that ensures the right people see it. Different stakeholders have different information needs, so it's important to tailor your reports accordingly. Monitoring tools provide great visualization options, and some are even incorporating AI and machine learning to help with analysis. The ultimate goal of a test progress report is to help stakeholders make informed decisions about the quality of the software and the testing process itself.

In the next video, we'll be talking about how to verify our test automation solution."

### Components (source en bas de page)

<template id="tpl-clean-progress-report">
  <div style="font-family: system-ui, sans-serif; max-width: 420px; background: #ffffff; color: #333333; border: 1px solid #cccccc; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,.12); margin: 0.5em 0 1em;">
    <div style="background: #e8e8e8; padding: 12px 16px; font-weight: 600; color: #333333;">
      Test Summary: Login test
    </div>
    <div style="padding: 16px; background: #ffffff; color: #333333;">
      <div style="display: flex; align-items: center; gap: 12px; margin-bottom: 12px;">
        <span style="background: #2e7d32; color: #ffffff; padding: 4px 12px; border-radius: 4px; font-weight: 600; font-size: 14px;">Passed</span>
        <span style="font-size: 28px; font-weight: 700; color: #2e7d32;">98%</span>
      </div>
      <div style="display: flex; align-items: center; gap: 8px; margin-bottom: 8px; color: #444444; font-size: 14px;">
        <span aria-hidden="true">&#9888;</span>
        <span>Failed tests: <strong>2 of 100</strong></span>
      </div>
      <div style="display: flex; align-items: center; gap: 8px; margin-bottom: 16px; color: #444444; font-size: 14px;">
        <span aria-hidden="true">&#9201;</span>
        <span>Average execution time: <strong>5.2s</strong></span>
      </div>
      <div style="height: 10px; background: #e0e0e0; border-radius: 5px; overflow: hidden;">
        <div style="width: 98%; height: 100%; background: #2e7d32;"></div>
      </div>
    </div>
  </div>
</template>

<template id="tpl-daily-report">
  <div style="font-family: system-ui, sans-serif; max-width: 560px; background: #ffffff; color: #333333; border: 1px solid #cccccc; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,.12); margin: 0.5em 0 1em;">
    <div style="background: #e8e8e8; padding: 12px 16px; font-weight: 600; color: #333333;">
      Daily Test Automation Report - April 25, 2025
    </div>
    <div style="padding: 16px; background: #ffffff; color: #333333;">
      <section style="background: #f7faf7; border: 2px solid #2e7d32; border-radius: 8px; padding: 16px; margin-bottom: 16px;">
        <h3 style="margin: 0 0 12px 0; font-size: 16px; font-weight: 700; color: #1b5e20;">Summary dashboard</h3>
        <div style="margin-bottom: 14px; font-size: 22px; font-weight: 700; color: #111111;">Total Tests: 2,000</div>
        <div style="margin-bottom: 12px; font-size: 14px; color: #333333;">
          <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
            <span>Passed</span><span><strong>1,950</strong> (97.5%)</span>
          </div>
          <div style="height: 12px; background: #e0e0e0; border-radius: 6px; overflow: hidden;">
            <div style="width: 97.5%; height: 100%; background: #2e7d32;"></div>
          </div>
        </div>
        <div style="margin-bottom: 12px; font-size: 14px; color: #333333;">
          <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
            <span>Failed</span><span><strong>45</strong> (2.25%)</span>
          </div>
          <div style="height: 12px; background: #e0e0e0; border-radius: 6px; overflow: hidden;">
            <div style="width: 2.25%; height: 100%; background: #c62828;"></div>
          </div>
        </div>
        <div style="margin-bottom: 0; font-size: 14px; color: #333333;">
          <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
            <span>Skipped</span><span><strong>5</strong> (0.25%)</span>
          </div>
          <div style="height: 12px; background: #e0e0e0; border-radius: 6px; overflow: hidden;">
            <div style="width: 0.25%; height: 100%; background: #f9a825; min-width: 2px;"></div>
          </div>
        </div>
      </section>
      <div style="display: flex; gap: 12px; flex-wrap: wrap;">
        <section style="flex: 1; min-width: 200px; background: #fafafa; border: 1px solid #e0e0e0; border-radius: 6px; padding: 12px;">
          <h4 style="margin: 0 0 8px 0; font-size: 12px; font-weight: 600; color: #666666; text-transform: uppercase; letter-spacing: 0.04em;">Top failing test suites</h4>
          <ul style="margin: 0; padding-left: 16px; font-size: 12px; color: #555555; line-height: 1.6;">
            <li>User Authentication (15 failures)</li>
            <li>Payment Processing (10 failures)</li>
            <li>Search Functionality (8 failures)</li>
          </ul>
        </section>
        <section style="flex: 1; min-width: 160px; background: #fafafa; border: 1px solid #e0e0e0; border-radius: 6px; padding: 12px;">
          <h4 style="margin: 0 0 8px 0; font-size: 12px; font-weight: 600; color: #666666; text-transform: uppercase; letter-spacing: 0.04em;">System details</h4>
          <div style="font-size: 12px; color: #555555; line-height: 1.7;">
            <div>Build Version: <strong>3.4.2</strong></div>
            <div>Environment: <strong>Staging</strong></div>
            <div>Date: <strong>April 25, 2025</strong></div>
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<template id="tpl-failure-breakdown">
  <div style="font-family: system-ui, sans-serif; max-width: 480px; background: #ffffff; color: #333333; border: 1px solid #cccccc; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,.12); margin: 0.5em 0 1em;">
    <div style="background: #e8e8e8; padding: 12px 16px; font-weight: 600; color: #333333;">
      Test Failure Breakdown
    </div>
    <div style="padding: 16px; background: #ffffff;">
      <div style="margin-bottom: 14px; font-size: 13px; color: #333333;">
        <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
          <span>Element Not Found</span><span><strong>35%</strong></span>
        </div>
        <div style="height: 10px; background: #eeeeee; border-radius: 5px; overflow: hidden;" role="progressbar" aria-valuenow="35" aria-valuemin="0" aria-valuemax="100" aria-label="Element Not Found">
          <div style="width: 35%; height: 100%; background: #b71c1c;"></div>
        </div>
      </div>
      <div style="margin-bottom: 14px; font-size: 13px; color: #333333;">
        <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
          <span>Timeout Errors</span><span><strong>25%</strong></span>
        </div>
        <div style="height: 10px; background: #eeeeee; border-radius: 5px; overflow: hidden;" role="progressbar" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100" aria-label="Timeout Errors">
          <div style="width: 25%; height: 100%; background: #c62828;"></div>
        </div>
      </div>
      <div style="margin-bottom: 14px; font-size: 13px; color: #333333;">
        <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
          <span>Validation Failures</span><span><strong>20%</strong></span>
        </div>
        <div style="height: 10px; background: #eeeeee; border-radius: 5px; overflow: hidden;" role="progressbar" aria-valuenow="20" aria-valuemin="0" aria-valuemax="100" aria-label="Validation Failures">
          <div style="width: 20%; height: 100%; background: #e53935;"></div>
        </div>
      </div>
      <div style="margin-bottom: 14px; font-size: 13px; color: #333333;">
        <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
          <span>Network Issues</span><span><strong>15%</strong></span>
        </div>
        <div style="height: 10px; background: #eeeeee; border-radius: 5px; overflow: hidden;" role="progressbar" aria-valuenow="15" aria-valuemin="0" aria-valuemax="100" aria-label="Network Issues">
          <div style="width: 15%; height: 100%; background: #ef6c00;"></div>
        </div>
      </div>
      <div style="margin-bottom: 0; font-size: 13px; color: #333333;">
        <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
          <span>Test Data Issues</span><span><strong>5%</strong></span>
        </div>
        <div style="height: 10px; background: #eeeeee; border-radius: 5px; overflow: hidden;" role="progressbar" aria-valuenow="5" aria-valuemin="0" aria-valuemax="100" aria-label="Test Data Issues">
          <div style="width: 5%; height: 100%; background: #f9a825; min-width: 4px;"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<template id="tpl-chat-notification">
  <div style="font-family: system-ui, sans-serif; max-width: 420px; background: #ffffff; color: #333333; border: 1px solid #cccccc; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,.12); margin: 0.5em 0 1em;">
    <div style="display: flex; gap: 12px; padding: 14px 16px; background: #ffffff;">
      <div style="width: 40px; height: 40px; border-radius: 8px; background: #4a154b; color: #ffffff; display: flex; align-items: center; justify-content: center; font-weight: 700; font-size: 14px; flex-shrink: 0;">TB</div>
      <div style="flex: 1; min-width: 0;">
        <div style="display: flex; align-items: baseline; gap: 8px; margin-bottom: 4px;">
          <span style="font-weight: 700; color: #1d1c1d;">Test Bot</span>
          <span style="font-size: 12px; color: #616061;">Today at 6:02 AM</span>
        </div>
        <div style="font-weight: 600; margin-bottom: 8px; color: #1d1c1d;">Daily Test Report Ready!</div>
        <ul style="margin: 0 0 12px 0; padding-left: 18px; font-size: 14px; color: #333333; line-height: 1.55;">
          <li>Pass Rate: <strong>97.5%</strong></li>
          <li>Failed Tests: <strong>45</strong></li>
          <li>Top Issue: Authentication Module (15 failures)</li>
        </ul>
        <a href="#" style="display: inline-block; background: #1264a3; color: #ffffff; text-decoration: none; padding: 6px 12px; border-radius: 4px; font-size: 13px; font-weight: 600;">View Full Report</a>
      </div>
    </div>
  </div>
</template>

<template id="tpl-test-dashboard">
  <div style="font-family: system-ui, sans-serif; max-width: 720px; background: #ffffff; color: #333333; border: 1px solid #cccccc; border-radius: 8px; overflow: hidden; box-shadow: 0 2px 8px rgba(0,0,0,.12); margin: 0.5em 0 1em;">
    <div style="background: #e8e8e8; padding: 12px 16px; font-weight: 600; color: #333333;">
      Test Dashboard - MyApp V3.4.2
    </div>
    <div style="padding: 16px; background: #ffffff;">
      <div style="display: flex; gap: 12px; flex-wrap: wrap; margin-bottom: 16px;">
        <section style="flex: 1; min-width: 160px; background: #fafafa; border: 1px solid #e0e0e0; border-radius: 8px; padding: 14px; text-align: center;">
          <div style="font-size: 12px; font-weight: 600; color: #666666; text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 10px;">Overall Health</div>
          <div style="width: 88px; height: 88px; margin: 0 auto 8px; border-radius: 50%; background: conic-gradient(#2e7d32 0 343.8deg, #e0e0e0 343.8deg 360deg); display: flex; align-items: center; justify-content: center;">
            <div style="width: 64px; height: 64px; border-radius: 50%; background: #ffffff; display: flex; align-items: center; justify-content: center; font-size: 16px; font-weight: 700; color: #2e7d32;">95.5%</div>
          </div>
        </section>
        <section style="flex: 1; min-width: 180px; background: #fafafa; border: 1px solid #e0e0e0; border-radius: 8px; padding: 14px;">
          <div style="font-size: 12px; font-weight: 600; color: #666666; text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 10px;">Test Trends</div>
          <svg viewBox="0 0 160 70" width="100%" height="70" aria-label="Test trends sparkline" style="display: block;">
            <polyline fill="none" stroke="#1565c0" stroke-width="2" points="8,52 30,45 52,48 74,28 96,32 118,18 142,22"></polyline>
            <circle cx="8" cy="52" r="3.5" fill="#1565c0"></circle>
            <circle cx="30" cy="45" r="3.5" fill="#1565c0"></circle>
            <circle cx="52" cy="48" r="3.5" fill="#1565c0"></circle>
            <circle cx="74" cy="28" r="3.5" fill="#1565c0"></circle>
            <circle cx="96" cy="32" r="3.5" fill="#1565c0"></circle>
            <circle cx="118" cy="18" r="3.5" fill="#1565c0"></circle>
            <circle cx="142" cy="22" r="3.5" fill="#1565c0"></circle>
          </svg>
        </section>
        <section style="flex: 1; min-width: 160px; background: #fafafa; border: 1px solid #e0e0e0; border-radius: 8px; padding: 14px;">
          <div style="font-size: 12px; font-weight: 600; color: #666666; text-transform: uppercase; letter-spacing: 0.04em; margin-bottom: 12px;">Defect Severity</div>
          <div style="display: flex; flex-direction: column; gap: 10px; font-size: 12px; color: #333333;">
            <div>
              <div style="margin-bottom: 4px;">Critical <span style="color: #666666;">(3)</span></div>
              <div style="display: flex; flex-wrap: wrap; gap: 4px;" aria-label="3 critical defects">
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #c62828; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #c62828; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #c62828; display: inline-block;"></span>
              </div>
            </div>
            <div>
              <div style="margin-bottom: 4px;">High <span style="color: #666666;">(7)</span></div>
              <div style="display: flex; flex-wrap: wrap; gap: 4px;" aria-label="7 high defects">
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef6c00; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef6c00; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef6c00; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef6c00; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef6c00; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef6c00; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #ef6c00; display: inline-block;"></span>
              </div>
            </div>
            <div>
              <div style="margin-bottom: 4px;">Medium <span style="color: #666666;">(12)</span></div>
              <div style="display: flex; flex-wrap: wrap; gap: 4px;" aria-label="12 medium defects">
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
                <span style="width: 10px; height: 10px; border-radius: 50%; background: #f9a825; display: inline-block;"></span>
              </div>
            </div>
          </div>
        </section>
      </div>
      <section style="background: #f7faf7; border: 1px solid #c8e6c9; border-radius: 8px; padding: 14px;">
        <div style="font-size: 13px; font-weight: 700; color: #1b5e20; margin-bottom: 12px;">Module Performance</div>
        <div style="margin-bottom: 12px; font-size: 13px; color: #333333;">
          <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
            <span>Authentication</span>
            <span><strong>82%</strong> <span style="color: #c62828;">&#9660; 8% from last</span></span>
          </div>
          <div style="height: 10px; background: #e0e0e0; border-radius: 5px; overflow: hidden;">
            <div style="width: 82%; height: 100%; background: #2e7d32;"></div>
          </div>
        </div>
        <div style="margin-bottom: 12px; font-size: 13px; color: #333333;">
          <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
            <span>Shopping Cart</span>
            <span><strong>95%</strong> <span style="color: #2e7d32;">&#9650; 3% from last</span></span>
          </div>
          <div style="height: 10px; background: #e0e0e0; border-radius: 5px; overflow: hidden;">
            <div style="width: 95%; height: 100%; background: #2e7d32;"></div>
          </div>
        </div>
        <div style="margin-bottom: 0; font-size: 13px; color: #333333;">
          <div style="display: flex; justify-content: space-between; margin-bottom: 4px;">
            <span>Search</span>
            <span><strong>100%</strong> <span style="color: #666666;">stable</span></span>
          </div>
          <div style="height: 10px; background: #e0e0e0; border-radius: 5px; overflow: hidden;">
            <div style="width: 100%; height: 100%; background: #2e7d32;"></div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
(function () {
  function defineWidget(tag, templateId) {
    if (!window.customElements || customElements.get(tag)) return;
    customElements.define(
      tag,
      class extends HTMLElement {
        connectedCallback() {
          if (this.childNodes.length) return;
          var tpl = document.getElementById(templateId);
          if (tpl) this.appendChild(tpl.content.cloneNode(true));
        }
      }
    );
  }
  defineWidget("clean-progress-report-widget", "tpl-clean-progress-report");
  defineWidget("daily-report-widget", "tpl-daily-report");
  defineWidget("test-failure-breakdown-widget", "tpl-failure-breakdown");
  defineWidget("chat-notification-widget", "tpl-chat-notification");
  defineWidget("test-dashboard-widget", "tpl-test-dashboard");
})();
</script>
