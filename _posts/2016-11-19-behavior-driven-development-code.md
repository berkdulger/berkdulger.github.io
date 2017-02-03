---
title:  "Behavior-Driven Development, Code"
date:   2016-11-19 10:16:01 -0600
header:
    image: sunrise-at-vermillion3.jpg
---


Önceki post'da kısaca Behavior-Driven Development(BDD)'dan bahsetmiştim. Bu post'da ise Cucumber kullanarak BDD'nin nasıl gerçekleştirilebileceğinden bahsedeceğim.

Aslında bakarsanız, birkaç senedir BDD'den haberdar olmama, firma olarak danışmanlık projelerimizde deneyimlememize rağmen, bir miktar ön yargı sahibiydim. Ancak bu önyargının, bir süre sonra, diğer ön yargılar gibi çok da gerçekçi olmadığının farkına vardım. Sanırım BDD ile tanışma sürecimde "Automation for Non-IT People" gibi "sıradışı" mottolar böyle bir yargıya sebebiyet verdi.

Ancak "Automation for Non-IT People" gelinebilecek en uç olgunluk seviyesi neredeyse. Bunun öncesinde birçok başka fayda sunuyor [BDD konsepti](https://www.linkedin.com/pulse/behavior-driven-development-concept-berk-d%C3%BClger). En basitinden yazdıktan bir süre sonra unuttuğunuz kodun ne yaptığını çok kısa bir sürede hatırlamanıza olanak tanıyor. Birçok yazılımcı için bu bile başlı başına büyük bir motivasyon!
 
![Ideas are Cheap!](https://berkdulger.github.io/images/IdeasAreCheap.png)

Daha az karmaşık olması için, Java 8'in lambda gibi özelliklerini kullanmadan basit bir proje oluşturdum. Direkt olarak GitHub'dan klonlayarak kullanabileceğiniz gibi, IntelliJ, Maven, Junit, Cucumber ile de projeyi hızlıca oluşturabilirsiniz.

Proje içerisinde kısaca .feature dosyası Gherkin (Linguistic) ile hazırladığınız senaryoları, Java kodu ile map'lemek oluyor Cucumber'ın yaptığı. Bu esnada değişkenlerinizi Regex olarak okuyarak kodunu içerisinde kullanmanıza olanak sağlıyor.

ProductSearchTest.java
    
    import cucumber.api.java.en.Given;
    import cucumber.api.java.en.Then;
    import cucumber.api.java.en.When;
    import org.junit.Assert;
    import org.openqa.selenium.By;
    import org.openqa.selenium.WebElement;
    
    
    publicclassSearchProductTestextendsBaseTest{
  
        @Given("^I opened (.*) website$")
        publicvoidopenWebSite(String webSite){
            driver.navigate().to("http://" + webSite);
        }
    
        @When("^I search for a product (.*)$")
        publicvoidsearchProduct(String product){
            driver.findElement(By.id("twotabsearchtextbox")).sendKeys(product);
            driver.findElement(By.id("twotabsearchtextbox")).submit();
        }
    
        @Then("^(.*) searches are displayed$")
        publicvoidisProductDisplayed(String product){
            Assert.assertTrue(driver.getTitle().contains(product));
        }

    }
ProductSearch.feature

    Feature: Search for a Product on Amazon.com
      Scenario: Search result check  
        Given I opened www.amazon.com website
        When I searchfor a product Playstation
        Then Playstation searches are displayed

Cucumber projesine [github.com/berkdulger/cucumber-tutorial-java7](github.com/berkdulger/cucumber-tutorial-java7) üzerinden erişebilirsiniz.

Herhangi bir sorunuz olursa, elimizden geldiğince yardımcı olmak isteriz. Kolay gelsin...