# Mooc

## Explain Configuration Management for Testware

### Screen

> **Introduction to Configuration Management**
>
> - Critical yet often overlooked aspect of test automation
> - Personal anecdote: undocumented staging vs. dev configuration
> - Prevents environment-specific failures

---

> **Components of Configuration Management**
>
> 1. **Test Environment Configuration**
>
> - Different login credential
> - Different URLs (like dev.myapp.com vs. staging.myapp.com)
> - Different feature flags enabled or disabled
> - Different database connection
>
> **Example:**
>
> ```json
> // environment-config.json
> {
>   "development": {
>     "baseUrl": "https://dev.myapp.com",
>     "username": "test_user",
>     "password": "dev_password",
>     "featureFlags": {
>       "newCheckout": true,
>       "darkMode": true
>     }
>   },
>   "staging": {
>     "baseUrl": "https://staging.myapp.com",
>     "username": "test_user",
>     "password": "staging_password",
>     "featureFlags": {
>       "newCheckout": true,
>       "darkMode": false
>     }
>   }
> }
> ```
>
> - Configuration values like base URL, passwords, and feature flags differ between environment
> - Tests can run in multiple environments (e.g., dev and staging) without changing the test code.
> - Configuration is typically stored with testware or in a shared repository if used across multiple frameworks or projects.
> - Example: Using a shared Gitlab repo with merge requests to manage test configurations and avoid confusion.

---

> **Components of Configuration Management**
>
> 2. **Test Data**
>
> Test Data can be specific to:
>
> - A particular test environment
> - A specific release of the SUT
> - A particular feature set
>
> ```text
> Test Data/
> ├── Development/
> │   ├── Users.csv          (50 test users)
> │   ├── Transactions.json  (simple transactions)
> │   └── Products.json      (limited product catalog)
> └── Staging/
>     ├── Users.csv          (500 test users)
>     ├── Transactions.json  (complex transactions)
>     └── Products.json      (full product catalog)
> ```
>
> - Smaller Test Automation Frameworks (TAFs) usually keep test data with the framework
> - Larger projects often rely on dedicated Test Data Management (TDM) systems

---

> **Components of Configuration Management**
>
> 3. **Test Suites/Test Cases**
>
> Organize test cases into different suites based on their purpose:
>
> - **Smoke tests**: Quick test to verify that the basic functionality works
> - **Regression tests**: More comprehensive tests to ensure existing features still work
> - **Feature-specific tests**: Tests focused on specific parts of the application.
>
> These test suites are often executed in different test levels, using different pipelines and enviornments.
>
> ```text
> Test Suites/
> ├── Smoke Tests/                    (run in CI, fast)
> │   ├── Login.test.js
> │   ├── BasicNavigation.test.js
> │   └── SimpleSearch.test.js
> ├── Regression Tests/               (run nightly, comprehensive)
> │   ├── AllUserJourneys.test.js
> │   └── EdgeCases.test.js
> └── Feature Tests/                  (run when specific features change)
>     ├── Checkout/
>     │   ├── StandardCheckout.test.js
>     │   └── GuestCheckout.test.js
>     └── UserProfile/
> ```
>
> - Smoke tests are run frequently in CI and are designed to be fast
> - Regression tests are more comprehensive and run less frequently, like overnight.
> - Feature tests are organized by feature area and might only run when that specific area changes.

---

> **Managing Different Release of the SUT**
>
> 1. **Feature Toggle Configuration**
>
> ```json
> // feature-toggles.json
> {
>   "release-1.0": {
>     "newCheckout": false,
>     "guestCheckout": true,
>     "savedCreditCards": false
>   },
>   "release-2.0": {
>     "newCheckout": true,
>     "guestCheckout": true,
>     "savedCreditCards": true
>   }
> }
> ```
>
> - Use feature toggles to define which features are enabled or disabled for each released or environment.
> - You testware can use these toggles to determine which test suites to execute for a given release or environment.
> You wouldn't run tests for the "savedCreditCards" feature on release 1.0 because that feature is set to 'false', meaning it isn't available yet.

---

>  **Managing Different Release of the SUT**
>
> 2. **Releasing Testware with the SUT**
>
> - Release your testware alongside your SUT, using the same version number.
> - this creates an exact match between the SUT version and the testware that can test it.
> - Typically implemented using a configuration management system with tags or branches
> - Each tag represents a specific version of both the SUT and its corresponding testware.
>
> ```bash
> git tag v1.0.0
> git tag v1.1.0
> git tag v2.0.0
> ```
>
> - Ragging testware is useful for projects with long-term support requirements.

---

> **Real-World Example**
>
> Environments:
>
> 1. **Development**: Where developers tested their code
> 2. **Staging**: A production-like environment for final testing
> 3. **Production**: The live system used by customers
>
> Configuration management approach:
>
> - **Environment Configuration**: We had a configuration file that specified URLs, API endpoints, and authentication methods for each environment.
> - **Test Data**: We had synthetic patient data for development and staging (never using real patient data). The development data was minimal, while staging had a more comprehensive dataset to test edge cases.
> - **Test Suites**: We had smoke tests that ran on every commit, regression tests that ran nightly, and compliance tests that ran before any release.
>
> This setup allowed us to:
>
> - Run the right tests in the right environments.
> - Easily switch between testing different releases.
> - Maintain consistency across our testing process.

---

> **Conclusion**
>
> 1. Systematically manage configurations, data, and suites.
> 2. Use features toggles for controlled rollouts
> 3. Co-version testware with SUT
> 4. Eliminate environment-specific failures through proper configuration management.

### Transcript

"Explain configuration management for Testware.

Now let's dive into something really important that often gets overlooked: configuration management for testware. I've seen so many automation projects get derailed because of poor configuration management.

Like, there was this one time on a project where our team spent days trying to figure out why our tests were failing in the staging environment but passing in development. Turns out we had different configuration settings for each environment, but nobody had documented them properly. It was a real headache.

So what exactly is configuration management? Well, it's basically how we keep track of and control changes to our test environments, test data, and test suites. It's super important because automated tests often need to run across multiple environments and different versions of the system under test.

Components of configuration management.

Let's break down the main components of configuration management in test automation. There are really three big pieces to this puzzle.

Test environment configuration.

First up we have test environment configuration. Each test environment in your development pipeline might have different settings. For example: different URLs like dev.myapp.com versus staging.myapp.com, different login credentials, different database connections, or different feature flags enabled or disabled.

Let me show you a simple example of what this might look like in code. As we can see in this code snippet, we have different configuration values for our development and staging environments. The base URL is different, the passwords are different, and even the feature flags have different values. This kind of setup allows our tests to run in both environments without having to change the test code itself.

Now where should you store this configuration? Well, typically it's stored with your testware — that is, all the artifacts relating to testing like test scripts, test data, and so on. But if you're using test automation across multiple projects, or if you have multiple test automation frameworks for the same project, you might want to store the configuration in a common core library or a shared repository.

For instance, at one of my previous companies, we had a shared GitLab repository just for our test configurations. Whenever someone needed to update a configuration value, they'd submit a merge request which would go through a review process. This helped prevent those "wait, who changed the staging URL?" moments that used to drive us crazy.

Test data.

The second component is test data. This is the information your tests use to verify that the SUT is working correctly. Test data can be specific to a particular test environment, a specific release of the SUT, or a particular feature set.

For example, in a banking application, you might need different test account numbers or transaction data, depending on whether you're testing in a development environment or a production-like environment.

Here's a simple visualization of how test data might be organized. As you can see, the users, transactions, and products data is organized into development and staging folders. As with environment configuration, test data is usually stored with smaller test automation frameworks. But for larger projects you might use specialized test data management systems.

I once worked on a project where we had to test a recommendation engine. We needed different sets of user behavior data for development, where we only needed a few user profiles, versus staging where we needed thousands of profiles to test performance. Having separate test data folders for each environment saved us tons of time and prevented confusion.

Test suites and test cases.

The third component is managing your test suites and test cases. It's common practice to organize test cases into different test suites based on their purpose.

Smoke tests: these would be quick tests to verify that the basic functionality works. Regression tests: these would be more comprehensive tests to ensure existing features still work. And feature-specific tests: these tests would focus on specific parts of the application. These test suites are often executed at different test levels using different pipelines and environments.

Let me show you a diagram of how this might look. As we can see in this diagram, the tests are organized hierarchically. Smoke tests are run frequently in CI and are designed to be fast. Regression tests are more comprehensive and run less frequently, like overnight. Feature tests are organized by feature area and might only run when that specific area changes.

Managing different releases of the SUT.

Now let's talk about how to handle different releases of the SUT. Each release determines a feature set, and you need test cases and suites to assess the quality of that release. There are two main approaches.

Feature toggle configuration.

One approach is to use feature toggles. This means defining which features are enabled or disabled for each release or environment. For example, let's say you're working on an e-commerce site and you're gradually rolling out a new checkout process. Your testware can then use these toggles to determine which test suites to execute for a given release or environment. For instance, you wouldn't run tests for the saved credit cards feature on release 1.0 because that feature is set to false, meaning it isn't available yet.

Releasing testware with the SUT.

Another approach is to release your testware alongside your SUT using the same version number. This creates an exact match between the SUT version and the testware that can test it. This approach is typically implemented using a configuration management system with tags or branches. For example, you might have something like this. Each tag represents a specific version of both the SUT and its corresponding testware.

I've found this approach to be really useful in projects with long-term support requirements. For instance, at a previous job, we had to maintain and occasionally patch older versions of our software for certain enterprise customers. Having the testware tagged with the same version made it easy to go back and run the appropriate tests when we needed to create a patch for an older version.

Real world example.

Let me share a concrete example from my own experience to tie all of this together. I once worked on a project where we were developing a healthcare portal with strict compliance requirements. We had three environments: development, where developers tested their code; staging, a production-like environment for final testing; and production, the live system used by customers.

Our configuration management approach looked like this. Environment configuration: we had a configuration file that specified URLs, API endpoints, and authentication methods for each environment. Test data: we had synthetic patient data for development and staging, never using real patient data. The development data was minimal, while staging had a more comprehensive data set to test edge cases. Test suites: we had smoke tests that ran on every commit, regression tests that ran nightly, and compliance tests that ran before any release.

For each major release, we tagged our testware with the same version as the SUT, but we also used feature toggles within each release to handle gradual feature rollouts. This setup allowed us to run the right tests in the right environments, easily switch between testing different releases, and maintain consistency across our testing process.

So to recap. Configuration management for testware involves managing test environment configurations like URLs and credentials; test data, which can vary by environment or release; and test suites and test cases organized by purpose. And there are two main approaches to handling different releases: using feature toggles to enable or disable tests for specific features, and releasing your testware alongside your SUT with the same version number.

Good configuration management makes your test automation more reliable, more maintainable, and less prone to those head-scratching "but it works on my machine" moments that we all dread.

In the next video, we'll talk about test automation dependencies for an API infrastructure, which builds on many of the concepts we discussed in this video."
