# Test automation - http://www.automationpractice.com
**Design Pattern:** Page Object Model with loadable components<sub><sup>(POC)</sub></sup> & AAA  
**Following tools were used in this framework:**  
Java, Selenium, TestNG, Cucumber, Gradle, , Allure Reports, SeleniumGrid, WebDriverManager, GitHub Pages
  * [About project](#about-project)
  * [Features](#features)
  * [How to run tests](#how-to-run-tests)
    + [TestNG](#testng)
    + [Cucumber](#cucumber)
  * [Test results & Test logs](#test-results--test-logs)
    + [CI/CD](#cicd)
    + [Localhost](#localhost)
    + [TestNG & Cucumber](#testng--cucumber)
  * [Logger (Slack Bot)](#logger-slack-bot)
    + [CI/CD](#cicd-1)
    + [Localhost](#localhost-1)
  * [SeleniumGrid](#selenium-grid-poc)
    + [CI/CD](#cicd-2)
    + [Localhost](#localhost-2)
    + [How to run tests](#how-to-run-tests-1)
  * [Authors](#authors)
  * [License](#license)
## ABOUT PROJECT
Performing Automationpractice as You don't have to download any WebDrivers - I'm using WebDriverManager, drivers will be downloaded by gradle.  
Supported tests executors:
- *Chrome*

## HOW TO RUN TESTS
There are multiple ways to run tests from this build. It all depends on what do you want to do:
### TestNG
- Right click on `TestNG.xml` file, and Run ->  This will run all tests attached to specific xml runner
- In terminal type `./gradlew test` -> This will run all tests from tests package.`(src/test/java/tests)`  
You can add some environment settings, before you run tests, e.g:
   - `-Dtests.executor="YOUR_HOST_NAME"` -> available hosts: Chrome,IE
  <sub>_**This is the best option to run tests, all tools, features are working well while running tests via this commend**_</sub>
### Cucumber
- Right click on `.feature` file, and Run -> This will run `.feature` file on default settings
- In terminal type `./gradlew cucumber` -> This will run all `.feature` files on default settings  
You can add some environment settings, before you run tests, e.g:
   - `-Dtests.executor="YOUR_HOST_NAME"` -> available hosts: Chrome, Firefox, Opera, Safari, Edge, IE, Safari, GRID, BrowserStack
- In terminal type `./gradlew cucumber -Dcucumber.filter.tags="@YOUR_TAG"` -> This will run all `.feature` scenarios which provided tag
- Right click on `CucumberRunner` file, and Run -> This will run all `.feature` files on default settings
  - <sub><sup>*This is highly unrecommended option since it's an experimental file and doesn't work well, check build.gradle for more information*</sup></sub>
- Create your own runner :hammer_and_wrench:
### Localhost
After each LOCAL cycle run two types of log information are saved inside repository, together with tests results
### TestNG & Cucumber
- Detailed logs in logs directory
- Colorful logs in testdata.xlsx file
- Allure HTML report in build/allure-results directory

In terminal type `allure generate build/allure-results --clean` to generate Allure tests results   
<sub><sup>*Allure tests results available for running tests via: CucumberRunner, `./gradlew test` or TestMethod with annotation @Test (src/test/java/tests)*</sup></sub>

### HOW TO RUN TESTS
1. Run SeleniumGridRunner
2. Make sure that SeleniumGrid is running properly, check http://localhost:4444/grid/console
3. In terminal type `./gradlew test -Dtests.executor=grid -Dremote.browser="YOUR_REMOTE_BROWSER"`
## AUTHORS
- **Kiran Thakur** - *Initial work* - [Kiran Thakur](https://github.com/kirankt077/)
