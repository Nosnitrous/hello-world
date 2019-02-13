package com.packt.webdriver.chapter1;


import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.WebElement;

import java.util.List;
import java.io.* ;

public class ElClo {
    public static void main(String[] args) {
        // 1.	Открыть страницу google.com (или любой другой поисковик на ваш выбор) и ввести в строке поиска habrahabr;
        WebDriver driver = new FirefoxDriver();
        driver.get("https://www.google.com");
        driver.Manage().Window.Maximize();
        WebElement searchBox = driver.findElement(By.name("q"));
        searchBox.sendKeys("Абра-кадабра");
        WebElement searchButton = driver.findElement(By.name("btnK"));
        System.out.println("Goto Абра-кадабра");
        searchButton.click();

        List<WebElement> Element = driver.findElements(By.className("iUh30"));

        String[] linkhrefs = new String[Element.size()];
        String Curlink = "" ;
        int j = 0;
        for (WebElement e : Element) {
            if (j==2)
                Curlink = e.getText();
                System.out.println("j = " + j + " text= " + e.getText() + " Curlink.contains(\"habrahabr.ru\") " + Curlink.contains("habrahabr.ru"));
                e.click();
                break;
            }
            j++;
        }
        TakesScreenshot scrShot =((TakesScreenshot)webdriver);
        File SrcFile=scrShot.getScreenshotAs(OutputType.FILE);
        FileUtils.copyFile(scrFile, new File("screenshot.png"));
        }
}
