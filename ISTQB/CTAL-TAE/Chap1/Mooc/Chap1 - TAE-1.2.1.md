# Mooc

## Explain how test automation is applied to across different SDLC Models

### Screen

> **Waterfall development**
>
> Need to complete each phase before moving to the next one.
> In waterfall, everything happens in a specific order:
>
> 1. Requirements (Blueprints)
> 2. Design (Planning the details)
> 3. Implementation (Construction)
> 4. Verification (Inspection)
> 5. Maintenance (Upkeep)

---

> **Test Automation in Waterfall**
>
> Start in or after the Implementation phase
>
> Like testing a car, it's only possible when it's mostly built
>
> Eg. government test project
>
> * Couldn't start automation until the 4th month
> * Test automation happened in a big chunk during verification
> * Required documentation for everything
> * Each phase needed formal approval

---

> **Test Automation in Waterfall**
>
> If we found major issues during automation going back to fix them was expensive and time-consuming
>
> Like finding foundation problems in a new home after you've already built the whole house

---

> **Waterfall - Pros and Cons**
>
> * Pros
>   * Stability of requirements - let us build automation tests without worrying about changes
>   * Documentation - Lots of documentation helps design thorough tests
> * Cons
>   * Late feedback - Issues discovered late are costly
>   * Rigid structure - Hard to update code and tests

---

> **V-model**
>
> 1. User requirements --(Planning and design)--> Acceptance testing execution
> 2. System requirements --(Planning and design)--> System testing execution
> 3. Global design --(Planning and design)--> Integration testing execution
> 4. Detailed design --(Planning and design)--> Component testing execution
> 5. Coding

---

> **Test Automation in V-model**
>
> Automation framework created for each test level
> Using house analogy, it's like having specialized tools for house inspections
>
> Eg. Project using V-model for medical device
>
> * Automated unit tests for individual component
> * Automated integration tests for component combinations
> * Automated systems tests for the entire device
> * Semi-automated acceptance tests for regulatory compliance

---

> **V-model - Pros and Cons**
>
> * Pros
>   * Early bug detection
>   * Structured approach - clear mapping between dev and testing
> * Cons
>   * Increased planning effort
>   * Potential for redundancy in tests across levels

---

> **Agile Development**
>
> Cycle: 1. Requirements, Analysis and design, implementation, test, evaluation
>
> Adaptation and improvisation while maintaining quality:
>
> * Continuous test automation
> * Cross functional collaboration
> * In-sprint automation
> * Code review and pair programming

---

> **Agile Automation Example**
>
> Ecommerce project
>
> * Developers wrote unit tests as they coded
> * Automation engineers created UI tests post-feature
> * All automated tests ran nightly
> * Failed tests fixed first thing in the morning
> * Could release to production multiple times per day

---

> **Agile model - Pros and Cons**
>
> * Pros
>   * Immediate feedback - allowing for rapid fixes
>   * Flexibility - framework adapt to change
>   * Collaboration - automation is a team effort
> * Cons
>   * High maintenance - frequent changes break tests
>   * Resource intensive - testers need strong coding skills and sprint time

---

> **Conclusion**
>
> 1. No one-size-fits-all approach
> 2. Adapt your automation strategy to your development model
> 3. Whether it's Waterfall, V-model, or Agile -- Timing and strategy matter
> 4. Implement automation thoughtfully

### Transcript

"Test automation in the software development life cycle, explaining how test automation is applied across

different software development life cycle models.

Now let's talk about how test automation fits into different software development life cycle models.

So you might be thinking is it test automation the same everywhere.

Well not exactly.

The way we approach automation can vary significantly depending on the development model we're using.

Let's break down how automation works in each major development approach, starting with the classic

waterfall approach.

So in waterfall development, we can think of it like building a house where you need to complete each

phase before moving on to the next one.

And waterfall.

Everything happens in a specific order.

First you get the requirements, which is like creating the blueprints for the house.

Next we do the design phase, which is planning the details.

Then we move on to implementation which is like the actual construction.

Then we do verification which is inspection.

And finally we do maintenance which is like upkeep for the house, like changing dirty air filters throughout

the home.

Here's the thing about test automation and waterfall.

It typically kicks in during or after the implementation phase.

Why?

Well, it's like trying to test a car.

You can't really test it until it's mostly built, right.

So let me give you a real life example.

I once worked on a government project where we were developing a tax processing system.

So in this waterfall cell project, We couldn't start running automated tests until the fourth month.

All our test automation happened in a large chunk during the verification phase.

We had to document everything and each phase needed formal approval before moving forward.

So the challenge was if we found major issues during automation, going back to fix them was expensive

and time consuming.

Kind of like finding foundation problems in a new home after you've already built the whole house.

If we look at the waterfall from a pros and cons perspective, the pros are stability of requirements.

Because requirements are defined upfront and remain relatively stable.

We can develop a comprehensive set of automated tests without worrying about constant changes.

Documentation.

There's usually a lot of documentation which can help in designing thorough automated tests.

The cons are late feedback, as we mentioned, since testing comes during or after implementation.

Many issues we find, automated or not, are discovered late in the process.

This can make fixes more costly and time consuming.

Rigid structure.

The linear nature doesn't allow for much flexibility if changes are needed.

It can be a hassle to update both the code and the automated tests.

Now let's talk about the V model.

I like to think of this as waterfalls smarter cousin.

Instead of waiting until the end to think about testing the V model plans test from the very beginning.

In the v-model, as you define high level requirements, you plan acceptance tests.

As you create detailed requirements, you plan system tests as you design components, you plan integration

tests, and as you code, you plan component tests.

The cool thing about automation in the V-model is that you can create automation frameworks for each

test level.

Going back to our house analogy, it's like having different specialized tools for different parts of

the house inspection.

There was this one project I worked on where we worked on a medical device that used a V model.

We had automated unit tests for individual components, automated integration tests for component combinations,

Automated system tests for the entire device.

And semi-automated acceptance tests for regulatory compliance.

Each level had its own automation framework, but they all worked together seamlessly.

The pros of the v-model are.

Early bug detection.

By aligning testing with development phases, we catch issues sooner.

Structured approach the clear mapping between development and testing phases helps in organizing our

automated testing efforts.

The downsides to V-model are.

Increased planning effort.

Coordinating between development and testing requires more upfront planning.

Potential for redundancy.

Sometimes automated tests at different levels might overlap, causing redundancy.

Now let's look at agile development in agile development.

This is where things get really exciting.

Unlike the waterfall or V-model, agile is all about adaptation and improvisation while maintaining

quality in agile development.

Test automation happens continuously.

Everyone collaborates, which eliminates silos.

The aim is for sprint automation, meaning automating tests within the same sprint as the development.

There are lots of code reviews and pair programming within the team.

In a recent e-commerce project I worked on, our developers wrote unit tests as they coded.

Our automation engineers created UI tests right after features were developed.

We ran all of our automated tests every night, and any failed tests were looked at and fixed.

First thing the next morning and we could release a production multiple times per day.

So the advantages of agile are immediate feedback.

Automated tests quickly identify issues allowing for rapid fixes.

Flexibility automation frameworks can adapt to changing requirements and frequent code updates.

Collaboration.

Eliminating silos means everyone contributes to the quality, making automation a team effort.

And on the flip side, challenges in agile are high maintenance.

Frequent changes in the code base can lead to broken tests EST, requiring constant updates to the automated

test suite.

Resource intensive in sprint automation demands that testers have strong coding skills, and that sufficient

time is allocated within sprints for test development.

So the main idea is there's no one size fits all approach to test automation.

The key is understanding your development model and adapting your automation strategy accordingly.

Whether you're in a strict waterfall environment, a structured v-model project, or a fast paced agile

team, automation can be your best friend if you implement it thoughtfully and at the right time.

In the next video, we will talk about selecting suitable test automation tools for a given system under

test."
