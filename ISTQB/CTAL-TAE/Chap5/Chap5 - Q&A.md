## Q&A

### Question 1 - TAE-5.1.1 (K3) Apply test automation at different test levels within pipelines

> [!question] Which of the following statements is TRUE regarding the integration of system and integration tests into CI/CD pipelines?

- A) System integration tests should always be executed before component tests in the pipeline to identify integration issues early.
- B) There are two main approaches: executing tests as part of the deployment phase, or executing tests as a separate pipeline triggered by successful deployment.
- C) System tests cannot be implemented as quality gates because they take too long to execute.
- D) The only valid pipeline configuration is to have component tests in the build phase and system tests in the deployment phase.

> [!answer] B)
>
> [!Explanation]
> A is incorrect because system integration tests typically come after component tests, not before. The pipeline usually progresses from lower-level tests to component tests to higher-level tests.
> B is correct because there are two main approaches to integrating system-level tests into pipelines. The first is executing tests as part of the deployment phase, where tests act as quality gates that can automatically fail and roll back a deployment if needed. The second is executing tests as a separate pipeline triggered after successful deployment, which is useful when running different test suites on each deployment.
> C is incorrect because system tests can be implemented as quality gates. While they may take longer to execute than component tests, they are often crucial quality gates before allowing deployment to production.
> D is incorrect because there are many valid pipeline configurations depending on the project needs. The configuration mentioned is just one possibility, not the only valid approach.

### Question 2 - TAE-5.1.1 (K3) Apply test automation at different test levels within pipelines

> [!question] In a continuous integration/continuous deployment pipeline, which test level typically acts as the LAST quality gate before deployment to production?

- A) Component tests.
- B) Component integration tests.
- C) System tests.
- D) Configuration tests.

> [!answer] C)
>
> [!Explanation]
> A is incorrect because component tests are usually run early in the pipeline during the build phase, not as the last quality gate before production deployment.
> B is incorrect because component integration tests typically run after component tests, but before system tests. They verify that low-level components work together correctly, but do not test the system as a whole.
> C is correct because system tests typically act as the last quality gate before deployment to production. These tests verify that the entire system works as expected from an end-user perspective, ensuring that the complete system meets the requirements before being released to production.
> D is incorrect because configuration tests for the test automation framework or test automation solution are usually run during the build of the test automation project itself, not as a quality gate for the system under test for production deployment.

### Question 3 - TAE-5.1.2 (K2) Explain configuration management for testware

> [!question] When a test automation solution needs to support multiple releases of the System Under Test (SUT), which approach is LEAST likely to be effective?

- A) Using feature toggle configuration to determine which test suites to execute.
- B) Releasing testware with the same version as the SUT using tags or branches.
- C) Hard-coding test environment URLs and credentials directly in test scripts.
- D) Organizing test suites by purpose (smoke, regression, feature-specific).

> [!answer] C)
>
> [!Explanation]
> A is incorrect because using feature toggle configuration is a recommended practice that allows tests to adapt to different feature sets and different releases, enabling or disabling specific test suites based on which features are active in a particular release.
> B is incorrect because releasing testware with the same version as the SUT using tags or branches creates an exact match between the SUT version and the testware that can test it, making it easy to maintain consistency across releases.
> C is correct because hard-coding test environment URLs and credentials directly in test scripts is the least effective approach for supporting multiple releases of the SUT. This practice creates maintenance nightmares, since any change to URLs or credentials would require updating every test script individually, making it difficult to switch between environments or releases.
> D is incorrect because organizing test suites by purpose is a good practice that allows for running different types of tests, like smoke, regression, or feature-specific, at appropriate times in the development pipeline, contributing to efficient testing across releases.

### Question 4 - TAE-5.1.2 (K2) Explain configuration management for testware

> [!question] Which of the following best describes the relationship between test data and test environment in configuration management for testware?

- A) Test data should be identical across all test environments to ensure consistency.
- B) Test data can be specific to a test environment and may vary between environments based on their purpose.
- C) Test data should always be generated randomly at runtime to avoid configuration management issues.
- D) Test environments should adapt to the available test data, not the other way around.

> [!answer] B)
>
> [!Explanation]
> A is incorrect because having identical test data across all environments isn't always appropriate or efficient. Different environments often have different purposes, like quick developer testing versus comprehensive pre-production validation, and thus benefit from different types of test data.
> B is correct because test data can indeed be specific to a test environment and may vary between environments based on their purpose. For example, development environments might use a smaller, simpler data set, while staging environments might use more comprehensive data to test edge cases or performance. This allows each environment to serve its specific testing needs effectively.
> C is incorrect because while random data generation has its place in testing, always generating random data at runtime isn't a comprehensive solution for test data management. Predefined test data is often needed for consistent, reproducible tests, especially for regression testing.
> D is incorrect because it reverses the proper relationship in effective configuration management. Test environments are defined first based on testing needs, and appropriate test data is created or selected for each environment.

### Question 5 - TAE-5.1.3 (K2) Explain test automation dependencies for an API infrastructure

> [!question] What is the main advantage of contract testing in an API infrastructure?

- A) It eliminates the need for integration testing completely.
- B) It allows defects from underlying services to be found earlier in the SDLC and makes identifying their source easier.
- C) It guarantees that all API changes will be backward compatible.
- D) It replaces the need for API documentation by generating it automatically.

> [!answer] B)
>
> [!Explanation]
> A is incorrect because contract testing complements, but does not eliminate, the need for integration testing. While contract testing verifies that services can potentially work together according to their contracts, integration testing is still needed to verify they actually work together in practice.
> B is correct because the main advantage of contract testing is that defects occurring from underlying services can be found earlier in the software development lifecycle, and the source of these defects can be more easily identified. Contract testing verifies that services can communicate with each other according to their specified contracts, catching integration issues before the services are deployed together.
> C is incorrect because contract testing does not guarantee backward compatibility. It verifies compliance with the current contracts, but does not prevent teams from changing those contracts in non-backward-compatible ways. Teams would need additional governance processes to ensure backward compatibility.
> D is incorrect because contract testing uses API documentation or contracts as input; it does not replace or generate it. Good API documentation is a prerequisite for effective contract testing, not an outcome of it.
