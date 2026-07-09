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
> C is correct because it's a fundamental limitation of test automation (unability to verify user experience/ handling scenario needing human judgement). 
> A and B are incorrect because they are disadvantages of test automation (cost effort consideration and ), not limitations. 
> D is incorrect because Test automation execute much faster than manual testing.

### Question 2 - TAE-1.2.1 (K2) Explain how test automation is applied across different software development lifecycle models

> [!question] In an Agile project using a CI/CD pipeline, which of the following test automation implementation approaches would be MOST effective?

- A) Develop comprehensive automated test suites after all features are implemented.
- B) Create automated tests during dedicated testing sprints separate from development.
- C) Implement automated tests incrementally within the same sprint as feature development.
- D) Wait until the system stabilizes before investing in automation infrastructure.

> [!answer] C)
> 
> [!Explanation]
> C is know as "Sprint Automation" approach, which aligns with agile principles and CI/CD practices by providing immediate feedback and maintaining the same pace as development.
> A is incorrect because it's Waterfall-like approach
> B is incorrect because it disconnects development and testing
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
> B is correct because it offers the best coverage for different testing needs and specific purposes.
> A is incorrect because a single tools rarely excel at all types of tests for complex system
> C is incorrect because it will create great constrains on the team (time consuming, compliance risks)
> D is incorrect because playback tools don't cover handle API or performance testing

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

