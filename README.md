# Counting_hyperlink
script for counting hyperlink in apage
package web_driver;

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class Count_link {

	public static void main(String[] args) throws Throwable {
		// TODO Auto-generated method stub
     System.setProperty( "webdriver.chrome.driver","E:\\Chromedriver.exe");
     	WebDriver driver = new ChromeDriver();
     	driver.manage().window().maximize();
     	driver.manage().deleteAllCookies();
     	driver.get("https://www.naukri.com/mnjuser/homepage");
     	Thread.sleep(5000);
     	//get collection of links in a web page stored in html tag
     	List<WebElement> all_Links =driver.findElements(By.tagName("a"));
     	System.out.println("No of links are::"+all_Links.size());
     	//print each link text
     	for (WebElement each : all_Links) {
     		
			System.out.println(each.getText());
			System.out.println(each.getAttribute("href"));
		}
     	Thread.sleep(5000);
     	driver.close();
	}

}
