## Q&A

### Question 1 - TAE-2.1.1 (K2) Describe the configuration needs of an infrastructure that enable implementation of test automation

> [!question] Which of the following is NOT considered a key aspect of designing for testability in a SUT (System Under Test)?

- A) Observability - providing interfaces that give insight into the SUT
- B) Controllability - providing interfaces that can be used to perform actions on the SUT
- C) Scalability - ensuring the SUT can handle increasing numbers of test executions
- D) Architecture transparency - providing clear, understandable components and interfaces

> [!answer] C)
>
> [!Explanation]
> A is incorrect because observability is one of the three key aspects of designing for testability: the SUT needs to provide interfaces that give insight into the SUT, allowing test cases to determine whether actual results match expected results.
> B is incorrect because controllability is a key aspect of designing for testability: the SUT needs to provide interfaces that can be used to perform actions through UI elements, function calls, communication elements, etc.
> C is correct because while scalability is an important quality attribute of a system, it is not listed as one of the key aspects of designing for testability in the syllabus.
> D is incorrect because architecture transparency is a key aspect of designing for testability: the documentation of an architecture needs to provide clear, understandable components and interfaces that give observability and controllability at all test levels and foster quality.

### Question 2 - TAE-2.1.2 (K2) Explain how test automation is leveraged within different environments

> [!question] In which environment would it be most appropriate to perform white box testing using an IDE (Integrated Development Environment)?

- A) The production environment
- B) The local development environment
- C) The pre-production environment
- D) The integration environment

> [!answer] B)
>
> [!Explanation]
> A is incorrect because testing in production generally involves monitoring real user interactions rather than white box testing. Production environments are used to assess functional and non-functional qualities in real time, often using techniques like canary releases or A/B testing.
> B is correct because the local development environment is where white box testing can be performed using an IDE to identify poor coding and quality problems as early as possible.
> C is incorrect because the pre-production environment is primarily used for non-functional testing and user acceptance testing by business stakeholders, not for white box testing.
> D is incorrect because the syllabus explicitly states that in the integration environment there is no white box testing, only black box testing. This environment is used for system integration and/or acceptance testing on a fully integrated SUT.

### Question 3 - TAE-2.2.1 (K4) Analyze a system under test to determine the appropriate test automation solution

> [!question] When analyzing a SUT (System Under Test) to determine the appropriate test automation solution, which of the following is NOT mentioned as a consideration in the requirements gathering process?

- A) Which test roles and skill sets should be supported?
- B) Which test levels should be supported?
- C) Which programming language should be used for implementation?
- D) Availability of test data and its quality?

> [!answer] C)
>
> [!Explanation]
> A is incorrect because which test roles and skill sets should be supported is explicitly listed among the syllabus requirements to consider.
> B is incorrect because which test levels should be supported is explicitly listed among the syllabus requirements to consider.
> C is correct because while the programming language is an important aspect of implementing a test automation solution, it is not specifically listed in the syllabus as one of the requirements to consider when analyzing a SUT to determine the appropriate test automation solution.
> D is incorrect because availability of test data and its quality is explicitly listed among the syllabus requirements to consider.

### Question 4 - TAE-2.2.2 (K4) Illustrate the technical findings of a tool evaluation

> [!question] When creating a comparison table to illustrate the technical findings of a tool evaluation, which approach would be LEAST effective?

- A) Listing the tools in the columns and the requirements in the rows
- B) Including information about the properties of each tool regarding each requirement
- C) Providing only the best-performing tool for each requirement without comparison
- D) Including information about priorities of requirements

> [!answer] C)
>
> [!Explanation]
> A is incorrect because this is correct practice: the syllabus states that the comparison table lists the tools in the columns and the requirements in the rows.
> B is incorrect because this is correct practice: the syllabus states that the cells contain information about the properties of each tool regarding each requirement.
> C is correct because this approach is the least effective: it defeats the purpose of a comparison table, which is to show a comprehensive view of how each tool performs against all requirements. Without comparative information, stakeholders cannot make an informed decision, especially when trade-offs are necessary.
> D is incorrect because this is correct practice: the syllabus mentions that cells should contain information about priorities, allowing stakeholders to understand which requirements are more important than others.
