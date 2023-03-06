import io.github.bonigarcia.wdm.WebDriverManager;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.Select;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.AfterMethod;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.Test;
public class InvalidUsername {

    public static void main(String[] args) {
        // To run this example download the chromedriver.exe for your browser version
        // and modify the path to it. This example works if the driver is put in automation/src/test/resources/drivers/ folder
        System.setProperty("webdriver.chrome.driver", "automation/src/test/resources/drivers/chromedriver.exe");System.setProperty("webdriver.chrome.driver", "automation/src/test/resources/drivers/chromedriver.exe");
        System.out.println("==========Setting up WebDriver==========");
        WebDriverManager.chromedriver().setup();
        ChromeDriver driver = new ChromeDriver();
        driver.manage().window().maximize();

        driver.get("http://training.skillo-bg.com:4300/posts/all");
        driver.manage().window().maximize();

        
        WebElement username = driver.findElement(By.cssSelector(("#defaultLoginFormUsername")));
        username.sendKeys("testing");

        WebElement password = driver.findElement(By.cssSelector(("#defaultLoginFormPassword")));
        password.sendKeys("test-test");

        WebElement signInButton = driver.findElement(By.xpath("//button[@class='my-4 btn btn-primary']"));
        signInButton.click();
//        driver.close();
    }
}
