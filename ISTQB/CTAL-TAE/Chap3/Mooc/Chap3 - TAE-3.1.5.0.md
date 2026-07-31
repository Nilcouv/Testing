# Mooc

## Apply Design Principles and Design Patterns in Test Automation

### Screen

> **Introduction to design principles & patterns**
>
> - Something that might sound a bit theoretical but is actually super practical - design principles and design patterns in test automation.
> - Proven solution to common problem in software design.
> - Like blueprints that have been tested by thousands of developers over many years.

---

> **Object-Oriented Programming Principles**
>
>  1. **Encapsulation** - Encapsulation is about bundling data and the methods that work on that data within a single unit. Hiding the complex stuff inside a class and only exposing what's necessary through public methods.
>
> **Example:**
>
> - You have a login functionality - With encapsulation, you might create a LoginPage class that handles all the internal details of logging in.
> - LoginPage.login("user", "pass") - The usernameField, passwordField, and loginButton fields are all private, meaning they can't be directly accessed from outside the class.
> - If the login process changes later, you only need to update it in one place.
> 
> ```java
> public class LoginPage {
>     private WebElement usernameField;
>     private WebElement passwordField;
>     private WebElement loginButton;
> 
>     // Constructor and initialization code here
> 
>     public void login(String username, String password) {
>     usernameField.sendKeys(username);
>     passwordField.sendKeys(password);
>     loginButton.click();
>     }
> }
> ```

---

> **Object-Oriented Programming Principles**
>
>  2. **Abstraction** - Abstraction is about simplifying complex systems by modeling classes based on the essential properties and behaviors, while hiding unnecessary details.
>
> - It's like using a TV remote - you press buttons without needing to understand the electrical signals
> - In test automation, abstraction helps us focus on what we need for testing, without getting bogged down in implementation details.
>
> **Example:**
>
> - We create a page interface that defines operations any page should perform:
>   - Navigating to the page
>   - Checking if it's displayed
>   - Getting its title
> - This interface is an abstraction of the concept of a "page" - it doesn't specify how the operations happen.
> - The HomePage class implements this interface and contains the actual implementation details ( WebDriver, URLs, element IDs, etc.)
> 
> ```java
> // implementation
> public interface Page {
>     void navigate();
>     boolean isDisplayed();
>     String getTitle();
> }
> 
> public class HomePage implements Page {
>     private WebDriver driver;
> 
>     public HomePage(WebDriver driver) {
>         this.driver = driver;
>     }
> 
>     public void navigate() {
>         driver.get("https://www.example.com/home");
>     }
> 
>     public boolean isDisplayed() {
>         return driver.findElement(By.id("home-header")).isDisplayed();
>     }
> 
>     public String getTitle() {
>         return driver.getTitle();
>     }
> }
> ```
> 
> - Our tests don't need to know implementation details -- they just work with the Page interface.
> 
> ```java
> // Test
> public void testPageNavigation(Page page) {
>     page.navigate();
>     assertTrue(page.isDisplayed());
>     assertEquals("Expected Title", page.getTitle());
> }
> ```
> 
> - The test is focused on the **behavior** we want to verify, not on how to interact with specific web elements.
> - By creating an **abstraction** of the "user interface", we were able to write tests once and run them on both web and mobile platforms.
> - **Abstraction separates what you want to test from how you need to interact with the system** -- making test code more maintainable.

---

> **Object-Oriented Programming Principles**
>
>  3. **Inheritance** - Inheritance allows a class to inherit **properties and methods** from another class.
>
> - It creates a **parent-child relationship**, where the child class can also add its own capabilities.
> - **Like biological inheritance** - you inherit traits but also have unique ones.
>
> In **test automation**, inheritance helps avoid **code duplication** by using **base classes** with common functionality.
>
> **Example:**
>
> - BasePage contains common functionality like:
>   - Waiting for a page to load
>   - Taking screenshots
>   - Scrolling to elements
> - ProductPage uses extends BasePage to inherit all those methods without rewriting them.
> - Super(driver) calls the parent constructor to handle initialization.
> - Refactoring to use a base class reduced the codebase size by ~30% and made maintenance much faster.

```java
public class BasePage {
    protected WebDriver driver;

    public BasePage(WebDriver driver) {
        this.driver = driver;
    }

    public void waitForPageToLoad() {
        // Common waiting logic here
        new WebDriverWait(driver, 10).until(
            webDriver -> ((JavascriptExecutor) webDriver)
                .executeScript("return document.readyState").equals("complete"));
    }

    public void takeScreenshot(String filename) {
        // Screenshot logic here
        File screenshot = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
        try {
            FileUtils.copyFile(screenshot, new File("./screenshots/" + filename + ".png"));
        } catch (IOException e) {
            e.printStackTrace();
        }

    }

    public void scrollToElement(WebElement element) {
        ((JavascriptExecutor) driver).executeScript(
            "arguments[0].scrollIntoView(true);", element);
    }
}

public class ProductPage extends BasePage {
    private WebElement addToCartButton;
    private WebElement quantityField;

    public ProductPage(WebDriver driver) {
        // Call the parent class constructor
        super(driver);

        // Initialize page-specific elements
        addToCartButton = driver.findElement(By.id("add-to-cart"));
        quantityField= driver.findElement(By.id("quantity"));
    }

    // Inherits all methods from BasePage (waitForPageToLoad, takeScreenshot, scrollToElement)

    // Plus adds its own specific methods
    public void addProductToCart() {
        scrollToElement(addToCartButton); // Using inherited method
        addToCartButton.click();
    }

    public void setQuantity(int quantity) {
        quantityField.clear();
        quantityField.sendKeys(String.valueOf(quantity));
    }
}
```

---

> **Object-Oriented Programming Principles**
>
> 4. **Polymorphism** - Polymorphism allows objects of different classes to be treated as objects of a common base class;
> 
> - Like a TV remote-power button - same action, different TV brands.
> - In test automation, polymorphism helps write flexible code without complex conditionals.
>
> **Example:**
>
> - If our application has different types of alerts or notifications that need to be handled in different ways, we can write something like this:
> 
> ```java
> // Base interface
> public interface Notification {
>     void acknowledge();
>     String getMessage();
> }
> ```
>
> - In this code snippet, we start with an interface notification that defines the common behaviors - acknowledging the notification and getting its message.
>
> ```java
> // Implementation for info notifications
> public class InfoNotification implements Notification {
>     private String message;
>
>     public InfoNotification(String message) {
>         this.message = message;
>     }
>
>     @Override
>     public void acknowledge() {
>         // Find and click the "OK" button
>         WebElement okButton = driver.findElement(By.id("info-ok-button"));
>         okButton.click();
>         System.out.println("Info notification acknowledged");
>     }
>
>     @Override
>     public String getMessage() {
>         return this.message;
>     }
> }
>
> // Implementation for error notifications
> public class ErrorNotification implements Notification {
>     private String message;
>     private String errorCode;
> 
>     public ErrorNotification(String message, String errorCode) {
>         this.message = message;
>         this.errorCode = errorCode;
>     }
> 
>     @Override
>     public void acknowledge() {
>         // Log the error code
>         System.out.println("Error occurred: " + errorCode);
> 
>         // Find and click the "Close" button
>         WebElement closeButton = driver.findElement(By.id("error-close-button"));
>         closeButton.click();
>         System.out.println("Error notification acknowledged");
>     }
> 
>     @Override
>     public String getMessage() {
>         return this.message + " (Error code: " + errorCode + ")";
>     }
> 
> }
> ```
> 
> - InfoNotification and ErrorNotification both implement the same interface but handle acknowledge() differently
> - InfoNotification clicks on OK, while ErrorNotification logs an error code and clicks Close.
> - In handleAnyNotification, we just call notification.acknowledge() -- the correct version runs based on the object at runtime.
> - This avoids if-else statements and keeps code clean.
>
> ---
> 
> - In an e-commerce app, we used polymorphism with different product page types by implementing a common ProductPage interface.
> - Adding a new product type later required no test changes -- just a new implementation.

---

### Transcript

"Apply design principles and design patterns in test automation. In this video, we're gonna talk about something that might sound a bit theoretical, but it's actually super practical, design principles and design patterns in test automation. They're basically proven solutions to common problems in software design. Think of them as recipes or blueprints that have been tested by thousands of developers over many years.

Object-oriented programming principles. Let's start with the foundations, object-oriented programming principles.

There are four major ones that you should know about. Encapsulation. Encapsulation is all about bundling data and the methods that work on the data within a single unit, like a class, and restricting direct access to some of the object's components. In plain English, it means hiding the complex stuff inside a class and only exposing what's necessary through public methods. It's like your car. You don't need to know how the engine works internally. You just need to know how to use the steering wheel, the pedals, and gears. For example, in test automation, let's say you have a login functionality. With encapsulation, you might create a login page class that handles all of the internal details of logging in.

Now your tests only need to call the LoginPage.login method without worrying about how it happens internally. In addition, the username field, password field, and login button fields are all private, meaning they can't be directly accessed from outside the class. And if the login process changes later, you only need to update it in one place.

Abstraction.

Abstraction is about simplifying complex systems by modeling classes based on the essential properties and behaviors they should have while hiding unnecessary details.

It's like using the television remote. You just press buttons to change channels or volume without needing to understand the electrical signals being sent to the TV.

You're working with an abstraction of the TV's functionality that's focused on what you need as a user. In test automation, abstraction helps us create models of the application's components that are focused on what we need for testing without getting bogged down in implementation details.

For instance, instead of dealing with all the complex HTML and CSS of a web page, we might create an abstract representation.

Let me explain how this code snippet uses abstraction.

First, we create a page interface that defines what operations any page should be able to perform:

navigating to the page, checking if it's displayed, and getting its title.

These are the essential behaviors we care about for testing, regardless of what specific page we're working with. This interface doesn't say a thing about how these operations happen. It's an abstraction of the concept of a page in our application. Then we have the homepage class that implements this interface. Inside this class, we have the actual implementation details

using WebDriver to interact with the browser, knowing specific URLs and element IDs, et cetera. But here's the beauty of abstraction. Our tests don't need to know any of these details.

They can just work with the page interface.

This test doesn't care if it's working with a homepage, a product page, or any other page. It just uses the abstracted interface.

The test is focused on the behavior we want to verify, not on how to interact with the specific web elements. I once worked on a project where we had to test the same functionality on both a web application and a mobile app. By creating an abstraction of the user interface that both implementations could follow, we were able to write our tests once and run them against both platforms. Without abstraction, we would have had to duplicate our tests with platform-specific code everywhere.

Abstraction is incredibly powerful for creating maintainable test code because it separates what you want to test from how you need to interact with the system to test it.

Inheritance.

Inheritance allows a class to inherit properties and methods from another class. It creates a parent-child relationship between classes, where the child class inherits features from the parent class, while also being able to add its own unique capabilities. Think of it like biological inheritance. A child inherits certain characteristics from their parents, but can also have their own unique traits. For example, you might inherit your eye color from your mom, but develop your own unique interests and skills. In test automation, inheritance helps us avoid code duplication by creating base classes with common functionality that other classes can inherit from.

This lets us write shared code once in a parent class, rather than repeating it in multiple places.

For example, we might have a base class that contains common methods that all page objects will need.

In this code snippet, first, we have a base page class that contains common functionality any page in our application might need, like waiting for a page to load, taking screenshots, and scrolling to elements. These are operations we'd need to do on many different pages.

Then we have a productPage class that uses the extends keyword to inherit from BasePage. This means productPage automatically has all the methods from the base page without us having to rewrite them. Notice how the productPage constructor calls super with driver passed in, and this invokes the parent class's constructor to handle the initialization logic defined there. And in the addProductToCart method, we call the inherited scrollToElement method. The productPage class didn't have to implement this method itself. It just leverages what it inherited from the base page. I once joined a project where they didn't use inheritance at all, and every page class had duplicate code for waiting mechanisms, screenshot handling, and error logging. About 50 to 60 lines of identical code copied and pasted in each of their 30-plus page classes. When they needed to update their waiting mechanism to handle a specific situation, they had to change it in all 30 files, which was tedious and error-prone.

By refactoring to use a base class with inheritance, we reduced the code base size by about 30% and made it much easier to maintain. When we later needed to enhance the screenshot functionality to include timestamps, we only had to update it in one place, the basePage class. And all page classes automatically got the improved functionality. Polymorphism. Polymorphism allows objects of different classes to be treated as objects of a common base class, with the specific implementation to use determined at runtime.

That sounds complicated, but in simpler terms, it means that different objects can respond to the same method call in different ways.

The word itself comes from Greek roots meaning "many forms." It's like having a TV remote with a power button that works on different TV brands.

The same button or method does something slightly different depending on which TV, meaning the class, you're controlling. But you don't need to use a different button for each TV.

In test automation, polymorphism allows us to write more flexible code that can handle different variants of similar objects without needing complex conditional logic.

For example, if our application has different types of alerts or notifications that need to be handled in different ways, we can write something like this.

In this code snippet, we start with an interface notification that defines the common behaviors, acknowledging the notification, and getting its message.

Then we have two different implementations, InfoNotification and ErrorNotification. Each implements the same interface, but handles the acknowledge method differently.

The info notification simply clicks an okay button, while the error notification logs an error code and clicks a close button.

The magic of polymorphism happens in the handle any notification method. This method accepts any object that implements the notification interface, and it doesn't need to know which specific type it received. It just calls Notification.acknowledge, and the correct implementation is chosen at runtime based on the actual type of object passed.

This means we can write a single method that works for multiple types of notifications without using if/else statements to check the type.

I once worked on an e-commerce application where we had to handle different types of product pages, physical products, digital downloads, subscription services, and bundled products. Instead of writing separate test methods for each product type with duplicated code, we used polymorphism. We created a product page interface with methods like add to cart and get price, then implemented specific versions for each product type.

Our tests could then work with any product type without needing to know the specific details of how that particular product type was handled. When the client later added a new product type, personalized products, we simply created a new implementation of the interface and all our existing tests worked with it without any changes.

The flexibility that polymorphism provided saved us from having to update dozens of test cases.

[music]"