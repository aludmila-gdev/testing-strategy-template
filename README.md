# Acceptance testing strategy 
------
## About the strategy
What is this document? what do i find in it? how was it divided? What topics does it contain? If possible, include anchor links for navigation in this document.

This documentation has the following sections:

1. [Test Approach](#test-approach)
2. [Test Deliverables](#test-deliverables)
3. [Test scenarios](#test-scenarios)
4. [Test Environment](#test-environment)
5. [Approach to test automation](#approach-to-test-automation)
    * [Choosing the tool for automating UI tests](#choosing-the-tool-for-automating-UI-tests)
    * [Choosing the tests that will be automated in the UI](#choosing-the-tests-that-will-be-automated-in-the-UI)
6. [Running the tests scripts](#running-the-tests-scripts)
7. [Test Report](#test-report)
8. [Dependencies](#dependencies)
9. [Bug Report](#bug-report)
10. [References](#references)

- - - -
## Test Approach
How are the tests described? (Gherkin, step by step, etc).

Where do I find detailed test cases?

How were the tests prioritized? What criteria are used?

What levels of testing will be performed? What were the criteria for this decision?

What types of testing will be performed ( Load testing, Security testing, Performance testing, CrossBrowser testing etc.)? What were the criteria for this decision?

- - - -
## Test Deliverables
* The test deliverables are:
    * Features files, with description of test cases and scenarios;
    * **_[LANGUAGE]_** codebase using **_[FRAMEWORK]_**;
    * **_[FORMAT]_** reports located in the **_[PATH]_**;
    * Test evidences in **_[FORMAT]_** located **_[PATH]_**;
    * Execution scripts using **_[SCRIPT LANGUAGE USED (MAKE, RAKE, ETC)]_**. The intention is that the tests are subject to integration in a pipeline.
    * Defects report which will be described in tool **_[BUG TRACKING TOOL]_**. [Link to access the bug tracking tool here.](https://www.google.com)

- - - -
## Test scenarios

The test scenarios were modeled based on the following techniques:
* Equivalence Partitioning
* Boundary Testing
* Decision Table
* State Transition Testing

### List of test scenarios:
|        ID          |                               Description                                            |  Technique |
|   :-------------:  |                             --------------                                           | --------- |
|      [CT-001]      | Check system behavior when **valid** email id and password is entered.               |     |
|      [CT-002]      | Check system behavior when **invalid** email id and **valid** password is entered.   |     |
|      [CT-003]      | Check system behavior when **invalid** email id and **invalid** password is entered. |     |
|      [CT-004]      | Check system behavior when email id and password are left blank and Sign in entered. |     |
|      [CT-005]      | Check Forgot your password is working as expected.                                   |     |

- - - -
## Test Environment
Below are all the tools / platforms used during the development of the testing strategy and automated testing code:


|        Item        |        Description        |        Version        |        Note        | 
|       :----:       |        -----------        |       :-------:       |        ----        | 
| IntelliJ IDEA      |           IDE             |        Last           |         N/A        |
| Google Chrome      | Testing browser           |       87.0.4280.88    |         N/A        |
|    Pa11y           | Accessibility testing automation tool |  5.0.0    |         N/A        |
| GitHub             | Code repository and documentation |   N/A         |         N/A        |
| Tool/Requirement   | Description               |        Last           |         N/A        |
| Tool/Requirement   | Description               |        Last           |         N/A        |

- - - -
##  Approach to test automation

### Choosing the tool for automating UI tests

The automation tool was chosen based on the following criteria:

**!!! DELETE CRITERIA THAT DO NOT APPLY AND LEAVE ONLY THOSE THAT WERE REALLY USED!!!**

* **Ease of Developing and Maintaining the Scripts:** Development & maintenance of test scripts should be as simple as possible to decrease the human and time resource utilization.
* **Ease of Test Execution for Non-Technical user:** The test suite execution should be simple for any project member to run them easily as and when required. Also, it should be easy for manual testers who have very little or no technical knowledge.
* **Support to Web, Desktop & Mobile application:** Leveraging 3 different tools for 3 types of platforms for test automation is a complicated task to handle. It is better to select a tool that supports all the three platforms.
* **Intuitive Test Report:** Test reports build confidence and so the reports need to be intuitive and simple for the management team to understand easily.
* **Cross Browser Testing:** Support to Cross browser testing is a must when there are multiple end-users and no particular browser restriction.
* **Support to Keyword & Data Driven Testing:** Keyword driven testing acts as an extension to the data driven testing framework. When a project becomes complex, test framework needs to be extended.
* **Technical Support and Assistance:** Automation Engineers definitely need help while handling critical problems of a project. The tool that provides technical support and assistance would be of great help.
* **Language Support like C#, Java, Python and others:** Every test scenario cannot be recorded. In some cases, the tester must write the code. So, the tool that supports the required language to write the customized scripts would be helpful.
* **TFS DevOps integration with builds:** Support to integrate with Continuous Integration tools for automated builds and deployments is necessary.
* **Pricing:** Depending on the above qualities and project cost estimates, evaluate the cost difference among the other available automation tools.

### Choosing the tests that will be automated in the UI
Below, the criteria that were used to decide which tests are good candidates for automation:

**!!!!!!! DELETE CRITERIA THAT DO NOT APPLY AND LEAVE ONLY THOSE THAT WERE REALLY USED!!!!!**
_How do you choose which tests to automate and which tests to leave for manual testing?_

**Tests that should be automated:**
* Business critical paths - the features or user flows that if they fail, cause a considerable damage to the business.
* Tests that need to be run against every build/release of the application, such as smoke test, sanity test and regression test.
* Tests that need to run against multiple configurations — different OS & Browser combinations.
* Tests that execute the same workflow but use different data for its inputs for each test run e.g. data-driven.
* Tests that involve inputting large volumes of data, such as filling up very long forms.
* Tests that can be used for performance testing, like stress and load tests.
* Tests that take a long time to perform and may need to be run during breaks or overnight.
* Tests during which images must be captured to prove that the application behaved as expected, or to check that a multitude of web pages looks the same on multiple browsers.
* Generally speaking, the more repetitive the test run, the better it is for automation.

**Tests that should not be automated:**
* Tests that you will only run only once. The only exception to this rule is that if you want to execute a test with a very large set of data, even if it’s only once, then it makes sense to automate it.
* User experience tests for usability (tests that require a user to respond as to how easy the app is to use).
* Tests that need to be run ASAP. Usually, a new feature which is developed requires a quick feedback so testing it manually at first
* Tests that require ad hoc/random testing based on domain knowledge/expertise - Exploratory Testing.
* Intermittent tests. Tests without predictable results cause more noise that value. To get the best value out of automation the tests must produce predictable and reliable results in order to produce pass and fail conditions.
* Tests that require visual confirmation, however, we can capture page images during automated testing and then have a manual check of the images.
* Test that cannot be 100% automated should not be automated at all, unless doing so will save a considerable amount of time.

### List of scenarios that have been automated based on established criteria
* CT-001 - Check system behavior when **valid** email id and password is entered. 
* CT-002 - Check system behavior when **invalid** email id and **valid** password is entered.
* CT-003 - Check system behavior when **invalid** email id and **invalid** password is entered.
* CT-004 - Check system behavior when email id and password are left blank and Sign in entered.
* CT-005 - Check Forgot your password is working as expected.

- - - -
## Running the tests scripts
* The following scripts do, respectively:

| Description		| 	Command   |
|	----------		|	:-------------:	|
| Install dependencies	 |   `make setup` | 
| Run tests on **Chrome** |     `make e2e_tests_on_chrome`    |
| Run tests on **Firefox** |  `make e2e_tests_on_firefox` |
| Run tests on **Safari** |  `make e2e_tests_on_safari` |

- - - -
## Test Report
* Below is an image of the test execution report:

 ![](README/report_screenshot.png)

- - - -
## Dependencies
The dependencies used in the functional testing automation project are:

| Tool		| 	Version   |
|----------		|   :-------------:	|
| TOOL1 		|   `2.7.0` 	| 
| TOOL2 	|     `3.1.2`    	|
| TOOL3 	|     `3.32.1`    	|
| TOOL4 	|     `3.4.2`    	|
| TOOL5 	|     `3.142.7`    	|

- - - -
## Bug Report

* **Bug id:** [001]
	* **Severity:** High 
	* **Priority:** High 
	* **Reported By:** me
	* **Reported On:** 10/01/2021
	* **Status:** New
	* **Environment:** Safari
	* **Description:** Describe here a brief summary of the problem.
	* **Steps to reproduce the problem:** Describe here the sequence of steps necessary to reproduce the problem:
	    1. Step 1
	    2. Step 2
	    3. Step 3
	    4. Step N
    * **Obtained Result:** Through the steps described above, what should have happened? How did the system really behave? What is the evidence for this malfunction? Add screenshots, videos, logs ... And everything else that can provide information about the current wrong state of the system.
    * **Expected Result:** Through the steps described above, what should happen? What behavior should the system behave? Put here evidence that justifies this (Text of the documentation you used to reach this conclusion).


* **Bug id:** [002]
	* **Severity:** High 
	* **Priority:** High 
	* **Reported By:** me
	* **Reported On:** 10/01/2021
	* **Status:** Fixed
	* **Environment:** Chrome
	* **Description:** Describe here a brief summary of the problem.
	* **Steps to reproduce the problem:** Describe here the sequence of steps necessary to reproduce the problem:
	    1. Step 1
	    2. Step 2
	    3. Step 3
	    4. Step N
    * **Obtained Result:** Through the steps described above, what should have happened? How did the system really behave? What is the evidence for this malfunction? Add screenshots, videos, logs ... And everything else that can provide information about the current wrong state of the system.
    * **Expected Result:** Through the steps described above, what should happen? What behavior should the system behave? Put here evidence that justifies this (Text of the documentation you used to reach this conclusion).

- - - -
## References
Important links that supported the development of this testing strategy:

* [Make a README](https://www.makeareadme.com/)
* [How to create Test Strategy Document (Sample Template)](https://www.guru99.com/how-to-create-test-strategy-document.html)
* [How To Write Test Strategy Document (With Sample Test Strategy Template)](https://www.softwaretestinghelp.com/writing-test-strategy-document-template/)
* [Online Markdown Editor - Dillinger, the Last Markdown Editor ever](https://dillinger.io/)
* [What is Test Scenario? Template with Examples](https://www.guru99.com/test-scenario.html)
* [Boundary Value Analysis and Equivalence Partitioning Testing](https://www.guru99.com/equivalence-partitioning-boundary-value-analysis.html)
* [Decision Table Testing: Learn with Example](https://www.guru99.com/decision-table-testing.html)
* [What is State Transition Testing? Diagram, Technique, Example](https://www.guru99.com/state-transition-testing.html#1)
* [How to Choose Which Test to Automate?](https://devqa.io/choose-tests-automate/)
* [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [4 Simple Steps to Select the Right Test Automation tool for your Project](https://www.saviantconsulting.com/blog/4-steps-select-test-automation-tool.aspx)
* [Template used in this document](https://github.com/knludi/testing-strategy-template)




