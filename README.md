# Firs-test-Dinamo-

using NUnit.Framework;
using OpenQA.Selenium;
using OpenQA.Selenium.Chrome;
using OpenQA.Selenium.Support.UI;
using System;

namespace csharp_example
{
    [TestFixture]

    public class TestHyest
    {
        private IWebDriver driver;
        private WebDriverWait wait;

        [SetUp]

        public void start()
        {
            driver = new ChromeDriver();
            wait = new WebDriverWait(driver, TimeSpan.FromSeconds(10));
        }

        [Test]

        public void FirstTest()
        {
            driver.Url = "http://www.fcdynamo.kiev.ua/ru/";
            driver.FindElement(By.Id("mid_6")).Click();
            driver.FindElement(By.Id("mid_17")).Click();
            driver.FindElement(By.Name("q")).SendKeys("Шорты");
          
        }

        [TearDown]

        public void stop()
        {
            driver.Quit();
            driver = null;
        }
    }

}