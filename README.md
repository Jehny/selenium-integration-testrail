# Selenium JAVA integration TESTRAIL
###Information environment

This project was developed in:

> **OS:** Windows

> **Driver:** All drivers are to windows

> **Config Paths:** All paths are with /  

#####Running the project without library JAR based on this project

###Structure

#####Package Base:

> This package there are classes responsible for reports, generic methods, browser settings and settings about testrail methods. E.g.: BaseTest it is responsible to connect reports and TESTRAIL API. The ReportTestListener it is responsible by reports and logs on HTML Report and log on TESTRAIL. 

#####Package Page:

> This package you will go to put all page object.

#####Package Tests:

> This package you will go to put all the test cases. Imagine that each page will be a test suite and each class that will be tested have to be added into test-suite.xml file.

#####Package Testrail:

> This package has settings about TestRail API Client and an Interface with settings of a Testng annotation to identify test cases on test classes.  

#####Folder config:

> It has a file that have many properties to config yout environment.

######properties file:

> TestRail configurations

> - **test.rail.url** = [http://urltestrail/]

> - **test.rail.username** = [Username]

> - **test.rail.password** = [Pass]

> - **test.rail.suite.id** = 0

> - **test.rail.project.id** = 1

> - **test.rail.runname.prefix** = iDevOps

> By default value is false on BaseTest
If you don't want post the result to testRail not set value.
e.g. test.rail.post.result

> - **test.rail.post.result** = true (It will put the result at TestRail)

#####Folder results-tests:

> This package has the report test folders. Each execution the project create a new folder with Date and time dynamically. This configuration are in BaseTest class.

#####Folder test-suites:

> This file you will go put the test class that you want to run.

######test-suites:


#####Running the project using library JAR based on this project

