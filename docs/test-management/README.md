# Test Design & Management

## Test Planning

### What is Test Planning?
Test planning is the process of defining the scope, approach, resources, and schedule of testing activities.

### Components of a Test Plan

#### 1. Test Objectives
- Define what needs to be tested
- Identify success criteria
- Set quality goals

#### 2. Test Scope
- **In Scope**: Features/functionalities to be tested
- **Out of Scope**: Features/functionalities not to be tested
- **Assumptions**: Conditions assumed to be true
- **Constraints**: Limitations and restrictions

#### 3. Test Strategy
- Testing approach (manual vs. automated)
- Types of testing to be performed
- Entry and exit criteria
- Suspension and resumption criteria

#### 4. Resource Planning
- **Team**: Roles and responsibilities
- **Environment**: Hardware, software, tools
- **Tools**: Testing tools required
- **Budget**: Cost estimation

#### 5. Schedule
- Milestones and deadlines
- Task dependencies
- Buffer time for contingencies

#### 6. Risk Management
- Identify potential risks
- Assess risk probability and impact
- Define mitigation strategies

### Test Plan Template Structure

```markdown
# Test Plan for [Project Name]

## 1. Introduction
- Purpose
- Scope
- References

## 2. Test Items
- Features to be tested
- Features not to be tested

## 3. Test Approach
- Testing levels
- Testing types
- Test techniques

## 4. Pass/Fail Criteria
- Entry criteria
- Exit criteria
- Suspension criteria

## 5. Test Deliverables
- Test plan document
- Test cases
- Test reports

## 6. Test Environment
- Hardware requirements
- Software requirements
- Network configuration

## 7. Schedule
- Test phases and milestones

## 8. Staffing and Training
- Roles and responsibilities
- Training requirements

## 9. Risks and Contingencies
- Identified risks
- Mitigation plans

## 10. Approvals
- Sign-off requirements
```

## Test Case Design

### What is a Test Case?
A test case is a set of conditions or variables under which a tester will determine whether a system under test satisfies requirements.

### Components of a Test Case

1. **Test Case ID**: Unique identifier
2. **Test Case Title**: Brief description
3. **Description**: Detailed test case description
4. **Preconditions**: Prerequisites before execution
5. **Test Steps**: Step-by-step instructions
6. **Test Data**: Input data required
7. **Expected Result**: Expected outcome
8. **Actual Result**: Observed outcome (filled during execution)
9. **Status**: Pass/Fail/Blocked/Skip
10. **Priority**: High/Medium/Low
11. **Severity**: Critical/Major/Minor/Trivial

### Test Case Example

```
Test Case ID: TC_001
Title: Verify user login with valid credentials
Description: Test the login functionality with valid username and password
Preconditions: 
  - User account exists in the system
  - User is on the login page

Test Steps:
1. Enter valid username
2. Enter valid password
3. Click "Login" button

Test Data:
  Username: testuser@example.com
  Password: ValidPass123!

Expected Result:
  - User is successfully logged in
  - User is redirected to dashboard
  - Welcome message is displayed

Priority: High
Severity: Critical
```

### Test Case Design Techniques

#### 1. Equivalence Partitioning
- Divide input data into equivalent partitions
- Test one value from each partition
- Example: Age field (0-17, 18-65, 66+)

#### 2. Boundary Value Analysis
- Test at boundaries of input domains
- Example: For range 1-100, test 0, 1, 100, 101

#### 3. Decision Table Testing
- Systematic approach for complex business logic
- Combinations of inputs and corresponding outputs

```
| Condition 1 | Condition 2 | Action 1 | Action 2 |
|------------|-------------|----------|----------|
| True       | True        | Execute  | Skip     |
| True       | False       | Skip     | Execute  |
| False      | True        | Skip     | Execute  |
| False      | False       | Skip     | Skip     |
```

#### 4. State Transition Testing
- Test system behavior with different states
- Example: Order states (Pending → Processing → Shipped → Delivered)

#### 5. Use Case Testing
- Derive test cases from use cases
- Focus on user scenarios

#### 6. Error Guessing
- Experience-based technique
- Predict where errors might occur

## Test Data Management

### What is Test Data?
Test data is the data that is used to execute tests, which can include input values, expected results, and setup data.

### Types of Test Data

#### 1. Valid Test Data
- Data that should be accepted by the system
- Tests positive scenarios

#### 2. Invalid Test Data
- Data that should be rejected by the system
- Tests negative scenarios

#### 3. Boundary Test Data
- Data at the edges of valid/invalid ranges

#### 4. Default Test Data
- Pre-configured or system-generated data

### Test Data Management Best Practices

1. **Data Security**
   - Mask sensitive data
   - Comply with data protection regulations
   - Use synthetic data when possible

2. **Data Quality**
   - Ensure data accuracy
   - Keep data up-to-date
   - Validate data integrity

3. **Data Reusability**
   - Create reusable datasets
   - Document data requirements
   - Version control test data

4. **Data Maintenance**
   - Regular cleanup
   - Archive old data
   - Refresh test databases

### Test Data Generation Techniques

- **Manual Creation**: Create data manually
- **Data Masking**: Anonymize production data
- **Data Subsetting**: Extract subset of production data
- **Synthetic Data**: Generate artificial data
- **Data Seeding**: Populate database with predefined data

## Bug Tracking and Reporting

### What is a Bug/Defect?
A bug is a flaw in the software that causes it to produce an incorrect or unexpected result, or to behave in unintended ways.

### Bug Life Cycle

```
New → Assigned → Open → Fixed → Retest → Verified → Closed
                    ↓
                Rejected / Deferred / Duplicate
```

### Bug Report Components

1. **Bug ID**: Unique identifier
2. **Summary**: Brief description
3. **Description**: Detailed explanation
4. **Steps to Reproduce**: How to recreate the bug
5. **Expected Result**: What should happen
6. **Actual Result**: What actually happens
7. **Severity**: Impact on system
8. **Priority**: Urgency of fix
9. **Environment**: OS, browser, version
10. **Attachments**: Screenshots, logs, videos

### Bug Report Example

```
Bug ID: BUG-001
Summary: Login button not responding on mobile devices

Description:
The login button on the authentication page does not respond 
to tap events on mobile devices using iOS Safari browser.

Steps to Reproduce:
1. Open the application on iPhone using Safari
2. Navigate to login page
3. Enter valid credentials
4. Tap the "Login" button

Expected Result:
User should be logged in and redirected to dashboard

Actual Result:
Nothing happens when tapping the login button

Environment:
- Device: iPhone 12 Pro
- OS: iOS 15.5
- Browser: Safari
- App Version: 2.3.1

Severity: Critical
Priority: High

Attachments:
- screenshot_login_page.png
- video_reproduction.mp4
```

### Severity vs Priority

#### Severity (Impact on System)
- **Critical**: System crash, data loss
- **Major**: Major functionality failure
- **Minor**: Minor functionality issue
- **Trivial**: Cosmetic issues

#### Priority (Urgency of Fix)
- **High**: Fix immediately
- **Medium**: Fix in next release
- **Low**: Fix when time permits

### Bug Tracking Tools
- **Jira**: Popular project management tool
- **Bugzilla**: Open-source bug tracker
- **Azure DevOps**: Microsoft's DevOps platform
- **GitHub Issues**: Integrated with GitHub
- **Trello**: Visual project management
- **Monday.com**: Work management platform

## Test Metrics and Reporting

### Key Test Metrics

#### 1. Test Coverage Metrics
```
Test Coverage = (Number of Requirements Tested / Total Requirements) × 100%
Code Coverage = (Lines of Code Executed / Total Lines of Code) × 100%
```

#### 2. Defect Metrics
```
Defect Density = Total Defects / Size of Software (KLOC)
  (KLOC = Kilo Lines of Code, i.e., thousands of lines of code)
Defect Detection Percentage = (Defects Found in Testing / Total Defects) × 100%
Defect Removal Efficiency = (Defects Found Before Release / Total Defects) × 100%
```

#### 3. Test Execution Metrics
```
Test Execution Rate = (Tests Executed / Total Tests) × 100%
Pass Percentage = (Passed Tests / Total Tests) × 100%
Fail Percentage = (Failed Tests / Total Tests) × 100%
```

#### 4. Test Progress Metrics
- Test cases written vs. planned
- Test cases executed vs. planned
- Defects found vs. expected
- Defects fixed vs. reported

### Test Reporting

#### Daily Test Status Report
- Tests executed
- Tests passed/failed
- New defects found
- Blockers and issues

#### Weekly Test Summary Report
- Test progress overview
- Key achievements
- Risks and issues
- Plans for next week

#### Test Closure Report
- Test summary and results
- Defect summary
- Lessons learned
- Recommendations

### Sample Test Metrics Dashboard

```
Total Test Cases: 500
Executed: 450 (90%)
Passed: 400 (89%)
Failed: 40 (9%)
Blocked: 10 (2%)

Defects Found: 85
Critical: 5
Major: 20
Minor: 45
Trivial: 15

Test Coverage: 92%
Code Coverage: 78%
Defect Density: 1.2 defects/KLOC
```

## Test Management Tools

### Popular Test Management Tools

#### 1. TestRail
- Comprehensive test case management
- Test run tracking
- Reporting and analytics

#### 2. Zephyr
- Integrates with Jira
- Real-time testing metrics
- Traceability

#### 3. qTest
- Enterprise test management
- Agile testing support
- CI/CD integration

#### 4. PractiTest
- End-to-end test management
- Flexible reporting
- Integration capabilities

#### 5. TestLink
- Open-source test management
- Requirements management
- Test execution tracking

## Best Practices in Test Management

1. **Early Planning**
   - Start test planning early in the project
   - Involve stakeholders in planning

2. **Clear Documentation**
   - Maintain up-to-date test documentation
   - Use templates for consistency

3. **Traceability**
   - Link test cases to requirements
   - Track defects to test cases

4. **Regular Reviews**
   - Review test plans and cases regularly
   - Update based on changes

5. **Automation Strategy**
   - Identify candidates for automation
   - Balance manual and automated testing

6. **Communication**
   - Regular status updates
   - Transparent reporting
   - Stakeholder engagement

7. **Continuous Improvement**
   - Analyze metrics and trends
   - Learn from defects
   - Refine processes based on lessons learned
