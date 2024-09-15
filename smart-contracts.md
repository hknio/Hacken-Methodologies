# Smart Contract Code Review And Security Analysis Methodology
Release: Version 2.2

## Table of Contents

1. [Document](#document)
2. [Background to the Smart Contracts Audit and Analysis](#part-1-background-to-the-smart-contracts-audit-and-analysis)
   - [Overview](#overview)
   - [Executive Summary](#executive-summary)
   - [The Value of Smart Contracts Audit](#the-value-of-smart-contracts-audit)
   - [How Does the Audit Help?](#how-does-the-audit-help)
3. [Smart Contracts Audit and Analysis Phases](#part-2-smart-contracts-audit-and-analysis-phases)
   - [Preparations for Smart Contracts Audit and Analysis](#preparations-for-smart-contracts-audit-and-analysis)
   - [Code Review and Analysis](#code-review-and-analysis)
   - [Testing](#testing)
   - [Report](#report)
   - [Remediation Check](#remediation-check)
   - [Issue Status](#issue-status)
   - [Vulnerabilities Severity Formula](#vulnerabilities-severity-formula)

---

# Document
| Name | Smart Contract Code Review And Security Analysis Methodology |
| ----------- | ----------- |
| Creators  | Hacken OU |
| Subject  | audit; security analysis; smart contracts; |
| Description  | The methodology described herein provides specific guidance on how to plan and execute an audit of smart contracts in line with the Smart Contracts Audit and Analysis Requirements provided by Hacken. |
| Contributor  | Luciano Ciattaglia | Director of Services, Hacken OU |
| Date  | September 13th, 2024 |
| Rights  | Hacken OU |

---

# Part 1. Background to the Smart Contracts Audit and Analysis.

## Overview
### Executive summary
The Smart Contracts Audit and Analysis Methodology constitutes a response to the Hacken customers’ requests and is based on years of experience in conducting smart contracts audits. The purpose of this document is to explain to the Hacken customers’ and community the audit process and artifacts to increase the quality of smart contract development and save the funds of Hacken customers and their users.

## The value of Smart Contracts audit 
### Audited smart contracts: why does it matter?
The total market capitalization of crypto has reached $2.64T (>6X growth vs 2020) while the total DeFi market capitalization has passed the level of $150B (>9X growth vs 2020). In 2021, the level of crypto adoption has increased by 880% compared to the estimates for 2020. And these figures keep on growing. The mass adoption of crypto is becoming a new reality. 

However, such skyrocketing crypto adoption is accompanied by growing security risks. In 2020, hackers stole crypto assets worth $1.9B and, in 2021, the majority of hacks are taking place in the DeFi segment ($361M out of $681M).   

The owners and core teams behind any crypto project should realize the scope of risks associated with smart contracts and need to know how to address these threats. The most common risks related to smart contracts are operational, implementation, and design risks. The exploitation of any of these flaws by hackers can damage the competitiveness of a project or even destroy it. 

No changes can be introduced into a smart contract once it is deployed. After initial exploitation, further hacks are likely to take place until all assets are stolen.
Smart contracts audit is the only effective way for projects to prevent the occurrence of serious security incidents. 

### How does the audit Help?
Most developers need guidance on how to write secure and high-quality smart contracts. Our methodology will serve the needs of our customers, their technical teams, and their potential clients (community).

**Our methodology will allow product owners to:**
1. Make sure that the development corresponds to the specified functional requirements.
2. Realize what steps need to be taken prior to the audit.
3. Realize what steps need to be taken during the audit.
4. Realize what steps need to be taken after the audit. 

<br />

**The value of our methodology for developers:**
1. Allows them to understand the audit process and its phases.
2. Provides recommendations on how to ensure secure development. 
3. Describes the most common mistakes.
4. Provides best practices of how to develop safe code.

# Part 2. Smart Contracts Audit and Analysis Phases
1. Smart Contracts Audit and Analysis process consists of the following phases:
2. Preparation
3. Code review and analysis
4. Testing
5. Reporting
6. Remediations check

## Preparations for Smart Contracts Audit and Analysis
### Why are preparations so important?
Preparation for an audit is as necessary as the audit itself.  

During the preparation, customers have a chance to review their projects one more time thoroughly and to ensure that everything they have planned is implemented correctly and the majority of possible risks are mitigated. Good preparation saves both time and money that projects can later spend for additional audits. Also, at this stage, a Customer themself can detect many issues. 

**To get maximum value from the audit, we recommend our Customers follow the following steps:**

1. Prepare functional requirements for the project.
2. Prepare a technical description of the project.
3. Setup development environment of the project.
4. Prepare unit tests.
5. Ensure that code follows best practices and security standards.

### Functional requirements
To understand the needs of the Customer and to ensure that everything is developed as planned, providing functional requirements is important.

The main question that should be answered here is: what do we want to achieve via these smart contracts? 

Functional requirements need to be clear, simple, and unambiguous. Here are some examples of well-written functional requirements:

- The contract should allow users to stake HAI tokens and receive other tokens as rewards.
- Total rewards should be divided among all users according to their % of the total volume of locked HAI.
- Users should be able to withdraw their funds and rewards whenever they want. 
- Total locked balance should be recalculated each time a user withdraws his tokens

Try to provide as many functional details as possible.

User stories can be useful as well. 

### Technical description
Technical description is also required. It should contain information about the used languages and technologies, deployment instructions, instructions on how to run tests etc. Non-functional requirements can also be included in this section.

### Setup development environment of the project
A development environment for the project should be configured by the Customer. Truffle, Hardhat, or any other comprehensive development environment can be used. Proper description of the environment should be provided. An example of the project environment configuration can be found **[here](https://github.com/hknio/sample_solidity_project)**.

### Unit tests
The code should be covered with unit tests. Test coverage should be 100%, with both positive and negative cases covered. Test cases that imitate usage of contracts by multiple users should be provided to ensure that contracts will not be vulnerable to DoS attacks and that operations of one user do not affect the other unless it is a part of requirements. Test should be executed on the emulated VM without the need to run local VM’s or connect to testnets.

We recommend using TDD during the development process.

### Code style and best practices
We highly advise adhering to the official language code style guides and formatting code before submission for audits. Code readability and compliance with the language style guide are some of the factors that determine the code recommendations. Furthermore, to expedite the bug-fix verification process, it is essential to format the code before the initial audit. This approach reduces the time required for verifying issues and minimizes the likelihood of overlooking errors in newly added code.

## Code review and analysis
Code review and analysis is performed by lead and assistant auditors across the whole process. Additional quality reviews are performed by an expert auditor to verify that all good security practices were performed during the workflow. All steps of this process:

1. Pre-audit
2. Overall review
3. Scan by automated tools
4. Funds and data flow diagrams
5. Line-to-line review
6. Checked items
7. Analysis of received data

### Pre-audit
The purpose of the pre-audit phase is to help customers understand how their project is being prepared for the audit and identify any areas that need improvement. Depending on the audit timeline, improvements can be made either before the actual audit or during the audit. 

### Overall review
At this step, lead and assistant auditors read the code to understand its structure and purpose.  Functional and technical requirements as well as other documents provided by clients are examined in details. No serious findings can be detected at this step. The main outcome of this step is a high-level description of the code provided by auditors. Those deliverables are used internally during the next steps of the audit.

### Scan by automated tools
Automated tools are used to search for simple issues and provide more information about smart contracts under review. The following tools are used: 

#### Solidity:

- Slither - Static analysis of Solidity source code for security vulnerabilities and best practices. 
- Mythril - Reversing and bug hunting framework for the Ethereum blockchain.
- Solgraph - Generates a DOT graph that visualizes function control flow of a Solidity contract and highlights potential security vulnerabilities.
- Echidna - program designed for fuzzing/property-based testing of Ethereum smart contracts.
- And other proprietary tools.

#### Rust:

- Clippy - A collection of lints to catch common mistakes and improve your Rust code. 
- Cargo-udeps - Find unused dependencies in Cargo.toml.
- Cargo-audit - Audit your dependencies for crates with security vulnerabilities reported to the RustSec Advisory Database.
- Cargo-geiger - detect usage of unsafe Rust.
- Cargo-crev - cryptographically verifiable code review for cargo.
- And other proprietary tools.

### Funds and data flow diagrams
At this step, auditors have more information about the code and can now build funds and data flow diagrams. We visualize all possible states of the contract and all its interactions with other contracts. All changes of data and funds flow should be displayed on those diagrams. 

During this step, some issues can be found and recorded by auditors.

This allows us to understand smart contracts before line-to-line review better.

BPMN and UML diagrams are used to visualize funds and data flows

### Line-to-line review
During the line-to-line review, auditors thoroughly read each line of the code and record every issue detected. We review contracts for all known issues such as the ones described in **[SWC](https://swcregistry.io/docs/SWC-100)**. We also look for possible data manipulations, access violations, flash loans, and other manipulations that can be performed through interaction with other contracts. This step also includes validation of the code according to code-style guides and best practices.

### Checked Items
Items differ for each language and platform that we audit smart contracts for. 

EVM (Solidity, Vyper, Yul): [Checked Items (EVM)](https://docs.google.com/document/d/1dPTb24Fr1P2bBGw-CcDBbbmE0CR27GdWIzL6DutDNMY/edit#heading=h.c7gbsyms3j2w)

Rust-based smart contract for Solala, Near, CosmWasm, and other platforms: [Checked Items (RUST)](https://docs.google.com/document/d/1uRSC_SaMHRqII4nX6m9yVONSp1YHUvOxTi-iaX9xWFo/)

### Testing
During the testing phase of the audit, if unit tests are configured for the project, auditors check coverage and write their own test cases if required. Ideally, code coverage should cover all positive and negative cases. Some issues can be reproduced with invalid config of dependency contracts. Auditors create such configs and run corresponding tests. 

If unit tests are not configured, auditors deploy smart contracts on the local network and check all required cases. 

Some sophisticated issues require complex exploiting contracts. Usually, if it is unclear how the issue can be exploited, auditors provide the sample attacking contracts. 

### Analysis of received data
All auditors review their findings and audit artifacts, and share results internally. Auditors prepare materials for the report. An expert auditor reviews all materials prepared by the lead auditor and performs a quality review of the report. Most possible issues are already documented at this step.

### Report
After all code review, analysis, and tests, auditors prepare a report. Reports have the following structure:
- Introduction	
- Scope	
- Audit Summary
- System Overview	
- Risks
- Findings
- Definitions
- Disclaimers

## Remediation Check
All issues are reported to the Customer in the preliminary report. If some points are unclear, we can provide more descriptions of issues or explain everything on a call.

The customer is entitled to one complimentary remediation check if the following conditions are met:
- **Timely Response:** Remedial actions must be implemented within the specified timeframe dictated by the Lead Auditor.
- **Code Integrity:** The fundamental code structure should remain unchanged. Major architectural modifications may disqualify the customer from a free remediation check.
- **Documentation:** All modifications to the code must be comprehensively documented by the customer, detailing what changes were made and why.
- **Commit Specificity:** The submitted commits must exclusively address the vulnerabilities or issues that were identified in the "Findings" section of the preliminary report.

Fixes must be submitted in a structured list, detailing the Finding ID and the corresponding commit hash.

After all fixes are validated, a final report is provided to the customer.

## Issue status
During the auditing, an issue can have one of the following statuses:
- **Pending Fix:** An issue newly discovered by the auditing team, not fixed yet.
- **Resolved:** An issue that has been resolved based on the auditor's recommendations. 
- **Accepted:** This status is assigned to an issue that the customer has recognized but chosen not to fix, either because it is deemed an intentional feature or it has been consciously ignored. While the issue remains unaddressed, it has been formally acknowledged by the client. 
- **Mitigated:** Changes that partially address an issue or implement a safeguard that reduces risk but does not fully eliminate the vulnerability.

> Hacken assumes no liability for any security breaches or vulnerabilities ("rekt" cases) that may arise due to these unresolved or partially resolved issues.

# Vulnerabilities severity formula
### [Hacken OÜ - Severity Formula Standart](https://github.com/hknio/severity-formula/blob/main/README.md)