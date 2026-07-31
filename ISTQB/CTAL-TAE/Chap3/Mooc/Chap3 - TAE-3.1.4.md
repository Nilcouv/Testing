# Mooc

## Apply Different Approaches For Automating Test Cases

### Screen

> **Introduction to Test Automation Approaches**
>
> Multiple approaches exist (beyond simple scripting)
>
> **Trade-offs:** Simplicity vs. long-term maintainability
>
> Evolution from basic to advanced techniques

---

> **Capture/Playback**
>
> Records manual actions --> replays them (e.g., Selenium IDE)
>
> **Types:**
> - no-code (hidden scripts)
> - Low-code (editable scripts)

---

> **Capture/Playback**
>
> **Pros**
>
> - It's incredibly easy to get started - you just click on "record" and test normally
> - You don't need any programming knowledge
> - You can create automated tests very quickly
>
> **Cons**
>
> - These tests are usually very fragile -- if anything changes in your application, the tests break
> - It's hard to scale this approach as your application grows
> - When tests fail, it can be difficult to understand why
> - You need the application to be available and working when you create the tests.

---

> **Linear Scripting**
>
> - Linear scripting = Step-by-step scripts without reuse (e.g., raw WebDriver code).
> - No custom libraries/functions -- like writing a story without chapters.
> - Differs from capture/playback; You write the code manually.
> - Often starts as modified capture/playback scripts.
>
> **Example:**
>
> ```python
> # Open the browser
> driver = webdriver.Chrome()
> 
> # Go to the website
> driver.get("https://www.example.com")
> 
> # Find the username field and type a username
> username_field = driver.find_element_by_id("username")
> username_field.send_keys("testuser")
> 
> # Find the password field and type a password
> password_field = driver.find_element_by_id("password")
> password_field.send_keys("password123")
> 
> # Click on the login button
> login_button = driver.find_element_by_id("login_button")
> login_button.click()
> 
> #Check if login was successful
> assert "Welcome" in driver.page_source
> ```

---

> **Linear Scripting**
>
> **Pros**
>
> - It's relatively easy to get started - definitely easier than some of the more advanced approaches
> - The scripts are straightforward to understand because they follow the test step by step
> - You have more control compared to capture/playback because you're writing the code
>
> **Cons**
>
> - There's a lot of duplication - if multiple tests need to log in, you're copying and pasting that code
> - Maintenance becomes a huge issue as your test suite grows.
> - When the application changes, you might need to update the code in multiple places.
> - You need some programming knowledge, though not advanced skills.

---

> **Structured Scripting**
>
> - Professional approach with reusable elements: libraries, steps, user journeys.
> - Reusable functions/methods (e.g., login() function)
> - Requires more programming knowledge but improves maintainability.
> - Changes (e.g., login page) update in one place, not every test.
>
> **Example:**
> 
> ```python
>
> def login(driver, username, password):
>     username_field = driver.find_element_by_id("username")
>     username_field.send_keys(username)
>     
>     password_field = driver.find_element_by_id("password")
>     password_field.send_keys(password)
>     
>     login_button = driver.find_element_by_id("login_button")
>     login_button.click()
> 
> # Now our tests become:
> driver = webdriver.Chrome()
> driver.get("https://www.example.com")
> login(driver, "testuser", "password123")
> assert "Welcome" in driver.page_source
> ```

---

> **Structured Scripting**
>
> **Pros**
>
> - Much better maintainability - changes to the application only require update in one place
> - Reusability across tests reduces duplication
> - Easier to understand and troubleshoot
> - More scalable as your test suite grows
>
> **Cons**
>
> - It requires solid programming knowledge
> - There's an initial time investment to set up the structure and libraries
> - More complex architecture to understand for new team members

---

> **TDD (Test-Driven Development)**
>
> - Development approach that results in automated tests
> - Revolutionary concept: Write tests BEFORE writing the code they test
>
> **Red-Green-Refactor cycle:**
> 
> - **Red** : Write a failing test for the functionality you want to develop
> - **Green** : Write a minimum code necessary to make the test pass
> - **Refactor** : Clean up the code while ensuring the test still passes
>
> **Example:**
>
> ```python
> # Red phase
> def test_email_validation():
>    # This test will initially fail because the validate_email function doesn't exist yet
> 
>    assert validate_email("test@example.com") == True
>    assert validate_email("not-an-email") == False
>    assert validate_email("missing@ltd") == False
>    assert validate_email("") == False
> 
> # Green phase
> def validate_email(email):
>    # Simple implementation that checks for @ symbol and a dot in the domain
>   if not email:
>        return False
>   return "@" in email and "." in email.split("@")[1] if len(email.split("@")) > 1 else False
> 
> # Refactor phase
> import re
> 
> def validate_email(email):
>   # More robust implementation using regular expressions
>   if not email:
>       return False
>
>   pattern = r'^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$'
>   return bool(re.match(pattern, email))
> ```

---

> **TDD (Test-Driven Development)**
>
> **Pros**
>
> - **Improves code quality and structure:** When you write tests first, you naturally design more modular, testable code
> - **Enhances testability from the start:** Your code is inherently testable because that's how it was designed
> - **Achieves better code coverage:** You're writing tests for all functionality as you go
> - **Reduces defects propagating to higher test levels:** You catch issues at the unit level before they become system-level problems.
> - **Improves communication:** Writing tests first forces clarity about what the code should do.
>
> **Cons**
>
> - **Learning curve:** It takes time to get comfortable with the TDD workflow - it feels backward at first!
> - **Can feel slower initially:** Writing test before code seems to slow down development at first, though it often saves time later by reducing bugs.
> - **Risk of false confidence:** If your tests don't cover important scenarios, TDD can give you a false sense of security

---

> **DDT (Data-Driven Testing)**
>
> - Separates test logic from data
>
> **Example:**
>
> ```python
> import pytest
> 
> # Test data - username, password, expected_result
> test_data = [
> ("testuser", "password123", "success"),
> ("testuser", "wrongpassword", "failure"),
> ("invaliduser", "password123", "failure"),
> ("", "", "failure"),
> ("testuser<script>", "password123", "failure") # Testing XSS attempt
> ]
>
> @pytest.mark.parametrize( "username,password, expected_result", test_data)
> def test_login(username, password, expected_result, setup_browser):
> driver = setup_browser
>
> # Navigate to login page
> driver.get("https://www.example.com/login")
>
> # Enter credentials
> username_field = driver.find_element_by_id( "username")
> username_field.send_keys(username)
>
> password_field = driver.find_element_by_id("password")
> password_field.send_keys(password)
> 
> # Click login button
> login_button = driver.find_element_by_id("login_button")
> login_button.click()
> 
> # Verify result
> if expected_result == "success":
> assert "Welcome" in driver.page_source, f"Login should succeed with{username}/{password}"
> else:
> assert "Error" in driver.page_source, f"Login should fail with{username}/{password}"
> ```
> 
> Usually data comes from a csv file
> ```python
> import pytest
> import csv
> 
> def load_test_data():
>     data = []
>     with open('login_test_data.csv', 'r') as f:
>         reader = csv.reader(f)
>         next(reader) # Skip header row
>         for row in reader:
>             username, password, expected_result = row
>             data.append( (username, password, expected_result))
>     return data
> 
> @pytest.mark.parametrize( "username, password, expected_result", load_test_data())
> def test_login(username, password, expected_result, setup_browser):
>     # Same test code as before
>     # ..
> ```
> 
> csv content would look like:
> 
> ```csv
> username, password, expected_result
> testuser, password123, success
> testuser, wrongpassword, failure
> invaliduser,password123, failure
> ,,failure
> testuser<script>,password123, failure
> ```

---

> **DDT (Data-Driven Testing)**
>
> **Pros**
>
> - **Reduces code duplication:** You write the test logic once and reuse it with different data
> - **Makes test maintenance easier:** When the application changes, you only need to update one test script.
> - **Enables non-programmers to contribute:** Test analysts can add new test cases by adding data to a spreadsheet
> - **Improves test coverage:** It's easy to test more scenarios without writing more code.
> - **Separates concerns:** Test logic and test data are kept separate, following good software design principles.
>
> **Cons**
>
> - **Data management:** You need to maintain your test data carefully, which can become a project in itself.
> - **Setup complexity:** Setting up the data-driven framework takes some initial effort.
> - **Debugging can be harder:** When a test fails, you need to figure out which data set caused the failure.

---

> **KDT (Keyword-Driven Testing)**
>
> In this approach:
>
> - Define high-level keywords that represent actions or verifications in your application.
> - Tests become a sequence of these keywords with associated data.
> - Pre-defined actions like "login", "SearchProduct", "AddToCart"
>
> **Example:**
> 
> ```robotframework
> *** Settings ***
> Documentation       Example of keyword-driven testing with Robot Framework
> Library             SeleniumLibrary
> 
> *** Variables ***
> ${URL}             https://www.example.com
> ${BROWSER}         chrome
> ${USERNAME}        testuser
> ${PASSWORD}        password123
> 
> *** Test Cases ***
> Valid Login Test
>     Open Browser To Login Page
>     Input Username  ${USERNAME}
>     Input Password  ${PASSWORD}
>     Submit Credentials
>     Welcome Page Should Be Open
>     [Teardown]  Close Browser
> 
> Invalid Password Test
>     Open Browser To Login Page
>     Input Username  ${USERNAME}
>     Input Password  Invalid
>     Submit Credentials
>     Error Message Should Be Displayed
>     [Teardown]  Close Browser
> 
> *** Keywords ***
> Open Browser To Login Page
>     Open Browser        ${URL}  ${BROWSER}
>     Maximize Browser Window
>     Page Should Contain Element     id:login-form
> 
> Input Username
>     [Arguments]     ${username}
>     Input Text      id:username     ${username}
> 
> Input Password
>     [Arguments]     ${password}
>     Input Text      id:password     ${password}
> 
> Submit Credentials
>     Click Button    id:login-button
> 
> Welcome Page Should Be Open
>     Page Should Contain     Welcome to your account
>     Title Should Be     User Dashboard
> 
> Error Message Should Be Displayed
>     Page Should Contain     Invalid username or password
>     Page Should Contain Element     class:error-message
> ```
>
> - The Settings section sets up the libraries we need.
> - The Variables section defines common values we'll use.
> - The Test Cases section contains our actual tests, which are sequences of keywords.
> - The Keywords section defines custom keywords that our tests use.

---

> **KDT (Keyword-Driven Testing)**
>
> **Real-World Example**
>
> - Worked at a company where business analysts could write tests
> 
> ```robotframework
> *** Test Cases ***
> Customer Can Purchase Auto Insurance
>     Login As        john.doe@example.com    password123
>     Navigate To     Auto Insurance
>     Select Coverage Type    Comprehensive
>     Enter Vehicle Details   Honda   Accord  2020
>     Enter Driver Information    John    Doe     01/15/1985  No Claims
>     Calculate Premium
>     Premium Should Be Between   $800    $1200
>     Select Payment Plan     Monthly
>     Complete Purchase
>     Confirmation Should Be Displayed
>     Policy Number Should Be Generated
> ```

---

> **KDT (Keyword-Driven Testing)**
>
> **Pros**
>
> - **Business-readable tests:** Tests are expressed in language that business stakeholders can understand
> - **Reusable components:** Keywords can be reused across many test cases.
> - **Non-technical participation:** Business analysts and manual testers can contribute to automation
> - **Framework for collaboration:** Provides a common language between technical and non-technical team members.
> - **Separation of concerns:** Implementers focus on keywords; test designers focus on test flows
>
> **Cons**
>
> - **Initial setup effort:** Creating a robust keyword library takes time.
> - **Maintenance overhead:** As the application changes, keywords need to be updated.
> - **Finding the right granularity:** Keywords that are too specific aren't reusable; keywords that are too general aren't meaningful.
> - **Learning curve:** New team members need to learn the available keywords.

---

> **BDD (Behavior-Driven Development)**
>
> - BDD is an extension of Test-Driven Development that focuses on the behavior of the system from the user's perspective
> - "Given-When-Then" natural language scenarios
>
> **Example**
> 
> - BDD scenario for login:
> 
> ```gherkin
> Feature: User Login
>     As a registered user
>     I want to log in to the application
>     So that I can access my account
> 
> Scenario: Successful login with valid credentials
>     Given I am on the login page
>     When I enter "testuser" as username
>     And I enter "password123" as password
>     And I click the login button
>     Then I should see the welcome message
> ```
>
> Scenario is mapped to the following code:
>
> ```python
> 
> @given("I am on the login page")
> def navigate_to_login_page(context):
>     context.driver.get("https://www.example.com")
> 
> @when('I enter "{username}" as username' )
> def enter_username(context, username):
>     username_field = context.driver.find_element_by_id( "username")
>     username_field.send_keys(username)
> 
> # And so on for the other steps
> ```

---

> **BDD (Behavior-Driven Development)**
>
> **Pros**
>
> - It improves communication between technical and non-technical team members
> - Scenarios serve as both documentation and executable tests
> - It focuses on business value and user behavior
> - It works well with Agile methodologies
>
> **Cons**
>
> - You still need additional test cases for edge cases and negative scenarios
> - Many teams misunderstand BDD as just a way to write tests in natural language
> - Implementing and maintaining the step definitions can be complex
> - Debugging can be challenging when scenarios get complex

---

> **Comparison of Approaches**
>
> | Category | Low | Medium | High |
> |---|---|---|---|
> | Entry Barrier | Capture/Playback, Linear Scripting | Structured Scripting, Data-Driven Testing | Test-Driven Development, Keyword-Driven Testing, Behavior-Driven Development |
> | Maintainability | Capture/Playback, Linear Scripting | Structured Scripting, Data-Driven Testing | Test-Driven Development, Keyword-Driven Testing, Behavior-Driven Development |
> | Scalability | Capture/Playback, Linear Scripting | Structured Scripting | Data-Driven Testing, Test-Driven Development, Keyword-Driven Testing, Behavior-Driven Development |
> | Business Involvement | Capture/Playback, Linear Scripting, Structured Scripting | Data-Driven Testing, Test-Driven Development | Keyword-Driven Testing, Behavior-Driven Development |

---

> **Evolution of Approaches**
>
> Each approach solves limitations of previous methods
> 
> Progressions : Linear --> Structured --> Data-Driven --> Keyword-Driven
>
> Teams Typically evolve approaches as automation maturity grows

---

> **Real-World Combination**
>
> **TDD:** Unit Tests
>
> **Structured + DDT:** API tests
>
> **KDT:** Common UI flows
>
> **BDD:** Critical user journeys
>
> The combination allowed us to leverage the strengths of each approach where it made the most sense

---

> **Conclusion**
>
> 1. Different approaches for automating test cases
> 2. The best strategy often involves using a combination of these approaches
>
> Those approaches are:
>
> - Capture/playback: Easy to start but hard to maintain
> - Linear Scripting: Simple programming but prone to duplication
> - Structured Scripting: Reusable components improve maintainability
> - Test-Driven Development: Write Tests before code for better quality
> - Data-Driven Testing: Separate test logic from test data
> - Keyword-Driven Testing: Use high-level keywords for business-readable test
> - Behavior-Driven Development: Natural language scenario bridge technical and business worlds.

### Transcript

"Apply different approaches for automating test cases.

Let's take a look at the different approaches you can use when automating your test cases.

You know, when I first started in test automation, I thought there was just one way to do it write

some code that clicks buttons and fills in fields, right?

But actually there are several different approaches, each with their own strengths and weaknesses.

Some are really simple to get started with, but might cause headaches later, while others take more

effort upfront, but can save you tons of time in the long run.

Let's start with the simplest approach capture playback.

So what exactly is capture playback?

Well, it's pretty much what it sounds like.

You use a tool that records your actions as you manually test the application, and then it can play

those actions back automatically.

It's kind of like recording a video of yourself testing, except the tool actually creates a script

that can repeat your exact actions.

There are tools out there that can do this, like Selenium IDE or Katalon recorder.

These tools watch what you do, click in buttons, type in text selecting options, and then generate

code to repeat those actions.

These tools come in two flavors.

No code tools that don't show you the generated code.

They just record and playback low code tools that show you the code they generate and you can modify

it if needed.

Let me share a quick real world example.

I once worked with a client who needed to quickly automate about 50 test cases for a website before

a major release.

We didn't have much time, so we used a capture playback tool to record all the test cases in just a

couple of days.

It was super fast to get up and running.

Now, the pros of this approach are pretty clear.

It's incredibly easy to get started.

You literally just click record and test normally.

You don't need any programming knowledge.

You can create automated tests very quickly.

But and this is a big but there are some serious cons.

These tests are usually very fragile.

If anything changes in your application, the tests break.

It's hard to scale this approach as your application grows.

When tests fail, it can be difficult to understand why you need the application to be available and

working when you create the tests.

I remember with that client I mentioned things were great for the first release, but when the second

release came around with some UI changes, almost all of our recorded tests broke and we had to rerecord

many of them.

So while capture playback is a good way to dip your toes into automation, or for very stable applications

with few changes, it's usually not the best long term strategy.

Linear scripting.

Linear scripting is basically where you write test cases line by line, without using any custom libraries

or functions.

It's like writing a story from start to finish without organizing it into chapters or sections.

The difference between this and capture playback is that you're actually writing the code yourself,

rather than having a tool generate it for you.

Though to be honest, many people start with capture playback and then modify the generated scripts,

which essentially turns into linear scripting.

Here's a simple example of what linear scripting might look like written in selenium WebDriver.

As you can see, it's just a straight through script with no reusable components or functions.

The pros of linear scripting are.

It's relatively easy to get started, definitely easier than some of the more advanced approaches.

The scripts are straightforward to understand because they follow the test step by step.

You have more control compared to capture playback because you're writing the code.

But again, there are significant cons.

There's a lot of duplication.

If multiple tests need to log in, you're copying and pasting that code.

Maintenance becomes a huge issue as your test suite grows.

When the application changes, you might need to update the same code in multiple places.

You need some programming knowledge, though, not advanced skills.

I once inherited a project with about 200 linear scripts, and when the login page was redesigned,

I had to manually update the login sequence in almost every single script.

It took days of tedious work that could have been avoided with a more structured approach.

Linear scripting is a step up from the capture playback approach, but might not be ideal for long term,

large scale test automation projects.

Structured scripting.

Now we're starting to get into the more professional approaches with structured scripting.

Structured scripting introduces the concept of reusable elements, test libraries, test steps, and

user journeys that can be used across multiple test scripts.

This approach requires more programming knowledge but creates much more maintainable test code.

The key difference here is that you break down your tests into functions or methods that can be reused.

For example, instead of writing the login sequence in every test, you create a login function that

any test can call.

Here's how our previous example might look with structured scripting.

See how much cleaner it is now?

If the login page changes, we only need to update the login function in one place, not in every test.

The pros of structured scripting are significant.

Much better maintainability.

Changes to the application only require updates in one place.

Reusability across tests reduces duplication.

Easier to understand and troubleshoot.

More scalable as your test suite grows.

The cons are.

It requires solid programming knowledge.

There is an initial time investment to set up the structure and libraries.

More complex architecture to understand for new team members.

In my experience, structured scripting is where you start to see real returns on your automation investment.

I recall working on an e-commerce project where we had dozens of tests that all needed to add products

to the cart.

By creating a reusable add to cart function.

We save countless hours of maintenance when the cart functionality was updated.

This is typically the minimum level of organization I'd recommend for any serious test automation project.

Test driven development.

Now let's shift gears a bit and talk about test driven development or TDD for short.

TDD is actually a development approach rather than strictly a test automation approach, but it results

in automated tests.

The concept is pretty revolutionary.

You write your tests before you write the code you're testing.

The TDD cycle is often described as red green, refactor red.

Write a failing test for the functionality you want to develop.

Green.

Write the minimum code necessary to make the test pass and refactor.

Clean up the code while ensuring the test still passes.

Let's say your team needs to develop a function to validate email addresses.

With TDD, you'd start by writing the test like this.

This test would initially fail because the validate email function doesn't exist yet.

That's the red phase.

You have a failing test that clearly defines what you want your code to do.

Next, you'd write the simplest implementation that makes the test pass.

Now, when you run the tests, it passes.

That's the green phase.

You've written just enough code to satisfy the test requirements.

Finally, you might refactor the code to make it robust while ensuring the test still passes.

That's the refactor phase.

You improve the code quality without changing this behavior.

The beauty of TDD is that it forces you to think about what you want your code to do before you write

it.

It's like creating a specification in the form of tests.

I remember working on a project where we used TDD to develop a critical medication dosage calculator

before writing any calculation logic.

We wrote tests for all the edge cases, pediatric doses, elderly patients, renal impairment adjustments,

and etc..

The resulting code was incredibly robust because we had considered all these scenarios up front.

The pros of TDD are really compelling.

It improves code quality and structure.

When you write your tests first, you naturally design more modular, testable code.

It enhances testability from the start.

Your code is inherently testable because that's how it was designed.

We can achieve better code coverage.

You're writing tests for all functionality as you go.

It reduces defects propagating to higher test levels.

You catch issues at the unit level before they become system level problems.

It improves communication.

Writing tests first forces clarity about what the code should do, but there are some challenges to

learning curve.

It takes time to get comfortable with the TDD workflow.

It feels backward at first.

It can feel slower initially.

Writing tests before code seems to slow down development at first, though it often saves time later

by reducing bugs.

Risk of false confidence if your tests don't cover important scenarios, TDD can give you a false sense

of security.

One of my colleagues was initially very resistant to TDD.

Why would I write tests for code that doesn't exist yet?

He'd ask.

But after a few weeks of practice, he became its biggest advocate.

He found that TDD actually helped him clarify his thinking about the code before diving into implementation,

leading to cleaner designs and fewer bugs.

Data driven testing.

Data driven testing, or DDT, is an approach where you separate your test logic from your test data.

This powerful technique allows you to run the same tests with different sets of data without duplicating

the test code.

So imagine you're a teacher giving the same exam or test to multiple students.

Instead of creating a new copy of the exam for each student, you create one exam template and just

fill in different students names at the top.

That's basically what data driven testing does one test template that runs with different data sets.

Think about it this way if you're testing a login form, you might want to try multiple combinations

of usernames and passwords valid ones, invalid ones, special characters, etc..

Instead of writing a separate test for each combination, you write one test and feed it different data

sets.

The data typically comes from external sources like CSV files, Excel spreadsheets, databases, or

XML files.

Here's a simple example of data driven testing in Python using pytest.

In this example, we define a list of test data of tuples, each containing a username, password,

and expected result.

The pytest parameterized decorator tells Pytest to run the test function once for each tuple in the

list.

But in real world scenarios, you typically load this data from an external file.

Here's how you might do that with a CSV file.

The actual CSV file might look something like this.

I once worked on a project testing a mortgage calculator.

We had to verify calculations for hundreds of different loan scenarios, different loan amounts, interest

rates, terms, down payments, etc. Using data driven testing, we created one test script and fed

it an Excel file with all the different scenarios.

When the calculation formula changed due to a regulatory update, we only had to update one script instead

of hundreds.

And when we needed to add new test cases, we just added rows to our existing Excel file without touching

the code at all.

The pros of data driven testing are substantial.

Reduces code duplication.

You write the test logic once and reuse it with different data.

Makes test maintenance easier.

When the application changes, you only need to update one.

Test script enables non-programmers to contribute.

Test analysts can add new test cases by adding data to a spreadsheet.

Improves test coverage.

It's easy to test more scenarios without writing more code.

Separates concerns.

Tests, logic and test data are kept separate.

Following good software design principles.

But there are some challenges to consider.

Data management.

You need to maintain your test data carefully, which can become a project in itself.

Setup complexity.

Setting up the data driven framework takes some initial effort.

Debugging can be harder when a test fails.

You need to figure out which data set caused the failure.

One important tip I learned the hard way always include enough information in your test data to make

debugging easier.

For example, include a descriptive test name or ID in each row of your data file.

When a test fails, this helps you quickly identify which scenario had the issue.

Keyword driven testing.

Now let's explore keyword driven testing or KDT.

Keyword driven testing takes the concept of separating test logic and test data even further.

In this approach, you define high level keywords that represent actions or verifications in your application,

and then your tests become a sequence of these keywords with associated data.

Think of keywords as building blocks for your test.

Instead of writing detailed scripts, you assemble tests using predefined actions like login, search,

product, add to cart, Etc. it's like building with Lego blocks.

Instead of sculpting from clay, you use standardized pieces to build something complex.

The robot framework is a popular open source framework for keyword driven testing.

So let's see how KDT works using robot as an example.

In the robot framework, a test case might look like this.

Let's break down what's happening here.

The settings section sets up the libraries we need.

The variables section defines common values.

We'll use.

The test cases section contains our actual tests which are sequences of keywords.

The keyword section defines custom keywords that our tests use.

Notice how readable the test cases are.

Someone who doesn't know programming could understand what these tests are doing.

That's one of the main benefits of keyword driven testing.

Behind the scenes, one keyword is implemented either as a custom keyword, like the ones we defined,

or as a built in keyword from a library like open browser from selenium library.

One of the most powerful aspects of Robot framework is that it comes with many built in libraries providing

keywords for web testing, API testing, database testing, etc. you can also create your own custom

keywords to encapsulate complex operations.

I once worked at a large insurance company where business analysts were heavily involved in testing

by implementing keyword driven testing with Robot Framework.

We created a library of keywords that matched the business language they use.

These analysts, who had no programming experience, could create automated tests by essentially writing

out the test steps as they would for manual testing.

For example, they could write tests like the following.

The pros of keyword testing include.

Business readable test.

Tests are expressed in language that business stakeholders can understand.

Reusable components.

Keywords can be reused across many test cases.

Non-technical participation.

Business analysts and manual testers can contribute to automation framework for collaboration.

It provides a common language between technical and non-technical team members.

Separation of concerns.

Implementers focus on keywords.

Test designers focus on test flows.

Cons include.

Initial setup effort.

Creating a robust keyword library takes time maintenance overhead as the application changes, keywords

need to be updated.

Finding the right granularity.

Keywords that are too specific aren't reusable.

Keywords that are too general aren't meaningful.

Learning curve new team members need to learn the available keywords.

I should mention a cautionary tale here.

So on one project, we went a bit overboard with the keyword abstraction and ended up with hundreds

of very specific keywords that were only used once or twice.

This made the framework hard to maintain.

The lesson was keep your keywords at a consistent level of abstraction that balances reusability with

clarity.

The most successful KDT implementations I've seen start with a small set of well-designed keywords and

grow organically as needed.

And they always include good documentation.

So team members know what keywords are available and how to use them.

Behavior driven development.

Last but not least, let's talk about behavior driven development or BDD.

BDD is an extension of test driven development that focuses on the behavior of the system from the user's

perspective.

It uses a natural language format, typically given when then, to describe test scenarios in a way

that non-technical stakeholders can understand the given when, then format works like this.

Given some initial context when an event occurs, then ensure some outcomes.

BDD scenarios are typically written in files called feature files, and tools like cucumber, Specflow

or Jbehave translate these into executable tests.

Here's an example of a BDD scenario for login.

The scenario is then mapped to code like this.

The pros of BDD are significant.

It improves communication between technical and non-technical team members.

Scenarios serve as both documentation and executable tests.

It focuses on business value and user behavior.

It works well with agile methodologies.

The cons include.

You still need additional test cases for edge cases and negative scenarios.

Many teams misunderstand BDD as just a way to write tests in natural language.

Implementing and maintaining the step definitions can be complex.

Debugging can be challenging when scenarios get complex.

I've seen BDD work wonders in organisations where there was previously a communication gap between business

and technical teams.

On one project we had weekly Three Amigos sessions where a developer, tester and business analyst would

write BDD scenarios together before development started.

This ensured everyone had the same understanding of the requirements, and the scenarios became the

acceptance criteria for the user.

Stories BDD is particularly effective when you need to ensure that everyone has a clear and shared understanding

of how the system should behave.

Comparing approaches.

Now that we've gone through all these approaches, you might be wondering which one is best.

Well, like most things in software, the answer is it depends.

Let's look at how these approaches compare in terms of key factors.

Entry barrier low would be capture playback and linear scripting.

Medium would be structured scripting and data driven testing.

High would be test driven development, keyword driven testing and behavior driven development.

Maintainability.

Low would be capture playback and linear scripting.

Medium would be structured scripting and data driven testing.

High would be test driven development, keyword driven testing, and behavior driven development.

Scalability low will be capture playback and linear scripting.

Medium will be structured scripting.

High will be data driven testing.

Test driven development.

Keyword driven testing and behavior driven development.

Business involvement.

Low would be capture playback.

Linear scripting.

Structured scripting.

Medium will be data driven testing and test driven development.

High would be keyword driven testing and behavior driven development.

Often the best approach is to combine multiple techniques.

For instance, you might use TDD for unit testing, structured scripting with data driven testing for

API tests, and BDD for end to end user acceptance tests.

I've seen teams successfully use capture playback to quickly prototype tests, then refactor them into

more structured approaches as the project matures.

Evolution of approaches.

One thing to remember is that these approaches represent an evolution in test automation thinking.

Each new approach was developed to address limitations and previous approaches.

For example, structured scripting evolved to address the maintenance problems of linear scripting.

Data driven testing evolved to separate test data from test logic.

Keyword driven testing evolved to make tests more accessible to non-programmers.

It's not uncommon for teams to start with simple approaches and gradually move to more sophisticated

ones as their automation maturity grows.

Real world application.

Let me share a real world example of how these approaches might be combined.

I once worked on a large e-commerce project where we used TDD for unit testing to back end services.

Structured scripting with data driven testing for the API tests.

Keyword driven testing for the most common UI workflows and BDD for critical user journeys that needed

business validation.

The combination allowed us to leverage the strengths of each approach, where it made the most sense

for our checkout flow, which was critical to the business.

We used BDD to ensure everyone understood exactly how it should work.

For testing product search with thousands of different search terms, we use data driven testing to

avoid writing thousands of separate tests.

All right.

So we've covered a lot.

Let's recap the different approaches for automating test cases.

Capture playback.

Easy to start with but hard to maintain.

Linear scripting.

Simple programming, but prone to duplication.

Structured scripting.

Reusable components improve maintainability.

Test driven development.

Write tests before code for better quality.

Data driven testing.

Separate test logic from test data.

Keyword driven testing.

Use high level keywords for business readable tests.

Behavior driven development.

Natural language scenarios.

Bridge.

Technical and business worlds.

Remember, there is no one size fits all approach.

The best strategy often involves using a combination of these approaches based on your specific project

needs.

Team skills and organizational culture.

As you progress in your test automation journey, you'll likely start with simpler approaches and evolve

towards more sophisticated ones as your experience and needs grow.

In the next video, we'll talk about design principles and design patterns in test automation, which

will help you implement these approaches more effectively."