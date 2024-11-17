# How to efficiently prepare for the audit

## Table of contents
- [Recommendations](#recommendations)
  - [Development environment](#development-environment)
  - [Clean and executable code](#clean-and-executable-code)
  - [Documentation](#documentation)
  - [Tests](#tests)
  - [Code freeze](#code-freeze)
- [Pre-Audit Checklist](#pre-audit-checklist)
- [Common Pitfalls in Audit Preparation](#common-pitfalls-in-audit-preparation)


## Recommendations
This document helps teams prepare for security audits of smart contracts, protocols, or other web3 projects. Proper preparation ensures auditors can evaluate the code effectively, identify vulnerabilities, and provide actionable feedback, resulting in a faster and more accurate audit process.

Not following these recommendations can lead to delays, incomplete findings, or lower audit quality. Issues like missing documentation, unclear code, or ongoing changes during the audit disrupt the process and make it harder to deliver reliable results.

### Development environment
The project should have a development environment. It can be any development environment preferred by the Customer development team (e.g., [Truffle](https://trufflesuite.com/), [Hardhat](https://hardhat.org/), [Foundry](https://getfoundry.sh/)). 

This step brings many advantages:

1. **Enhanced debugging:** Facilitates tracking down and fixing coding errors efficiently.
2. **Simplified testing:** You can freely test and break things without affecting the live code.
3. **Better version control:** Helps manage different versions of your code and track changes.
4. **Reduced risk of accidental live deployment:** Avoids premature or accidental deployment of unfinished code.

**Key requirements**:
- No private dependencies are included. All dependencies can be downloaded without setting up additional keys.
- Any other global packages except a packages manager and a language compiler are required.
- The setup is OS-agnostic and can be run on Windows, Linux, or macOS.
- Run instructions are provided and, if executed, allow the compilation of the source code.

### Clean and executable code
The code must follow the following rules:
- The code adheres to an official language style guide. Some popular style guides: [**Solidity**](https://docs.soliditylang.org/en/latest/style-guide.html), [**Vyper**](https://docs.vyperlang.org/en/stable/style-guide.html), [**Rust**](https://doc.rust-lang.org/1.0.0/style/README.html), etc.
- The code can be compiled.
- All TODO and FIX comments are resolved and do not occur in the code.

Ensuring the code follows those rules will decrease the time required for additional reviews and overall post-audit communication.

### Documentation
The project should have sufficient documentation. Both technical documentation and functional requirements must be in place.

**Technical documentation** describes and explains anything related to the software product, ranging from internal documentation for teams to external documentation written for end users. 

**Key points of interest**:
- Programming languages and technologies utilized;
- Instructions for deployment;
- Usage of third party dependencies/programs;
- Development environment description;
- Run instructions;
- Tests run instructions;
- Benchmarks;
- System architecture and internal/external interactions;

#### **Functional requirements** 
Clear and comprehensive functional requirements are essential for understanding the app and verifying its functionality. While your smart contract code may be secure, it might not align with your intended goals. This is another reason why it’s beneficial to get an external opinion to ensure the application functions as intended. Having as many functional details as possible helps check whether your smart contract code works as intended.

Functional requirements typically describe the desired behavior of a system and are used to help ensure that the system is able to meet the needs of its end users and key stakeholders. **Good functional requirements** should be clear, specific, and easy to understand. They should also be testable so that they can be used to verify that the product is functioning correctly. 

- ❌ **Ambiguous requirement**: Users should be able to earn tokens.
- ✅ **Specific requirement**: The contract should enable users to stake ABC tokens and earn XYZ tokens as rewards.

<br/>

**Key points of interest**:
- How should an end user interact with the system;
- Inputs and outputs of the system;
- Any constraints or limitations of its behavior;
- Any performance or reliability requirements.

We only consider documentation written in English.

### Prepare Unit Tests
There are several benefits of smart contract unit testing. For the customer, unit tests can provide assurance that their smart contract works as intended and can help to prevent costly errors or bugs that could result in loss of funds or other problems. For the auditor, unit tests provide a way to validate the functionality of the smart contract and can help to streamline the audit process by providing a clear and concise set of tests to verify the contract's behavior as well as speed up the verification of newly found issues.

Unit tests can detect security vulnerabilities even before initiating your crypto audit. Projects that include tests significantly reduce audit time and cost, allowing auditors to focus on more complex issues.

**Recommendations to follow**:
- Cover positive cases (happy path);
- Cover negative cases;
- Cover cases of construct usage by multiple users;
- Ensure that no additional keys to run tests are needed(private keys, etherscan keys, infura keys, etc.).
- Code coverage plugin is configured.

### Code freeze

#### What is Code Freeze?

A code freeze is the process of halting changes to the codebase during the audit. It ensures that the auditors work on a stable version of the code, preventing inconsistencies and improving the reliability of findings.

#### Key Benefits of Code Freeze:

* **Stability:** Ensures that auditors review an unchanging codebase.
* **Accuracy:** Reduces errors caused by ongoing updates during the audit.
* **Efficiency:** Prevents delays associated with reviewing newly introduced changes.

#### Example: Implementing Code Freeze with GitHub

1. **Create a Release Branch**:  
   A release branch, such as `release-audit`, should be created from the main branch to isolate the version being audited.  
   ```bash
   git checkout -b release-audit  
   git push origin release-audit  
2. **Restrict Changes:** Use GitHub's branch protection rules to prevent updates to the `release-audit` branch. Navigate to the repository settings and:
    - Access Settings > Branches > Add Rule.
    - Select the `release-audit` branch.
    - Enable "Require pull request reviews before merging" and "Restrict who can push to matching branches."
3. **Enforce Freeze:** Announce the code freeze to the team, specifying that non-critical updates should be committed to other branches and merged later.
4. **Manage Fixes:** If any vulnerability arises during the audit, apply the necessary changes in the `release-audit` branch and notify the auditors of the updates.

## Pre-Audit Checklist
The pre-audit checklist provides a structured approach to ensure that all necessary components are in place before starting the audit. Adhering to this list minimizes delays and ensures a focused evaluation:

1. Development environment is configured and accessible.
2. Code adheres to style guides and compiles successfully.
3. All documentation is complete and up-to-date.
4. Comprehensive tests are in place.
5. Code freeze is implemented.

## Common Pitfalls in Audit Preparation
Certain common issues can delay or complicate the audit process. Identifying and addressing these issues in advance ensures a smoother and more efficient audit.

Pitfalls to Avoid:

- **Insufficient Documentation:** Missing or unclear documentation increases the difficulty of understanding the project’s functionality.
- **Incomplete Testing:** Limited or missing tests, especially for edge cases, leave critical vulnerabilities undetected.
- **Unresolved Comments:** The presence of "TODO" or "FIX" comments indicates incomplete work and decreases the perceived readiness of the project.