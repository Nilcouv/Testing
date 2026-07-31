# Mooc

## Apply Design Principles and Design Patterns in Test Automation

### Screen

> **Facade Pattern**
>
> - The facade pattern provides a simplified interface to a complex system or set of classes.
> - In test automation, the facade pattern helps us hide the complexity of test libraries and expose only what testers need to create test cases.
>
> **Example:**
>
> ```java
> // Complex subsystem classes
> class WebElementFinder {
>     public WebElement findById(String id) { /* implementation */ }
>     public WebElement findByXPath(String xpath) { /* implementation */ }
>     public WebElement findByCSS(String css) { /* implementation */ }
> }
>
> class WebElementInteractor {
>     public void click(WebElement element) { /* implementation */ }
>     public void type(WebElement element, String text) { /* implementation */ }
>     public void select(WebElement element, String option) { /* implementation */ }
> }
>
> class WaitManager {
>     public void waitForVisible(WebElement element, int seconds) { /* implementation */ }
>     public void waitForClickable(WebElement element, int seconds) { /* implementation */ }
>     public void waitForPageLoad(int seconds) { /* implementation */ }
> }
>
> // Facade that simplifies the interface
> class UserActions {
>     private WebElementFinder finder;
>     private WebElementInteractor interactor;
>     private WaitManager waiter;
>
>     public UserActions() {
>         finder = new WebElementFinder();
>         interactor = new WebElementInteractor();
>         waiter = new WaitManager();
>     }
>
>     // Simple methods that hide the complexity
>     public void clickButton(String id) {
>         WebElement button = finder.findById(id);
>         waiter.waitForClickable(button, 10);
>         interactor.click(button);
>     }
>
>     public void enterText(String fieldId, String text) {
>         WebElement field = finder.findById(fieldId);
>         waiter.waitForVisible(field, 10);
>         interactor.type(field, text);
>     }
>
>     public void login(String username, String password) {
>         enterText("username", username);
>         enterText("password", password);
>         clickButton("loginButton");
>         waiter.waitForPageLoad(10);
>     }
> }
>
> // Client code - much simpler!
> public void testLogin() {
>     UserActions actions = new UserActions();
>     actions.login("testuser", "password123");
>     // Verify login was successful
> }
> ```
>
> - Notice how the UserActions facade presents a much simpler interface for the test code.
> - Instead of dealing with finding elements, waiting, and interacting separately, the test just calls login().
> - By creating a simple facade that wrapped the common actions, we were able to ease them into automation gradually.
> - They could start with high-level methods like login() and searchForProduct(), and as they gained confidence, they could learn the more complex underlying APIs.

---

> **Singleton Pattern**
>
> - The singleton pattern ensures that a class has only one instance and provides a global point of access to that instance.
> - In test automation, the singleton pattern is often used for things like driver management, configuration, and logging.
>
> ```java
> public class DriverManager {
>     // The single instance
>     private static DriverManager instance;
>     private WebDriver driver;
>
>     // Private constructor prevents direct instantiation
>     private DriverManager() {
>         // No instantiation outside this class
>     }
>
>     // Global access point
>     public static synchronized DriverManager getInstance() {
>         if (instance == null) {
>             instance = new DriverManager();
>         }
>         return instance;
>     }
>
>     public WebDriver getDriver() {
>         if (driver == null) {
>             // Initialize the driver if it's not already created
>             String browserType = ConfigManager.getInstance().getBrowser();
>             if ("chrome".equalsIgnoreCase(browserType)) {
>                 driver = new ChromeDriver();
>             } else if ("firefox".equalsIgnoreCase(browserType)) {
>                 driver = new FirefoxDriver();
>             } else {
>                 driver = new ChromeDriver(); // Default
>             }
>             driver.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
>         }
>         return driver;
>     }
>
>     public void quitDriver() {
>         if (driver != null) {
>             driver.quit();
>             driver = null;
>         }
>     }
> }
>
> // Usage in tests
> public void testSearch() {
>     WebDriver driver = DriverManager.getInstance().getDriver();
>     driver.get("https://example.com");
>     // Test code ...
> }
> ```
>
> - This pattern ensures that all your tests use the same WebDriver instance, which prevents issues like having multiple browser windows open at the same time and helps with resource management.
> - Be careful with singletons. They can make testing more difficult and create hidden dependencies. Use them judiciously.

---

> **POM (Page Object Model)**
>
> - POM is probably the most widely used design pattern in UI test automation.
> - It creates a separate class for each page of the application, which contains the page elements and methods to interact with those elements.
>
> The key benefit is that it separates the test logic from the page-specific details, making tests more maintainable.
>
> ```typescript
> // Base page class with common functionality
> import { Page } from 'playwright';
>
> export abstract class BasePage {
>     protected page: Page;
>
>     constructor(page: Page) {
>         this.page = page;
>     }
>
>     async navigateTo(url: string): Promise<void> {
>         await this.page.goto(url);
>     }
>
>     async getPageTitle(): Promise<string> {
>         return await this.page.title();
>     }
>
>     async waitForPageLoad(): Promise<void> {
>         await this.page.waitForLoadState('networkidle');
>     }
> }
> ```
>
> ```typescript
> export class LoginPage extends BasePage {
>     // Page element locators - using Playwright's locator syntax
>     readonly usernameInput = () => this.page.locator('#username');
>     readonly passwordInput = () => this.page.locator('#password');
>     readonly loginButton = () => this.page.locator('#loginBtn');
>     readonly errorMessage = () => this.page.locator('.error-message');
>
>     constructor(page: Page) {
>         super(page);
>     }
>
>     async navigateToLoginPage(): Promise<void> {
>         await this.navigateTo('https://example.com/login');
>     }
>
>     // Page actions
>     async enterUsername(username: string): Promise<void> {
>         await this.usernameInput().fill(username);
>     }
>
>     async enterPassword(password: string): Promise<void> {
>         await this.passwordInput().fill(password);
>     }
>
>     async clickLogin(): Promise<void> {
>         await this.loginButton().click();
>         // Playwright automatically waits for navigation
>     }
>
>     async getErrorMessageText(): Promise<string> {
>         await this.errorMessage().waitFor({ state: 'visible' });
>         return await this.errorMessage().textContent() || '';
>     }
>
>     async isErrorMessageDisplayed(): Promise<boolean> {
>         return await this.errorMessage().isVisible();
>     }
>
>     // Higher-level action that combines steps
>     async loginWithCredentials(username: string, password: string): Promise<void> {
>         await this.enterUsername(username);
>         await this.enterPassword(password);
>         await this.clickLogin();
>     }
> }
> ```
>
> ```typescript
> export class DashboardPage extends BasePage {
>     readonly welcomeMessage = () => this.page.locator('#welcome-message');
>     readonly userMenuDropdown = () => this.page.locator('.user-menu');
>     readonly logoutButton = () => this.page.locator('.logout-button');
>     readonly reportsLink = () => this.page.locator('a[href="/reports"]');
>
>     constructor(page: Page) {
>         super(page);
>     }
>
>     async isWelcomeMessageDisplayed(): Promise<boolean> {
>         return await this.welcomeMessage().isVisible();
>     }
>
>     async getWelcomeMessageText(): Promise<string> {
>         return await this.welcomeMessage().textContent() || '';
>     }
>
>     async navigateToReports(): Promise<void> {
>         await this.reportsLink().click();
>         await this.page.waitForURL('**/reports');
>     }
>
>     async logout(): Promise<void> {
>         await this.userMenuDropdown().click();
>         await this.logoutButton().click();
>         await this.page.waitForURL('**/login');
>     }
> }
> ```
>
> ```typescript
> import { test, expect } from '@playwright/test';
>
> test.describe('Login Functionality', () => {
>     test('should login successfully with valid credentials', async ({ page }) => {
>         // Initialize page objects
>         const loginPage = new LoginPage(page);
>         const dashboardPage = new DashboardPage(page);
>
>         // Perform login
>         await loginPage.navigateToLoginPage();
>         await loginPage.loginWithCredentials('testuser', 'password123');
>
>         // Assertions
>         await expect(dashboardPage.welcomeMessage()).toBeVisible();
>         expect(await dashboardPage.getWelcomeMessageText()).toContain('Welcome, Test User!');
>     });
>
>     test('should show error message with invalid credentials', async ({ page }) => {
>         const loginPage = new LoginPage(page);
>
>         await loginPage.navigateToLoginPage();
>         await loginPage.loginWithCredentials('testuser', 'wrongpassword');
>
>         // Assertions
>         await expect(loginPage.errorMessage()).toBeVisible();
>         expect(await loginPage.getErrorMessageText()).toBe('Invalid username or password');
>     });
> });
> ```
>
> - By using the Page Object Model pattern, if the login page changes, you only need to update the LoginPage class, not all the tests that use it.
> - For example, if the login button's ID changes from loginBtn to submitLogin, you only update it in one place - the loginButton locator in the LoginPage class.

---

> **Flow Model Pattern**
>
> - The Flow Model Pattern is an expansion of the Page Object Model.
> - It introduces an additional layer of abstraction over the page objects, which stores all the user flows that interact with multiple page objects.
> - Page Objects represent the "pages" of your application, while Flow Models represent the "journeys" users take through those pages.
>
> **Examples:**
>
> ```java
> // Flow class for login-related flows
> public class LoginFlow {
>     private WebDriver driver;
>     private LoginPage loginPage;
>     private DashboardPage dashboardPage;
>
>     public LoginFlow(WebDriver driver) {
>         this.driver = driver;
>         this.loginPage = new LoginPage(driver);
>         this.dashboardPage = new DashboardPage(driver);
>     }
>
>     public void navigateToLoginPage() {
>         driver.get("https://example.com/login");
>     }
>
>     public boolean loginWithValidCredentials(String username, String password) {
>         navigateToLoginPage();
>         dashboardPage = loginPage.loginWithCredentials(username, password);
>         return dashboardPage.isWelcomeMessageDisplayed();
>     }
>
>     public String loginWithInvalidCredentials(String username, String password) {
>         navigateToLoginPage();
>         loginPage.loginWithCredentials(username, password);
>         return loginPage.getErrorMessage();
>     }
>
>     public void loginAndNavigateToReports() {
>         loginWithValidCredentials("testuser", "password123");
>         dashboardPage.navigateToReports();
>     }
> }
> ```
>
> - The class contains instances of all the pages involved in login flows (LoginPage and DashboardPage).
> - It provides methods that represent complete user stories or journeys, not just individual page actions.
> - Each method handles the coordination between multiple pages to accomplish a business task.
> - Example: loginAndNavigateToReports() combines logging in and navigating to reports into a single method call.
> - This abstracts away the details of which pages are involved and which methods need to be called.
> - This is powerful because it allows your tests to focus on business scenarios rather than UI interactions.
> - Notice how the flow encapsulates the navigation between pages - the test doesn't need to know that going to reports happens on the dashboard page after login.
>
> ```java
> // Flow class for shopping-related flows
> public class ShoppingFlow {
>     private WebDriver driver;
>     private HomePage homePage;
>     private SearchResultsPage searchResultsPage;
>     private ProductPage productPage;
>     private CartPage cartPage;
>     private CheckoutPage checkoutPage;
>
>     public ShoppingFlow(WebDriver driver) {
>         this.driver = driver;
>         this.homePage = new HomePage(driver);
>         // Initialize other pages ...
>     }
>
>     public void searchForProduct(String keyword) {
>         homePage.navigate();
>         searchResultsPage = homePage.search(keyword);
>     }
>
>     public void addProductToCart(String productName) {
>         searchForProduct(productName);
>         productPage = searchResultsPage.selectFirstProduct();
>         cartPage = productPage.addToCart();
>     }
>
>     public OrderConfirmation completePurchase(CreditCard card, Address shippingAddress) {
>         checkoutPage = cartPage.proceedToCheckout();
>         checkoutPage.enterShippingDetails(shippingAddress);
>         checkoutPage.enterPaymentDetails(card);
>         return checkoutPage.placeOrder();
>     }
>
>     // Combines multiple steps into one flow
>     public OrderConfirmation searchAndBuyProduct(String productName, int quantity) {
>         searchForProduct(productName);
>         productPage = searchResultsPage.selectFirstProduct();
>         productPage.setQuantity(quantity);
>         cartPage = productPage.addToCart();
>
>         CreditCard card = new CreditCard("John Doe", "4111111111111111", "12/25", "123");
>         Address address = new Address("123 Main St", "Anytown", "NY", "12345");
>
>         return completePurchase(card, address);
>     }
> }
> ```
>
> - It manages a larger set of page objects (HomePage, SearchResultsPage, ProductPage, CartPage, CheckoutPage).
> - It provides methods at different levels of granularity:
>   - Small flows like searchForProduct()
>   - Medium flows like addProductToCart()
>   - Complete flows like searchAndBuyProduct()
> - It handles the transitions between multiple pages automatically.
> - The searchAndBuyProduct() method is particularly impressive because it encapsulates an entire purchase flow in a single method call.
>
> ```java
> // Test using flow models
> @Test
> public void testCompletePurchase() {
>     WebDriver driver = DriverManager.getInstance().getDriver();
>     ShoppingFlow shoppingFlow = new ShoppingFlow(driver);
>
>     OrderConfirmation confirmation = shoppingFlow.searchAndBuyProduct("smartphone", 2);
>
>     assertTrue(confirmation.isOrderSuccessful());
>     assertEquals(2, confirmation.getQuantity());
>     // Other assertions ...
> }
> ```
>
> - Notice how incredibly concise and readable it is:
>   - The test creates a ShoppingFlow instance
>   - It calls a single method searchAndBuyProduct() to perform a complex operation
>   - Then it makes assertions on the result
> - The Flow Model Pattern is especially useful for complex applications where user flows often span multiple pages.
> - It allows you to encapsulate entire business processes in a single method call, making your tests more readable and maintainable.
> - By implementing flow models, we were able to encapsulate these complex flows in easy-to-use methods like completePurchaseWithCreditCard() or completePurchaseWithPayPal().

---

> **Common Pitfalls**
>
> - **Over-engineering** - Start simple and refactor as needed
> - **Forgetting the goal** - If your design makes tests harder to write or understand, reconsider it
> - **Rigid framework** - Don't build frameworks that are so rigid they can't adapt to changing requirements
> - **Ignoring context** - Choose patterns appropriate to your context

---

> **Best Practices**
>
> - **Use Proven Patterns** - Start with Page Object Model for structured tests
> - **Prioritize Readability** - Clear tests are easier to maintain and debug
> - **Refactor Incrementally** - Improve code gradually to avoid regressions
> - **Maintain Independence** - Ensure tests can run in isolation for reliability
> - **Balance Abstraction** - Avoid too much or too little abstraction in design

---

> **Conclusion**
>
> 1. OOP + SOLID + Patterns = Maintainable automation
> 2. POM + Flow models = Scalable UI testing

---

### Transcript

"Apply design principles and design patterns in test automation.

Design patterns.

Design patterns are proven solutions to common problems in software design.

They're like recipes or blueprints that have been tested by thousands of developers over many years.

Let's look at some key patterns that are particularly useful in test automation.

Facade pattern.

The facade pattern provides a simplified interface to a complex system or set of classes.

It's like the front desk at a hotel.

You don't need to interact with housekeeping, maintenance, and the restaurant separately.

You just talk to the front desk and they coordinate everything for you.

In test automation.

The facade pattern helps us hide the complexity of test libraries and expose only what testers need to

create test cases.

Here's a simple example of the facade pattern.

Notice how the UserActions facade presents a much simpler interface for the test code.

Instead of dealing with finding elements, waiting, and interacting separately, the test just calls

login.

I once worked at a company where we were trying to get manual testers to learn automation.

They were intimidated by the complexity of Selenium WebDriver.

By creating a simple facade that wrapped the common actions, we were able to ease them into automation

gradually.

They could start with high-level methods like login and searchForProduct, and as they gained confidence,

they could learn the more complex underlying APIs.

Singleton pattern.

The singleton pattern ensures that a class has only one instance and provides a global point of access

to that instance.

It's like having only one principal at a school.

There's just one person in charge and everyone knows how to find them.

In test automation, the singleton pattern is often used for things like driver management, configuration,

and logging.

Let's look at an example code snippet that uses the singleton pattern.

So as you can see, we have a single instance of the DriverManager.

And we have a private constructor that prevents direct instantiation.

And there's a global access point with the synchronized method.

And then down at the bottom on line 43, we can see how it would be used in a test where we have our

WebDriver variable.

And that is an instance of the DriverManager getInstance().getDriver().

So this pattern ensures that all your tests use the same WebDriver instance, which prevents issues

like having multiple browser windows open at the same time and helps with resource management.

But be careful with singletons.

They can make testing more difficult since you can't easily swap out dependencies and create hidden

dependencies.

So use them judiciously.

As an example with more positive results using the pattern, I once had a project where before we implemented

the singleton pattern, each test was creating its own browser instance.

When we ran tests in parallel, we'd have dozens of Chrome windows open, which bogged down the test machine.

After implementing the Singleton DriverManager, we were able to control browser creation and reuse

instances when appropriate, which made our tests run much faster.

Page Object Model.

The Page Object Model, or POM,

as you may hear it called, is probably the most widely used design pattern in UI test automation.

It creates a separate class for each page of the application, which contains the page elements and

methods to interact with those elements.

The key benefit is that it separates the test logic from the page-specific details, making tests more

maintainable.

Here's an example illustrating how it works.

Here we create a BasePage class that has all the common functionality for pages.

Next, we create a class for the LoginPage that extends the BasePage and has its own page-specific

methods.

Then we create another class for the DashboardPage.

Finally, we write a test using the page objects. By using the Page Object Model pattern,

if the login page changes, you only need to update the LoginPage class, not all the tests that use

it.

For example, if the login button's ID changes from loginBtn to submitLogin, you only need to

update it in one place —

the loginButton locator in the LoginPage class.

Flow Model pattern.

The Flow Model pattern is an expansion of the Page Object Model.

It introduces an additional layer of abstraction over the page objects, which stores all the user flows

that interact with multiple page objects.

Think of it this way: page objects represent the pages of your application, while flow models represent

the journeys users take through those pages.

Let's break this pattern down into its components with an example code snippet.

This first code snippet shows a LoginFlow class that encapsulates login-related user journeys.

Here's what's happening.

The class contains instances of all the pages involved in login flows, LoginPage and DashboardPage.

It provides methods that represent complete user stories or journeys, not just individual page actions.

Each method handles the coordination between multiple pages to accomplish a business task.

For example, loginAndNavigateToReports combines logging in and navigating to reports into a single

method call.

This abstracts away the details of which pages are involved and which methods need to be called.

This is powerful because it allows your tests to focus on business scenarios rather than UI interactions.

Notice how the flow encapsulates the navigation between pages.

The test doesn't need to know that going to reports happens on the dashboard page after login.

This second snippet shows a more complex ShoppingFlow class that manages e-commerce user journeys.

Here's what makes it valuable.

It manages a larger set of page objects: HomePage, SearchResultsPage, ProductPage, CartPage,

and CheckoutPage.

It provides methods at different levels of granularity.

Small flows like searchForProduct, medium flows like addProductToCart, and complete flows like searchAndBuyProduct.

It handles the transitions between multiple pages automatically.

The searchAndBuyProduct method is particularly impressive because it encapsulates an entire purchase

flow in a single method call.

Without the flow model, this would require a test to directly interact with five different page

objects and manage all the transitions between them.

Another benefit is that the flow can handle data creation like the credit card and address objects internally.

This keeps tests cleaner and more focused on the business scenario rather than test data

setup.

This third snippet shows a test that uses the flow model.

Notice how incredibly concise and readable it is.

The test creates a ShoppingFlow instance.

It calls a single method searchAndBuyProduct to perform a complex operation.

Then it makes assertions on the result.

The Flow Model pattern is especially useful for complex applications where user flows often span multiple

pages.

It allows you to encapsulate entire business processes in a single method call, making your tests more

readable and maintainable.

On an e-commerce project I worked on, we had complicated checkout flows involving multiple pages and

different paths depending on the customer type, payment method, shipping options, etc. By implementing

flow models, we were able to encapsulate these complex flows into easy-to-use methods like completePurchaseWithCreditCard

or completePurchaseWithPayPal.

Our tests became much more focused on the business scenarios, rather than the mechanics of navigating

through the application.

The double layer of abstraction with page objects plus the flow models gives you a clear separation between

the how of interacting with page elements (the page objects), the what of completing business processes

(flow models), and the why of verifying application behavior

(the tests).

This makes your code much more maintainable and easier to understand.

Common pitfalls and best practices.

Before we wrap up, let's talk about some common pitfalls and best practices when applying these principles

and patterns.

Some of the pitfalls are over-engineering.

Don't create complex abstractions just for the sake of it.

Start simple and refactor as needed.

Rigid frameworks: don't build frameworks that are so rigid that they can't adapt to changing requirements.

Forgetting the goal.

Remember, the goal is to test the application, not to build a perfect framework.

If your design makes tests harder to write or understand, reconsider it.

Ignoring context.

What works for a large enterprise application might be overkill for a simple website.

Choose patterns appropriate to your context.

And some of the best practices include:

Start with proven patterns.

Begin with established patterns like the Page Object Model before experimenting with custom solutions.

Focus on readability: tests should tell a story about how the application is used,

not get lost in implementation details.

Refactor regularly as your understanding evolves.

Also

refactor your framework to incorporate new insights.

Keep tests independent.

Each test should be able to run independently of others.

Avoid dependencies between tests.

Balance

abstraction and correctness.

Too much abstraction can make code hard to understand, while on the other hand, too little can make

it hard to maintain.

Conclusion.

We've covered a lot of ground covering design patterns.

Let's recap the key points.

Test automation is a software development activity, so software design principles apply.

The four key object-oriented principles —

encapsulation, abstraction, inheritance and polymorphism — provide the foundation for good test automation

design.

The SOLID principles —

Single Responsibility,

Open-Closed,

Liskov Substitution,

Interface Segregation and Dependency Inversion —

help create more maintainable and flexible code.

Key design patterns for test automation include the facade pattern, singleton pattern, Page Object Model,

and the Flow Model pattern.

Applying these principles and patterns isn't just theoretical; it makes a real difference in how maintainable,

scalable, and effective your test automation is.

In the next video, we'll talk about implementing test automation.

Building on these design concepts to create robust, maintainable test automation solutions."
