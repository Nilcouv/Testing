## Q&A

### Question 1 - TAE-1.1.1 (K2) Explain the advantages and disadvantages of test automation

> [!question] A large e-commerce company is implementing test automation for their critical payment processing system. Which of the following statements BEST describes a key limitation of test automation in this context?

- A) The automated tests will require significant maintenance when the system is updated.
- B) The automated tests will be more expensive to create than manual tests initially.
- C) The automated tests can only verify outcomes that can be programmatically evaluated.
- D) The automated tests will run more slowly than manual tests would.

> [!answer] C)
> 
> [!Explanation] 
> A is incorrect because it is a disadvantage of test automation (maintenance effort), not a fundamental limitation.
> B is incorrect because it is a disadvantage of test automation (cost consideration), not a limitation.
> C is correct because it is a fundamental limitation of test automation (inability to verify user experience / handling scenarios needing human judgement).
> D is incorrect because test automation executes much faster than manual testing.

### Question 2 - TAE-1.2.1 (K2) Explain how test automation is applied across different software development lifecycle models

> [!question] In an Agile project using a CI/CD pipeline, which of the following test automation implementation approaches would be MOST effective?

- A) Develop comprehensive automated test suites after all features are implemented.
- B) Create automated tests during dedicated testing sprints separate from development.
- C) Implement automated tests incrementally within the same sprint as feature development.
- D) Wait until the system stabilizes before investing in automation infrastructure.

> [!answer] C)
> 
> [!Explanation]
> A is incorrect because it is a Waterfall-like approach.
> B is incorrect because it disconnects development and testing.
> C is correct because it is known as the "in-sprint automation" approach, which aligns with Agile principles and CI/CD practices by providing immediate feedback and maintaining the same pace as development.
> D is incorrect because it introduces delays and risk by waiting, contradicting integration principles.

### Question 3 - TAE-1.2.2 (K2) Select suitable test automation tools for a given system under test

> [!question] A team is developing a complex healthcare system with multiple interfaces and strict regulatory requirements. The system includes both web and mobile interfaces, real-time data processing, and integration with external medical devices. Which combination of test automation tools would be MOST suitable?

- A) A single comprehensive commercial test automation tool that covers all testing needs.
- B) Multiple specialized tools: API testing tool, UI automation tool, and performance testing tool.
- C) Custom-built automation framework with minimal external tool dependencies.
- D) Record-and-playback tool with built-in support for multiple platforms.

> [!answer] B)
> 
> [!Explanation]
> A is incorrect because a single tool rarely excels at all types of tests for a complex system.
> B is correct because it offers the best coverage for different testing needs and specific purposes.
> C is incorrect because it will create great constraints on the team (time consuming, compliance risks).
> D is incorrect because record-and-playback tools do not handle API or performance testing.

### Question 4 - TAE-1.2.1 (K2) Explain how test automation is applied across different software
development lifecycle models

> [!question] Which of the following scenarios would present the BIGGEST challenge for test automation implementation in a V-model development lifecycle?

- A) The system requires Testing on multiple browser versions.
- B) Test data needs to be maintained across test environments.
- C) Requirements are frequently changing after test automation development has started.
- D) The system has complex security requirements.

> [!answer] C)
> 
> [!Explanation]
> A is incorrect because it's a technical challenge not specific to the V-model and manageable within
> B is incorrect because it's a common challenge not specific to the V-model and can be planned within
> C is correct because changing requirement after the start of test automation create greate disruption and require significant rework
> D is incorrect because it's not specific to the V-model and can be incorporated within

### Question 5 - TAE-1.2.2 (K2) Select suitable test automation tools for a given system under test

> [!question] A startup is developing a mobile application and needs to implement test automation. Which of the following factors is MOST critical when selecting automation tools?

- A) The availability of record-and-playback features for quick test creation.
- B) The programming language compatibility with the development team's skills.
- C) The cost of the automation tool licenses.
- D) The popularity of the tool in the market.

> [!answer] B)
> 
> [!Explanation]
> A is incorrect because it limits advanced testing, long-term and maintenance capabilities
> B is correct because it allows collaboration between developers and testers affecting team's ability to maintain and extend test automation framework, in a resources limited context such as startups.
> C is incorrect because technical needs are more important than startup budget consideration, and my lead to unadapted tools selection
> D is incorrect because tools popularity doesn't mean it's suitable for the project's specificities and team capabilities

### Question 6 - TAE-1.1.1 (K2) Explain the advantages and disadvantages of test automation

> [!question] In a Waterfall project, when is the MOST appropriate time to begin developing automated regression tests?

- A) During the requirements phase to ensure early test coverage.
- B) In parallel with system implementation to enable continuous Testing.
- C) After system testing to focus on known functionalities.
- D) During the maintenance phase when the system is stable.

> [!answer] B)
> 
> [!Explanation]
> A is incorrect because it is too early.
> B is correct because it allows issues early detection, better test coverage, more resource efficient and assure test automation readiness for regression testing.
> C is incorrect because it is too late.
> D is incorrect because it is far too late.

### Question 7 - TAE-1.1.1 (K2) Explain the advantages and disadvantages of test automation

> [!question] A test manager is evaluating whether to implement test automation for a new financial trading platform. The platform requires real-time validation of thousands of concurrent transactions, complex regulatory compliance checks, and must operate 24/7. However, the team has limited automation experience and a tight budget. Which of the following BEST describes the primary advantage that would justify the investment in test automation for this scenario?

- A) Test automation will eliminate the need for manual testers, reducing overall project costs.
- B) Test automation can execute tests that would be impossible to perform manually, such as real-time validation of thousands of concurrent transactions.
- C) Test automation will find more defects than manual testing because it can check all possible test combinations.
- D) Test automation will make the test scripts more adaptable to changes in requirements.

> [!answer] B)
>
> [!Explanation]
> A is incorrect because test automation supplements manual testing rather than eliminating manual testers.
> B is correct because it is impossible to validate thousands of concurrent transactions manually. This capability directly addresses the critical requirement of the financial trading platform.
> C is incorrect because automation cannot check all possible test combinations.
> D is incorrect because automated tests are typically less adaptable to requirement changes, not more.

### Question 8 - TAE-1.2.1 (K2) Explain how test automation is applied across different software development lifecycle models

> [!question] A development team is transitioning from a traditional V-model to Agile development. They have an existing test automation framework that was designed for the V-model approach. Which of the following statements BEST describes how the test automation approach needs to change?

- A) The existing test automation framework should be discarded because V-model automation is incompatible with Agile.
- B) Test automation should be postponed until after several sprints are complete to ensure stable requirements.
- C) The team should aim for in-sprint automation with continuous execution, involving TAEs and business representatives in roadmap planning.
- D) Test automation should only focus on acceptance testing since component testing happens too quickly in Agile.

> [!answer] C)
>
> [!Explanation]
> A is incorrect because existing frameworks can often be adapted rather than discarded.
> B is incorrect because postponing automation contradicts Agile principles of early and continuous feedback.
> C is correct because the Agile model aims for in-sprint automation (tests are automated within the same sprint as feature development). It requires close collaboration between TAEs, developers and business representatives, emphasizes continuous test execution and breaking silos between teams.
> D is incorrect because component testing remains important in Agile and should also be automated.

### Question 9 - TAE-1.1.1 (K2) Explain the advantages and disadvantages of test automation

> [!question] A test automation engineer is explaining to stakeholders why certain quality characteristics cannot be verified through test automation. Which of the following combinations of limitations BEST supports this explanation?

- A) Test automation can only verify machine-interpretable results and requires clear test oracles; therefore, subjective qualities like user experience cannot be automated.
- B) Test automation is too expensive and time-consuming; therefore, it is better to use manual testing for all quality characteristics.
- C) Test automation tools lack the capability to interact with modern user interfaces; therefore, GUI testing must be done manually.
- D) Test automation can only run pre-programmed tests; therefore, it cannot adapt to changing requirements during execution.

> [!answer] A)
>
> [!Explanation]
> A is correct because it identifies two fundamental limitations of test automation (ability to check machine-interpretable results, and requirement for automated test oracles). Subjective quality characteristics like usability, user experience or aesthetic appeal cannot be checked automatically.
> B is incorrect because cost is a disadvantage, not a fundamental limitation on what can be verified.
> C is incorrect because modern automation tools can interact with user interfaces.
> D is incorrect because inability to adapt during execution is a disadvantage of rigidity, not the core reason why subjective qualities cannot be automated.

### Question 10 - TAE-1.2.2 (K2) Select suitable test automation tools for a given system under test

> [!question] A company is developing a multi-platform SUT that includes a web application, mobile apps (iOS and Android), and backend web services. The test team consists of manual testers with basic programming knowledge. Which test automation tool selection approach would be MOST appropriate?

- A) Select a single commercial tool that claims to support all platforms to minimize tool diversity.
- B) Choose open-source tools for each platform type and train the team in multiple programming languages.
- C) Select low-code or no-code solutions that match the team's limited programming experience.
- D) Focus only on API testing tools since they provide the best return on investment.

> [!answer] C)
>
> [!Explanation]
> A is incorrect because a single tool rarely excels across all platform types.
> B is incorrect because training the team in multiple programming languages exceeds their current skill level.
> C is correct because selecting low-/no-code solutions is the most appropriate approach for a team with limited programming experience.
> D is incorrect because focusing only on API testing would leave web and mobile interfaces uncovered.

### Question 11 - TAE-1.2.1 (K2) Explain how test automation is applied across different software development lifecycle models

> [!question] In a waterfall project, the test automation team wants to begin developing automated tests early in the project lifecycle. However, the implementation phase hasn't started yet. Which of the following BEST describes when and how test automation can be effectively implemented in a waterfall model?

- A) Test automation must wait until the verification phase when all software components are ready for testing.
- B) Test automation implementation can happen in parallel to the implementation phase, with test execution during verification.
- C) Test automation should begin during the requirements phase to maximize efficiency.
- D) Test automation in waterfall is not recommended; the team should switch to Agile.

> [!answer] B)
>
> [!Explanation]
> A is incorrect because test automation development can start before the verification phase.
> B is correct because the implementation of test automation happens in parallel or after the implementation phase, according to the syllabus, while tests are run during the verification phase.
> C is incorrect because starting during requirements is too early without implementable components.
> D is incorrect because test automation is applicable in waterfall; switching methodology is not required.

