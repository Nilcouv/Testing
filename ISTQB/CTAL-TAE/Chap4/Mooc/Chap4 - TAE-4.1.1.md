# Mooc

## Apply Guidelines that Support Effective Test Automation Pilot and Deployment Activities

### Screen

> **What is a Test Automation Pilot?**
>
> - Act as a "Test drive" before full deployment.
> - Pilot projects are small-scale implementations of automation strategy.
> - The impact it can have on the direction of your project is huge.
>
> eg. healthcare application - pilot allowed to detect early security requirements problem > saved months of wasted efforts.

---

> **Setting Up Guidelines for Your Pilot**
>
> - Programming languages
> - Suitable Tools
> - Test Levels to Cover
> - Test Cases Selected
> - Test Case Development Approach

---

> **Programming Languages**
>
> - Match language to development team's expertise
> - Enables developer collaboration on automation
> - eg. Healthcare project: Python/Java mismatch caused delays

---

> **Tool selection Strategy**
>
> - **Web Testing** - Selenium, Cypress, Playwright
> - **API Testing** - Postman, RestAssured, Karate
> - **Mobile Testing** - Appium, XCUITest, Expresso
>
> eg. Team choosed commercial tool with amazing record and playback features (look easy to use) > had to start over 6 months later (Tool couldn't handled complex web application with dynamic elements)

---

> **Test Level Coverage**
>
> ```mermaid
> flowchart BT
>     CT["Component Tests<br/>(Unit Tests)"]
>     CIT["Component Integration Tests"]
>     ST["System Tests"]
>     SIT["System Integration Tests"]
>     AT["Acceptance Tests"]
>
>     CT --> CIT
>     CIT --> ST
>     CIT --> SIT
>     ST --> AT
>     SIT --> AT
> ```
>
> - Focus on the longest, slowest manual test first.
> - Focus on component tests that would give developers faster feedback.
> - Test pyramid diagram reference


---

> **Test Case Selection**
>
> - Include happy paths, complex flows, and edge cases.
> - Shows how the automation solution would handle different types of tests.

---

> **Development Approaches**
>
> - **Linear scripting** - Simple scripts without much reusable code (quick to start, hard to maintain)
> - **Structured scripting** - Creating reusable functions and libraries
> - **Data-driven testing** - Separating test data from test logic
> - **Keyword-driven testing** - Defining keyword that represent actions
> - **Behavior-driven development (BDD)** - Using natural language specifications (_allow collaboration with stakeholder, more setup_)

---

> **Creating Initial Prototypes Examples**
>
> **Prototypes** 
> 
> - A Selenium WebDriver Solution in java with the Page Object Model
> - A Cypress solution with TypeScript
> - A BDD approach using Cucumber wiht Selenium
>
> **Evaluation Criteria**
>
> - Speed of execution
> - Ease of writing
> - Readability of the code
> - Stability of the tests
> - Learning curve for the team

---

> **Pilot Timeline & CI/CD integration**
>
> Defining timelines is crucial for meeting schedules and ensuring your pilot's success.
>
> - **Week 1** - Setup and initial test cases.
> - **Week 2** - Expand test coverage
> - **Week 3** - Integrate with CI/CD pipeline.
> - **Week 4** - Evaluation and recommendation

---

> **Integration with CI/CD**
>
> - Integrate your automation solution into CI/CD during the pilot
> - CI/CD = code is automatically built, tested, and deployed
> - Integration reveals issues in TAS, SUT, or tool coordination early
>
> **Example**
>
> - local tests passed: CI pipeline failed due to server memory issues
> - Catching this early avoided future debugging headaches.
>
> **Adjust CI/CD as test suite grows:**
>
> - Smoke tests on every commit
> - Critical regression tests nightly
> - Full regression suite weekly

---

> **Non-Technical Evaluation Factors**
>
> - **Team knowledge/skills** - Assess skills and experience gaps.
> - **Team structure** - Define roles and responsibilities
> - **Licensing/organizational rules** - Check organizational policies and tool licenses.
> - **Testing types planned** - Plan for manual, automated, and other tests.

---

> **Evaluating the Pilot**
>
> - Did the chosen tools and approaches work for your specific application?
> - How difficult was it to create and maintain the automated tests?
> - Did the tests provide reliable results, or were there many flaky tests?
> - How well did the solution integrate with your existing tools and processes?
> - What was the learning curve like for your team ?

---

> **Pilot Evaluation & Real-World Examples**
>
> | Company A (Success) | Company B (Failure) |
> |---|---|
> | • Diverse cases<br>• Team involved<br>• 4-week pilot<br>• 2000 tests<br>• 10% maintenance | • Rushed pilot<br>• Easy cases only<br>• 6-month pilot<br>• Hundreds of brittle tests<br>• Restart needed |

---

> **Conclusion**
>
> 1. A well-planned pilot project is absolutely crucial for the success of your test automation efforts
> 2. Define clear guidelines and evaluate different approaches
> 3. Integrate with your CI/CD pipeline and consider both technical and non-technical factors
> 4. Pilot goal: Find optimal approach for YOUR context.
> 5. Balance Technical and organizational factors.

### Transcript

"Apply guidelines that support effective test, automation, pilot, and deployment activities.

Let's dive into one of my favorite parts of test automation setting up a pilot project.

I've been through this process many times, and let me tell you, getting this initial phase right can

make or break your entire automation journey.

What is a test automation pilot?

First things first, let's talk about what a pilot project actually is.

Think of it like a test drive before buying a car.

A test automation pilot is basically a small scale version of your automation strategy that you implement

before rolling it out across your entire project.

It's kind of like dipping your toes into the water before diving in.

The beauty of a pilot is that it doesn't take forever to complete, but the impact it can have on the

direction of your project is huge.

I remember working on a healthcare application where we spent just two weeks on a pilot, and it completely

changed our approach to test automation.

We realized that our initial tool choice wasn't going to work with the complex security requirements

of the application.

That small investment saved us months of wasted effort.

Setting up guidelines for your pilot.

So what guidelines should you follow when setting up your pilot?

Based on the information you've gathered about your system under test and project requirements?

Here are the key things you want to evaluate.

Programming languages.

You'll need to decide which programming language or languages you'll use for your test automation.

This is super important because it impacts who on your team can contribute to the automation effort.

For example, if your development team uses TypeScript for the application, it might make sense to

use TypeScript for your automation too.

That way, your developers can help with the automation code when needed.

I worked on a project where we chose Python for our automation.

Even though the application was built in Java, the learning curve for the testers was steep and we

spent more time teaching Python than actually automating tests.

Suitable tools.

Next, you'll want to look at commercial off the shelf tools or open source options.

And there are so many choices out there for web testing.

You might consider selenium webdriver, Cypress or Playwright for API testing tools like Postman Rest

Assured or karate might be your go to mobile testing.

Appium UI tests or espresso could be what you need.

The key here is to match the tool to your specific needs.

I once worked with a team that chose a commercial tool with amazing record and playback features, because

it looked easy to use.

Six months later, they realized they couldn't handle their complex web application with dynamic elements,

and they had to start over.

Test levels to cover.

You also need to decide which test levels you want to cover with automation.

Remember those test levels we talked about earlier in the course component testing, which could also

be unit testing, component integration testing, system testing.

System integration testing and acceptance testing.

Not all levels need automation right away.

Maybe start with system level tests that take the longest to run manually, or focus on component tests

that will give developers faster feedback.

Here's a simple diagram to visualize the test levels.

Notice the dotted lines that make a triangle shape that gives reference to the classic test pyramid

that many teams use to visualize and approach the testing, where the focus is more on lower level test

types compared to higher levels.

Test cases selected.

Not all test cases are created equal when it comes to automation for your pilot.

You want to select a representative sample that will really show whether your automation approach works.

I usually recommend including a few simple happy path scenarios that should always pass a couple of

complex scenarios with multiple steps and at least one edge case or negative test on a banking project

I worked on.

We selected ten test cases for our pilot covering account login, simple transfers, complex multi-currency

transfers, and a couple of error scenarios.

This mix gave us a really good feel for how our automation solution would handle different types of

tests.

Test case development approach.

Finally, you need to think about your approach to developing test cases.

Will you use linear scripting?

Simple scripts without much reusable code, structured scripting, creating reusable functions and libraries.

Data driven testing.

Separating test data from test logic.

Keyword driven testing.

Defining keywords that represent actions.

Behavior driven development using natural language specifications.

Each approach has its pros and cons.

For instance, BDD is fantastic for collaboration with business stakeholders, but it requires more

setup.

Linear scripting is quick to start with, but becomes a maintenance nightmare as you scale.

Creating initial prototypes based on all these considerations.

You can create several different prototypes to showcase the advantages and disadvantages of different

approaches.

Let me give you a real world example.

On an e-commerce project, we created three different prototypes a selenium WebDriver solution in Java

with the page object model, a Cypress solution with TypeScript, and a BDD approach using cucumber

with selenium, we implemented the same five tests in each prototype, then evaluated them based on

speed of execution, ease of writing, new test, readability of the code, stability of the tests,

and learning curve for the team.

This comparison made it crystal clear which approach was the best fit for our specific project.

Timeline.

Definition.

Defining timelines is crucial for meeting schedules and ensuring your pilot's success.

Make sure you periodically check on the progress to identify any risks and address them early.

A typical pilot might take 2 to 4 weeks, depending on the complexity of your application.

I usually recommend breaking it down like this.

Week one.

Set up an initial test cases.

Week two expand test coverage and tackle any initial challenges.

Week three integration with CI, CD and refinement.

Week four evaluation and recommendation.

Integration with CI CD.

Speaking of CI CD, it's super important to try integrating your automation solution into your continuous

integration continuous delivery pipeline.

During the pilot, in case you're new or need a refresher on the concept, CI, CD is an approach for

code changes are automatically built, tested, and prepared for deployment.

Disintegration often reveals issues early, either in your system under test your test automation solution,

or in how different tools in your organization work together.

For example, on one project, our tests ran perfectly on our local machines, but when we added them

to the CI pipeline, they kept failing randomly.

It turned out there was a memory issue on the CI server that only appeared under certain conditions.

Finding this during the pilot saved us from having a lot of future troubleshooting.

As your test suite grows, you might want to adjust your CI CD setup to run tests in different ways.

Run smoke tests on every commit.

Run critical regression tests nightly.

Run the full regression suite weekly.

Evaluated non-technical aspects during your pilot.

You'll also need to evaluate some non-technical aspects.

Team knowledge and experience.

Do your team members have the skills needed for test automation?

If not, you'll need to factor in training time.

Team structure.

How is your team organized?

Do you have dedicated automation engineers or are your manual testers expected to write automation code?

Licensing and organizational rules.

Are there any restrictions on what tools you can use?

Some organizations have strict rules about open source software or cloud based solutions.

Types of plan testing.

What kinds of testing do you plan to automate?

Functional testing.

Performance testing.

Security testing.

Evaluating the pilot.

Once your pilot is complete, it's time for the test automation engineers and test managers to evaluate

its success or failure.

This evaluation should consider.

Did the chosen tools and approaches work for your specific application?

How difficult was it to create and maintain the automated tests?

Did the tests provide reliable results or were there many flaky tests?

How well did the solution integrate with your existing tools and processes?

What was the learning curve like for your team?

I've seen many organizations rush through this evaluation phase eager to get started with the real automation.

But trust me, taking the time to thoroughly assess your pilot can save you months of work and frustration

down the road.

Real life example.

A Tale of Two Pilots.

Let me share a quick story about two different pilot projects I was involved with company A took time

to define clear guidelines for their pilot.

They selected a mix of simple and complex test cases.

Try three different automation approaches and involved a whole team in the evaluation.

Their pilot took four weeks, but at the end they had a solid direction for their automation strategy.

Two years later, they had over 2000 automated tests running daily with a maintenance overhead of just

10%.

Company B was in a rush and skipped most of the planning.

They picked a tool because their competitors were using it automated whatever.

Test cases were easy to automate and didn't bother with CI CD integration during the pilot.

Six months later, they had hundreds of brittle failing tests that nobody trusted, and they ended up

scrapping the whole effort and starting over.

So to wrap up, a well planned pilot project is absolutely crucial for the success of your test automation

efforts.

Take the time to define clear guidelines, evaluate different approaches, integrate with your CI CD

pipeline, and consider both technical and non-technical factors.

Remember, the goal of a pilot isn't just to prove that automation can work, it's to find a specific

approach that will work best for your unique project, team, and organization.

In the next video, we'll talk about the risks associated with test automation development and how to

mitigate them.

We should now have a better understanding of how to set up an effective test automation pilot."