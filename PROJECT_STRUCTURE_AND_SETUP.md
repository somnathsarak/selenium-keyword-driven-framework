# Selenium Keyword-Driven Framework - Project Structure & Setup

## Overview
This is a **Keyword-Driven Test Automation Framework** built with:
- **Java 11+**
- **Maven** (Build & Dependency Management)
- **Selenium WebDriver 4.15.0**
- **TestNG 7.8.1**
- **ExtentReports 5.1.1**
- **Apache POI 5.2.3** (Excel & Data Management)
- **Log4j2** (Logging)
- **Gson** (JSON Handling)

---

## Maven Dependencies Included

```xml
<!-- All dependencies configured in pom.xml -->
✓ Selenium WebDriver (4.15.0)
✓ TestNG (7.8.1)
✓ WebDriverManager (5.6.3) - Auto browser driver management
✓ ExtentReports (5.1.1) - Advanced reporting
✓ Apache POI (5.2.3) - Excel data management
✓ Gson (2.10.1) - JSON parsing
✓ Log4j2 (2.20.0) - Logging framework
✓ JUnit (4.13.2) - Testing
```

---

## Complete Maven Project Structure

```
selenium-keyword-driven-framework/
├── pom.xml                                 ✓ Maven configuration with ALL dependencies
├── .gitignore                              ✓ Git ignore file
├── README.md                               ✓ Project description
├── PROJECT_STRUCTURE_AND_SETUP.md         ✓ This file
│
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/selenium/kwdf/
│   │   │       ├── base/
│   │   │       │   ├── BaseTest.java
│   │   │       │   ├── WebDriverUtils.java
│   │   │       │   ├── ConfigReader.java
│   │   │       │   └── ExtentReportManager.java
│   │   │       │
│   │   │       ├── keywords/
│   │   │       │   ├── BrowserKeywords.java          # Browser operations
│   │   │       │   ├── ElementKeywords.java          # Element interactions
│   │   │       │   ├── ValidationKeywords.java       # Assertions & validations
│   │   │       │   ├── DataKeywords.java             # Data handling
│   │   │       │   ├── WaitKeywords.java             # Wait operations
│   │   │       │   └── KeywordFactory.java           # Keyword execution engine
│   │   │       │
│   │   │       ├── utils/
│   │   │       │   ├── DataProvider.java             # Excel data management
│   │   │       │   ├── JSONParser.java               # JSON handling
│   │   │       │   ├── LoggerUtils.java              # Logging wrapper
│   │   │       │   ├── ReportUtils.java              # Report generation
│   │   │       │   └── TestDataManager.java          # Test data handling
│   │   │       │
│   │   │       ├── listeners/
│   │   │       │   ├── TestListener.java             # TestNG listeners
│   │   │       │   └── RetryAnalyzer.java            # Retry logic
│   │   │       │
│   │   │       └── models/
│   │   │           ├── TestStep.java                 # Test step model
│   │   │           └── TestData.java                 # Test data model
│   │   │
│   │   └── resources/
│   │       ├── config.properties                     # Configuration file
│   │       ├── log4j2.properties                     # Log4j configuration
│   │       ├── testng.xml                            # TestNG configuration
│   │       ├── test_data/
│   │       │   ├── test_cases.xlsx                   # Test case data
│   │       │   ├── test_scenarios.json               # Test scenarios
│   │       │   └── keywords_mapping.json             # Keyword mapping
│   │       └── keywords/
│   │           └── keyword_library.xlsx              # Keyword library
│   │
│   └── test/
│       ├── java/
│       │   └── com/selenium/kwdf/
│       │       └── tests/
│       │           ├── SampleKeywordTest.java        # Sample test using keywords
│       │           └── KeywordExecutionTest.java     # Keyword execution test
│       │
│       └── resources/
│           └── test-config.properties                # Test environment config
│
├── test-reports/                           # Test reports directory
├── target/                                 # Maven build directory
│   └── surefire-reports/                   # Surefire reports
└── test-output/                            # TestNG output directory
```

---

## Key Features

### 1. **Keyword-Driven Framework**
- Centralized keyword library
- Easy to maintain and extend
- Non-technical users can write tests

### 2. **Data-Driven Testing**
- Excel support (Apache POI)
- JSON data files
- External data management

### 3. **Comprehensive Logging**
- Log4j2 integration
- File & console logging
- Detailed execution logs

### 4. **Advanced Reporting**
- ExtentReports with dark theme
- Step-by-step execution details
- System information capture
- Screenshots on failure

### 5. **Test Management**
- TestNG framework
- Test listeners
- Retry mechanism for flaky tests
- Parallel execution support

### 6. **Configuration Management**
- External configuration via properties
- Environment-specific settings
- Easy setup changes

---

## Maven Commands

### Install Dependencies
```bash
mvn clean install
```

### Run Tests
```bash
mvn clean test
```

### Run Specific Test
```bash
mvn test -Dtest=SampleKeywordTest
```

### Generate Reports
```bash
mvn surefire:report
```

### Clean Build
```bash
mvn clean
```

### Package JAR
```bash
mvn clean package
```

---

## Configuration Files

### 1. **pom.xml** ✓ (CREATED)
- Maven project configuration
- All dependencies defined
- Build plugins configured

### 2. **config.properties** (TO BE CREATED)
```properties
# Application Configuration
baseURL=https://example.com
browser=chrome
implicit_wait=10
explicit_wait=15
page_load_timeout=30

# Test Data
test_data_path=src/main/resources/test_data
keyword_library_path=src/main/resources/keywords

# Reporting
report_path=test-reports
```

### 3. **log4j2.properties** (TO BE CREATED)
- Log configuration
- File logging
- Console output
- Log levels

### 4. **testng.xml** (TO BE CREATED)
- Test suite configuration
- Test groups
- Listeners configuration
- Parallel execution settings

---

## Keyword Library Structure

### Browser Keywords
```java
open()          // Open application URL
close()         // Close browser
maximize()      // Maximize window
refresh()       // Refresh page
getTitle()      // Get page title
getUrl()        // Get current URL
```

### Element Keywords
```java
click()         // Click element
type()          // Enter text
clear()         // Clear field
submit()        // Submit form
select()        // Select dropdown
getText()       // Get element text
```

### Validation Keywords
```java
assertEquals()      // Assert equality
assertContains()    // Assert contains text
assertVisible()     // Assert element visible
assertNotVisible()  // Assert element hidden
assertEnabled()     // Assert element enabled
```

### Wait Keywords
```java
waitForElement()    // Wait for element presence
waitForElementVisible()  // Wait for visibility
waitForElementClickable() // Wait for clickability
waitForPageLoad()   // Wait for page load
```

### Data Keywords
```java
readExcelData()     // Read from Excel
readJSONData()      // Read from JSON
writeExcelData()    // Write to Excel
getTestData()       // Get specific test data
```

---

## Test Data Format

### Excel Format (test_cases.xlsx)
```
TestCaseID | TestScenario | Keyword | ObjectName | Value | ExpectedResult
-----------|--------------|---------|------------|-------|----------------
TC001      | Login Test   | click   | LoginBtn   |       | Login page opens
TC002      | Search Test  | type    | SearchBox  | Hello | Search results
```

### JSON Format (test_scenarios.json)
```json
{
  "TestCases": [
    {
      "TestCaseID": "TC001",
      "Steps": [
        {
          "Keyword": "click",
          "ObjectName": "LoginBtn",
          "Value": ""
        }
      ]
    }
  ]
}
```

---

## Dependency JAR Files Included

All dependencies are automatically downloaded by Maven from:
- **Maven Central Repository** (https://repo.maven.apache.org/maven2/)
- **JCenter Repository** (deprecated but cached)

Key JAR files:
- `selenium-java-4.15.0.jar`
- `testng-7.8.1.jar`
- `extentreports-5.1.1.jar`
- `poi-5.2.3.jar`
- `poi-ooxml-5.2.3.jar`
- `log4j-core-2.20.0.jar`
- `log4j-api-2.20.0.jar`
- `gson-2.10.1.jar`
- `webdrivermanager-5.6.3.jar`

---

## Setup Instructions

### Step 1: Clone Repository
```bash
git clone https://github.com/somnathsarak/selenium-keyword-driven-framework.git
cd selenium-keyword-driven-framework
```

### Step 2: Install Dependencies
```bash
mvn clean install
```

### Step 3: Configure Properties
- Edit `src/main/resources/config.properties`
- Update baseURL, browser, credentials
- Configure timeouts as needed

### Step 4: Create Test Data
- Add Excel files to `src/main/resources/test_data/`
- Create JSON files with test scenarios
- Set up keyword mapping

### Step 5: Write Tests
- Use keyword library in test classes
- Follow keyword-driven approach
- Use data-driven patterns

### Step 6: Execute Tests
```bash
mvn clean test
```

### Step 7: View Reports
- Open `test-reports/ExtentReport_*.html`
- Check `target/surefire-reports/index.html`
- Review `test-output/index.html`

---

## Framework Status

- ✓ **Maven Project**: Configured
- ✓ **All Dependencies**: Added to pom.xml
- ✓ **JAR Files**: Managed by Maven
- ✓ **Project Structure**: Documented
- ⏳ **Base Classes**: To be created
- ⏳ **Keyword Classes**: To be created
- ⏳ **Utility Classes**: To be created
- ⏳ **Test Classes**: To be created
- ⏳ **Configuration Files**: To be created

---

## Next Steps

1. Create all Java classes in appropriate packages
2. Implement keyword library
3. Create utility classes for data handling
4. Set up configuration files
5. Create sample tests
6. Implement ExtentReports integration
7. Set up TestNG listeners
8. Create test data Excel/JSON files
9. Execute tests and validate
10. Generate comprehensive reports

---

## Version Info

- **Framework Version**: 1.0.0
- **Java Version**: 11+
- **Maven Version**: 3.8+
- **Selenium Version**: 4.15.0
- **TestNG Version**: 7.8.1
- **ExtentReports**: 5.1.1
- **Apache POI**: 5.2.3

---

## Support & References

- **Maven**: https://maven.apache.org/
- **Selenium**: https://www.selenium.dev/
- **TestNG**: https://testng.org/
- **ExtentReports**: https://www.extentreports.com/
- **Apache POI**: https://poi.apache.org/
- **Log4j2**: https://logging.apache.org/log4j/2.x/

---

**Created**: December 24, 2025  
**Last Updated**: December 24, 2025  
**Status**: Foundation Setup Complete ✓
