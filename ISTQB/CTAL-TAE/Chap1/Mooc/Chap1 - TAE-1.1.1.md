# MOOC

## Explain the advantages and disadvantages of tests automation

### Screen

> What is Test Test automation
> using specialized software tools to :
> - control and setup test suite to run automatically using purpose-built software tools
> - Execute those tests without manual intervention
> - Compare what actually happened with what we expected to happen
>
> Ex. E-commeerce website
> at every change, needs to verify functionnalies, such as the ability to log in as user, add products to the cart, the payment processing, order confirmation and email notification

> Advantages of Test Automation
> 
> 1. efficency - ability to run more tests per build compare to manual testing
> 2. testing the impossible - test impossible to run manually (eg. simulating 1000 simultaneous users, verifying the responses time in milliseconds, running tests accross multiple devices at the same time, testing systems remotely in different locations)
> 3. Complex Test Cases - ability to create complex tests scenarios hard to execute manually
> 4. Speed - automated test Execution is much faster than human (eg. few second compare to 5-minutes manually)
> 5. Remove Human Error - more consistant and repeatable, no forgetting steps, getting distracted or making a typo
> 6. Cost effeciency - more cost effective over time. initial investment higher but running automation is cheaper than manual testing
> 7. Consistency & reliability - Automation tests don't get tired, distracted or make mistakes

> Disadvantages of tests automation
>
> 1. Cost considerations - initial expense higher by hirering specialized automation engineer, buying hardware or tools, training the existing team
> 2. Time investment - Need setup time for the framework (eg. like building the solid house foundation before starting to add bedrooms )
> 3. Maintenance - Test scripts need regular maintenance to work, automation tests must change with application changes
> 4. Rigidity of tests - less flexible than manual testing, can break due to small application changes. keep tests in sync with evolving codebase can be challenging
> 5. Potential for introducing new bugs - Test scripts are code too, bugs in scripts can cause false positives or negatives. can be source of frustration and be time consuming 

> Limitation of Test Automation
>
> 1. not everything can be automated - Human judgement still needed (eg. evaluating if a user interface is intuitive)
> 2. Verifying only what automated tests are programmed to do - limited to specific scenarios, other areas may go unverified
> 3. Machine interpretation - Can only verify what machines can interpret. Can't assess if something "looks right" or "feels right"
> 4. Test Oracle Challenge - Need a way to verify result automatically. Difficult when : "Mutliple valid answer exist" or "availability changes in real-time (eg. flight booking system)

> Conclusion
>
> 1. Test automation is powerful, but not a magic solution
> 2. Key : find the right balance between automated and manual testing 
> 3. Good test automation = Reliable co-worker handling repetitive tasks
> 4. Human testers focus on creative and exploratory testing

### Transcript

"Purpose of test automation.

Explain the advantages and disadvantages of test automation.

Automated testing helps reduce the burden of tedious, slower manual testing and quickly resolves potential

problems.

Using automated tools, automated testing can help you quickly set up test preconditions, execute tests,

and compare actual outcomes to expected outcomes, ultimately reducing the time spent on testing.

We can use automated testing for regression, functional, or load testing.

So what exactly do we mean by test automation?

Well, it's basically using specialized software tools to do three main things control and setup.

Test suites to run automatically using purpose built software tools.

Execute those tests without manual intervention and compare what actually happened with what we expect

it to happen.

It's kind of like having a really efficient robot assistant that can run through all your test scenarios

without getting tired.

I'll give you a quick real world example.

So imagine you're working on an e-commerce website, and every time developers make changes, you need

to verify functionality like users ability to still log in products added to the cart, the payment

processing works order confirmation and verifying that email notifications are sent.

Doing this manually every time would be tedious, right?

So that's where test automation comes in.

Now let's talk about the good parts, meaning the advantages of test automation.

And believe me, there are quite a few.

The first advantage is efficiency.

So first off, you can run way more tests per build compared to manual testing.

Like I've seen teams go from running 50 manual tests per day to running thousands of automated tests

in just a few minutes or hours.

A second advantage is testing the impossible.

Automation lets you do things that would be practically impossible to test manually.

Think about testing how your system handles 1000 simultaneous users, verifying responses that happen

in milliseconds, running tests across multiple devices at the same time.

Testing systems remotely in different locations.

A third advantage is complex test cases.

You can create super complex test scenarios that will be really hard to do manually.

A forfeit advantage is speed tests can run much faster than a human executed test, like a test that

might take a human five minutes might take just a few seconds when automated.

A fifth advantage is removal of human error.

One thing I really love about automation is that it's not subject to human error.

You know how sometimes we might forget a step or get distracted while manually testing a scenario?

Well, automated tests do exactly the same thing every single time.

Another advantage is cost efficiency.

Once you set up test automation, it's typically more cost effective over time.

The initial investment might be higher, but once automated tests are running, they're often less costly

than repeated manual testing.

And another advantage is consistency and reliability.

Unlike humans, automated tests don't get tired, distracted, or make mistakes.

They execute tests the same way every single time.

This removes the variability that can sometimes creep in with manual testing and ensures a reliable

process.

Of course, automation is not without disadvantages and challenges.

One disadvantage is cost considerations.

Test automation can be expensive initially.

You might need to hire specialized automation engineers.

years.

Buy new hardware or tools.

Train your existing team.

I've personally worked with teams that struggle with this initial investment, but it usually pays off

in the long run.

Time investment.

You've got to be patient because setting up a good automation framework takes time.

It's like building a house.

You need a solid foundation before you can start adding bedrooms.

Maintenance.

Here's something people often overlook.

Test scripts need regular maintenance.

When your application changes, your automated tests may need to change too.

Rigidity of tests.

Automated tests can sometimes be less flexible.

For example, if your application undergoes frequent small changes, those tweets can cause automated

tests to fail, even if the app's functionality hasn't changed.

Keeping automated tests in sync with a constantly evolving codebase can be a challenge.

It may slow down development if not managed well.

Potential for introducing new bugs.

So it may come as a surprise, but test automation can introduce bugs.

Writing test scripts is like writing any other code, and it's susceptible to errors.

If a bug creeps into your automation code, it can lead to false positives or negatives.

Giving teams inaccurate feedback.

This can be really frustrating and time consuming to track down.

There are also limitations to test automation.

One limitation is that not everything can be automated.

You know how those tests that require human judgment, like evaluating if a user interface is intuitive?

Those scenarios still need manual testing.

What about verifying only what automated tests are programmed to do?

There can be numerous areas to verify, but each test is limited to testing a specific scenario which

may leave other scenarios unverified.

Machine interpretation.

Automated tests can only verify what machines can interpret.

They can't tell you if something looks right or feels right to users.

Test Oracle challenge.

You need to have a way to automatically verify results.

A test oracle is basically your mechanism for determining whether a test passed or failed, and is how

you know if the system behaved correctly.

And sometimes that's harder than it sounds like in situations where multiple valid answers could exist.

Or if you're testing something like a flight booking system where availability changes in real time.

So to wrap up, test automation is incredibly powerful, but it's not a magic solution.

The key is finding the right balance between automated and manual testing for your specific situation.

Remember, good test automation is kind of like having a reliable coworker who can handle all the repetitive

stuff, freeing up your human testers to focus on more creative and exploratory testing.

In the next video, we'll look at test automation in the software development lifecycle."