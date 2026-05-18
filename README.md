package assignmentSele;

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class Assign8 {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		WebDriver driver = new ChromeDriver();

        driver.manage().window().maximize();
        driver.get("https://vinothqaacademy.com/webtable/");

        List<WebElement> rows = driver.findElements(
                By.xpath("//table[@id='myTable']/tbody/tr"));
        
        for (int i = 1; i <= rows.size(); i++) {
            List<WebElement> cols = driver.findElements(
                    By.xpath("//table[@id='myTable']/tbody/tr[" + i + "]/td"));

            for (int j = 1; j <= cols.size(); j++) {

                String data = driver.findElement(
                        By.xpath("//table[@id='myTable']/tbody/tr[" + i + "]/td[" + j + "]"))
                        .getText();

                System.out.print(data + "   ");
            }

            System.out.println();
        }

        driver.quit();
    }


}
