import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import io.cucumber.java.en.*;

public class LoginSteps {
    WebDriver driver = new ChromeDriver(); // Initialize your WebDriver

    @Given("I am on the login page")
    public void i_am_on_the_login_page() {
        driver.get("https://app.fuelbuddy.in");
    }

    @When("I enter my valid username and password")
    public void i_enter_my_valid_username_and_password() {
        driver.findElement(By.id("username")).sendKeys("your_username");
        driver.findElement(By.id("password")).sendKeys("your_password");
    }

    @When("I click the login button")
    public void i_click_the_login_button() {
        driver.findElement(By.id("loginButton")).click();
    }

    @Then("I should be redirected to the dashboard")
    public void i_should_be_redirected_to_the_dashboard() {
        // Add assertions or checks for redirection
    }

    @Then("I should see a welcome message")
    public void i_should_see_a_welcome_message() {
        // Add assertions to verify the welcome message
    }

    @After
    public void closeBrowser() {
        driver.quit();
    }
}

import org.junit.runner.RunWith;
import io.cucumber.junit.Cucumber;
import io.cucumber.junit.CucumberOptions;

@RunWith(Cucumber.class)
@CucumberOptions(
    features = "src/test/resources",
    glue = "your.step.definitions.package",
    plugin = {"pretty", "html:target/cucumber-reports"}
)
public class TestRunner {
}

