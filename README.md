# Selenium JAVA integration TESTRAIL

### Information environment

This project was developed in:

> **OS:** Windows

> **Driver:** All drivers are to windows

> **Config Paths:** All paths are with /  

### Instalation

> 1. Download the project

> 2. Import as project maven

> 3. Configure the Build Path to actual JAVA

> 4. Configure properties file with your credentials, URL and testrail credentials.

> 5. Click right button under project root and Run as -> Maven install

> 6. To run the project many times: Click right button under project root and Run as -> Maven test

##### Running the project without library JAR based on this project

### Structure

##### Package Base:

> This package there are classes responsible for reports, generic methods, browser settings and settings about testrail methods. E.g.: BaseTest it is responsible to connect reports and TESTRAIL API. The ReportTestListener it is responsible by reports and logs on HTML Report and log on TESTRAIL. 

##### Package Page:

> This package you will go to put all page object.

##### Package Tests:

> This package you will go to put all the test cases. Imagine that each page will be a test suite and each class that will be tested have to be added into test-suite.xml file.

##### Package Testrail:

> This package has settings about TestRail API Client and an Interface with settings of a Testng annotation to identify test cases on test classes.  

##### Folder config:

> It has a file that have many properties to config yout environment.

###### properties file:

> TestRail configurations

> - **test.rail.url** = [http://urltestrail/]

> - **test.rail.username** = [Username]

> - **test.rail.password** = [Pass]

> - **test.rail.suite.id** = [Suite ID in TestRail (Can not be NULL, put 0 if you don't have)]

> - **test.rail.project.id** = [Project ID in TestRail]

> - **test.rail.runname.prefix** = [Project name for example]

> By default value is false on BaseTest
If you don't want post the result to testRail not set value.
e.g. test.rail.post.result

> - **test.rail.post.result** = true (It will put the result at TestRail)

##### Folder results-tests:

> This package has the report test folders. Each execution the project create a new folder with Date and time dynamically. This configuration are in BaseTest class.

##### Folder test-suites:

###### test-suites file:

> This file you will go put the test class that you want to run.

Example:
```xml
<classes>
  <class name="sample.tests.SimplePageTest" />
  <class name="sample.tests.SimplePageTest2" />
</classes> 
```
OR

```xml
<classes>
  <class name="sample.tests.SimplePageTest" />
</classes>
<classes>
  <class name="sample.tests.SimplePageTest2" />
</classes> 
```

There are some properties as:

>  - **Environment** and **Browser** that it should be informed

#### Test Cases Scripts and Test Case TestRail

> If you want run the test cases on Test rail with scripts you should put testcaseId in your test.
e.g:

```java
@Test
@TestRail(testCaseId = {1})
public void test() throws IOException, APIException, InterruptedException {
  page.login();
}
```

OR 

```java
@Test
@TestRail(testCaseId = {1, 2, 3})
public void test() throws IOException, APIException, InterruptedException {
  page.login();
}
```

----------------------------------------------------------------------------------------------------------------------------------------

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

----------------------------------------------------------------------------------------------------------------------------------------

### Running the project using library JAR based on this project

If you want only use the options and do your own implementation use the library.

##### HOW to do

> 1. Do the instalation step

> 2. In pom.xml file add the dependency

```xml
<dependency>
    <groupId>automationtestrail</groupId>
    <artifactId>automation</artifactId>
    <version>1.0</version>
    <scope>system</scope>
    <systemPath>${project.basedir}/lib/selenium-testrail-integration.jar</systemPath>
</dependency>
```

> 3. GET the JAR file and add on lib folder in your project

[The JAR file](https://github.com/Jehny/selenium-integration-testrail/tree/master/lib) 

> 4. To use this methods and testrail integration in the Page Objects and Test Cases extends to BaseTest Class.

e.g: 

```java
public class SimplePageTest extends BaseTest {}
```


