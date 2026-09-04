# Mooc

## Apply Test Automation ad Different Test Levels within Pipelines

### Screen

> **Introduction to Pipeline Test Automation**
>
> - Usually, the newest team member had to stay late to manually kick off all the weekend tests
> - But once we integrated our tests into pipelines, the computer took over that job, and suddenly everyone could start their weekend on time.

---

> **What are Pipelines**
>
> - Pipeline = CI/CD Pipeline
>   - CI = Continuous Integration
>   - CD = Continuous Delivery/ Deployment
>
> Code goes in one end, passes through various quality checkpoints (like our automated test), and if if passes all the checks, it comes out the other end ready to be deployed.
> These pipelines automate the process of building, testing and deploying software.
>
> ```mermaid
> flowchart LR
>     CC["Code change"] --> B["Build"] --> CT["Component Tests"] --> DT["Deploy to Test"] --> ST["System Tests"] --> DP["Deploy to Production"]
> ```

---

> **Test Levels in Pipelines - Configuration Tests**
>
> - Configuration tests for your Test Automation Framework or Solution
> - These are specialized tests that check if your automation framework it self is set up correctly.
> - A configuration tests might verify that those paths are correct and that the files actually exist.
> - These tests run during the build of your test automation project and are like a pre-flight check to make sure your testing tools are ready to go

---

> **Test Levels in Pipelines - Component Tests**
>
> - These are tests that focus on individual components like library classes or web components.
> - Your component test might check if it correctly validates dates or prevent users from selecting dates in the pasts?
> - These tests act as quality gates for your pipeline.
> - If these tests fail, the pipeline stops right there, preventing bad code from moving forward.

---

> **Test Levels in Pipelines - Component Integration Tests**
>
> - These check if low-level components work together correctly.
> - These often run together with component tests in the continuous integration pipeline.
> - A component integration test would verify that after logging in, the user profile displays the correct information.

---

> **Test Levels in Pipelines - System Tests**
>
> - These tests verify that the entire system works as expected from an end-user perspective.
> - A system test might involve checking that a user can complete an entire workflow, like registering for an account, adding items to a cart, and completing a purchase.
> - These tests act as the last quality gate before deployment; like a final inspection before shipping a product.

---

> **Test Levels in Pipelines - System Integration Tests**
>
> - These verify that separately developed system components work together correctly.
> - These are often part of a continuous delivery pipeline.
> - A system integration test would verify that communication with a payment gateway or third-party service works correctly.

---

> **Different Approaches to Pipleline Integration - First Approach**
>
> Approach 1: Test as Part of de Deployment
>
> - Tests are executed as part of the deployment phase, after the components are deployed
> - If the test fail, the deployment can automatically fail and even be rolled back.
> - If you need to rerun tests, you'll need to redeploy everything first, which can be time-consuming.
> - Be careful about flaky tests in this phase; They can trigger unnecessary rollbacks.

---

> **Different Approaches to Pipeline Integration - Second Approach**
>
> Approach 2: Tests as a Separate Pipeline
>
> - Tests are executed as a separate pipeline triggered after a successful deployment.
> - Tests don't act as quality gate in this approach; They're more informational.
> - Include simple automated "smoke tests" to verify deployment success.
> - Useful when different teams need to run specialized test suites post-deployment.

---

> **Beyond Basic Pipeline Integration - Running Periodic Test Suites**
>
> - Pipelines can be set up to run test suites periodically, like nightly regression.
> - Nightly regression is useful for running longer test suites automatically.
> - Gives you a complete quality report each morning before you even start working.

---

> **Beyond Basic Pipeline Integration - Running Non-functionnal Test**
>
> - Pipelines can run non-functional tests like performance, security, or accessibility.
> - Example: Running weekly performance tests to monitor response times after code changes.

---

> **Beyond Basic Pipeline Integration - Real World Example**
>
> Main pipeline steps:
>
> 1. Developer commits code
> 2. CI server runs the build
> 3. Component tests run automatically (45 seconds)
> 4. If they pass, component integration tests run (1 minutes)
> 5. If those pass the code is automatically deployed to a test environment
> 6. System tests run to verify critical paths (3 minutes)
> 7. If they pass, the code is deployed to a staging environment
> 8. System integration tests run to verify external integration (5 minutes)
> 9. Every night, at midnight, a full regression suite runs (10 minutes)
>
> In addition, a separate pipeline runs performance tests every Sunday night
>
> Approach:
>
> - Caught 85% of issues before reaching production
> - 15% left were edge cases hard to anticipate.

---

> **Conclusion**
>
> 1. Multiple integration approaches available.
> 2. Support scheduled/non-functional testing.
> 3. Right tests in right pipeline stages.
> 4. Fast, reliable tests early; comprehensive tests later

---

### Transcript

"Apply test automation at different test levels within pipelines.

Let's discuss how to apply test automation at different test levels within pipelines. One of the biggest benefits of test automation is that you can run tests without anyone having to closely watch them.

Let me tell you a quick story. I remember when I first started in testing, we had this Friday afternoon ritual where someone, usually the newest team member, had to stay late to manually kick off all the weekend tests. But once we integrated our tests into pipelines, the computer took over that job and suddenly everyone could start their weekend on time. That's the power of unattended test execution.

What are pipelines anyway?

So before we dive in, let's make sure we're on the same page about pipelines. When I say pipeline, I'm usually talking about a CI/CD pipeline, where CI stands for continuous integration and CD stands for either continuous delivery or continuous deployment, depending on who you ask.

Think of a pipeline like an assembly line in a factory. Code goes in one end, passes through various quality checkpoints like our automated tests, and if it passes all the checks, it comes out the other end ready to be deployed. These pipelines automate the process of building, testing, and deploying software.

Here's a simple visualization of what a pipeline might look like. As you can see, we start with a code change, run through a number of quality checking steps, and finally deploy to production if all previous steps passed.

Test levels in pipelines.

Now let's talk about how different test levels fit into these pipelines.

Configuration tests.

First up we have what are called configuration tests for your test automation framework or solution. Basically these are specialized tests that check if your automation framework itself is set up correctly. For example, let's say you have scripts that need to access certain files. A configuration test might verify that those paths are correct and that the files actually exist. These tests run during the build of your test automation project, and are like a preflight check to make sure your testing tools are ready to go.

Component tests.

Next, we have component tests, which are part of the build step of your pipeline. These are tests that focus on individual components like library classes or web components. For instance, if you're building a web app with a date picker component, your component tests might check if it correctly validates dates or prevents users from selecting dates in the past. These tests act as quality gates for your pipeline. So what does that mean? Well, if these tests fail, the pipeline stops right there, preventing bad code from moving forward.

Component integration tests.

Moving on. We have component integration tests which check if low-level components work together correctly. These often run together with component tests in the continuous integration pipeline. For example, if you have a logging component and a user profile component, a component integration test will verify that after logging in, the user profile displays the correct information.

System tests.

Then we have system tests which typically get integrated into a continuous deployment pipeline. These tests verify that the entire system works as expected from an end-user perspective. A system test might involve checking that a user can complete an entire workflow, like registering for an account, adding items to a cart, and completing a purchase on an e-commerce site. These tests act as the last quality gate before deployment, like a final inspection before shipping a product.

System integration tests.

Finally, we have system integration tests which verify that separately developed system components work together correctly. These are often part of a continuous delivery pipeline. For example, if your application needs to communicate with a payment gateway or a third-party service, a system integration test would verify that this communication works correctly.

Different approaches to pipeline integration.

Now, there are two main approaches to integrating system-level tests into your pipelines.

In the first approach, your tests are executed as part of the deployment phase, after the components are deployed. This has a big advantage: if the tests fail, the deployment can automatically fail and even be rolled back. It's like having an emergency brake that automatically engages if something goes wrong. The downside? If you need to rerun tests, you'll need to redeploy everything first, which can be time-consuming.

I worked on a project where we used this approach, and while it was great for catching issues before they hit production, we sometimes had false alarms from flaky tests that would trigger a rollback unnecessarily. We had to be really careful about which tests we included in this phase.

In the second approach, your tests are executed as a separate pipeline that gets triggered after a successful deployment. This is useful when you expect to run different test suites or various test automation code on each deployment. The tests don't act as quality gates in this approach. They're more informational. You would typically include a few simple automated smoke tests to verify that the deployment itself was successful, but you wouldn't run your full test suite as part of the deployment process.

I've seen this approach work well in organizations where different testing teams need to run their own specialized tests on the deployed software.

Beyond basic pipeline integration.

Pipelines aren't just for deployment testing. They can be used for other test automation purposes, too.

Running periodic test suites.

You can set up pipelines to run different test suites periodically. For example, you might run a full regression test suite every night, often called nightly regression, especially for longer-running tests. Imagine coming into work each morning and having a complete report on the quality of your software waiting for you. That's what automated nightly regression gives you.

Running non-functional tests.

Pipelines can also run non-functional tests, either as part of a continuous deployment pipeline or separately. These tests check things like performance, security, or accessibility. For example, you might set up a pipeline to run performance tests once a week to monitor if any code changes have impacted how quickly your application responds.

Real world example.

Let me share a real world example of how all this fits together. On one of my previous projects, we had a financial application with very strict quality requirements. Our pipeline looked something like this.

First, the developer commits code. Second, the CI/CD server runs the build. Third, component tests run automatically, around 45 seconds. Fourth, if they pass, component integration tests run, which take about a minute. Fifth, if those pass, the code is automatically deployed to a test environment. Sixth, system tests run to verify critical paths, which take about three minutes. Seventh, if they pass, the code is deployed to a staging environment. Eighth, system integration tests run to verify external integrations, which take around five minutes. And finally, in step nine, every night at midnight, a full regression suite would run, which would take around ten minutes.

We also had a separate pipeline that ran performance tests every Sunday night when the system usage was low. This approach caught about 85% of issues before they ever reached production, and the remaining 15% were usually edge cases that were hard to anticipate.

So to wrap up, we've learned that test automation is ideal for pipelines because tests can be run unattended. Different test levels fit into different parts of the pipeline: configuration and component tests in the build phase, and system and integration tests after deployment. Tests can be part of the deployment itself or run as a separate pipeline. Pipelines can also run periodic regression or non-functional tests.

Remember, the key is to put the right tests in the right places. You want your fastest, most reliable tests early in the pipeline to catch problems quickly, and your more comprehensive tests later in the pipeline to ensure overall quality.

In the next video, we'll talk about configuration management for testware, which is another critical piece of the puzzle when working with test automation in pipelines."
