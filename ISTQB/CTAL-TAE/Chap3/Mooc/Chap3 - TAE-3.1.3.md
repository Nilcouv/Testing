# Mooc

## Apply Layering Of Test Automation Framework

### Screen

> **What is a TAF (Test Automation Framework)?**
>
> **TAF** = Foundation of your Test Automation Solution (like a house's blueprint)
>
> **Includes**:
> - Test harness/runner
> - Test libraries
> - Test scripts
> - Test suites

---

> **What is a TAF (Test Automation Framework)?**
>
> - A test harness or test runner is basically the component that executes your tests.
> - Test libraries are collections of reusable code that help you perform common actions in your tests.
> - Test scripts are the actual automated tests themselves - the step-by-step instructions that verify your application works correctly
> - Test suites are collections of related test scripts that you run together.
>
> Layering prevents maintenance nightmares (e.g., monolithic 2000-line scripts)

---

> **Understanding TAF Layers**
>
> **TAF Layers**
> Test Scripts <-> Business Logic <-> Core Libraries
>
> - Layers = Distinct borders for code with similar purposes
> - Goal: Organized, maintainable, reusable code
> - Industry Standard: 3 main layers (keep it simple)

---

> **The Three Main Layers**
>
> 1. Test Scripts layer
> 2. Business Logic layer
> 3. Core Libraries layer

---

> **Test Scripts layer**
>
> - Top layer; Defines WHAT to test (e.g., login, checkout)
>
> **Example**
> ```python
> def test_valid_login():
>    # This calls methods from the Business Logic layer
>    login_page.enter_username("testuser")
>    login_page.enter_password("password123")
>    login_page.click_login_button()
>
>    # Verify the result
>    assert dashboard_page.is_displayed(),   "Dashboard should be displayed after login"
> ```

---

> **Business logic layer**
>
> - Middle layer; defines HOW to test for the specific SUT
>
> Customized for the application
> ```python
> class LoginPage(BasePage):   # Inherits from a class in Core Libraries
>    def enter_username(self, username):
>       self.find_element(By.ID, "username_field").send_keys(username)
>
>    def enter_password(self, password):
>       self.find_element(By.ID, "password_field").send_keys(password)
>
>    def click_login_button(self):
>       self.find_element(By.ID, "login_button").click()
> ```

---

> **Core Libraries layer**
>
> - Bottom layer; reusable, SUT-agnostic tools (e.g., WebDriver, API clients)
>
> ```python
> class BasePage:
>    def __init__(self, driver):
>       self.driver = driver
>
>    def find_element(self, by, value):
>       return self.driver.find_element(by, value)
>
>    def wait_for_element(self, by, value, timeout=10):
>        # Implementation of a wait mechanism
>        pass
> ```

---

> **How These Layers Work Together**
>
> 1. **Test Script layer** > "Test valid login"
> 2. **Business Logic layer** > "Enter username/password. click login button"
> 3. **Core Libraries layer** > "Find elements, enter text, click buttons"
>
> Separation of concerns --> easier maintenance (e.g., only update Business Logic if UI changes)

---

> **Scaling Test Automation**
>
> ```text
>        ──────── PROJECT #1 ────────        ── PROJECT #2 ──
> ┌──────────────────┐ ┌──────────────────┐ ┌──────────────────┐
> │ App #1           │ │ App #2           │ │ App #3           │
> │  Test Scripts    │ │  Test Scripts    │ │  Test Scripts    │
> └────────┬─────────┘ └────────┬─────────┘ └────────┬─────────┘
>          ▼                    ▼                    ▼
> ┌──────────────────┐ ┌──────────────────┐ ┌──────────────────┐
> │ App #1           │ │ App #2           │ │ App #3           │
> │  Business Logic  │ │  Business Logic  │ │  Business Logic  │
> └────────┬─────────┘ └────────┬─────────┘ └─────────┬────────┘
>          │                    │                     │
>          └────────────────────┼─────────────────────┘
>                               ▼
>                ┌──────────────────────────┐
>                │      Core Libraries      │
>                │    (shared across all)   │
>                └──────────────────────────┘
> ```
>
> Core libraries enable reuse across projects:
> 
> - Project #1: TAFs for App #1 and App #2
> - Project #2: TAF for App #3 (Same Core libraries)
>
> Example : Financial services company with centralized Test Engineer team

---

> **Real-World Example; E-commerce Testing**
>
> 1. Test Scripts layer
> 2. Business Logic layer
> 3. Core Libraries layer
>
> **Core Libraries Layer**
>
> in our Core Libraries, we might have:
>
> - A WebDriver wrapper that handles browser initialization, navigation, finding elements, etc.
> - A REST client for API testing
> - A database connector for verifying data
> - A logging utility
> - A reporting utility
>
> **Business Logic Layer**
>
> In our Business Logic Layer, we'd have classes specific to our e-commerce site:
>
> - HomePage (with methods like search_for_product, navigate_to_category, etc)
> - ProductPage (with methods like add_to_cart, select_size, etc.)
> - CartPage (with methods like proceed_to_checkout, update_quantity, etc.)
> - CheckoutPage (with methods like enter_shipping_info, enter_payment_info, etc.)
>
> **Test Script Layer**
>
> Finally, in our Test Script Layer, we'd have actual test cases:
>
> - Test_search_functionality
> - Test_add_to_cart
> - Test_checkout_process
> - Test_account_creation

---

> **Benefits of Layering**
>
> - Maintainability - Updates usually limited to one layer
> - Reusability - Core libraries shared across projects
> - Scalability - Easy to add new test scripts
> - Readability - Test scripts focus on business logic
> - Division of labor - Technical vs. domain experts work on different layers.

---

> **Challenges and Best Practices**
>
> **Challenges**
> 
> - **Initial Investment** - Setting up a layered framework takes more time upfront compared to writing simple scripts. But the payoff comes in maintenance and scalability.
> - **Learning Curve** - Team members need to understand the layering concept and follow the patterns consistently.
> - **Over-engineering** - it's easy to make the framework too complex with too many layers or abstractions.
>
> **Best Practices**
>
> - **Start Simple** - Begin with three main layers we discussed. You can add more complexity later if needed
> - **Document Well** - Make sure everyone understands the purpose of each layer and how they should interact
> - **Use Design Patterns** - Patterns like Page Object Model work well with this layered approach.
> - **Code Reviews** - Regular reviews help ensure everyone is following the layering principles correctly.

---

> **Conclusion**
>
> 1. Layering creates maintainable, reusable, scalable automation
> 2. 3 layers: Test Script (What), Business Logic (how), Core Libraries (Tools)
> 3. Saves long-term time despite upfront investment.

### Transcript

"Apply layering of test automation frameworks.

What is the test automation framework?

Let's talk about something that's super important but often overlooked when people start building test

automation.

The concept of layering in test automation frameworks.

You know how when you're building a house, you don't throw everything together in one big pile,

right?

You have a foundation, walls, roof, plumbing, electrical systems all organized in a logical way.

Well, test automation frameworks work the same way.

Layering helps us organize our automation code to make it more maintainable, reusable, and scalable.

Before we jump into layering, let's quickly talk about what a test automation framework or

TAF actually is.

A test automation framework is essentially the foundation of your entire test automation solution.

Think of it as the engine that powers all of your automated testing efforts.

It includes things like a test harness, also known as a test runner, test libraries, test scripts,

and test suites.

Let me break down what some of these terms mean in case you're new to them.

A test harness or test runner is basically the component that executes your test.

It's like the conductor of an orchestra telling each test when to start and coordinating everything.

Test libraries are collections of reusable code that help you perform common actions in your tests.

For example, you might have a library for interacting with databases or for handling complex UI components.

Test scripts are the actual automated tests themselves.

The step by step instructions that verify your application works correctly, and test suites are collections

of related test scripts that you run together.

Now, I remember when I first started with test automation many years ago, I had this one massive script

that did everything.

It was like 2000 lines of code.

And let me tell you, it was an absolute nightmare to maintain.

Every time the application changed, I had to spend hours figuring out what broke in my script.

That's why layering is so important.

It helps us avoid these kind of maintenance nightmares.

Understanding TAF layers.

So what do we mean by layers in a test automation framework?

TAF layers define distinct borders between classes of code that have similar purposes.

It's like organizing your kitchen.

You keep all the plates together, all the glasses together, all the utensils together.

In the same way, we organize our test automation code by putting similar functionality together.

Now, you might be thinking, couldn't we create a separate layer for every single purpose?

And technically, yes we could, but that would make our design unnecessarily complicated.

So the recommendation is to keep the number of layers low, just enough to give us good organization

without overcomplicating things.

In the industry, there's a common pattern of using three main layers.

The first is the test scripts layer, the second is the business logic layer, and the third is the

core libraries layer.

Let's talk about each of these in detail.

The three main layers.

Test scripts layer.

The test scripts layer sits at the top of our framework.

Its purpose is to provide a repository of test cases for the system under test, and to organize them

into test suites.

This layer contains the actual test scripts that verify specific functionality in your application.

For example, if you're testing an e-commerce site, you might have test scripts for login functionality,

product search, adding items to cart checkout process.

The key thing about this layer is that it should be focused on the what of testing, not the how.

Test scripts should call the services of the business logic layer to actually do the work.

They should never make direct calls to the core libraries.

Let me give you a real world example.

Let's say we're testing a login page.

Notice how simple and readable this is.

It's almost like reading plain English.

That's because all of the complex implementation details are hidden in the lower layers.

Business logic layer.

The business logic layer sits in the middle of our framework.

This layer contains all the system dependent libraries.

By system dependent, I mean code that's specific to the particular application you're testing.

These libraries inherit or use the core libraries, which we'll talk about next, but they're customized

for your specific application.

They implement the how of your testing.

Continuing with our login example, the business logic layer might have a login page class like this.

This layer is also used to set up the TAF to run against your specific system under test, and to

handle any additional configurations needed.

Core libraries layer.

At the bottom of our framework is the Core Libraries layer.

This layer contains all the libraries that are independent of any specific system under test.

These are the generic reusable components that could be used in any project with the same technology

stack.

For example, you might have core libraries for interacting with web browsers, making API calls, working

with databases, handling test data, or logging test results.

The beauty of this layer is that once you build it, you can reuse it across multiple projects or applications.

It's like having a toolkit of basic tools that you can use for any project.

Going back to our login example, the core libraries might have a base class like this.

This code doesn't know anything about the specific application we're testing.

It just provides generic functionality that any web testing project might need.

How these layers work together.

So how did these layers work together?

Let's visualize it with our login example.

The test scripts layer says what we want to test.

I want to test that a user can log in with valid credentials.

The business logic layer says how to test it with our specific application.

To log in to this application, I need to enter text in the username field.

Enter text in the password field and click the login button.

The Core Libraries layer provides the basic functionality.

I know how to find elements on a web page, enter text, click buttons, and wait for elements to appear.

This separation of concerns makes our framework much more maintainable and flexible.

If the application changes, for example, if the ID of the username field changes, we only need to

update the business logic layer.

The test scripts and core libraries can stay exactly the same.

Scaling.

Test automation.

Now here's where things get really interesting.

Let's look at how this layered approach helps us scale our test automation efforts.

This diagram shows a great example of how core libraries provide a reusable base for multiple TAFs.

Let me describe this for you.

Imagine we have two projects.

Project one has two applications that need testing.

App number one and app number two.

Project number two on the right side has one application that needs testing app number three and project

number one.

We have one test automation engineer who builds two separate TAFs, one for each app, on top of the

same set of core libraries in project number two.

A different test automation engineer builds a TAF for app number three.

But instead of starting from scratch, they leverage the same core libraries that were used in project

number one.

This is a huge time saver.

Instead of reinventing the wheel, the second engineer can build on the foundation that's already been

created.

I've seen this approach work wonders in large organizations.

For example, at a financial services company I worked with, they had a central test engineering team

that maintained a set of core libraries.

Each product team then built their own business logic and test scripts on top of these core libraries.

When a new project started, they could get up and running with automation much faster because they

didn't need to build everything from scratch.

Real world example ecommerce testing.

Let's look at a more complete example to see how this works in practice.

Imagine we're building a test automation framework for an e-commerce website.

Core libraries layer in our core libraries.

We might have a WebDriver wrapper that handles browser initialization, navigation, finding elements,

etc. a Rest client for API testing, a database connector for verifying data, a logging utility, and

a reporting utility.

These components are completely reusable and know nothing about our specific e-commerce site.

Moving on to the business logic layer.

We'd have classes specific to our e-commerce site, a home page with methods like search for product,

navigate to category, etc. A product page with methods like add to cart, select size, etc..

A cart page with methods like proceed to checkout Update quantity and a checkout page with methods like

enter shipping info.

Enter payment info.

These classes use the core libraries but are customized for our specific application.

And finally, in our test scripts layer, we'd have actual test cases.

Test search functionality.

A test for add to cart, a test for the checkout process, and maybe a test for the account creation.

These tests would use the business logic layer to perform actions and verifications.

Benefits of layering.

Now that we understand how layering works, let's talk about why it's so beneficial.

Maintainability.

When your application changes, you usually only need to update one layer.

Typically the business logic layer.

This makes maintenance much easier.

Reusability.

Core libraries can be reused across multiple projects, saving a ton of development time.

Scalability.

As your testing needs grow, you can easily add new test scripts without changing the underlying framework.

Readability.

Test scripts become much more readable because they focus on business logic rather than implementation

details.

Division of labor.

Different team members can work on different layers based on their expertise.

For example, someone with deep technical skills might work on the core libraries, while a domain expert

might focus on the test scripts.

Challenges and best practices.

Of course, like anything in software development, layering comes with its challenges.

Initial investment.

Setting up a layered framework takes more time up front compared to writing simple scripts, but the

payoff comes in maintenance and scalability.

Learning curve.

Team members need to understand the layering concept and follow the patterns consistently.

Overengineering.

It's easy to make the framework too complex with too many layers or abstractions.

To address these challenges, here are some best practices.

start simple, begin with the three main layers we discussed.

You can add more complexity later if needed.

Document well. Make sure everyone understands the purpose of each layer and how they should interact.

Use design patterns.

Patterns like page object model, which we'll discuss in a later video, work well with this layering

approach.

Code reviews.

Regular reviews help ensure everyone is following the layering principles correctly.

To conclude, layering your test automation framework is a powerful technique that helps you create

maintainable, reusable, and scalable automation by separating your code into test scripts, business

logic, and core libraries layers.

You can make your automation more robust and easier to maintain.

Remember our kitchen analogy?

Just like you organize your kitchen by keeping similar items together, you organize your automation

code by keeping similar functionality together.

This makes it much easier to find things and make changes when needed.

In my experience, teams that take the time to implement proper layering in their frameworks save enormous

amounts of time in the long run.

Even though it requires a bit more investment up front.

In our next video, we'll look at different approaches for automating test cases, which will build

on this layering concept.

We'll explore techniques like linear scripting, structured scripting, data driven testing, and keyword

driven testing."