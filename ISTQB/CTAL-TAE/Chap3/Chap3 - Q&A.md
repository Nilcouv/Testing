## Q&A

### Question 1 - TAE-3.1.1 (K2) Explain the major capabilities in a test automation architecture

> [!question] In the gTAA (Generic Test Automation Architecture), which capability is responsible for adapting automated tests to the various components or interfaces of the SUT (System Under Test)?

- A) Test Generation
- B) Test Definition
- C) Test Adaptation
- D) Test Execution

> [!answer] C)
>
> [!Explanation]
> A is incorrect because test generation is an optional capability that supports the automated design of test cases based on a test model. It is focused on creating tests, not adapting them to interfaces.
> B is incorrect because test definition supports the definition and implementation of test cases and/or test suites. It separates the test definition from the SUT and/or test tools, but does not handle adapting tests to interfaces.
> C is correct because the test adaptation capability provides the necessary functionality to adapt the automated tests for the various components or interfaces of the SUT. It provides different adapters for connecting to the SUT via APIs, protocols and services, and serves as the bridge between the TAF (Test Automation Framework) and the SUT.
> D is incorrect because test execution supports test execution and test logging. It provides a test execution tool to run selected tests automatically, and a test logging and reporting component, but does not handle adapting tests to different interfaces.

### Question 2 - TAE-3.1.2 (K2) Explain how to design a test automation solution

> [!question] When designing a TAS (Test Automation Solution), which of the following is NOT a key aspect that should be addressed in the TAA (Test Automation Architecture)?

- A) Selecting test automation tools and tool-specific libraries
- B) Identifying connectivity and interface requirements
- C) Creating manual test cases for edge case scenarios
- D) Connecting to test management and defect management tools

> [!answer] C)
>
> [!Explanation]
> A is incorrect because selecting test automation tools and tool-specific libraries is a crucial aspect of the TAA: the tools and libraries provide the foundation for the automation solution.
> B is incorrect because identifying connectivity and interface requirements (firewalls, database connections, URLs/connections, mocks and stubs, message queues and protocols) is an essential part of designing the automation architecture.
> C is correct because creating manual test cases is not part of designing a test automation architecture. The TAA focuses specifically on the technical design of the automation solution, not on creating manual test cases.
> D is incorrect because connecting to test management and defect management tools is an important part of the TAA: it enables integration between the TAF (Test Automation Framework) and testing or defect-tracking processes.

### Question 3 - TAE-3.1.3 (K3) Apply layering of test automation frameworks

> [!question] In a layered TAF (Test Automation Framework), if an engineer wanted to add support for a new API (Application Programming Interface) authentication method across all applications being tested, which layer should they modify?

- A) Test Scripts layer
- B) Business Logic layer
- C) Core Libraries layer
- D) Test Execution layer

> [!answer] C)
>
> [!Explanation]
> A is incorrect because the test scripts layer contains specific test cases for the SUT (System Under Test). Adding authentication functionality here would not make it reusable across applications.
> B is incorrect because the business logic layer contains libraries specific to a particular application or SUT. Implementing the authentication method here would limit it to one application instead of making it available across all applications.
> C is correct because the core libraries layer contains libraries that are independent of any specific SUT and can be reused across multiple projects or applications. A new API authentication method used across all applications should be implemented there to enable reuse.
> D is incorrect because the test execution layer is not one of the standard layers in the TAF layering pattern discussed in the syllabus. The typical layers are test scripts, business logic and core libraries.

### Question 4 - TAE-3.1.4 (K3) Apply different approaches for automating test cases

> [!question] A test team wants to automate their regression test suite for an e-commerce application. They have a mix of technical and non-technical testers, and they want business analysts to be able to contribute to the automation effort. Which approach would be MOST suitable for their needs?

- A) Linear Scripting
- B) Capture/Playback
- C) Keyword-Driven Testing
- D) Test-Driven Development

> [!answer] C)
>
> [!Explanation]
> A is incorrect because linear scripting requires programming knowledge and does not provide a good way for non-technical team members to contribute. It is also hard to maintain and scale.
> B is incorrect because capture/playback is easy to start with, but very difficult to maintain for a regression suite that needs to be run regularly and maintained over time. It is also not a collaborative approach that would allow business analysts to contribute effectively.
> C is correct because KDT (Keyword-Driven Testing) allows both technical and non-technical team members to contribute. Test cases are defined as a list or table of keywords and test data, from a user's perspective, so business analysts and non-technical testers can create automated test cases. Technical team members implement the keywords; non-technical members design tests using those keywords.
> D is incorrect because TDD (Test-Driven Development) is a development approach primarily used by developers, not a testing approach that would allow non-technical testers and business analysts to contribute to the automation effort.
