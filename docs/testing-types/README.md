# Testing Types

## Manual Testing

### What is Manual Testing?
Manual testing is the process of manually checking software for defects. It requires a tester to play the role of an end user and use most features of the application to ensure correct behavior.

### Types of Manual Testing

#### 1. Exploratory Testing
- **Definition**: Simultaneous learning, test design, and execution
- **When to use**: New features, complex scenarios
- **Benefits**: Finds unexpected defects, creative approach
- **Techniques**: Session-based testing, freestyle exploration

#### 2. Ad-hoc Testing
- **Definition**: Informal testing without planning
- **When to use**: Quick checks, time constraints
- **Benefits**: Fast, requires minimal preparation
- **Limitations**: Not repeatable, no documentation

#### 3. Smoke Testing
- **Definition**: Basic functionality verification
- **When to use**: After new builds, before detailed testing
- **Benefits**: Quick validation of critical features
- **Example**: Can users log in? Can they access main features?

#### 4. Sanity Testing
- **Definition**: Focused testing on specific functionality
- **When to use**: After bug fixes, minor changes
- **Benefits**: Quickly verify specific areas
- **Example**: Testing only the payment module after a fix

## Automated Testing

### What is Automated Testing?
Automated testing uses software tools to execute pre-scripted tests on a software application before it is released into production.

### Benefits of Automation
- **Speed**: Tests run faster than manual execution
- **Repeatability**: Consistent test execution
- **Coverage**: More tests can be executed
- **Early Detection**: Integration with CI/CD
- **Cost-Effective**: Long-term savings on repetitive tests

### Types of Automated Tests

#### 1. Unit Tests
```python
# Example: Testing a simple function
def test_add_numbers():
    assert add(2, 3) == 5
    assert add(-1, 1) == 0
    assert add(0, 0) == 0
```

#### 2. Integration Tests
```python
# Example: Testing database integration
def test_user_creation():
    user = create_user("test@example.com")
    saved_user = database.get_user(user.id)
    assert saved_user.email == "test@example.com"
```

#### 3. End-to-End Tests
```python
# Example: Testing complete user flow
def test_checkout_process():
    login("user@example.com", "password")
    add_item_to_cart("product-123")
    proceed_to_checkout()
    complete_payment()
    assert order_confirmation_displayed()
```

### Automation Testing Tools
- **Selenium**: Web application testing
- **Cypress**: Modern web testing
- **Playwright**: Cross-browser automation
- **JUnit/TestNG**: Java testing frameworks
- **PyTest**: Python testing framework
- **Jest**: JavaScript testing

## Performance Testing

### What is Performance Testing?
Performance testing determines how a system performs in terms of responsiveness and stability under a particular workload.

### Types of Performance Testing

#### 1. Load Testing
- **Purpose**: Validate performance under expected load
- **Example**: Testing with 1000 concurrent users
- **Metrics**: Response time, throughput, resource utilization

#### 2. Stress Testing
- **Purpose**: Determine breaking point of the system
- **Example**: Gradually increase users until system fails
- **Metrics**: Maximum load, recovery time

#### 3. Spike Testing
- **Purpose**: Test sudden increase in load
- **Example**: Black Friday sale traffic
- **Metrics**: System stability, error rate

#### 4. Endurance Testing
- **Purpose**: Test system over extended period
- **Example**: Run at normal load for 24-48 hours
- **Metrics**: Memory leaks, resource degradation

#### 5. Scalability Testing
- **Purpose**: Determine system's ability to scale
- **Example**: Add more servers and measure improvement
- **Metrics**: Linear scalability, resource efficiency

### Performance Testing Tools
- **JMeter**: Open-source load testing
- **Gatling**: High-performance load testing
- **K6**: Modern load testing
- **LoadRunner**: Enterprise performance testing
- **Locust**: Python-based load testing

## Security Testing

### What is Security Testing?
Security testing identifies vulnerabilities and ensures that data and resources are protected from potential intruders.

### Common Security Tests

#### 1. Vulnerability Scanning
- Automated tools scan for known vulnerabilities
- Tools: Nessus, OpenVAS, Qualys

#### 2. Penetration Testing
- Simulated attacks on the system
- Manual and automated approaches
- Tools: Metasploit, Burp Suite, OWASP ZAP

#### 3. Security Auditing
- Inspection of security policies and procedures
- Code reviews for security issues

#### 4. Security Scanning
- Static analysis of code
- Tools: SonarQube, Checkmarx, Veracode

### Common Security Vulnerabilities (OWASP Top 10)

1. **Injection**: SQL, NoSQL, OS command injection
2. **Broken Authentication**: Session management issues
3. **Sensitive Data Exposure**: Unencrypted data
4. **XML External Entities (XXE)**: XML processor vulnerabilities
5. **Broken Access Control**: Unauthorized access
6. **Security Misconfiguration**: Default settings, errors
7. **Cross-Site Scripting (XSS)**: Malicious scripts
8. **Insecure Deserialization**: Object manipulation
9. **Using Components with Known Vulnerabilities**: Outdated libraries
10. **Insufficient Logging & Monitoring**: Lack of detection

## Usability Testing

### What is Usability Testing?
Usability testing evaluates how easy and user-friendly the software is.

### Key Aspects
- **Learnability**: How easy for new users to learn
- **Efficiency**: How quickly users can perform tasks
- **Memorability**: How easily users remember the interface
- **Errors**: How many errors users make and recovery
- **Satisfaction**: How pleasant the experience is

### Usability Testing Methods
- **Moderated Testing**: Facilitator guides users
- **Unmoderated Testing**: Users test independently
- **A/B Testing**: Compare two versions
- **Eye Tracking**: Track where users look
- **Think Aloud Protocol**: Users verbalize thoughts

## Regression Testing

### What is Regression Testing?
Regression testing ensures that recent changes haven't adversely affected existing functionality.

### When to Perform Regression Testing
- After bug fixes
- After new feature additions
- After code refactoring
- After configuration changes

### Types of Regression Testing

#### 1. Complete Regression
- Execute all test cases
- Time-consuming but thorough

#### 2. Partial Regression
- Test affected areas only
- Faster, risk-based approach

#### 3. Unit Regression
- Test specific units/components
- Used after code changes

### Regression Testing Strategies
- **Retest All**: Run all existing tests
- **Regression Test Selection**: Run subset of tests
- **Prioritization**: Run most important tests first
- **Hybrid Approach**: Combine multiple strategies

## Compatibility Testing

### What is Compatibility Testing?
Compatibility testing checks if the software works across different environments.

### Types of Compatibility Testing

#### 1. Browser Compatibility
- Different browsers (Chrome, Firefox, Safari, Edge)
- Different browser versions

#### 2. Operating System Compatibility
- Windows, macOS, Linux
- Different OS versions

#### 3. Device Compatibility
- Desktop, mobile, tablet
- Different screen sizes and resolutions

#### 4. Network Compatibility
- Different network conditions
- Bandwidth variations

#### 5. Database Compatibility
- Different database systems
- Different database versions

### Tools for Compatibility Testing
- **BrowserStack**: Cross-browser testing
- **Sauce Labs**: Cloud testing platform
- **LambdaTest**: Browser compatibility testing
- **CrossBrowserTesting**: Multi-browser testing
