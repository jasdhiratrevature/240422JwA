## Testing Study Guide
NOTE: the content in this study guide is somewhat abbreviated: more details can be found on many of these subjects in the week-3 directories 

### Intro to Testing
- Why test?
  - Discover defects, faults, bugs
  - Increase stability of the project
  - Increase developer confidence in the code
  - Improve the ability to refactor
- Testing principles
  - Testing shows presence of defects, not their absence
  - Exhaustive testing is impossible
  - Test early to save time/money
  - Defect clustering
  - Pesticide paradox: old tests prevent don't identify new issues
  - Testing is context dependent (use different approach to different types of software)
  - Absence of defects does not imply "good" software, other considerations like usability are important
- Fundamental test process
  - Test Planning and Control
  - Test Analysis and Design
  - Test Implementation and Execution
  - Evaluating Exit Criteria and Reporting
  - Test Closure
- Verification vs Validation
  - Verification: did we build the product right?
    - Verify by passing test cases
  - Validation: did we build the right product?
    - Validate by passing user acceptance testing
- Testing Lifecycle: analogous to Software Development Lifecycle
  - Requirements Analysis
  - Test Planning
  - Test Case Development
  - Test Environment Setup
  - Test Execution
  - Test Reporting
- Defect Lifecycle
  - New
  - Assigned
  - Open
  - Fixed
  - Re-test
  - Reopened
  - Rejected
  - Deferred
  - Closed
- Defect Report
  - A defect is any condition, behavior or functionality that produces an incorrect or unexpected result compared to the requirements
  - Important info to raise when reporting a defect:
    - Priority
    - Severity
    - Environment information (OS, browser, etc)
    - Steps to reproduce
- Testing documents
  - Test Plan
    - describes scope, objective of testing
    - written to identify potential risks and issues of the project
  - Test strategy
    - defines HOW the testing is to be done
    - what testing techniques to be used
  - In smaller projects, test strategy can be a section in the test plan document

## Types of Testing
- Functional
  - broad category of tests, relates to features that a user can use (i.e. WHAT the system does)
- Non-functional
  - broad category of tests, relates to the way the software operates (i.e. HOW the system operates)
  - Can include:
    - Security
    - Usability
    - Compatibility
    - Performance
- Static testing
  - broad category, refers to testing/examining a program's code without running it
- Dynamic testing
  - broad category, involves interacting with the system while the program runs
- White box
  - Testing with knowledge of the internal structure or code of the application
- Black box
  - Testing functionality without knowing the internal structure or code
  - Only testing WHAT happens, not HOW the feature is implemented
- Testing Pyramid
  - Unit testing
    - Testing of the smallest individual parts (units) of the application
    - Base of pyramid - most tests should be unit tests
  - Integration testing
    - Testing the interactions of individual units working together
  - System testing
    - Testing how the system functions as a whole
    - Also known as end-to-end (e2e) tests, because a feature is tested from front end (UI) all the way through the tech stack to the backend (database)
  - User Acceptance testing
    - End user of the application validates that it satisfies their requirements
    - Top of pyramid, should have relatively fewer system and UAT tests
- Performance Testing
  - Endurance: testing how long an application can be sustained under normal load
  - Performance: testing responsiveness and latency under normal load
  - Load: measuring performance at differing loads of traffic
  - Stress: continually increasing the load to identify the breaking point of the application
- Compatibility Testing
  - Testing that a feature or application works the same on different platforms, operating systems, browsers, etc
- Regression testing
  - testing done after one or more new features are implemented to check if the new feature/s broke old features
- Automated testing
  - Not subject to human error
  - Quicker than manual testing
  - Initial upfront investment, but saves time in the long run
  - Reliable, can run 24/7
  - Can handle complex and large applications
  - Well suited for unit, integration, regression, and performance testing
- Manual testing
  - Subject to human error
  - Slower than automated testing
  - Easier for smaller or simpler applications or features
  - Well suited for usability or UAT testing
- Smoke testing
  - Subset of acceptance testing, performed on entire system
  - Test that verifies basic and critical functionality to identify glaring defects (i.e. if there's smoke, there's fire)
  - Performed first in a build, so that if it fails we don't need to waste time testing more advanced features
  - e.g. for a calculator, testing that pressing the ON button causes the screen to light up. if this fails there is no point in checking its other features
- Sanity testing
  - Subset of regression testing, performed on specific feature
  - Performs a "sanity check" to verify bugs have been fixed or functionality works as intended
  - e.g. for a calculator, check that 2+2=4. if this fails, there is no point in checking further addition
- Exploratory testing
  - Type of manual testing where test cases are not created in advance but instead on the fly
  - Helps to learn about the system
- Alpha/Beta testing
  - Alpha: end users come on-premise to test, this phase comes first
  - Beta: limited release to specific end-users for testing, not on-premise

### Testing Techniques
- Positive / negative
  - Positive
    - verify the "happy path", or what happens when valid inputs are given
    - e.g. verify that a login form will redirect to the home page when valid username and password are entered
  - Negative
    - verify the "sad path", or the error states that can occur when invalid inputs are given
    - e.g. verify that a login form does NOT redirect to home page when invalid credentials are given
- Equivalence partitioning
  - Possible inputs to try are infinite, so break them up into "classes"
  - Choose a representative from each class to represent entire class
  - e.g. for testing calculator division operation, partition inputs into negative, 0, and positive
  and have 3 test cases: one with negative number, one using 0, one using positive number
  - Boundary value analysis: most defects occur at the boundaries of equivalence classes
- State transition diagram
  - Identifies the different states of the system and the possibilities of navigating between the states
  - e.g. defect lifecycle is an example of state transition. project management tools model these states
- Decision tables
  - List all possible combinations of inputs and the resulting output
  - Provides good visualization of requirements