# QA Fundamentals

## What is Quality Assurance?

Quality Assurance (QA) is a systematic process of determining whether a product or service meets specified requirements. It focuses on improving and stabilizing production and associated processes to avoid or at least minimize issues that lead to defects.

### Key Objectives of QA
- Ensure product quality meets customer expectations
- Identify defects before production release
- Reduce costs by catching issues early
- Improve development processes
- Build customer confidence and trust

## Types of Testing

### 1. Functional Testing
Validates that the software functions according to requirements.
- **Unit Testing**: Testing individual components
- **Integration Testing**: Testing component interactions
- **System Testing**: Testing the complete system
- **Acceptance Testing**: Validating against business requirements

### 2. Non-Functional Testing
Focuses on aspects like performance, usability, and reliability.
- **Performance Testing**: Speed, scalability, stability
- **Security Testing**: Vulnerabilities and threats
- **Usability Testing**: User experience
- **Compatibility Testing**: Different environments

### 3. Maintenance Testing
- **Regression Testing**: Ensuring changes don't break existing functionality
- **Smoke Testing**: Basic functionality checks
- **Sanity Testing**: Focused verification of specific functionality

## Testing Principles

### 1. Testing shows presence of defects
Testing can prove that defects exist but cannot prove that there are no defects.

### 2. Exhaustive testing is impossible
Testing everything is not feasible; risk-based testing is necessary.

### 3. Early testing
Testing activities should start as early as possible in the SDLC.

### 4. Defect clustering
A small number of modules usually contain most of the defects.

### 5. Pesticide paradox
Running the same tests repeatedly will eventually stop finding new bugs.

### 6. Testing is context-dependent
Testing approach varies based on the context of the application.

### 7. Absence of errors fallacy
Finding and fixing defects does not help if the system is unusable.

## Software Development Life Cycle (SDLC)

### Common SDLC Models

#### Waterfall Model
- Sequential approach
- Each phase must be completed before the next begins
- Best for: Well-defined requirements

#### Agile Model
- Iterative and incremental approach
- Continuous feedback and adaptation
- Best for: Rapidly changing requirements

#### V-Model
- Verification and Validation model
- Testing activities parallel to development
- Best for: Projects requiring high reliability

#### DevOps
- Collaboration between development and operations
- Continuous integration and delivery
- Best for: Fast-paced, cloud-based applications

## Testing Life Cycle (STLC)

### 1. Requirement Analysis
- Understand requirements
- Identify testable requirements
- Determine test approach

### 2. Test Planning
- Define test strategy
- Estimate resources and timeline
- Identify risks

### 3. Test Case Development
- Create test cases
- Prepare test data
- Set up test environment

### 4. Test Environment Setup
- Configure hardware and software
- Prepare test data
- Verify environment readiness

### 5. Test Execution
- Run test cases
- Log defects
- Re-test fixed defects

### 6. Test Closure
- Evaluate test completion criteria
- Document lessons learned
- Archive test artifacts

## Quality Metrics

### Key Metrics to Track
- **Defect Density**: Defects per unit of code
- **Test Coverage**: Percentage of code/requirements tested
- **Defect Detection Percentage**: Defects found in testing vs. production
- **Test Execution Rate**: Tests executed vs. planned
- **Defect Resolution Time**: Average time to fix defects

## Roles in QA

### QA Engineer
- Design and execute test cases
- Report and track defects
- Verify fixes

### QA Lead
- Plan testing activities
- Manage test team
- Report to stakeholders

### Test Automation Engineer
- Develop automated test scripts
- Maintain automation framework
- Integrate tests with CI/CD

### Performance Test Engineer
- Design and execute performance tests
- Analyze performance bottlenecks
- Recommend optimizations
