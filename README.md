This project discuss about Testing Approach and Planning for given scenarios:

### Problem Statement

Imagine the following situation. You need to establish a QA process in a cross-functional team.
The team builds a front-end application using REST APIs.

1. Where would you start? What would be your first steps?
2. Which process would you establish around testing new functionality? How would you want the features to be tested?
3. Which tools would you suggest using to help your team with a daily work?
4. If you would do a test automation which techniques or best practices would you use the application?

### Solution

1. Where would you start? What would be your first steps?
   Answer:
 - Will thoroughly understand the problem statement defining the system (solution proposed).
 - Will identify different modules forming the system.
 - Will identify different integration points/areas.
 - Will collect information about different REST APIs involved in the System.
 - Will collect information about the contracts of those API.
 - Will collect information about the different End to End flows.
 - Will make sure that proper Unit and Integration test coverage is being taken care around these REST APIs.
 - Will plan out End to End tests to be executed every-time a new code checkin comes into different code repositories for
 quicker feedback about checkin.

2. Which process would you establish around testing new functionality? How would you want the features to be tested?
    Answer:
  - Quality should start from initial level, thus will take part in requirement gathering and analysis to understand what and
  how the feature will be developed, what REST calls will be involved and what communication contracts will it be following. Will make sure that enough information about these area is being gathered and documented along with story.
  - I will suggest to follow Testing Pyramid based TDD approach to fail fast than later.
  - I will recommend teams to ensure strong code coverage by automated tests (Unit & Integration at preliminary level; followed by End to End Functional Automation). Adding a web-hook to keep check on minimum code coverage (e.g. 90% code coverage is mandatory), which is integrated with CI will help in keeping eye on this.
  - As a QA process I will review the code to check if enough tests has been covered under unit and integration tests for newly developed feature or story.
  - Will identify required Test scenarios for functional automation that seats at top of TDD (that means the scenarios that couldn't be added under Unit or Integration tests) and will add it to Functional Automation code base in parallel to development of that feature/story. So, that part can be checked in as soon as the feature gets delivered to testing or in later phase.
  - Regarding the feature Functional testing (beyond Automation), will test REST end points to check desired results of hitting them.
  Will test different functional scenarios like what response it returns for both positive and negative scenarios. Impact of hitting a REST end point on the desired area like if it is expected to create a new dataset/record as a result of the same, will verify DBs for the same to validate dataset/record got created, and a vice-versa testing can be done around REST APIs.
  - Regarding the feature Non-Functional performance testing, will create an automated test suite with the help of performance testing tool like gatling with multiple assertions to test feature behaviour under load.
  - Regarding the feature Functional testing with GUI in place, will test feature through application with various testing technics like equal partitioning, boundary value analysis, exploratory testing etc.

3. Which tools would you suggest using to help your team with a daily work?
    Answer:
  - For Basic testing - Web Browser's Devloper Tool
  - For Functional automation - Guage Framework - Free and open source.
  - For REST testing - Postman - Basic version comes for free.
  - For Load & Performance testing - Gatling - Free and open source.

4. If you would do a test automation which techniques or best practices would you use the application?
    Answer:
  - Will follow Test Design Pattern - it will make sure that test being written should be maintainable, and best coding practices getting followed. eg. Could use Page object model pattern for multipage AUT to enhances test maintenance and reduces code duplication.
  - Will identify and annotate/tag tests for different purpose. eg. Tests for Smoke, Tests for Regression etc.
  - I will follow Data Driven Testing approach to use the same test with different inputs due to test a considerable variety of scenarios without need of code changing.
  - Will externalise common elements for reusability and to avoid redundant code.
  - For GUI tests - as a best practice I will make use of explicit and fluent waits as much as possible for faster execution of Tests.
  - For GUI tests - as a web element locator will use id/name/class etc. on higher priority than xpath.
  - For GUI tests - Will keep 'Screenshots on failure' enabled for faster debugging
  - I will suggest to follow Testing Pyramid based TDD approach to fail fast than later. Which means Unit test will have the highest number count, test count for Integration will be less than Unit and at Top least number of the automated Functional tests covering End to End tests.
  - The above approach helps in delivering features with high confidence that it is not breaking existing features or system.
  - I will make sure that CI integrated web-hook confirming minimum test coverage is being maintained, so build should fail if it doesn't follow the criteria.
  - For test consistency purpose, can think of using docker and a dedicated environment for automated test.
