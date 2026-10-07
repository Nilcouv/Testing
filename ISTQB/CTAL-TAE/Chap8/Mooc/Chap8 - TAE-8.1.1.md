# Mooc

## Discover Opportunities for Improving Test Cases Through Data Collection and Analysis.

### Screen

> **Test Histograms**
>
> - Test automation generates a ton of data that we can leverage to make our tests better
> - Most teams aren't taking full advantage of this goldmine of information
> - A "test histogram" is simply a visual representation of test data that helps us identify patterns and trends, such as:
>   - How many tests passed or failed
>   - How long each test took to run
>   - What types of errors occurred most frequently
>   - Which tests are the most "fragile" (meaning they fail inconsistently)
>
> ```mermaid
> %%{init: {'xyChart': {'showLegend': true}, 'themeVariables': {'plotColorPalette': '#2e7d32, #c62828'}}}%%
> xychart-beta
>     title "Test Execution Data"
>     x-axis ["Week 1", "Week 2", "Week 3", "Week 4", "Week 5", "Week 6", "Week 7"]
>     y-axis "Number of test cases" 0 --> 120
>     bar "Passed tests" [60, 70, 80, 90, 95, 100, 105]
>     bar "Failed tests" [60, 50, 40, 30, 25, 20, 15]
> ```
>
> - We're tracking passed tests in green and failed tests in red over a seven-week period.
> - The total number of tests is fixed each week (combined height of the green and red bars).
> - The number of failed tests is decreasing over time.
> - The pass rate is improving significantly from week to week.
>
> With this data, a Test Automation Engineer can make data-driven decisions about which test cases to maintain, improve, or possibly retire.
>
> Real-World Example:
>
> - We noticed that about 14% of our tests were failing intermittently.
> - Most of these failures happened because of timing issues — our tests weren't waiting long enough for certain elements to appear on the page.
> - By identifying this pattern, we were able to refactor those specific test cases, and our failure rate dropped to under 3%.

---

> **Artificial Intelligence and Machine Learning**
>
> - Artificial Intelligence and Machine Learning are becoming increasingly accessible in test automation.
> - Modern test automation tools are beginning to incorporate AI and ML capabilities
> - Self-healing tests: automatically updating locators when UI elements change.
> - Suggesting improvements to test scripts
> - Visual testing that can detect unintended UI changes.
>
> With AI-powered self-healing, the tool might automatically identify that the button still exists but with a slightly different selector, and update your test accordingly.
>
> ```mermaid
> flowchart LR
>     OT["**Original Test**<br/>find button by #submit-button"]
>     CU["**Changed UI**<br/>button id changed to: #form-submit"]
>     UT["**Update Test**<br/>find button by #form-submit"]
>     WAf["**Without AI: Test Fails**<br/>Element not found: #submit-button"]
>     AA["**AI Analysis**<br/>locator has changed<br/>Suggesting new locator"]
>     WAp["**With AI: Test Passes**<br/>Element found with self-healing locator"]
>
>     OT --> CU --> UT
>     WAf ~~~ AA --> WAp
>     CU --> AA
>     WAp --> UT
>
>     style OT fill:#1565c0,color:#fff,stroke:#0d47a1
>     style CU fill:#f9a825,color:#000,stroke:#f57f17
>     style WAf fill:#c62828,color:#fff,stroke:#b71c1c
>     style AA fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style WAp fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style UT fill:#2e7d32,color:#fff,stroke:#1b5e20
> ```
>
> - The original test looks for a button with the ID #submit-button.
> - The UI changes and the button ID becomes #form-submit, which would normally cause our test to fail.
> - With AI-assisted testing, the tool analyzes what changed in the UI, suggests a new locator, and updates the test to use #form-submit instead.
> - The result is that our test passes even though the UI changed.
>
> Real-World Example:
>
> - They saw about a 40% reduction in test maintenance efforts.
> - Instead of constantly updating selectors manually, the team could focus on writing new tests and improving existing functionality.
> - Some advanced tools can analyze test execution data to predict which tests are most likely to find bugs in the future.
> - This helps teams prioritize which tests to run first, especially when time is limited.

---

> **Schema Validation**
>
> - Schema validation is particularly useful when testing APIs or working with databases.
> - It allows us to verify that the structure and format of data we're working with matches what we expect.
> - Without schema validation, we'd have to write individual assertions for each of these checks, which would be tedious and error-prone.
>
> ```mermaid
> flowchart LR
>     ARq["**API Request**<br/>GET /users/123"]
>     ARs["**API Response**<br/>#123;<br/>#quot;id#quot;: 123,<br/>#quot;name#quot;: #quot;John Doe#quot;,<br/>#quot;email#quot;: #quot;john@example.com#quot;,<br/>#quot;role#quot;: #quot;admin#quot;<br/>#125;"]
>     JS["**JSON Schema**<br/>#123;<br/>#quot;type#quot;: #quot;object#quot;,<br/>#quot;required#quot;: #91;#quot;id#quot;, #quot;name#quot;, #quot;email#quot;#93;,<br/>#quot;properties#quot;: #123;<br/>#quot;id#quot;: #123; #quot;type#quot;: #quot;number#quot; #125;,<br/>#quot;name#quot;: #123; #quot;type#quot;: #quot;string#quot; #125;,<br/>#quot;email#quot;: #123; #quot;type#quot;: #quot;string#quot;, #quot;format#quot;: #quot;email#quot; #125;<br/>#125;<br/>#125;"]
>     SV["**Schema Validation**<br/>Compares response against expected schema"]
>     VP["**Validation Passes**<br/>Required fields present<br/>correct data types"]
>     BV["**Bonus Validation**<br/>role field accepted<br/>not in schema but allowed"]
>     SVE["**Schema Violation Example**<br/>If email were invalid:<br/>Format validation failed"]
>
>     ARq --> ARs
>     ARs --> JS
>     ARs --> SV
>     JS --> SV
>     SV --> VP
>     SV --> BV
>     SV --> SVE
>
>     style ARq fill:#1565c0,color:#fff,stroke:#0d47a1
>     style ARs fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style JS fill:#f9a825,color:#000,stroke:#f57f17
>     style SV fill:#6a1b9a,color:#fff,stroke:#4a148c
>     style VP fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style BV fill:#2e7d32,color:#fff,stroke:#1b5e20
>     style SVE fill:#c62828,color:#fff,stroke:#b71c1c
> ```
>
> 1. We make an API request (GET /users/123).
> 2. We receive a JSON response with user data.
> 3. We have a JSON schema that defines the expected structure of the response.
> 4. Our validation process compares the actual response against this schema.
> 5. The validation result indicates whether the response meets our expectations.
>
> - The response must be a JSON object.
> - The object must have "id", "name", and "email" fields.
> - "id" must be a number.
> - "name" must be a string.
> - "email" must be a string in email format.
> - Our response passes validation because it has all required fields with the correct data types.
>
> Example:
>
> - Initially, we had dozens of individual assertions in each test case to verify that fields like product ID, name, price, etc. were present and had the correct type.
> - When we switched to schema validation, we were able to replace all those individual assertions with a single schema validation check.
> - This made our tests more concise and more robust.
> - When the API was updated to include a new field, our tests didn't break because the schema allowed for additional fields.
>
> Another advantage of schema validation is that when a test fails, the error message clearly indicates exactly what went wrong.
> Example: "Property 'price' is required but missing" or "Expected type number for field 'price', but got string."

---

> **Conclusion**
>
> - Data collection and analysis:
>   - Test histograms provide visual representations of test data, helping us identify trends and problematic test cases.
>   - AI and ML techniques can help with things like self-healing tests and identifying patterns in test failures.
>   - Schema validation allows us to efficiently verify the structure and format of data in our tests.
> - We should be actively collecting and analyzing data from those tests to continuously improve them.
> - Teams that implement these approaches typically experience:
>   - Reduced test maintenance effort
>   - Fewer false positives
>   - Better detection of real issues
>   - More confidence in their automated tests

---

### Transcript

"Discover opportunities for improving test cases through data collection and analysis.

Test histograms.

One of the cool things about test automation is that it generates a ton of data we can leverage to make our tests better. Think about it. Every test run gives us information about execution times, pass/fail rates, error messages, and so much more. And honestly, most teams aren't taking full advantage of this goldmine of information.

So let's look at different approaches to collect and analyze this data, to discover opportunities for improving our test cases. Starting with something called a test histogram.

Now, if you've never heard of this before, it's simply a visual representation of test data that helps us identify patterns and trends. A test histogram basically shows the distribution of test results over time or across different test runs. This can include things like how many tests passed or failed, how long each test took to run, what types of errors occur most frequently, or which tests are most fragile, meaning they fail inconsistently.

Let me show you what a basic test histogram might look like. As we can see in this chart, we're tracking passed tests in green and failed tests in red over a seven-week period. This type of visualization immediately shows us a couple of important trends. One, the total number of tests is fixed each week, which is the combined height of the green and red bars. Two, the number of failed tests is decreasing over time. And three, the pass rate is improving significantly from week to week.

Now here is where it gets really useful for improving our test cases. With this data, a test automation engineer can identify which specific test cases are consistently failing and prioritize fixing those. They can see if certain test cases fail after specific changes to the system under test. They can track which test cases are fragile, and they can make data-driven decisions about which test cases to maintain, improve, or possibly retire.

Let me share a quick real-world example on a project I worked on last year. We used a test histogram to track our automated UI tests, and we noticed that about 15% of our tests were failing intermittently. When we dug into the data, we found that most of these failures happened because of timing issues. Our tests weren't waiting long enough for certain elements to appear on the page. By identifying this pattern, we were able to refactor those specific test cases to use more reliable waiting mechanisms. And our failure rate dropped to under 3%.

Artificial intelligence and machine learning.

All right. So the next approach I want to talk about is using artificial intelligence and machine learning to help improve our test cases. Now, I know that may sound fancy or complex, but it's becoming increasingly accessible. Modern test automation tools are beginning to incorporate AI and ML capabilities to help us with things like self-healing tests, automatically updating locators when UI elements change, identifying patterns in test failures, suggesting improvements to test scripts, and visual testing that can help detect unintended UI changes.

For example, let's say you have a test that finds a button on a web page using a specific CSS selector. If the developers change the structure of the page, that selector might no longer work, causing your test to fail. With AI-powered self-healing, the tool might automatically identify that the button still exists, but with a slightly different selector, and update your test accordingly.

Here's what this might look like conceptually. As we can see in this diagram, we've got a process flow showing how AI can help with self-healing tests. On the left, we start with our original test that looks for a button with the ID #submit-button, but then the UI changes and the button ID becomes #form-submit, which would normally cause our test to fail. In the traditional approach, on the bottom left, the test simply fails with element not found. But with AI-assisted testing — the right-side flow — the tool analyzes what changed in the UI, suggests a new locator, and updates the test to use #form-submit instead. The result is that our test passes even though the UI changed.

I worked with a team recently that implemented this kind of AI-powered self-healing for their UI tests, and they saw about a 40% reduction in test maintenance efforts. Instead of constantly updating selectors manually, the team could focus on writing new tests and improving existing functionality.

One more thing about AI and test automation. Some advanced tools can also analyze test execution data to predict which tests are most likely to find bugs in the future. This helps teams prioritize which tests to run first, especially when time is limited.

Schema validation.

Now let's talk about another powerful technique for improving our test cases: schema validation. Schema validation is particularly useful when testing APIs or working with databases. Basically, it allows us to verify that the structure and format of data we're working with matches what we expect.

For example, when testing a REST API, we might want to verify that a response includes all the required fields, that each field has the correct data type, and that there are no unexpected fields. Without schema validation, we'd have to write individual assertions for each of these checks, which would be tedious and error-prone.

Here's a visualization of how schema validation works in API testing. As we can see in this diagram, schema validation involves several components. First, we make an API request — in this case a GET request to /users/123. We receive a JSON response with user data. We have a JSON schema that defines the expected structure of the response. Our validation process compares the actual response against this schema. The validation results indicate whether the response meets our expectations.

In this example, the schema requires that the response must be a JSON object. The object must have id, name, and email fields. The id must be a number. The name must be a string, and the email must be a string in email format. Our response passes validation because it has all required fields with the correct data types. The schema also allows additional fields that aren't explicitly defined, like role in this case.

I'll share a concrete example from my experience. I worked on a project where we were testing an e-commerce API that returned product information. Initially, we had dozens of individual assertions in each test case to verify that fields like product ID, name, price, etc. were present and had the correct types. When we switched to schema validation, we were able to replace all those individual assertions with a single schema validation check. Not only did this make our tests more concise, but it also made them more robust. For instance, when the API was updated to include a new field, our tests didn't break because the schema allowed for additional fields.

Another big advantage of schema validation is that when a test fails, the error message clearly indicates exactly what went wrong. Instead of a generic assertion-failed message, you might get something like "Property 'price' is required but missing" or "Expected type number for field 'price' but got string."

Putting it all together.

So we've covered three powerful approaches for improving our test cases through data collection and analysis. Test histograms provide visual representations of test data, helping us identify trends and problematic test cases. AI and ML techniques can help with things like self-healing tests and identifying patterns in test failures. And schema validation helps us efficiently verify the structure and format of data in our tests.

The key takeaway here is that we shouldn't just be running our automated tests — we should be actively collecting and analyzing data from those tests to continuously improve them. This creates a virtuous cycle where our tests become more reliable, more efficient, and more effective at catching real issues.

In my experience, teams that implement these approaches typically see reduced test maintenance effort, fewer false positives, better detection of real issues, and more confidence in their automated tests.

And remember, you don't have to implement all of these approaches at once. Start with one, like creating simple test histograms to track pass/fail rates, and then gradually expand your data collection and analysis capabilities as you get more comfortable.

In the next video, we'll explore how to analyze the technical aspects of a deployed test automation solution and provide recommendations for improvement."
