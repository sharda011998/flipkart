# flipkart
This is the flipkart project using Java with Selenium

package Online_Shopping;



import org.testng.annotations.Test;

import org.testng.annotations.BeforeClass;

import org.testng.annotations.Parameters;

Iimport java.io.FileInputStream;

import java.io.FileNotFoundException;

import java.io.IOException;

import java.util.ArrayList;

import java.util.Set;

import java.util.concurrent.TimeUnit;

import org.apache.poi.ss.usermodel.Sheet;

import org.apache.poi.xssf.usermodel.XSSFSheet;

import org.apache.poi.xssf.usermodel.XSSFWorkbook;

import org.openqa.selenium.By;

import org.openqa.selenium.WebDriver;

import org.openqa.selenium.edge.EdgeDriver;

import org.testng.annotations.AfterClass;

import org.testng.annotations.AfterTest;
public class NewTest (

WebDriver driver;

@Test(priority=0)

public void facewash() throws IOException, InterruptedException {

//click on the seach button

driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[1]/div/div/div/div/div[1]/div/div/div/div[1]/div[1]/header/div[1]/div[2]/form/div/div/input")).click();

String file = "C:\\Users\\sharda.pande\\Desktop\\Accerated task\\Flipkard.xlsx";

//creat instance

FileInputStream inputstream = new FileInputStream(file);

XSSFWorkbook wb = new XSSFWorkbook(inputstream);

XSSFSheet Sheet = wb.getSheet("sheet1");

int length = Sheet.getLastRowNum()-Sheet.getFirstRowNum();

String facewash-Sheet.getRow(1).getCell(0).getStringCellValue();

//Search the first product face wash

driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[1]/div/div/div/div/div[1]/div/div/div/div[1]/div[1]/header/div[1]/div[2]/form/div/div/input")).sendKeys(facewash); Thread.sleep(500);

//Search the first product

driver.findElement(By.xpath("/html/body/div[1]/div/div[1]/div/div/div/div/div[1]/div/div/div/div[1]/div[1]/header/div[1]/div[2]/form/div/button")).click();
// click on first product

driver.findElement(By.xpath("/html/body/div/div/div[3]/div[1]/div[2]/div[4]/div/div[2]/div/a[1]/div[1]/div/div/img")).click(); Thread.sleep(1000);

Set<String>windows= driver.getWindowHandles();

for(String str:windows)

driver.switchTo().window(str);

String currentUrl = driver.getCurrentUrl();

System.out.println(currentUrl);

//click on add to card

driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[3]/div[1]/div[1]/div[2]/div/ul/li[1]/button")).click();

//Switch the tab new to old

Thread.sleep(5000);

ArrayList<String> newTab = new ArrayList<String>(driver.getWindowHandles());

driver.switchTo().window (newTab.get(0));

driver.navigate().back();

Thread.sleep(1000);
}
@Test(priority=2)

public void search_second_product() throws InterruptedException, IOException {

String file = "C:\\Users\\sharda.pande\\Desktop\\Accerated task\\Flipkard.xlsx";

//creat instance

FileInputStream inputstream = new FileInputStream(file);

XSSFWorkbook wb = new XSSFWorkbook(inputstream);

XSSFSheet Sheet = wb.getSheet("sheet1");

int length = Sheet.getLastRowNum()-Sheet.getFirstRowNum();

//search the body locationsecond product

String bodylocation=Sheet.getRow(2).getCell(0).getStringCellValue();

//pass the parameter String

driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[1]/div/div/div/div/div[1]/div/div/div/div[1]/div[1]/header/div[1]/div[2]/form/div/div/input")).sendKeys(bodylocation);

Thread.sleep(5000);

//click on the search button

driver.findElement(By.xpath("/html/body/div[1]/div/div[1]/div/div/div/div/div[1]/div/div/div/div[1]/div[1]/header/div[1]/div[2]/form/div/button")).click();

Thread.sleep(5000);

/tabe the body location

driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[3]/div/div[2]/div[2]/div/div[4]/div/a[1]/div[1]/div/div/img")).click();

Thread.sleep(5000);

Set<String>windows1= driver.getWindowHandles();
for(String str:windows1)

driver.switchTo().window(str);

String currentUrl = driver.getCurrentUrl();

System.out.println(currentUrl);

//click on add to card

driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[3]/div[1]/div[1]/div[2]/div/ul/li[1]/button")).click();

//go to the orginal window

ArrayList<String> bodylocatio = new ArrayList<String>(driver.getWindowHandles());

driver.switchTo().window(bodylocatio.get(0));

//back to the orginal sight

driver.navigate().back();

// Thread.sleep(5000);

//click on the seach button

I

// driver.findElement(By.xpath("/html/body/div[1]/div/div[1]/div/div/div/div/div[1]/div/div/div/div[1]/div[1]/header/div[1]/div[2]/form/div/button"}} click[]
}
//click on add to card

driver.findElement(By.xpath("//*[@id=\"container\"]/div/div[3]/div[1]/div[1]/div[2]/div/ul/li[1]/button")).click();

ArrayList<String> cream = new ArrayList<String>(driver.getWindowHandles());

driver.switchTo().window(cream.get(0));

//back to the orginal sight

driver.navigate().back();

}




@Parameters({"Browser","path","url"})

@BeforeClass

public void beforeClass(String Browser, String path, String url) {

System.setProperty(Browser, path);

diver = new EdgeDriver();

driver.get(url);

driver.manage().window().maximize();

driver.manage().timeouts().implicitly Wait(20, TimeUnit.SECONDS);
}

public void afterTest() {

}

}
