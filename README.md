Here's a **README.md** file for your Selenium-based BDD test suite using Behave:

---

# Selenium BDD Automation with Behave

This project demonstrates browser automation using Selenium and BDD (Behavior-Driven Development) with Behave. The test suite automates key user interactions on the [SauceDemo](https://www.saucedemo.com) website.

## Prerequisites

### System Requirements
- Python 3.x installed
- Google Chrome installed
- Chromedriver compatible with your Chrome version (ensure `chromedriver` is in your PATH)

### Python Dependencies
Install the required Python libraries:
```bash
pip install selenium behave allure-behave
```

## Test Scenarios

This test suite automates the following actions:

1. **Launch Chrome Browser**  
   Opens the SauceDemo login page.
2. **Login**  
   Logs in using the username `standard_user` and password `secret_sauce`.
3. **Filter Products**  
   Filters products by a specific criterion (e.g., "Low to High").
4. **Navigate Left-Side Menu**  
   Opens the sidebar menu and logs out.
5. **Select a Product**  
   Selects a product from the list.
6. **Add to Cart**  
   Adds the selected product to the shopping cart.
7. **View Cart Items**  
   Opens the shopping cart to view added items.
8. **Close Browser**  
   Closes the browser window.

## Running the Tests

### Step 1: Set Up the Environment
- Ensure `chromedriver` is in your PATH. 
- Update the `driver` initialization line if you use a different browser (e.g., Firefox).

### Step 2: Execute the Tests
Navigate to the project directory and run the tests using Behave:
```bash
behave
```

### Step 3: Generate Allure Reports (Optional)
To generate and view reports with Allure:
1. Run the tests with Allure integration:
   ```bash
   behave --no-capture --tags=@your_tag --format allure_behave.formatter:AllureFormatter --outfile=allure-results
   ```
2. Serve the report:
   ```bash
   allure serve allure-results
   ```

## Code Walkthrough

The tests use the following Behave decorators for BDD steps:

- **@given**: Prepares the test setup (e.g., opening the browser).
- **@when**: Defines the main user actions (e.g., logging in).
- **@then**: Asserts the expected behavior (e.g., filtering products, navigating menus).

### Key Libraries Used
- **Selenium**: Automates browser actions.
- **Behave**: Implements BDD test scenarios.
- **Allure**: Provides advanced reporting capabilities.

## Notes and Tips

1. **Time Delays**: Replace `time.sleep()` with explicit waits (`WebDriverWait`) for more robust automation.
2. **Selectors**: Ensure that element locators (IDs, class names) align with the website's current structure.
3. **Test Tags**: Use `@tags` in your `.feature` files to selectively run specific tests.

## Troubleshooting

- **Browser Compatibility Issues**: Ensure your `chromedriver` version matches your Chrome browser version.
- **Element Not Found Errors**: Update the locators if the SauceDemo website structure changes.
- **Slow Performance**: Replace `time.sleep()` with explicit waits for efficiency.
