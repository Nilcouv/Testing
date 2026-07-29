# Mooc

## 

### Screen

> **SOLID Principles**
>
> 1. **SRP (Single Responsibility Principle)**
>
> - A class should have only one reason to change - only one job or responsibility
> - Like you would't want your chef to also be your plumber - Different skills, different problems.
>
> **Example:**
> 
> ``` Java
> // This violates SRP - too many responsibilities
> public class TestUtils {
>     // Database operations
>     public void connectToDatabase() { /* ... */ }
>     public ResultSet executeQuery(String query) { /* ... */ }
> 
>     // File operations
>     public void saveScreenshot(String filename) { /* ... */ }
> 
>     public String readTestData(String filepath) { /* ... */ }
> 
>     // Browser operations
>     public void launchBrowser(String browser) { /* ... */ }
>     public void clickElement(String locator) { /* ... */ }
> 
>     // Reporting
>     public void startTestReport() { /* ... */ }
>     public void logTestResult(String testName, boolean result) { /* ... */ }
> }
> ```
> 
> ``` Java
> // Following SRP - each class has a single responsibility
> public class DatabaseUtils {
>     public void connect() {/ *... */ }
>     public ResultSet executeQuery(String query) { / *... */ }
> }
> 
> public class FileUtils {
>     public void saveScreenshot(String filename) { /* ... */ }
>     public String readTestData(String filepath) { /* ... */ }
> }
> 
> public class BrowserUtils {
>     public void launch(String browser) { /* ... */ }
>     public void clickElement(String locator) { /* ... */ }
> }
> 
> public class ReportUtils {
>     public void startReport() { /* ... */ }
>     public void logResult(String testName, boolean result) { /* ... */ }
> }
> ```
> 
> - Had a 3000-line TestHelper class handling everything -- database, UI, Reports
> - Fixing one bug risked breaking unrelated features.
> - Refactoring with SRP created smaller, focused classes.

---

>  **SOLID Principles**
> 
> 2. **OCP (Open-Closed Principle)**
>
> - Software should be open for extension but closed for modification
> - You should add new functionality without changing existing code.
> - In test automation, create frameworks that can be extended without modifying core code.
>
> **Example:**
> 
> 
> ``` Java
> // Without OCP
> public class Validator {
>     public boolean validate(String input, String type) {
>         if (type.equals("email")) {
>         // Email validation logic
>             return input.matches("[a-zA-Z0-9.%+-]+@[a-zA-Z0-9 .- ]+\\.[a-zA-Z]{2,}");
>         }else if (type.equals("phone")) {
>             // Phone validation logic
>             return input.matches("\\d{10}|( ?: \\d{3}-){2}\\d{4}/\\(\\d{3}\\)\\d{3} -?\\d{4}");
>         } else if (type.equals("zipcode")) {
>             // Zipcode validation logic
>             return input.matches("\\d{5}|\\d{5}-\\d{4}");
>         }
>         return false;
>     }
> }
> 
> // Problem: If we need to add a new validation type (e.g., credit card),
> // we have to modify the existing Validator class
> ```
> 
> ```Java
> // Following OCP
> public abstract class Validator {
>     public abstract boolean validate(String input);
> }
> 
> public class EmailValidator extends Validator {
>     @Override
>     public boolean validate(String input) {
>         return input.matches("[a-zA-Z0-9 ._ %+-]+@[a-zA-Z0-9 .- ]+\\.[a-zA-Z]{2,}");
>     }
> }
> 
> public class PhoneValidator extends Validator {
>     @Override
>     public boolean validate(String input) {
>         return input.matches("\\d{10}|( ?: \\d{3}-){2}\\d{4}|\\(\\d{3}\\)\\d{3} -? \\d{4}");
>     }
> }
> 
> public class ZipCodeValidator extends Validator {
>     @Override
>     public boolean validate(String input) {
>         return input.matches("\\d{5}|\\d{5}-\\d{4}");
>     }
> }
> // Now if we need to add credit card validation, we just create a new class:
> public class CreditCardValidator extends Validator {
>     @Override
>     public boolean validate(String input) {
>         // Credit card validation logic
>         return input.matches("^( ?: 4[0-9]{12}( ?: [0-9]{3})?| ... )$");
>     }
> }
> 
> // No existing code was modified!
> ```
> 
> - Original code violated OCP because adding new validation types required modifying the existing class.
> - Refactored by creating a ReportGenerator interface with separate implementations (HTML, PDF).

---

> **SOLID Principles**
> 
> 3. **LSP (Liskov Substitution)**
>
> - Subclass objects should be replaceable with superclass objects without breaking the program.
> - If Class B is a subclass of Class A, you can use B anywhere you use A without issues.
> - Like a recipe calling for any citrus fruit - orange or lemon works without changing the recipe.
>
> **Example:**
> 
> ``` Java 
> class Rectangle {
>     protected int width;
>     protected int height;
> 
>     public void setWidth(int width) {
>         this.width = width;
>     }
> 
>     public void setHeight(int height) {
>         this.height = height;
>     }
> 
>     public int getArea() {
>         return width * height;
>     }
> }
> 
>     class Square extends Rectangle {
>     // A square's width and height must be the same
>     @Override
>     public void setWidth(int width) {
>         this.width = width;
>         this.height = width; // Also set height to maintain square properties
>     }
>     @0verride
>     public void setHeight(int height) {
>         this.height = height;
>         this.width = height; // Also set width to maintain square properties
>     }
> }
> // This code breaks LSP
> void testRectangle(Rectangle r) {
>     r.setWidth(5);
>     r.setHeight(4);
>     assert r.getArea() == 20; // This will fail if r is a Square!
> }
> ```
> 
> ``` Java
> interface Browser {
>     void navigate(String url);
>     WebElement findElement(String locator);
> }
> 
> class ChromeBrowser implements Browser {
>     private WebDriver driver;
> 
> public ChromeBrowser() {
>     driver = new ChromeDriver();
> 
>     @Override
>     public void navigate(String url) {
>         driver.get(url);
>     }
>     @Override
>     public WebElement findElement(String locator) {
>         return driver.findElement(By.cssSelector(locator));
>     }
> }
> 
> class FirefoxBrowser implements Browser {
>     private WebDriver driver;
> 
>     public FirefoxBrowser() {
>         driver = new FirefoxDriver();
>     }
> 
>     // Similar implementations that behave the same way
>     // ...
> }
> 
> class LoginTest {
>     private Browser browser;
> 
>     @BeforeEach
>     void setUp() {
>         // Using ChromeBrowser, but we could substitute FirefoxBrowser
>         // without changing any of the test code below
>         browser = new ChromeBrowser();
>     }
>     @Test
>     void testValidLogin() {
>         browser.navigate("https://example.com/login");
>         // Rest of test code
>     }
> }
> ```
> 
> - ChromeBrowser and FirefoxBrowser can be substitued for each other in the test because they both properly implement the Browser interface.

---

> **SOLID Principles**
>
> 4. ISP (Interface Segregation Principle)
>
> - Don't force to implement methods they don't use
> - It's better to have smaller, specific interfaces than one bloated one.
> - In test automation, split interfaces by functionality -- e.g., LoginAction, SearchActions, CartAction -- Instead of one massive AppAction interface.
> 
> **Example:**
> 
> ``` Java
> // Violating ISP - one big interface
> interface Page {
>     void navigate();
>     void search(String keyword);
>     void sort(String criterion);
>     void filter(Map<String, String> filters);
>     void addToCart(String productId);
>     void checkout();
>     void login(String username, String password);
>     void register(User user);
>     void contactSupport(String message);
>     // And many more methods ...    
> }
> 
> // Now every page class must implement ALL these methods,
> // even if they don't need them!
> class AboutUsPage implements Page {
>     public void navigate() { /* implementation */ }
> 
>     // Have to implement methods that don't make sense for this page
>     public void search(String keyword) { throw new UnsupportedOperationException(); }
>     public void sort(String criterion) { throw new UnsupportedOperationException(); }
>     public void filter(Map<String, String> filters) { throw new UnsupportedOperationException(); }
>     public void addToCart(String productId) { throw new UnsupportedOperationException();
> }
> // And so on ...
> }
> ```
> 
> ``` Java
> // Following ISP with focused interfaces
> interface Navigable {
>     void navigate();
> }
> 
> interface Searchable {
>     void search(String keyword);
>     List<Result> getResults();
> }
> 
> interface Purchasable {
>     void addToCart(String productId);
>     void checkout();
> }
> 
> // Pages implement only the interfaces they need
> class AboutUsPage implements Navigable {
>     public void navigate() { /* implementation */ }
> }
> 
> class ProductCatalogPage implements Navigable, Searchable {
>     public void navigate() { /* implementation */ }
>     public void search(String keyword) { /* implementation */ }
>     public List<Result> getResults() { /* implementation */ }
> }
> 
> class ProductPage implements Navigable, Purchasable {
>     public void navigate() { /* implementation */ }
>     public void addToCart(String productId) { /* implementation */ }
>     public void checkout() { /* implementation */ }
> }
> ```
> 
> - I had a project where we had a Reporter interface with methods for starting reports, adding results, capturing screenshots, and generating different report formats.
> - Some reporting tools we integrated with didn't support screenshots, so they had empty implementations that did nothing
> - By applying ISP, we split into BasicReporter, ScreenshotCapable, and MultiFormatReporter interfaces.
> - This made it much clearer which reporters supported which featured, and we didn't have to implement placeholder methods for unsupported features.

---

> **SOLID Principles**
>
> 5. DIP (Dependency Inversion Principle)
>
> - High-level modules should not depend on low-level modules.
> - Both should depend on abstractions.
> - Abstractions should not depend on details; details should depend on abstractions.
> - Depend on interfaces or abstract classes, not concrete implementations for more flexible, change-friendly code.
> 
> **Example:**

``` Java
// Violating DIP - direct dependency on concrete class
class LoginTest {
    private ChromeDriver driver; // Directly depends on ChromeDriver

    public LoginTest() {
    driver = new ChromeDriver(); // Hardcoded dependency
    }

    public void testLogin() {
        driver.get("https://example.com/login");
        // Rest of the test ...
        }
}
```

``` Java
// Following DIP - depend on abstractions
interface WebDriver {
    void get(String url);
    WebElement findElement(By by);
    // Other browser methods ...
}

class ChromeDriver implements WebDriver {
    // Chrome-specific implementation
}

class FirefoxDriver implements WebDriver {
    // Firefox-specific implementation
}

class LoginTest {
    private WebDriver driver; // Depends on the abstraction

    // Inject the dependency through the constructor
    public LoginTest(WebDriver driver) {
        this.driver = driver;
    }
    public void testLogin() {
        driver.get("https://example.com/login");
    // Rest of the test ...
    }
}
// Usage:
LoginTest chromeTest = new LoginTest(new ChromeDriver());
LoginTest firefoxTest = new LoginTest(new FirefoxDriver());
```

- Originally, tests depended directly on Selenium Webdriver.
- Switching to Appium was difficult because of API differences.
- Refactoring introduced a Driver interface implemented by both Selenium and Appium wrappers.
- Switching drivers became trivial -- same tests run on web and mobile by injecting different driver implementations.

---

### Transcript

"Apply design principles and design patterns in test automation.

SOLID principles.

Now let's talk about SOLID principles.

These are fundamental principles in object-oriented design that were introduced by Robert C. Martin, sometimes called Uncle Bob.

The word SOLID is actually an acronym with each letter representing a different principle. These principles make your code more maintainable, flexible, and easier to understand. Think of SOLID principles like the rules for building a stable house. If you follow them, your structure will be much less likely to collapse as you add onto it or renovate it. Single responsibility principle.

The single responsibility principle states that a class should have only one reason to change, meaning it should have only one job or responsibility. Think of it like this. You wouldn't want your chef to also be your plumber, right? They're different jobs requiring different skills, and problems in one area shouldn't affect the other.

In test automation, this means that each class should focus on testing one specific aspect of the application. For example, let's say we're building a test framework and we start with a class called TestUtils that handles everything.

In this code snippet, the TestUtils class is doing way too much. Following SRP, we should split it into focused classes.

So as you can see in this code snippet, we have separate classes, each with their own single responsibility.

I once joined a project with a massive 3,000-line test helper class that had methods for everything from database connections to UI interactions to report generation.

When we needed to fix a bug in the screenshot functionality that came up, we were afraid to touch the class because changes might break completely unrelated features like database queries.

So after we decided to refactor the code to follow SRP, we had smaller, focused classes that were much easier to maintain.

When we later needed to update the database connection logic to support a new type of database, we only had to modify the DatabaseUtils class without any risk to the rest of the system.

Open-closed principle. The open-closed principle states that software entities should be open for extension but closed for modification.

In simpler terms, you should be able to add new functionality without changing existing code.

In test automation, this often means creating frameworks that you can extend for new features without having to modify the core framework code.

Let's look at an example. Let's say we have a validation system for form inputs.

This code example violates OCP because adding a new validation type requires modifying the existing validator class.

Let's refactor the code to follow OCP.

Now we see in this code snippet that we've broken up the different types of validation into their own class, and then if we need to add a new validator type, like credit card at the bottom of the code snippet, we just add another class specific for that.

There was a project I worked on where we had a reporting system that initially supported only HTML reports. When a client requested PDF reports, the developer modified the existing reporting class which broke some of the HTML reporting features. We refactored to follow OCP by creating a report generator interface with separate implementations for HTML and PDF. When another client later requested Excel reports, we simply added a new implementation without touching the existing code.

Liskov substitution principle.

The Liskov substitution principle, named after computer scientist Barbara Liskov, states that objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.

In simpler terms, if class B is a subclass of class A, then you should be able to use B anywhere you use A without things breaking or behaving unexpectedly. It's like if you have a recipe that calls for any citrus fruit. An orange should work just as well as a lemon without having to change the recipe. Even though they taste different, they're both citrus fruits with similar properties.Let's look at a classic example that violates LSP.

This example violates LSP because you can't substitute a square for a rectangle without breaking the code that expects rectangle behavior.

And as you can see in our test example that starts on line 34,

when we do our assertion for the getArea, the test will fail

if r, which is the variable we pass into the test method, is a square.

Now here's a test automation example that does follow LSP.

In this example, ChromeBrowser and FirefoxBrowser can be substituted for each other in other tests because they both properly implement the browser interface.

Interface Segregation Principle. The Interface Segregation Principle states that clients should not be forced to depend on interfaces they don't use. In other words, it's better to have many specific interfaces than one general-purpose interface. In test automation, this might mean creating focus interfaces for different aspects of your application rather than one giant interface.

Here's an example of violating ISP. So as you can see, we had this one big page interface, and then every page class that uses it must implement all of the methods even if they don't need them.

Now let's refactor the code to follow ISP by creating specific interfaces.

Now in this refactored code, we have focus interfaces like navigable, searchable and purchasable,

and pages that implement these interfaces only have to implement the ones where they have

[laughs]

methods that they actually want to use.

I had a project where we had a reporter interface with methods for starting reports, adding results, capturing screenshots, and generating different report formats.

Some reporting tools we integrated with didn't support screenshots, so they had empty implementations that did nothing.

By applying ISP, we split it into basic reporter, screenshot-capable, and multi-format reporter interfaces. This made it much clearer which reports supported which features, and we didn't have to implement placeholder methods for unsupported features.

Dependency Inversion Principle. The Dependency Inversion Principle states that high-level modules should not depend on low-level modules.

Both should depend on abstractions, and abstractions should not depend on details. Details should depend on abstractions. That sounds pretty abstract itself, right? Let me explain. It means you should depend on interfaces or abstract classes rather than concrete implementations. This makes your code more flexible and easier to change.

It's like plugging devices into electrical outlets. You don't need to know the details of how electricity is generated or delivered. You just need to know the standard interface, meaning the outlet.

And the power company doesn't need to know what devices you're plugging in.

Here's an example of violating DIP.

So in this code example, we see our login test class that directly depends on the Chrome driver.

Now let's refactor that code to follow DIP.

So in this refactored version, we are depending on abstractions. So we have our WebDriver interface and then each of our browser drivers can implement the WebDriver and have their own specific implementation.

And then in our login tests, we can inject the dependency that we need through the classes constructor.

I once worked on a project where we directly depended on Selenium WebDriver throughout our tests. When we needed to switch some tests to use Appium for mobile testing, it was a huge effort because Appium has a slightly different API. After refactoring to follow DIP by creating our own driver interface that both our Selenium and Appium wrappers implemented, switching between them became trivial.

We could even run the same tests on web and mobile just by injecting a different driver implementation. [music]"