# Selenium-
Selenium testing 
#1
// In this tutorial we will learn about the selenium Locators
//Here we are locating by ID,NAME,CLASSNAME

package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class seleniumtutorials2 {
    public static void main(String[] args) {
        //Open the chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //max the chrome browser
        driver.manage().window().maximize();

        //navigate to the url
        driver.get("http://automationpractice.com/index.php");

        //[By Id]
        driver.findElement(By.id("search_query_top")).sendKeys("T-Shirts");
        //OR
        WebElement search=driver.findElement(By.id("search_query_top"));
        search.sendKeys("T-Shirts");

        //[By Name]
        driver.findElement(By.name("search_qu")).sendKeys("Shirts");

        //[By Class]
       driver.findElement(By.className("search_query form-control ac_input")).sendKeys("Shirts");





    }
}
#2
// In this tutorial we will learn about LinkText and Partial LinkText
//LinkText and Partial LinkText is used to click on links on the web page.


package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class seleniumtutorial3 {
    public static void main(String[] args) {
        //Open the chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //max the chrome browser
        driver.manage().window().maximize();

        //navigate to the url
        driver.get("http://automationpractice.com/index.php?id_category=8&controller=category");


        //[By LinkText]
       driver.findElement(By.linkText("Printed Chiffon Dress")).click();

        //[By Partial LinkText]
        driver.findElement(By.partialLinkText("Chiffon Dress")).click();
    }
}

#4
//In this tutorial using the TagName as a Selenium Locator to inspect
//multiple elements on the web page.
//Here we are navigated to www.google.com to find the no. of links on this page
// also we have found the link texts by for loop.

package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.util.List;

public class seleniumtutorials4 {
    public static void main(String[] args) {
        //Open the chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //max the chrome browser
        driver.manage().window().maximize();

        //navigate to the url
        driver.get("https://www.google.com/");

        //By TagName
        List<WebElement> link=driver.findElements(By.tagName("aR"));
        System.out.println(link.size());//27

        //name of links
        for (WebElement l : link)
        {
            System.out.println(l.getText());
        }


    }
}

#5
package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class selniumtutorial5 {
    public static void main(String[] args) {
        //Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //navigate to the URl
        driver.get("https://opensource-demo.orangehrmlive.com/");

        //Max the window
        driver.manage().window().maximize();

        //Enter valid username
        driver.findElement(By.id("txtUsername")).sendKeys("Admin");

        //enter valid password
        driver.findElement(By.name("txtPassword")).sendKeys("admin123");

        //click on login
        driver.findElement(By.id("btnLogin")).click();

        //Verify the URL
        //getCurrentURL()
        String act_url=driver.getCurrentUrl();
        System.out.println(act_url);
        //verify
        String desired_url="https://opensource-demo.orangehrmlive.com/index.php/dashboard";
        if (act_url.equals(desired_url))
        {
            System.out.println("pass");
        }
        else {
            System.out.println("fail");
        }

        //Verify Title
        //getTitle()
        String act_title=driver.getTitle();
        System.out.println(act_title);
        String desired_title="OrangeHRM";
        //verify
        if(act_title.equals(desired_title))
        {
            System.out.println("pass");
        }
        else {
            System.out.println("fail");
        }
        String ps=driver.getPageSource();
        System.out.println(ps);
        //close the browser
        driver.close();







    }
}

#6

package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class seleniumtutorials6 {
    public static void main(String[] args) {
        //Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //navigate to the URl
        driver.get("https://www.ebay.com/");

        //Max the window
        driver.manage().window().maximize();

        //Absolute Xpath
        driver.findElement(By.xpath("/html[1]/body[1]/header[1]/table[1]/tbody[1]/tr[1]/td[3]/form[1]/table[1]/tbody[1]/tr[1]/td[1]/div[1]/div[1]/input[1]")).sendKeys("T-Shirts");
        driver.findElement(By.xpath("/html[1]/body[1]/header[1]/table[1]/tbody[1]/tr[1]/td[3]/form[1]/table[1]/tbody[1]/tr[1]/td[3]/input[1]")).click();

        //Relative Xpath
        driver.findElement(By.xpath("//input[@id='gh-ac']")).sendKeys("Shirts for men");
        driver.findElement(By.xpath("//input[@id='gh-btn']")).click();

        //or operator
       driver.findElement(By.xpath("//input[@id='gh-ac'or @name='_nkw']")).sendKeys("Shirts for men");


        //and operator
        driver.findElement(By.xpath("//input[@id='gh-ac'and @name='_nkw']")).sendKeys("Shirts for women");


        //contains method
        driver.findElement(By.xpath("//input[contains(@name,'_n')]")).sendKeys("Shirts for kids");

       //starts-with
       driver.findElement(By.xpath("//input[starts-with(@name,'_n')]")).sendKeys("Tshirts for kids");

        //text()
        driver.findElement(By.xpath("//a[text()=' Sell']")).click();




    }
}

#7
package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.util.List;

public class seleniumtutorials7 {
    public static void main(String[] args) {
        //Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //navigate to the URl
        driver.get("https://money.rediff.com/gainers");

        //Max the window
        driver.manage().window().maximize();

        //Xpath axes
        //self node
        String selfnode=driver.findElement(By.xpath("//a[contains(.,'Raj Television Netwo')]/self::a")).getText();
        System.out.println("The self node is "+selfnode);

        //parent node
        String parentnode=driver.findElement(By.xpath("//a[contains(.,'Raj Television Netwo')]/parent::td")).getText();
        System.out.println("The parent node is "+parentnode);

        //child nodes
        List<WebElement> childnode=driver.findElements(By.xpath("//a[contains(.,'Raj Television Netwo')]/ancestor::tr/child::*"));
        System.out.println("The no of child nodes are "+childnode.size());

        //Ancestor Node
        String ancestornode=driver.findElement(By.xpath("//a[contains(.,'Raj Television Netwo')]/ancestor::tr")).getText();
        System.out.println("The ancestor node is "+ancestornode);

        //Following
        List<WebElement> followingtag=driver.findElements(By.xpath("//a[contains(.,'Raj Television Netwo')]/following::*"));
        System.out.println("The no of following elements from the current HTML tag is "+followingtag.size());

        //following-siblings
        List<WebElement> followingsib=driver.findElements(By.xpath("//a[contains(.,'Raj Television Netwo')]/ancestor::tr/following-sibling::*"));
        System.out.println("The following siblings are "+followingsib.size());

        //preceding
        List<WebElement> pre=driver.findElements(By.xpath("//a[contains(.,'Raj Television Netwo')]/preceding::*"));
        System.out.println("The no of preceding nodes are- "+pre.size());

        //preceding siblings
        List<WebElement> presiblings=driver.findElements(By.xpath("//a[contains(.,'Raj Television Netwo')]/ancestor::tr/preceding-sibling::*"));
        System.out.println("The no of preceding siblings are - "+presiblings.size());




        driver.close();




    }
}

#8
package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.util.List;

public class seleniumtutorials8 {
    public static void main(String[] args) {
        //Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //navigate to the URl
        driver.get("https://developer.salesforce.com/signup?d=70130000000td6N");

        //Max the window
        driver.manage().window().maximize();

        //Xpath Axes
        //self node
        driver.findElement(By.xpath("//input[@id='company']/self::input")).sendKeys("ABC");

//        //Parent node
//        String parent=driver.findElement(By.xpath("//input[@id='company']/parent::*")).getText();
//        System.out.println("The parent value is -- "+parent);

        //child nodes
        List<WebElement> childnodes=driver.findElements(By.xpath("//input[@id='company']/parent::form/child::*"));
        System.out.println("The no of child nodes are--" +childnodes.size());

        //following nodes
        List<WebElement> foll=driver.findElements(By.xpath("//input[@id='company']/following::*"));
        System.out.println("The no of following nodes are-- "+foll.size());

        //preceding
        List<WebElement> pre=driver.findElements(By.xpath("//input[@id='company']/preceding::*"));
        System.out.println("The no of precedings are--"+pre.size());

        //foll-siblings
        List<WebElement> follsib=driver.findElements(By.xpath("//input[@id='company']/following-sibling::*"));
        System.out.println("The no of following siblings are -- "+follsib.size());

        //preceding siblings
        List<WebElement> presib=driver.findElements(By.xpath("//input[@id='company']/preceding-sibling::*"));
        System.out.println("The no of preceding siblings are -- "+presib.size());
    }
}

#9

package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class seleniumTutorials9 {
    public static void main(String[] args) {
        //Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //navigate to the URl
        driver.get("https://books-pwakit.appspot.com/");

        //Max the window
        driver.manage().window().maximize();

        //host
        WebElement host=driver.findElement(By.tagName("book-app"));

        //shadow dom
        JavascriptExecutor j=(JavascriptExecutor) driver;
        WebElement shadowdom= (WebElement) j.executeScript("return arguments[0].shadowRoot",host);


        //app-header
        WebElement appheader=shadowdom.findElement(By.tagName("app-header"));

        //app-toolbar
        WebElement apptool=appheader.findElement(By.cssSelector("app-toolbar.toolbar-bottom"));

        //book-input
        WebElement book=apptool.findElement(By.tagName("book-input-decorator"));

        //Input
        book.findElement(By.cssSelector("input#input")).sendKeys("selenium Webdriver");

    }
    }

    #11
package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class SeleniumTutorials11 {
    public static void main(String[] args) throws InterruptedException {
        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //open the amazon page
        driver.get("https://www.amazon.com/");
        System.out.println("opening the amazon page through driver.get()");

        //max
        driver.manage().window().maximize();

        //Navigate to the ebay page
        driver.navigate().to("https://www.ebay.com/");
        System.out.println("Navigated to ebay through driver.navigate.to()");

        //enter some value
        driver.findElement(By.xpath("//input[@id='gh-ac']")).sendKeys("T-shirt for men");

        //refresh the browser
        Thread.sleep(2000);
        driver.navigate().refresh();
        System.out.println("Refresh the browser");

        //navigate back to amazon
        Thread.sleep(2000);
        driver.navigate().back();
        System.out.println("The page is navigated back to amazon");

        //navigate Forward to ebay
        Thread.sleep(2000);
        driver.navigate().forward();
        System.out.println("the page is navigated forward");

        //close the browser
        driver.close();




    }
}

#12
package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;

public class SeleniumTutorials12 {
    public static void main(String[] args) throws InterruptedException {
        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

       //Navigate to the page
        driver.navigate().to("https://wordpress.com/");

        //max
        driver.manage().window().maximize();

        //click on get start
        driver.findElement(By.xpath("//a[normalize-space()='Get Started']")).click();

        //back
        Thread.sleep(5000);
        driver.navigate().back();

        //forward
        Thread.sleep(5000);
        driver.navigate().forward();

        //refresh
        Thread.sleep(5000);
        driver.navigate().refresh();

        //close the browser
        Thread.sleep(6000);
        driver.close();


    }
}

#13
package com.selenium;

import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;

import java.util.List;
import java.util.SortedMap;

public class seleniumtutorials13 {
    public static void main(String[] args) throws InterruptedException {
        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //2.Open the URl
        driver.get("https://opensource-demo.orangehrmlive.com/");

        //max
        driver.manage().window().maximize();

        //Enter username and password
        driver.findElement(By.id("txtUsername")).sendKeys("Admin ");
        driver.findElement(By.id("txtPassword")).sendKeys("admin123");

        //clear the username and password
        Thread.sleep(5000);
        driver.findElement(By.id("txtUsername")).clear();
        Thread.sleep(4000);
        driver.findElement(By.id("txtPassword")).clear();

        //submit
        driver.findElement(By.xpath("//input[@value='LOGIN']")).submit();

        //gettext()
       String gettext= driver.findElement(By.linkText("Forgot your password?")).getText();
        System.out.println("The text is "+gettext);

        //getLocation()
        WebElement element=driver.findElement(By.id("txtUsername"));
        Point point=element.getLocation();
        System.out.println("X cordinates" +point.x);
        System.out.println("Y cordinates "+point.y);

        //getsize
       WebElement element1= driver.findElement(By.id("txtUsername"));
       Dimension dim=element1.getSize();
        System.out.println("Height is "+dim.height);
        System.out.println("Width is "+dim.width);

        //getTagname

        String gettagname=driver.findElement(By.id("txtUsername")).getTagName();

        System.out.println(gettagname);

        //to print the no of links on the page
       List<WebElement> links= driver.findElements(By.tagName("a"));
        System.out.println(links.size());

        //check if the login button is displayed on the page
        Boolean bool1=driver.findElement(By.xpath("//input[@value='LOGIN']")).isDisplayed();//T
        System.out.println(bool1);

        //Check if the login button is enabled
        Boolean bool2=driver.findElement(By.xpath("//input[@value='LOGIN']")).isEnabled();//T
        System.out.println(bool2);

        //Check if the login button is selected or not
        Boolean bool3=driver.findElement(By.xpath("//input[@value='LOGIN']")).isSelected();//F
        System.out.println(bool3);


    }
}

#14

package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.util.Set;

public class SelniumTutorials14 {
    public static void main(String[] args) throws InterruptedException {
        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //open the URL
        driver.get("https://demoqa.com/browser-windows");

        //max
        driver.manage().window().maximize();

        //print parent window handle
        String parentwindowhandle=driver.getWindowHandle();
        System.out.println("the parent window handle is "+parentwindowhandle);

        //click 3 times
       for(int i=1;i<=3;i++)
       {
           driver.findElement(By.xpath("//button[normalize-space()='New Window']")).click();
           Thread.sleep(3000);
       }
       //print the window handles
        Set<String> windowhandles=driver.getWindowHandles();
       String lastwindowhandle= "";
    for (String handle:windowhandles)
    {
       System.out.println("The window handles are "+handle);
        //switching
        System.out.println("Switching windows "+handle);
        Thread.sleep(2000);
        driver.switchTo().window(handle);
        //Navigating to the google
        Thread.sleep(3000);
        driver.get("http://www.google.com");
        driver.manage().window().maximize();
    }
    //close parent window first
        Thread.sleep(2000);
   driver.switchTo().window(parentwindowhandle);
    driver.close();
    //switch to the other windows
        Thread.sleep(2000);
        driver.switchTo().window(lastwindowhandle);
        Thread.sleep(2000);
        driver.quit();


    }
}

#15
package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

import java.util.List;

public class SeleniumTutorials15 {
    public static void main(String[] args)  {
        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //open the URL
        driver.get("https://www.seleniumeasy.com/test/basic-select-dropdown-demo.html");

        //max
        driver.manage().window().maximize();

        //Select Class
        Select selectelement=new Select(driver.findElement(By.xpath("//div//div//div[1]//div[2]//select[1]")));
        //Or
//        WebElement dropdown=driver.findElement(By.xpath("//div//div//div[1]//div[2]//select[1]"));
//        Select selectelement=new Select(dropdown);

        //Find the options present in the dropdown menu
       List<WebElement> options =selectelement.getOptions();
        System.out.println(options.size());

        //print
        for (WebElement e:options)
        {
            System.out.println("The values are "+e.getText());
        }

        //Select the options
        //selectbyvalue
//        selectelement.selectByValue("Friday");
        //Selectbyindex
//        selectelement.selectByIndex(3);
       //SelectByVisibleText()
        selectelement.selectByVisibleText("Monday");

        //ismultiple()
        Boolean bool1=selectelement.isMultiple();

        System.out.println(bool1);

        selectelement.deselectByVisibleText("Monday");




     
    }
}

#16
package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;

import java.util.List;

public class SeleniumTutorials16 {
    public static void main(String[] args) throws InterruptedException {
        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //open the URL
        driver.get("https://www.seleniumeasy.com/test/basic-select-dropdown-demo.html");

        //max
        driver.manage().window().maximize();

        //Select Class
        Select selectelement = new Select(driver.findElement(By.xpath("//body/div/div/div/div[2]/div[2]/select[1]")));
        //Or
//        WebElement dropdown=driver.findElement(By.xpath("//div//div//div[1]//div[2]//select[1]"));
//        Select selectelement=new Select(dropdown);

        //Find the options present in the dropdown menu
        List<WebElement> options = selectelement.getOptions();
        System.out.println(options.size());

        //print
        for (WebElement e : options) {
            System.out.println("The values are " + e.getText());
        }

        //isMultiple
        Boolean bool1=selectelement.isMultiple();
        System.out.println(bool1);

        //select
        //selectByIndex
        selectelement.selectByIndex(0);
        //selectByValue()
        selectelement.selectByValue("New York");
        //selectByVisibleText
        selectelement.selectByVisibleText("Washington");

        //first selected value
        System.out.println(selectelement.getFirstSelectedOption().getText());

        //deselect
        Thread.sleep(2000);
        selectelement.deselectByIndex(3);
        //deselectbyvalue
        selectelement.deselectByValue("Washington");
        //deselectbyvisibletext
      selectelement.deselectByVisibleText("California");


    }
}

#17
package com.TutorialsofSelenium;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class SeleniumTutorials17 {
    public static void main(String[] args) throws InterruptedException {

        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //navigate to the URL
        driver.get("https://www.goibibo.com/flights/?utm_source=google&utm_medium=cpc&utm_campaign=DF-Brand-EM&utm_adgroup=Only%20Goibibo&utm_term=!SEM!DF!G!Brand!ETA!108599293!6504095653!491718594877!e!goibibo!c!&ef_id=CjwKCAiA9bmABhBbEiwASb35V6oEH8H_qAAuHLmQirX9_U-HS2cpgsgTJ1U6QCggc5Av55P1XWX0OhoCQxMQAvD_BwE:G:s&gclid=CjwKCAiA9bmABhBbEiwASb35V6oEH8H_qAAuHLmQirX9_U-HS2cpgsgTJ1U6QCggc5Av55P1XWX0OhoCQxMQAvD_BwE");

        //max
        driver.manage().window().maximize();

        //autosuggestion
       WebElement from= driver.findElement(By.xpath("//input[@id='gosuggest_inputSrc']"));
       from.click();
       from.sendKeys("Dubai");
       Thread.sleep(2000);
       from.sendKeys(Keys.ARROW_DOWN);
       Thread.sleep(2000);
       from.sendKeys(Keys.ENTER);

       //to
        WebElement to= driver.findElement(By.xpath("//input[@id='gosuggest_inputDest']"));
        to.click();
        to.sendKeys("Indore");
        Thread.sleep(2000);
        to.sendKeys(Keys.ARROW_DOWN);
        Thread.sleep(2000);
        to.sendKeys(Keys.ENTER);




    }
}


#18

  package com.TutorialsofSelenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class SeleniumTutorials18 {
    public static void main(String[] args) throws InterruptedException {

        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

        //navigate to the URL
        driver.get("https://www.demoqa.com/automation-practice-form");

        //max
        driver.manage().window().maximize();

        //handle the checkboxes
        WebElement sports=driver.findElement(By.xpath("//label[normalize-space()='Sports']"));
        sports.click();
        WebElement reading= driver.findElement(By.xpath("//label[normalize-space()='Reading']"));
        Thread.sleep(2000);
        reading.click();
        WebElement music= driver.findElement(By.xpath("//label[normalize-space()='Music']"));
        Thread.sleep(2000);
        music.click();
        //uncheck
       sports.click();
       Thread.sleep(2000);
       reading.click();
       Thread.sleep(2000);
       music.click();
       Thread.sleep(2000);

       //validation
        //isDisplayed:T/F if the element is displayed
        //isSelected:T/F if the element is selected
        //isEnabled:T/F if the element is enabled

        //isDisplayed()
        Boolean bool1=sports.isDisplayed();
        System.out.println(bool1);
        if(bool1==true)
        {
            sports.click();
        }
        //isSelected
        Boolean bool2=reading.isSelected();
        System.out.println(bool2);
        if(bool2==false)
        {
            reading.click();
        }
        //isEnabled
        Boolean bool3=music.isEnabled();
        System.out.println(bool3);
        if(bool3==true)
        {
            music.click();
        }
    }
}  



#10_commands

package com.selenium;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

import java.util.Set;

public class seleniumtutorials10 {
    public static void main(String[] args) throws InterruptedException {
        //1.Open  the Chrome browser
        System.setProperty("webdriver.chrome.driver", "D://selenium jars and drivers//drivers//chromedriver/chromedriver.exe");
        WebDriver driver = new ChromeDriver();

//        //navigate to the URL
      driver.get("https://demoqa.com/browser-windows");

//      //2.Navigate to the url
//        //Assign the url to a string variable
//        String url="https://demoqa.com/browser-windows";
//        driver.get(url);

        //max the window
        driver.manage().window().maximize();

        //URL of the page
        String urlofthepage=driver.getCurrentUrl();
        System.out.println("The URL of the page is "+urlofthepage);

        //Verify the URL
        if (urlofthepage.equals("https://demoqa.com/browser-windows"))
        {
            System.out.println("The URL is verified");
        }
        else
        {
            System.out.println("The URL is not verified");
        }

        //Title of the page
        String title=driver.getTitle();
        System.out.println("The title of the page is "+title);
        //verify
        if(title.equals("ToolsQA"))
        {
            System.out.println("The title is verified");
        }
        else
        {
            System.out.println("The title is not verified");
        }
        //length of the title
        int titlelength=driver.getTitle().length();
        System.out.println("The length of the title is "+titlelength);

        //pagesource
        String ps=driver.getPageSource();
        System.out.println("The page source is "+ps);

        //length of page source
        int pslength=driver.getPageSource().length();
        System.out.println("The length of the page source is "+pslength);

        //click()
        driver.findElement(By.xpath("//body/div/div/div/div/div/div/div[1]/button[1]")).click();

//        //close()
//        Thread.sleep(5000);
//        driver.close();

        //quit
        Thread.sleep(5000);
        driver.quit();






    }
}
