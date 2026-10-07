# Mooc

## Restructure the Automated Testware to Align with System Under Test Updates

### Screen

> **Understanding the Challenge**
>
> When your SUT (System Under Test) undergoes changes, those changes can ripple through your entire TAS (Test Automation Solution).

---

> **Impact of SUT Changes on Test Automation**
>
> ```mermaid
> flowchart LR
>     SUT["**SUT**<br/>(System Under Test)<br/>New Feature Added<br/>UI Redesign"]
>
>     subgraph impacted[" "]
>         direction LR
>         TAF["**TAF**<br/>(Test Automation Framework)<br/>May need updates"]
>         CL["**Component Libraries**<br/>Functions may break"]
>         TSD["**Test Scripts & Test Data**<br/>Locators fail"]
>         TEC["**Test Environment Configuration**<br/>Settings outdated"]
>     end
>
>     SUT -->|changes| impacted
>
>     style SUT fill:#1565c0,color:#fff,stroke:#0d47a1
>     style TAF fill:#c62828,color:#fff,stroke:#b71c1c
>     style CL fill:#c62828,color:#fff,stroke:#b71c1c
>     style TSD fill:#c62828,color:#fff,stroke:#b71c1c
>     style TEC fill:#c62828,color:#fff,stroke:#b71c1c
> ```
>
> Potential Issues
>
> * Tests fail unexpectedly
> * False positives increase
> * Maintenance time grows
> * Coverage gaps appear
> * Performance degrades
>
> Key point
>
> Any change, no matter how trivial, may have wide-ranging adverse impact on the reliability and performance of the TAS (Test Automation Solution)

---

> **The Incremental Approach**
>
> - You don't want to try to fix everything all at once
> - We need to adopt what we call a "minimum viable product mindset"
> - This means making changes incrementally, testing them thoroughly, and then moving on to the next set of changes.
>
> ```mermaid
> flowchart LR
>     IC["**1. Identify Changes**<br/>• Analyze SUT updates<br/>• List affected areas"]
>     PU["**2. Prioritize Updates**<br/>• Critical tests first<br/>• High-value features"]
>     MS["**3. Make Small Changes**<br/>• Update one module<br/>• Minimal code changes"]
>     TL["**4. Test Limited Scope**<br/>• Run affected tests<br/>• Verify no side effects"]
>     MI["**5. Measure Impact**<br/>• Check performance<br/>• Monitor stability"]
>     FR["**6. Full Regression**<br/>• Run complete suite<br/>• Verify all tests pass"]
>
>     IC --> PU --> MS --> TL --> MI --> FR
>
>     style IC fill:#1565c0,color:#fff,stroke:#0d47a1
>     style PU fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style MS fill:#f9a825,color:#000,stroke:#f57f17
>     style TL fill:#6a1b9a,color:#fff,stroke:#4a148c
>     style MI fill:#00838f,color:#fff,stroke:#006064
>     style FR fill:#c62828,color:#fff,stroke:#b71c1c
> ```
>
> **Real Example**: Login Page Redesign
>
> - Week 1: Update login button locator (from CSS to ID selector)
> - Week 2: Modify username/password field interactions
> - Week 3: Update error message validation
> - Week 4: Refactor entire login test module with new patterns
> - Result: Zero test failures, minimal disruption to CI/CD pipeline.

---

> **Key Areas for Restructuring**
>
> **1. Identify Changes in Test Environment Components**
>
> - Evaluate what changes and improvements need to be made.
> - Changes might include testware, function libraries, or the operating system.
> - Each change impacts the Test Automation Solution's performance.
> - Example: Upgrading from Java 8 to Java 11 caused compatibility issues

---

> **Key Areas for Restructuring**
>
> **2. Increasing Efficiency of Core Function Libraries**
>
> Before: Multiple Specific Functions
>
> ```javascript
> clickButtonById(String id)
> // Only works with ID attribute
>
> clickButtonByClass(String className)
> // Only works with class attribute
>
> clickButtonByXpath(String xpath)
> // Only works with XPath
>
> clickLinkById(String id)
> // Separate function for links
>
> clickLinkByText(String text)
> // Another link-specific function
> ```
>
> After: Consolidated Generic Function
>
> ```javascript
> clickElement(By locator, ElementType type)
> // Works with any locator strategy:
> // - By.id("elementId")
> // - By.className("class")
> // - By.xpath("//xpath")
> ```
> 
> Benefits:
>
> - Single function to maintain
> - Flexible locator strategies
> - Type-safe element handling
> - Reduced code duplication
>
> Impact of Consolidation
>
> - Lines of code: 150 --> 45 (70% reduction)
> - Maintenance points: 5 functions --> 1 function (80% reduction)

---

> **Key Areas for Restructuring**
>
> **3. Refactoring the Test Automation Architecture**
>
> - Your TAA (Test Automation Architecture) must evolve with your SUT (System Under Test)
> - You can't just bolt on new features -- analyze and update the architecture thoughtfully.
> - Example: A team started with UI tests using Selenium WebDriver
> - When a mobile app and API layer were added, they refactored the architecture to support multiple test types.
>
> ```mermaid
> %%{init: {'flowchart': {'nodeSpacing': 12, 'rankSpacing': 10, 'padding': 16, 'subGraphTitleMargin': {'top': 20, 'bottom': 12}}, 'themeVariables': {'clusterBkg': '#eceff1', 'titleColor': '#0d47a1'}}}%%
> flowchart LR
>     subgraph OWO["Original: Web-Only Architecture"]
>         direction TB
>         OWO_SP[" "]
>         WU["Web UI Tests"]
>         SW["Selenium WebDriver"]
>         PO["Page Objects"]
>         TD["Test Data"]
>
>         OWO_SP ~~~ WU ~~~ SW ~~~ PO ~~~ TD
>     end
>
>     subgraph EMP["Evolved: Multi-Platform Architecture"]
>         direction TB
>         EMP_SP[" "]
>         TL["**Test Layer**<br/>• Web UI Tests<br/>• Mobile Tests<br/>• API Tests"]
>         AL["**Abstraction Layer**<br/>Common interfaces for all test types"]
>         DL["**Driver Layer**<br/>• Selenium WebDriver<br/>• Appium (Mobile)<br/>• RestAssured (API)<br/>• Playwright (modern web)"]
>         OM["**Object Models**<br/>• Page Objects (Web)<br/>• Screen Objects (Mobile)<br/>• Endpoint Objects (API)"]
>         CU["**Common Utilities**<br/>• Test Data Management<br/>• Reporting<br/>• Configuration"]
>
>         EMP_SP ~~~ TL ~~~ AL ~~~ DL ~~~ OM ~~~ CU
>     end
>
>     OWO -->|Evolves to| EMP
>
>     style OWO fill:#bbdefb,color:#0d47a1,stroke:#0d47a1,stroke-width:2px
>     style EMP fill:#c8e6c9,color:#1b5e20,stroke:#1b5e20,stroke-width:2px
>     style OWO_SP fill:none,stroke:none,color:transparent
>     style EMP_SP fill:none,stroke:none,color:transparent
>     style WU fill:#1565c0,color:#fff,stroke:#0d47a1
>     style SW fill:#1565c0,color:#fff,stroke:#0d47a1
>     style PO fill:#1565c0,color:#fff,stroke:#0d47a1
>     style TD fill:#1565c0,color:#fff,stroke:#0d47a1
>     style TL fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style AL fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style DL fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style OM fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style CU fill:#2e7d32,color:#fff,stroke:#1b5e20
> ```

---

> **Key Areas for Restructuring**
>
> **4. Maintaining Naming Conventions and Standards**
>
> - Maintaining consistent naming conventions is critical when restructuring testware.
> - New test automation code and function libraries must align with existing standards
> - Example: Stick with camelCase (e.g., clickLoginButton()) if that's the team standard
> - Inconsistent naming makes code harder to read and maintain.

---

> **Key Areas for Restructuring**
>
> **5. Evaluating and Optimizing Existing Test Scripts**
>
> ```mermaid
> %%{init: {'themeVariables': {'quadrant1Fill': '#c8e6c9', 'quadrant2Fill': '#ffcdd2', 'quadrant3Fill': '#fff9c4', 'quadrant4Fill': '#bbdefb', 'quadrantPointFill': '#000000', 'quadrantPointTextFill': '#000000', 'quadrantXAxisTextFill': '#000000', 'quadrantYAxisTextFill': '#000000', 'quadrantTitleFill': '#000000', 'quadrant1TextFill': '#1b5e20', 'quadrant2TextFill': '#b71c1c', 'quadrant3TextFill': '#f57f17', 'quadrant4TextFill': '#0d47a1', 'quadrantInternalBorderStrokeFill': '#424242', 'quadrantExternalBorderStrokeFill': '#000000'}}}%%
> quadrantChart
>     title Test Script Evaluation Matrix
>     x-axis Low Business Value --> High Business Value
>     y-axis Low Maintenance Effort --> High Maintenance Effort
>     quadrant-1 "Refactor<br/>Worth improving"
>     quadrant-2 "Eliminate<br/>High effort, low return"
>     quadrant-3 "Monitor<br/>Keep but deprioritize"
>     quadrant-4 "Keep & Enhance<br/>Your best tests"
>     Legacy UI test: [0.25, 0.80]
>     Complex checkout test: [0.80, 0.80]
>     Old smoke test: [0.25, 0.20]
>     Critical API test: [0.80, 0.20]
> ```
>
> Action: Regularly review and categorize your tests using this matrix

---

> **Best Practices for Restructuring**
>
> - Document Everything - Note why changes were made (future you will thank yourself)
> - Use Version Control Effectively - Write clear commit messages (e.g., refactor: Update login tests to use new data-testid attributes)
> - Communicate with Your Team - Ensure everyone is aware of changes to shared code.
> - Test Your Tests - Run them multiple times to ensure stability (flaky tests are worse than none)
> - Plan for Rollback: Always be ready to revert if the restructuring doesn't work out.

---

> **Real-World Example**
>
> 1. First, we identified all the tests that directly accessed the database
> 2. We created an API layer for test data setup and verification
> 3. We gradually migrated tests from database access to API calls
> 4. We restructured our page objects to work with both the old and new UI during the transition
> 5. We implemented feature toggles in our tests to handle features being migrated
>
> Result: Tests more maintainable, faster, and found more bugs — testing through the same interfaces as real users. 

---

> **Conclusion**
>
> - Restructuring your automated testware to align with SUT (System Under Test) updates is about taking the opportunity to improve your architecture, consolidate your functions, and eliminate technical debt.
> - Remember:
>   - Always use an incremental approach
>   - Focus on high-value areas first
>   - Consolidate similar functions to reduce maintenance.
>   - Evolve your architecture thoughtfully
>   - Regularly evaluate your tests and eliminate the ones that aren't providing value.
>   - Maintain consistency in naming and coding standards.
>   - View SUT changes as an opportunity to make your test automation even better

---

### Transcript

"Restructure the automated testware to align with system under test updates.

In this video, we're going to talk about how to restructure our automated testware when the system under test gets updated.

I remember working on this e-commerce project where every few months the development team would completely redesign major parts of the application. And let me tell you, maintaining our test automation suite was like trying to hit a moving target. But over time, we developed strategies to handle these changes more effectively. And that's exactly what we're going to explore today.

Understanding the challenge.

So first, let's understand what we're dealing with here. When your system under test undergoes changes, those changes can ripple through your entire test automation solution. It's kind of like — imagine you have a perfectly organized closet, and then someone comes in and changes all the hangers from wooden to plastic ones. Sure, it's just hangers, but now you need to reorganize everything to make sure your clothes still fit properly.

Let me show you what this looks like in practice. As we can see in this diagram, when the system under test changes — maybe they've added a new feature or redesigned the UI — those changes don't just affect one thing. They ripple out and impact your test automation framework, your component libraries, your test scripts, and even your test environment configuration. And on the right side of the diagram, you can see all the potential issues that can arise, like tests failing unexpectedly, false positives, increased maintenance time, growing technical debt, etc. It can be quite overwhelming if you're not prepared for it.

The incremental approach.

Now here's the thing. When you need to make changes to align with SUT updates, you don't want to try to fix everything all at once. That's like trying to renovate your entire house in one weekend. It's just not going to work out well.

Instead, we need to adopt what we call a minimum viable product mindset. This means making changes incrementally, testing them thoroughly, and then moving on to the next set of changes.

Let me show you what this process looks like. As you can see in this process flow diagram, we have six key steps that form a cycle. We start by identifying the changes in the SUT. Then we prioritize which updates to make first, usually focusing on the critical tests with high-value features. Then — and this is key — we make small changes, test them with a limited scope, measure the impact, and only then run a full regression test.

Look at the example on the bottom. When a login page was redesigned, instead of trying to update everything at once, the team spread it out over four weeks. Each week they tackled a specific aspect, and by the end they had zero test failures and minimal disruption. That's the power of the incremental approach.

Key areas for restructuring.

Now let's dive into the specific areas where we need to focus our restructuring efforts. There are several key areas that typically need attention when the SUT changes.

Identifying changes in test environment components.

First up, we need to evaluate what changes and improvements need to be made. This might include changes to the testware itself, updates to custom function libraries, or even changes to the operating system. Each of these has an impact on how your test automation solution performs.

For example, I once worked on a project where the development team upgraded from Java 8 to Java 11. Now you might think, oh, it's just a Java version upgrade — how bad could it be? Well, some of our test libraries weren't compatible with Java 11, and we had to spend weeks updating dependencies and rewriting parts of our framework.

Increasing efficiency of core function libraries.

As your test automation solution matures, you'll discover new, more efficient ways to perform tasks. Maybe you'll find a better way to wait for elements to load. Or perhaps you'll discover a more reliable method for handling dynamic content. These improvements need to be incorporated into your core function libraries.

Let me show you an example of what this consolidation might look like. As we can see in this comparison, on the left side we have five different functions: one for clicking buttons by ID, another for clicking by class, another for XPath, and separate functions for links. That's a lot of code to maintain. But on the right side, after consolidation, we have just one flexible function that can handle all these scenarios.

The consolidated function takes two parameters: a locator — which could be of any type like id, class name, XPath, etc. — and an element type. This gives us a 70% reduction in lines of code and an 80% reduction in maintenance points. That's huge.

And the best part is: when the SUT changes and maybe switches from using IDs to data attributes, we only need to update our tests to use the new locator strategy. We don't need to create a whole new function.

Refactoring the test automation architecture.

Now, as your system under test evolves and matures, your test automation architecture needs to evolve with it. This is really important. You can't just bolt on new features as afterthoughts. You need to thoughtfully analyze and update your architecture.

Let me give you a real-world example. I worked with a team that started with a simple web application. Their test automation was straightforward — just Selenium WebDriver tests for the UI. But then the company decided to add a mobile app and an API layer. If they had just tried to squeeze mobile and API tests into their existing web-focused framework, it would have been a mess. Instead, they refactored their architecture to support multiple test types.

As we can see in this architecture evolution diagram, on the left we have the original architecture. It's pretty simple — just focused on web UI testing with Selenium WebDriver, page objects, and some test data. But look at what happens on the right when we evolve it to support multiple platforms.

The evolved architecture introduces an abstraction layer. This is crucial. This layer provides common interfaces that all test types can use, whether they're web tests, mobile tests, or API tests. Below that, we have different drivers for different platforms: Selenium for web, Appium for mobile, RestAssured for APIs, and maybe even Playwright for modern web applications.

Notice how we've also evolved from just page objects to object models that include page objects for web, screen objects for mobile, and endpoint objects for APIs. And at the bottom, we have common utilities that all test types can share — things like test data management, reporting, and configuration.

When the SUT adds a new feature or platform, we're ready for it.

Maintaining naming conventions and standards.

Now, this might seem like a small thing, but trust me, maintaining consistent naming conventions is super important when you're restructuring your testware.

As you introduce changes, you need to make sure that any new test automation code and function libraries stay consistent with your previously defined standards. For example, if your team must always use camelCase for method names like clickLoginButton, don't suddenly start using snake_case like click_login_button for the method name. It might seem trivial, but inconsistency makes your code harder to read and maintain. I've seen projects where different team members use different naming conventions, and it was a nightmare to work with.

Evaluating and optimizing existing test scripts.

Finally, we need to talk about evaluating your existing test scripts. This is where you really need to be honest about which tests are providing value, and which ones are just dead weight.

Let me show you a framework for evaluating your test scripts. As we can see in this evaluation matrix, we are plotting our tests based on two factors: maintenance effort on the vertical axis and business value on the horizontal axis. This creates four quadrants, each with a different action strategy.

In the top left quadrant we have tests that require high maintenance but provide low business value — like that legacy UI test that breaks every time someone sneezes near the code. These should be eliminated. They're just not worth the effort.

In the top right, we have high maintenance but high value tests — like a complex checkout test that covers critical business functionality but needs constant updates. These are candidates for refactoring. Maybe we can break them down into smaller, more maintainable pieces or use better locator strategies.

The bottom left contains low maintenance, low value tests — that old smoke test that still runs but doesn't really tell us much anymore. We can keep running it, but don't spend time improving it.

And finally, the bottom right quadrant. This is where your best tests live: low maintenance but high value. These are the tests you want to keep and even enhance — like a critical API test that runs reliably and catches real issues. That's the type of test that's gold.

Best practices for restructuring.

Now, before we wrap up, let me share some best practices I've learned over the years.

Document everything. When you make changes, document why you made them. Six months from now, you'll thank yourself when you're trying to remember why you refactored that particular function.

Use version control effectively. Create meaningful commit messages. Instead of \"updated tests\" as your commit message, write something like: refactor: update login tests to use new data-testid attributes after UI redesign.

Communicate with your team. If you're restructuring shared code, make sure everyone knows about it. Nothing is worse than someone spending hours debugging because they didn't know you changed the core function.

Test your tests after restructuring. Run your tests multiple times to ensure they're stable. Flaky tests are worse than no tests at all.

Plan for rollback. Sometimes, despite our best efforts, our restructuring doesn't work out. Have a plan to roll back your changes if needed.

Real-world example.

Let me share one more real-world example. I worked with an e-commerce company that decided to migrate from a monolithic architecture to microservices. Their test automation was tightly coupled to the monolith, with tests directly accessing the database and making assumptions about the internal structure.

The restructuring took six months, but here's what we did. First, we identified all the tests that directly accessed the database. We created an API layer for test data setup and verification. We gradually migrated tests from database access to API calls. We restructured our page objects to work with both the old and new UI. During the transition, we implemented feature toggles in our tests to handle features being migrated.

The result? When the migration was complete, our tests were more maintainable, faster, and actually found more bugs — because they were testing through the same interfaces that real users would use.

So to wrap up: restructuring your automated testware to align with system under test updates is not just about making your tests work again — it's about making them better. It's about taking the opportunity to improve your architecture, consolidate your functions, and eliminate technical debt.

Remember: always use an incremental approach. Don't try to fix everything at once. Focus on high-value areas first. Consolidate similar functions to reduce maintenance. Evolve your architecture thoughtfully, not as an afterthought. Regularly evaluate your tests and eliminate the ones that aren't providing value. Maintain consistency in naming and coding standards. And most importantly, view SUT changes not as a burden, but as an opportunity to make your test automation even better.

In our next video, we'll explore more opportunities for using test automation tools beyond just testing."
