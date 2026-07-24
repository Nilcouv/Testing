# Mooc

## Select suitable test automation tools for a given system under test

### Screen

> **Understanding the system under test**
>
> Don't pick tools before what you are testing
>
> Eg. UI tool bought before realizing 80% of testing was API

---

> **Analysis Steps - Project requirements**
>
> Ask yourself:
>
> * What types of testing do you need? -- (UI, API, Performance, etc.)
> * What platforms are you testing? (Web, Mobile, Desktop)
> * What's your timeline looking like?
> * What's your budget situation?
>
> Eg. healthcare project
>
> Needed to:
>
> * Test web and mobile
> * Verify complex calculation
> * Ensure HIPAA compliance (Health Insurance Portability and Accountability Act)
> * Integrate with multiple third-party systems
>
> Ended up using multiple tools
>
> * Selenium -- Web UI testing
> * Appium -- for mobile testing
> * Postman -- API testing
> * Custom scripts -- calculation verification

---

> **Technical Experience Consideration**
>
> For teams with limited programming experience:
>
> * Look for low-/no-code solutions
> * Consider tools with record-and-playback features
> * Focus on tools with good GUI interfaces
>
> For Technical teams:
>
> * Consider tools that use the same language as your application
> * Look for tools with good API documentation
> * Evaluate the framework's extensibility
>
> Eg. Startup project - QA team selected Testcafe because:
>
> * Easy learning curve
> * Provided good record-and-playback features
> * Still allowed for custom code when needed
> * Had great documentation

---

> **Cross-team benefits**
>
> Matching dev stack and tools = Faster debugging
>
> Eg.
>
> * Java --> TestNG/JUnit
> * Javascript --> Cypress/Playwright
> * Python --> Robot Framework/Pytest

---

> **Common Pitfalls to Avoid**
>
> 1. Swiss Army Knife Trap -- Trying to do everything
> 2. Following the Crowd -- using tools just because others do
> 3. The "Budget Blinder" Error -- Cheapest often becomes costly

---

> **Evaluation Process**
>
> 1. Create a comparison matrix -- Requirements in rows, tools in columns
> 2. Run a pilot project -- Try 2-3 tools on small project, get team feedback, check maintenance needs

---

> **Pro tips - Open source**
>
> When evaluating open source tools:
>
> * Check the community activity
> * Look at the last release date
> * Review outstanding issues
> * Check documentation quality

---

> **Pro tips - Commercial**
>
> When evaluating commercial tools:
>
> * Ask for extended trial period
> * Get training quote
> * Check support response times
> * Verify licensing models

---

> **Conclusion**
>
> 1. Choosing the right tool is crucial for long-term success
> 2. Don't rush - Better to spend time now than regret later

### Transcript

"Select suitable test automation tools for a given system under test.

Now let's tackle something that stumps a lot of teams.

Choosing the right test automation tools.

It's kind of like picking out the right tools for a home improvement project.

So you might be at a store shopping for tools, and see a multi-purpose tool that looks like it can

handle all your needs.

But sometimes you really need specific specialized tools to get the job done right.

Understanding the system under test.

So before you even look at tools, you need to really understand what you're testing.

I once worked with a team that jumped straight into buying a really nice but expensive UI automation

tool, only to realize later that 80% of their testing need to be done at the API level.

Talk about an expensive lesson learned.

So let's break down how to avoid that kind of situation.

Starting with analyzing steps.

Here's what you need to look at.

Project requirements.

Think about what types of testing do you need like UI, API, performance, etc..

What platforms are you targeting like web, mobile or desktop?

What's your timeline looking like?

And what's your budget situation?

There was a time when I worked on a healthcare project where we needed to test both web and mobile interfaces.

Verify complex calculations.

Ensure HIPAA compliance, which stands for the Health Insurance Portability and Accountability Act To

and integrate with multiple third party systems.

In this case, we actually ended up using multiple tools selenium for web UI testing, Appium for mobile

testing, postman for API testing and we created custom scripts for calculation verification.

Technical experience considerations.

Now here's something really important that people often overlook your team's technical expertise.

Let me break this down.

For teams with limited programming experience.

Look for low code or no code solutions.

Consider tools with record and playback features, and focus on tools with good GUI interfaces for technical

teams.

Consider tools that use the same language as your application.

Look for tools with good API documentation and evaluate the framework's extensibility.

I remember working with a startup where most of the QA team came from manual testing backgrounds.

We chose a tool called Test Cafe because it had an easy learning curve, provided good record and playback

features, still allow for custom code when needed, and had great documentation.

This approach works way better than if we jump straight into something more complex, like Playwright

or Cypress.

Even though these are excellent tools for the more technical teams.

Cross team benefits.

Here's a cool benefit when your automation tools match your development stack, developers can actually

help debug test automation issues.

I've seen this save countless hours of troubleshooting.

For example, if your app is with Java and using testing or JUnit for automation, that means developers

could probably jump in pretty easily since those are common Java testing tools.

If you're a JavaScript shop, using Cypress or playwright makes perfect sense for Python applications.

Robot framework or Pytest may feel right at home.

Common pitfalls to avoid.

Let me share some mistakes I've seen teams make.

The Swiss Army knife trap.

Don't choose a tool just because it claims to do everything.

Sometimes multiple specialized tools work better than one that tries to do it all.

The fall in the crowd.

Mistake.

Just because everyone is using a particular tool doesn't mean it's right for your project.

Jake.

I've seen teams struggle with tools like selenium when they really needed something simpler.

The budget blender error going for the cheapest option often ends up being more expensive in the long

run, due to maintenance and limitations.

Evaluation process.

Here's a practical approach to tool evaluation.

Try creating a comparison matrix where you list your requirements in rows.

Put potential tools in columns.

Rate how well each tool meets each requirement.

Run a pilot project.

Try the top 2 to 3 tools with a small project.

Get feedback from the team and evaluate maintenance needs.

Pro tips.

Now let me share some insider tips.

Open source Consideration.

If you're thinking about open source tools, check the community activity.

Look at the last release date, review outstanding issues and check documentation quality.

Commercial tools.

When evaluating commercial tools, ask for extended trial periods.

Get training quotes, check support response times, and verify licensing models.

So remember, choosing the right automation tools is crucial for long term success.

Don't rush the decision.

It's better to spend extra time evaluating tools than to realize six months from now, that you made

the wrong choice.

In the next video, we will discuss preparing for automation."
