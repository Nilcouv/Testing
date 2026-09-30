# Mooc

## Explain the correct behavior for a given automated test script and/or test suit

### Screen

> **Importance of Verifying Test Automation**
>
> - Make sure your automated test scripts and test suites are behaving correctly
> - We need to test our test automation.
> - Verify that automated test suites are working as expected and are fit for us
> - A critical part of being a Test Automation Engineer that people sometimes overlook
> - Automated test suites aren't just "set it and forget it" tools.
> - They are complex pieces of software that need to be verified for completeness, consistency, and correct behavior.
> - How can we trust the results if we're not sure the automation is working properly ?
>
> **Example**: An elaborate suite for a payment processing system showed all tests passing — everything looked good. One key validation test was not actually checking what we thought (selector issue). Result: a false sense of security from tests that were not really testing what we needed. That is why verifying the automation itself matters.

---

> **Verification Steps for Automated Test Suites**
>
> **1. Check The Composition of the Test Suite**
>
> Check the composition of your test suite. Verify that:
>
> - All test cases have properly defined expected results.
> - The necessary test data is present and correct.
> - You're using the correct version of the TAF (Test Automation Framework)
> - You're testing against the correct version of the SUT (System Under Test)
>
> **Example**:
>
> **Test Suite Composition Checklist**
>
> - [x] All test cases have defined expected results
> - [x] Required test data is present and valid
> - [x] Using correct version of TAF (Test Automation Framework)
> - [x] Test against correct version of SUT (System Under Test)
> - [x] Test oracle mechanisms are functioning correctly
> - [ ] All required test fixtures are available

---

> **Verification Steps for Automated Test Suites**
>
> **2. Verify New Tests for New TAF Features**
>
> - Verify any new test that use features of the TAF (Test Automation Framework)
> - New functionality must be monitored closely to ensusre it works as expected.
> - Real-world example: 
>   - A new Selenium wait mechanism had a bug, causing random test failures.
>   - We spent days debugging because we didn't verify the new feature properly
>
> ```javascript
> function testNewWaitFeature() {
>   // Setup a controlled test environment
>   const element = createTestElement();
>
>   console.log("Testing new wait feature in isolation ... ");
>
>   // Test case 1: Element appears after 1 second
>   setTimeout(() => { element.style.display = "block"; }, 1000);
>   const result1 = customWaitForElement(element, 2000);
>   assert(result1 === true, "Wait should succeed when element appears within timeout");
>
>   // Test case 2: Element never appears (timeout)
>   const hiddenElement = createTestElement(true);
>   const result2 = customWaitForElement(hiddenElement, 1000);
>   assert(result2 === false, "Wait should timeout when element doesn't appear");
>
>   // Test case 3: Element appears exactly at timeout boundary
>   setTimeout(() => { element.style.display = "block"; }, 1000);
>   const result3 = customWaitForElement(element, 1000);
>   assert(result3 === true, "Wait should handle edge cases at timeout boundary");
>
>   console.log("All verification tests for new wait feature passed!");
> }
> ```
>
> Three scenarios verified:
>
> - Element appears within timeout
> - Element doesn't appear (timeout)
> - Element appears exactly at timeout (edge case).
>
> Only integrate into main suite after all tests pass.
>
> This prevents bugs from spreading into full automation runs.

---

> **Verification Steps for Automated Test Suites**
>
> **3. Consider the Repeatability of Tests**
>
> - A good automated test should give you the same result every time you run it under the same conditions
> - If you have test cases in your suite that don't give reliable results you should move them out of the active automated test suite.
> - Analyze them separately to find the root cause of the inconsistency
> - Moving it to a separate 'need fixing' suite and clearly marking it as flaky saved us from false alarms while we corked on making it more robust.

---

> **Verification Steps for Automated Test Suites**
>
> **4. Consider the intrusiveness of Automated Test Tools**
>
> - Consider how intrusive our automated test tools are to the SUT (System Under Test)
> - Test intrusiveness refers to how much your Test Automation Solution affects or changes the behavior of the SUT (System Under Test)
> - The TAS will often be tightly coupled with the SUT. that's by design, to ensure better compatibility for interactions
> - When your TAS runs within the SUT environment. it might actually change how the SUT behaves compared to when a real user interacts with it manually.
>
> **Test Automation Intrusiveness**
>
> ```mermaid
> %%{init: {'flowchart': {'nodeSpacing': 80, 'rankSpacing': 10}}}%%
> flowchart TB
>     subgraph manual ["Manual Testing</br> (Non-Intrusive)"]
>         direction LR
>         U["User"] -->|"interacts"| SUT1["SUT<br/>(System Under Test)"]
>         SUT1 ~~~ D1["✓ Normal behavior<br/>✓ True user experience"]
>     end
>
>     subgraph auto ["Automated Testing (Potentially Intrusive)"]
>         direction LR
>         TAS["TAS<br/>(Test Automation Solution)"] -->|"interacts"| SUT2["SUT with TAS"]
>         SUT2 ~~~ D2["⚠ May mask real issues<br/>⚠ May behave differently<br/>⚠ May affect performance<br/>⚠ May cause test-only failures"]
>     end
>
>     manual ~~~ auto
>
>     style U fill:#2e7d32,color:#fff
>     style SUT1 fill:#2e7d32,color:#fff
>     style TAS fill:#2e7d32,color:#fff
>     style SUT2 fill:#c62828,color:#fff
>     style D1 fill:none,stroke:none
>     style D2 fill:none,stroke:none
> ```
>
> - The TAS's (Test Automation Solution) presence might actually change how SUT behaves
> - The SUT might behave differently when tested automatically versus manually
> - Performance might be affected by the presence of the TAS
> - You might see failures during automated testing that don't occur in production
> - Real issues might be masked or appear differently
> - Automated tests running constantly can consume significant server resources, slowing down the application.

---

> **Real-world Example: Finding the Right Balance**
>
> Automating tests for a financial application: a comprehensive suite for transaction flows looked fine in the test environment, but production issues still slipped through. Investigation found problems in all four verification areas:
>
> - **Composition issues**: Some of our test cases were missing expected results for certain edge cases
> - **New feature issues**: We had recently added API-level tests using a new library, but hadn't properly verified the library itself
> - **Repeatability issues**: Some of our UI tests had timing issues that made them occasionally pass even when they should fail
> - **Intrusiveness issues**: Our test automation was bypassing some security checks that real users couldn't bypass
>
> By addressing each area systematically, the suite became reliable enough to catch issues before they reached production.

---

> **Conclusion**
>
> 1. Check the composition of your test suite to ensure it's complete
> 2. Verify new tests that use new features of your Test Automation Framework
> 3. Consider the repeatability of your tests and isolate flaky ones
> 4. Be aware of how intrusive your automated test tools might be.

---

### Transcript

"Explain the correct behavior for a given automated test script and/or test suite.

Importance of verifying test automation.

Now let's talk about how to make sure your automated test scripts and test suites are behaving correctly. It's kind of ironic that we need to test our test automation, right? But trust me, this is super important stuff. So let's dive into what we need to do to verify that our automated test suites are working as expected and are fit for use.

This is actually a really critical part of being a test automation engineer that people sometimes overlook. You see, automated test suites aren't just set-it-and-forget-it tools. They're actually complex pieces of software themselves that need to be verified for completeness, consistency, and correct behavior. I mean, how can we trust the results of our automated tests if we're not sure the automation itself is working properly?

I remember working on a project where we had this elaborate test suite that was supposedly checking our payment processing system. Everything looked good. All tests were passing. But then we discovered that one of our key validation tests wasn't actually checking what we thought it was checking, due to a selector issue. We were getting a false sense of security from tests that weren't really testing what we needed.

Verification steps for automated test suites.

So what steps can we take to verify our automated test suites? Let's break it down into four main areas.

First things first, we need to check the composition of our test suite. This means making sure it's complete and has all the necessary components. For example, you want to verify that all test cases have properly defined expected results, the necessary test data is present and correct, you're using the correct version of the test automation framework, and you're testing against the correct version of the system under test.

Here's a simple checklist that you might use. As we can see in this checklist, we're verifying all the essential components that make up a complete test suite. Now, this might seem basic, but you'd be surprised how often issues slip through because people skip these fundamental checks. For example, I once worked on a project where a developer updated the system under test but forgot to tell the testing team. We kept running our automated tests against the old version and wondering why we were getting weird results. So yeah, always check you're using the right versions.

The second step is to verify any new tests that use new features of the test automation framework. Whenever you introduce new functionality to your test automation framework or use a feature for the first time, you need to be extra careful. You should verify and monitor these new tests closely to make sure the feature is working as expected.

I'll give you a real-world example from one of my projects. We upgraded our Selenium WebDriver to a newer version that included a new wait mechanism. We wrote tests using this new feature, but we didn't verify the feature itself properly. Turns out it had a bug that only manifested under specific conditions, which meant some of our tests would randomly fail. We spent days debugging the tests before realizing it was the new feature causing the issue.

So how do you verify these new features? Well, one approach is to create simple, isolated tests that focus solely on the new feature before integrating it into your main test suite. Here's a simplified example.

As we can see in this code snippet, we're specifically testing a new custom wait feature in isolation before using it in our main test suite. We've created three test cases that verify the feature works as expected. The first one is when an element appears within the timeout period. The second test case is for when an element doesn't appear — the timeout case. And the third is when an element appears exactly at the timeout boundary — an edge case. Only after all these verification tests pass will we feel confident incorporating this new feature into our main test suite. This approach helps us catch issues with the feature itself before it causes problems in our actual tests.

The third aspect is the repeatability of your tests. This is one of the most important characteristics of good automated tests. A good automated test should give you the same result every time you run it under the same conditions. If your tests are flaky — meaning sometimes passing and sometimes failing without any changes to the code — then they're not reliable and you can't trust them.

Here's what you should do: if you have tests in your suite that don't give reliable results, maybe due to race conditions or environmental factors, you should move them out of the automated test suite, then analyze them separately to find the root cause of the inconsistency. Otherwise, your team will waste a lot of time investigating failures that might just be due to the flakiness of the test itself.

I've seen teams spend hours debugging an issue that was just a timing problem in the test, not an actual bug in the application. In one case, we had a test that would fail about 20% of the time because it didn't properly wait for an animation to complete before checking the UI state. Moving it to a separate "needs fixing" suite and clearly marking it as flaky saved us from false alarms while we worked on making it more robust.

Finally, we need to consider how intrusive our automated test tools are to the system under test. Now, if this concept is new to you, test intrusiveness refers to how much your test automation solution affects or changes the behavior of the system under test. The TAS will often be tightly coupled with the SUT, and that's by design to ensure better compatibility for interactions. But this close integration can sometimes lead to problems. For instance, when your TAS runs within the SUT environment, it might actually change how the SUT behaves compared to when a real user interacts with it manually. This can affect performance or even functionality.

Let me illustrate this with a diagram. As we can see in this diagram, there's a fundamental difference between manual testing and automated testing in terms of intrusiveness. In manual testing, a user interacts directly with the system under test, experiencing it as it was designed to be used. There is no additional software layer that might affect behavior. But in automated testing, the test automation solution interacts with the system under test, and its presence might actually change how the SUT behaves. This can lead to several problems: the SUT might behave differently when tested automatically versus manually; performance might be affected by the presence of the TAS; you might see failures during automated testing that don't occur in production; real issues might be masked or appear differently.

I've seen this happen with a web application where our automated tests were running constantly in the background and consumed significant server resources. This caused the application to slow down during testing in ways that users never experienced. The developers initially dismissed our performance concerns because "it's just the tests causing that, not the application itself." But of course, this made it harder to identify genuine performance issues.

A high level of intrusion can show failures during testing that aren't evident in production. If this causes a lot of test failures that can't be reproduced manually, confidence in the test automation can drop dramatically. Developers might start requiring that all failures identified by test automation be reproduced manually before they'll investigate, which defeats much of the purpose of automation.

Real-world example: finding the right balance.

Let me share a quick real-world example that ties all of these concepts together. I was working on a project where we were automating tests for a financial application. We had a comprehensive test suite that checked various transaction flows and validations. Everything seemed to be working perfectly in our test environment. However, when the application went to production, we started getting reports of issues that our automated tests hadn't caught. After investigation, we discovered several problems with our test automation.

The first one was composition issues: some of our test cases were missing expected results for certain edge cases. The second one was new feature issues: we had recently added API-level tests using a new library, but hadn't properly verified the library itself. The third one was repeatability issues: some of our UI tests had timing issues that made them occasionally pass even when they should fail. And the fourth problem was intrusiveness issues: our test automation was bypassing some security checks that real users couldn't bypass. By addressing each of these areas systematically, we were able to improve our test automation to the point where it reliably caught issues before they reached production.

So to wrap things up, verifying the correct behavior of your automated test scripts and test suites is absolutely crucial. You need to check the composition of your test suite to ensure it's complete, verify new tests that use new features of your test automation framework, consider the repeatability of your tests and isolate flaky ones, and be aware of how intrusive your automated test tools might be.

Remember, your automated tests are only as good as their ability to consistently and accurately detect issues in your SUT. By following these verification steps, you can ensure that your test automation is a reliable tool for maintaining software quality.

In our next video, we'll look at how to identify when test automation produces unexpected results and what to do about it."
