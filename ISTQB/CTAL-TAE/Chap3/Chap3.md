

---

# Notes

## Test Automation Architecture - Introduction

This chapter explore archtecture concepts of Test Automation Implementation, such as:

- gTAA (Generic Test Automation Architecture)
*and major capabilities. Provide a high level framework on how test automation communicate with other systems*
- TAS (Test Automation Solution) Design
*Using on functional, non-functional and technical requirements*
- TAF (Test Automation Framework) Layering
*To organize code into layers, each with a specific responsibility (test scripts, business logic, libraries)*
- Approaches to Automate Test Cases
*From capture/replay, Linear Scripting to Structured Scripting, DDT (Data Driven Testing) and BDD (Behavior Driven Development).*
- Design principles and patterns
*to professionnalize code writing*

## Explain the Major Capabilities in a Test Automation Architecture

### gTAA (Generic Test Automation Architecture)

gTAA (Generic Test Automation Architecture) is a high level design concept that gives an abstract view of how test automation cummunicates with other systems. (It shows the big picture of how everything is connected together)

Ex. Designing a TAA (Test Automation Architecture) for a banking application. It helps to understand how automation interact with the banking application, but also test management system, CICD pipppeling and our configuration management system. It helps to visualize those connections and plan accordingly.

**Figure 1 : diagramme gTAA**

```mermaid
flowchart LR
    GP["Gestion<br/>de projet"]
    GT["Gestion<br/>des tests"]
    GC["Gestion de<br/>configuration"]
    SUT["Système<br/>sous test"]
    
    subgraph TAF["Framework d'automatisation des tests"]
        direction RL
        Gen["Génération<br/>des tests"]
        Def["Définition<br/>des tests"]
        Exec["Exécution<br/>des tests"]
        Adapt["Adaptation<br/>des tests"]
    end
    
    GP <--> TAF
    GT <--> TAF
    GC <--> TAF
    SUT <--> TAF
```
gTAA represents multiple interfaces interacting with the test automation framework.

### The interfaces of gTAA

- SUT interface : It connects the framework to the system being tested (ex. web elements, APIs). ex. for banking application, this interface define how automation interact with web elements of a web application (frotn end), and API call (backend).
- Project management interface : Tracks automation progress (ex. Jira integration)
- Test mangaement interface : Maps manual test cases to automated tests. It helps to maintain relationships between initial manual test cases  after automation is implemented.
- Configuration management interface : Manage CI/CD pipelines, environements, and versioning. It helps to manage versioning and deployment for automation code. Ex. project where test management interface is not properly defined. Tracing automated tests with manual test cases become difficult, wasting weeks to reconcile the information.

### Layers of the TAF (Test Automation Framework)

Capabilities provided by test automation tools and libraries:

- Test generation capabilty : Automatically designs test cases from models (e.g., model-based testing > approach modeling the system behavior to generate automatically test cases from the model with a tool. like asking a computer to find all the path for a given map. ex. telecommunication project where hundreds of test cases where generated from a state model of how calls should be routed for a complex call routing system, saving weeks of work and covering all possible scenarios. test generation is optional because all project does not require this level of sophistication)
- Test definition capability : Support définition and implementation of test cases and/or test suites (ex. separation of test definition and SUT/tools). this capabilities separates the definition from the SUTand/or test tools (define where we want to test). It separates high level test (ex. login, logout) from low level test (ex. enter username, password, etc.). It creates the blueprint for automation (its like a recipe to follow to create the automated test). ex. healthcare project, comprehensive test definition layers allowing BA (business analyst) to define tests in excel using keywork driven approach. Which are Test automation framework translatable into executable code. this seperation allow non technical team member to contribute to the test definition process.
- Test execution capability : It provides execution tools to support running test and record results, such as scheduling running tests at a specific time, running parallel tests to save time, handling test dependencies to execute specific tests first, managing test data, reporting test results in a meaningful way, etc. ex. e-commerce project, where test capability of the tool allows runing 500+ tests nightly, in 2 hrs, by executing in parallel multiple tests accros multiple browsers and environments.
- Test adaptation capability : Adapt tests to different components/interfaces of the SUT (ex. adapters for different APIs, protocols, services). ex. SUT with both a web interface and a mobile app, test adpatation layer will provide component to interact with both interfaces, using different tools or libraries for each. Is the difference between a brittle solution breaking at every UI change and a robust solution withstanding frequent changes to the SUT. ex. Healthcare project, test adaptation layer abstracting the mean interacting with the system, allowing to only update the adaptation layer after a complete UI redesign, while test definition remained unchanged.

Ex. Building a TAS (Test Automation Solution) for a online banking application:

- Test Generation :  use of a model-based testing tool to generate test cases for complex workflows (ex. funds transfers between accounts).
- Test Definition : Define test cases in a structure way using keyword driven or date driven approach, specifying what needs to be tested.
- Test Execution : Setting up framework to execute tests automatically, as part of the nightly build process and generate report.
- Test Adaptation : Adapters creation allowing tests to interact with web interface, mobile app and APIs of the banking application.

Implemanting this capabilities creates a comprehensive TAS, able to test all aspects of the banking application.

### Conclusion

1. gTAA provides abstract view of automation communication between automation and connected systems.
2. Four key interfaces:
    - SUT interface
    - Project management interface
    - Test management interface
    - Configuration management interface
3. Core capabilities:
    - Test generation
    - Test definition
    - Test execution
    - Test adaptation

Understanding theses capabilities is crucial for designing effective TAS, able to scale with the project, and adapt to changes in the SUT.

## Explain How to Design a Test Automation Solution

### What is a TAS (Test Automation Solution)?

is the complete package/ everything you need for automating testing activities (beyond just tools/scripts) and define by 3 types of requirements:
1. Functional requirements of SUT
2. Non-functional requirements of SUT
3. Technical requirements

Ex. healthcare application, 
- functional requirements are like "users must be able to schedule appointment" and "doctores must be able to view patient records""
- non-functionnal requirements are like "security : must be compliant with HIPAA" and " performance : must handle 10 000 concurrent users"
- technical requirements are like " compatibility : support specific browsers and operating systems"

### Imptementing a TAS

- Tool Options :
  - Commercial tools (pâid)
  - Open-source tools (free)
  - Combination of both (most common - no single tool can cover all testing activities needs)

Ex. healcare project, used 2 tools : Tricentis Tosca (UI testing - strong support for healtcare industry regulations), Jmeter (performance testing - good at simulating heavy users loads)

Note: Always need to develop some custom components or adapters specific to your SUT. (every application has its unique characteristics. offshell tools won't perfectly addres all your needs)

### Role of TAA (test automation architecture)

Defines the technical design for the automation solution (like blueprint/master plan for autoimation efforts).

TAA must address the following key aspects:

- Selecting tools/libraries
- Developing plugins/components
- Identifying connectivity/interfaces requirements
- Connecting to test/defect management tools
- Utilizing version control

#### Selecting tools/libraries

Most critical decision. 

Ex. A project, tool selected based on team familiarity, tool was not adapted for API testing representing a major part of the testing effort. ended up by switching to another tool mid project, costing a lot of time and effort.

When selecting, consider:

- Application type (web, mobile, API, etc.)
- Testing needs (UI, API, performance, security, etc.)
- Team skills
- Budget
- Integration capabilities

Ex. For testing React frontend and REST API, you may select:

- Selenium and RestAssured, if the team is familiar with Java
- Cypress and Postman, if the team is familiar with Javascript

#### Developing plugins/components

Project may require to develop custom plugins/components to extend the tool functionnality and capabilities to cover specific SUT needs. pretty common, no off the shelf solution can cover all specific needs of SUT.

Ex. Ecommerce project, application had unique checkout process, selected testing tool unable to properly interect with those process, was forced to develop a custom component understanding the specific dom structure of the checkout page to reliably interact with.

### Identifying connectivity/interfaces requirements*

often overlooked until it's too late. have too identify all connectivity and interfaces requirements from the get go for TAS

Includes:

- Firewall configurations (did testing require access system accross firewall?)
- Database connections (does automation need to verify data in database?)
- URL/endpoints (what endpoints does automation need to access?)
- Mocks/stubs (Do you need to simulate components unavailable ?)
- Message queues (is system using asynchronous messaging ?)
- Protocols (What communication protocols does SUT use ?)

Ex. setting up TAF (Test Automation Framework), some of the connections were blocked by firewall, had to redesign part of the TAS to comply with customer security constraints.

### Connecting to test/defect management tools

TAS doesn't exist in isolation, have to connect to test management (TestRail) and defect management (Jira) tools.

Ex. On test failures, auto-create jira tickets with screenshots/logs AND/OR update test cases status in TestRail. (save time and increase testing reliability)

### Utilizing version control

Have to consider how manage automation code (like development), which implies selecting:

- version control system (Git, SVN, etc.)
- organized repository structure
Establishing branching strategy (feature, release, hotfix)
defining processes for code reviews, merges, and releases

EX. Project where repository structure was badly planned, ended up with unwieldy monolithic repository, problem increase as the project grew, had to refactor into multiple repositories organized by test level, unit, API and UI.

### Real world example

Ecommerce website automation:
- Requirements:
  - Functional : Browse products, checkout
  - Non-functional : Holiday traffic, <2sec load time
  - Technical : Chrome/Firefox/Safari, Mobile
- Tools :
  - Selenium webdriver (UI testing)
  - Jmeter (performance testing)
  - RestAssured (API testing)
  - Browserstack (cross browser testing)
- Custom components :
  - Shopping cart wrapper
  - Custom reporting (aggregate result from different test type)
- Connectivity requirements :
  - DB access (verify order placement)
  - Mock payment gateway (checkout testing)
  - API endpoint (product catalog testing)
- Tool integration : 
  - Jira (tickets manager to manage defects)
  - TestRail (test manager to manage test cases)
- Version control :
  - Git (reposity organized by test type)
  - Jeckins (CI/CD pipeline for continuous integration)
  - Docker (create controled environments)

### Common pitfalls to avoid

1. Tool first approach - selection based on tool usage rather than testing needs
2. Ignoring maintanability - Bad TAS architecture planning making it unmaintainable and hard to scale
3. Insufficient abstraction - Granular tests creation, limiting test reuse and maintanability. break with every UI change..
4. Neglecting reporting - minimal investment limiting repprting capabilities and increasing difficilty to interpret test results.
5. Siloed approach - TAS development not integrated with development process/ SDLC. 

### Conclusion

TAS design is more than selecting tools and writing scripts. It requires :

* Understanding SUT requirements
* Right mix of tools + custom components
* Comprehenbsive connectivity planning
* Integration with testing/dev ecosystem
* Proper code management

Test Automation is a journey, not a destination (evolve with the application, emergence of new technic, etc.)

## Apply Layering of Test Automation Frameworks

### What is a TAF (Test Automation Framework)?

TAF (Test Automation Framework) is the frame of a TAS (Test Automation Solution). It's like a house's bleuprint determining the placement and the function of each room. It includes :

- Test harness/runner -is the component executing the tests (like the conductor of an orchestra telling when to start and coordinating everything)
- Test libraries - are the collection of reusable code, that help to perform common actions of the tests (ex. fill a field, click a button, etc.). You may have several libraries to handle different types of actions, like interacting with a database, or for handling complex UI components.
- Test scripts -  are the automated tests (steps-by-steps instructions  verifying the application works as expected)
- test suites - are the collection of test scripts, that are runned together.

Layering avoid monolithic test script (ex 2000 line script), promoting maintanability and reusability of test code.

### The Three Main Layters
#### TAF layers

```mermaid
flowchart TD
    A["Test Scripts"] --> B["Business Logic"] --> C["Core Libraries"]
```

Layers are distinct boprders for code with similar purposes (like organizing a kitchen where plates, glasses and ustensiles are stored separately). The goal is to organize test automation code by similar functions to improve maintainability and reusability of code. The industry standard is to use 3 main layers (Keep it simple), which are:

- Test scripts layer - Sit at the top of the framework. Focus on WHAT to test. its purpose is to provide a repository of SUT test cases and organize them into test suites. It contains test scripts verifying specific functionnality of the application. (ex. testing ecommerci site, test script for longin functionnality, product search, adding items to cart, check out process, etc.). Must call the services of the business logic layer to perform the tests, never the core libraries layer.

```python
def test_valid_login():
  # This calls methods from business logic layer
  login_page.enter_username("test@example.com")
  login_page.enter_password("password")
  login_page.click_login_button()
  
  # Verify the result
  assert dashboard_page.is_displayed(), "Dashboiard should be displayed after login"
```

- Business logic layer - Sit at the middle of the framework. Focus on HOW to test for the specific SUT. Contains all the librairies specific to the application, which inherited or use the core libraries, and are customized to the SUT. Layer also used to set up  the TAF (Test Automation Framework) under specific SUT and handle specific configurations.

```python
class LoginPage(BasePage): # Inherits from a class in Core Libraries.
  def enter_username(self, username):
    self.find_element(By.ID, "username_field").send_keys(username)

  def enter_password(self, password):
    self.find_element(By.ID, "password_field").send_keys(password)

  def click_login_button(self):
    self.find_element(By.ID, "login_button").click()
```

- Core libraries layer - Sit at the base of the framework. contains all the librtairies independant/non-specific to any SUT. are the generic reusable component useable in any project with the same technology stack ( SUT-agnostic tools. ex. Webdriver, API clients.). May ave several specific libraries for specific uses and needs (interacting with web browser, making api calls, working with database, or logging test results, etc.).

```python
class BasePage:
  def __init__(self, driver):
    self.driver = driver

  def find_element(self, by, value):
    return self.driver.find_element(by, value)

  def waint_for_element(self, by, value, timeout=10):
    # implement wait a wait logic
    pass
```

### How these layers interact

- test scrpts layer define WHAT to test (login process)
- business logic layer define HOW to test (enter username, password, click login button)
- core libraries layer provide the tools to perform the actions (find element, enter text, click button, etc.)

this approach Separate responsabilities, make code more maintainable and flexible.
Ex. ID username change, ojnly business logic must be updated. Test scripts and core libraries remain unchanged.

### Scaling test automation

```mermaid
flowchart LR

    subgraph P1["Project #1"]
        A1["App #1 Test Scripts"] --> B1["App #1 Business Logic"]
        A2["App #2 Test Scripts"] --> B2["App #2 Business Logic"]
    end

    subgraph P2["Project #2"]
        A3["App #3 Test Scripts"] --> B3["App #3 Business Logic"]
    end

    C["Core Libraries"]
    B1 --> C
    B2 --> C
    B3 --> C
```

Core libraries enable reuse accross projets (ex. new project, instead of starting from scratch, they leverage the same core libraries).

Ex. Financial services company, centralize a test engineer team for all the organization maintaining a core librairy, each product team build specific business logic and test scripts on top of these core libraries. Allow to get up and running test automation much faster for new project.

### Real World Example : E-commerce testing

Building TAF for e-commerce website:

1) Scripting layer with test cases such as:

  - Test_search_functionality,
  - Test_add_to_cart,
  - Test_checkout_process,
  - Test_account_creation.

2) Business logic layer have classes specific to SUT:

- HomePage with methods such as :
  - search_for_product,
  - navigate_to_category,
  - etc.
- ProductPage with methods such as :
  - add_to_cart,
  - select_size,
  - etc.
- CartPage with methods such as :
  - Proceed_to_checkout,
  - Update_quantity,
  - etc.
- CheckoutPage with methods such as :
  - enter_shipping_info,
  - enter_payment_info,
  - etc.
  
3) Core libraries layer includes:

  - A webdriver wrappers handling browser initialization, navigation, finding elements, etc.
  - A REST client for API testing.
  - A database connector for verifying data.
  - A Logging utiliy
  - A reporting utility

### Benefits of layering

- Maintainability : updates usually limited to one layer
- Reusability : Cora libraries shared accross projects
- Scalabiltiy : Easy to add new test scripts
- Readability : Test scripts focus on business logic
- Division of labor : Technical vs domain experts work on different layers.

### Challenges and best practices

#### Challenges

- Initial investment : higher upfront cost in time and money, but higher maintenability and scalability in the long term.
- Learning curve : higher complexity as team member have to understand layering concepts, and follow the patterns.
- Over-engineering : risk of creating too many layers or abstractions.

#### Best practices

- Start simple : Start small with the 3 layers discussed, and add more layers as needed.
- Document well : Assure team understand the purpose of each layer, and how they interact with each other.
- Use design patterns : such as Page Object Model, Work well with layered approach.
- Code reviews : Ensure layering principles are followed correctly.

### Conclusion

1. Layering creates maintainable, reusable, and scalable automation.
2. 3 layers : Test scripts (what), Business logic (how), Core libraries (tools).
3. Saves long-term time despite upfront investment.

## Apply Different Approaches to Automate Test Cases



## Object Oriented Programming Principles



## Solid Principles



## Design Patterns



## Test Automation Architecture Q&A


