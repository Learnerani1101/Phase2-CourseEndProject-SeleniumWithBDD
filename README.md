PizzaHut Automation Framework

Project Overview
The PizzaHut Automation Framework is designed to automate the end-to-end user flow of the pizzahut.co.in website. This project implements a Behavior Driven Development (BDD) approach to ensure high-quality functional testing of the pizza ordering process, including basket management and pricing validation.

Tech Stack & Framework
•	Language: Java 21
•	Automation Tool: Selenium WebDriver (v4.34.0)
•	BDD Tool: Cucumber (v7.23.0)
•	Unit Testing: JUnit (v4.12)
•	Design Pattern: Page Object Model (POM) with Page Factory
•	Build Tool: Maven
•	Reporting: Extent Reports (Cucumber 7 Adapter


Prerequisites
Ensure following installed on local machine:
1.Eclipse IDE with Cucumber Plugin
2.Java JDK 21
3.Selenium
4.Maven
5.Git

Getting Started
1. Maven Dependencies
Add the following dependencies to your pom.xml to set up the environment:
XML
<dependencies>
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-java</artifactId>
        <version>7.23.0</version>
    </dependency>

    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-junit</artifactId>
        <version>7.23.0</version>
        <scope>test</scope>
    </dependency>

    <dependency>
        <groupId>org.seleniumhq.selenium</groupId>
        <artifactId>selenium-java</artifactId>
        <version>4.34.0</version>
    </dependency>

    <dependency>
        <groupId>io.github.bonigarcia</groupId>
        <artifactId>webdrivermanager</artifactId>
        <version>6.3.2</version>
    </dependency>

    <dependency>
        <groupId>tech.grasshopper</groupId>
        <artifactId>extentreports-cucumber7-adapter</artifactId>
        <version>1.14.0</version>
    </dependency>
    
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-picocontainer</artifactId>
        <version>7.23.0</version>
    </dependency>
</dependencies>

🧩  The Concept: BDD + Page Object Model
When you combine Behavior-Driven Development (BDD) with the Page Object Model (POM), you are essentially separating the what from the how.
Behaviour-Driven Development (BDD)
BDD uses Gherkin syntax (Given, When, Then) to write tests in plain English. This allows non-technical stakeholders (like Product Managers) to understand exactly what is being tested.
•Focus: The "What"—User behavior and business requirements.
•Tool: Usually Cucumber or SpecFlow.

🧩 Page Object Model (POM)
POM is a design pattern that creates an object repository for storage of all web elements. 
The project utilizes Page Factory to initialize web elements.
•Locators: Stored within Page Classes to maintain clean code.
•Hooks: @Before and @After hooks are used to initialize and close the WebDriver session automatically.

📂 Folder Structure: 
|--- stepDefinitions/           <-- Gherkin-to-Code mapping 
|        |--- HomeSteps.java 
|        |--- PizzasMenuSteps.java 
|        |--- DrinkMenuSteps.java 
|        |--- OrderDealSteps.java 
|        |--- BasketMenuSteps.java 
|
|----- runners/    <-- Cucumber Execution Engine 
|         |--- Runner.java 
|
|------ utils/    <-- Framework Helpers 
|         |--- ExtentReportUtil.java 
|         |--- ScenarioContext.java 
|         |--- ScreenshotUtil.java 
|         |--- TestConfigurationReader.java 
|         |--- WebDriverFactory.java 
|
|------ resources/ 
|         |--- features/     <-- BDD User Stories 
|                   |--- pizzahut_pizza_orderflow.feature 
|
|--- pom.xml                 <-- Dependency Management [cite: 92, 94]
|--- README.md 


🧪 Execution
To run the tests:
1.Navigate to the TestRunner.java file.
2.Right-click and select Run As > JUnit Test.
3.Alternatively, use the terminal:
Bash
mvn test

📊 Reporting
After execution, the Extent Report will be generated in the test-output or target folder (depending on your extent.properties configuration). It provides:
•	Step-by-step Pass/Fail status.
•	Execution time.
•	Visual breakdown of the test suite.



[def]: image.png
