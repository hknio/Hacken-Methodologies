# Decentralized Application Code Review and Security Analysis Methodology
Release: Version 2.0

# Table of Contents
1. [Document](#document)
2. [Introduction](#introduction)
3. [Code Review and Security Analysis](#code-review-and-security-analysis)
   - [Requirements](#requirements)
   - [Secure Code Review](#secure-code-review)
   - [Static Security Analysis](#static-security-analysis)
   - [Standardization](#standardization)
   - [Findings](#findings)
4. [Assessment Report](#assessment-report)
5. [Limitations](#limitations)

---
# Document
| Document Attribute | Value |
|--------------------|-------|
| Name | Blockchain protocol and security analysis methodology |
| Creators | Hacken OU |
| Subject | Audit; security analysis; dapp; pentest; attack vectors; |
| Description | The methodology outlined in this document offers specific guidance on how to plan and execute an audit of decentralized applications (dApps) developed by Hacken OU. This document aims to equip all relevant stakeholders with a comprehensive understanding of the auditing process, as well as the steps needed to adequately prepare for it. |
| Contributor | Luciano Ciattaglia \| Director of Services at Hacken OU |
| Contributor | Stephen Ajayi \| Dapp Audit Technical Lead at Hacken. |
| Date | November 2nd, 2023 |
| Rights | Hacken OU |

---

# Introduction

This document describes the decentralized application code review and security analysis process developed and used by security engineers at Hacken. It uses well-known and industry-accepted core principles as its base: confidentiality, integrity, and availability. By extending the existing conventional security concepts, this methodology aims at providing the best analysis value for an application interacting with a decentralized network.

A decentralized application code review and security analysis is a secure code review and static application security testing. For more information on these aspects of the process, refer to the related sections of this document.

---

# Code Review and Security Analysis

## Requirements

This methodology was specifically designed for reviewing applications that interact with blockchain networks. Although this methodology can be used while reviewing conventional applications, it is not recommended. The following eligibility criteria can be used to determine if an application is a good fit.

### Eligibility Criteria ("any of"):

| # | Criteria |
|---|----------|
| 1 | The application performs cross-chain operations. |
| 2 | The application has custody over or interacts with sensitive information such as private keys, seed phrases, etc. |
| 3 | The application signs and/or broadcasts transactions without relying on third-party injected/connected providers. |
| 4 | The application reacts to blockchain events. |
| 5 | The application indexes blockchain and the integrity is crucial. |
| 6 | The application uses message signing as a means of authentication. |

This methodology requires the following resources to be provided:
- The source code with a clearly defined scope.
- The documentation with functional requirements and technical details about the application.

## Secure Code Review

Secure code review is a detailed analysis of the software source code by security engineers to identify potential security vulnerabilities, weaknesses, and exploitable issues.

The process involves a line-by-line examination of the code to identify security issues, which could include concerns specific to blockchain integration such as data manipulations, incorrect integrations with a blockchain platform, incorrect interpretations of network responses, and other manipulations that could be performed through interaction with a decentralized network.

In addition to the code analysis, security engineers also create a system overview that includes data flow and high-level architecture diagrams. This helps to provide a better understanding of the system and its constraints. The system overview helps identify how data flows within the application, where data is stored, and how different components interact with one another.

## Static Security Analysis

Static security analysis is a crucial step in ensuring the security of an application. This testing method involves the examination of an application's source code without executing it, to identify any potential security vulnerabilities. It plays a vital role in a comprehensive security strategy by revealing hidden security flaws that could otherwise go unnoticed.

As applications continue to grow in complexity, the need for advanced and sophisticated static analysis becomes important. It is recommended to use the latest technology and tools, such as AI-powered testing and platform-specific security analysis tools. At Hacken, we employ a proprietary and confidential list of both public and private security analysis tools to conduct our reviews.

The outcome of a successful analysis is a report that outlines the discovered security vulnerabilities, as well as an assessment of the application's reliability and code quality. It serves as a valuable artifact, providing crucial insights and recommendations for improving the application's security.

## Standardization

This review aims to identify commonly known and more specific vulnerabilities. The review process may consider a wide range of potential issues, some of which are listed in the table below. Each item in the table should have one of the following statuses in the assessment report: Passed, Failed, or Not Relevant

Standardized Checked Items:

| # | Item |
|---|------|
| 1 | **Private keys are safely used and stored**<br>Private keys should be encrypted, stored in a secure secret manager, and provided to the application with a secure method. |
| 2 | **Strong authentication via message signing**<br>A signed authentication message should be exclusive to the application. It should have an expiration date and time-specific nonce provided by the system. |
| 3 | **Blockchain branching out is accounted for**<br>The application should wait an adequate number of blocks to reduce the risk of a chain re-organization. |
| 4 | Healthy integration with the blockchain nodes |
| 4.1 | The application indexes blockchain and the integrity is crucial. |
| 4.2 | The application uses message signing as a means of authentication. |
| 5 | **Blockchain data is sanitized**<br>The application should not trust the inputs from the blockchain when they can be considered the same as user inputs. |
| 6 | Secure integration with the blockchain |
| 6.1 | **Events are validated**<br>The application should check the event origin, its type and structure. |
| 6.2 | **Proper mapping of types**<br>Blockchain-specific types (uint256, bytes, etc.) should be mapped to the correct language-specific types without data loss. |
| 6.3 | **Error-proof data indexing**<br>The application should not silently skip anything it could not process at some point in time. It should have a retry mechanism or sufficient logging. |
| 6.4 | **Secure integration with the smart contracts**<br>The application should follow the smart contract specification and expect all relevant and possible outcomes. |
| 7 | Dependencies are up-to-date and not vulnerable |

The assessment report must adhere to the definitions provided in this methodology to ensure consistency and accuracy in the reporting of findings.

Issue Severity Definition:

| Severity | Description |
|----------|-------------|
| Critical | These issues present a major security vulnerability that poses a severe risk to the system. They require immediate attention and must be resolved to prevent a potential security breach or other significant harm. |
| High | These issues present a significant risk to the system, but may not require immediate attention. They should be addressed in a timely manner to reduce the risk of the potential security breach. |
| Medium | These issues present a moderate risk to the system and cannot have a great impact on its function. They should be addressed in a reasonable time frame, but may not require immediate attention. |
| Low | These issues present no risk to the system and typically relate to the code quality problems or general recommendations. They do not require immediate attention and should be viewed as a minor recommendation. |
| Pending Fix | The issue was presented to the Customer. The remediation after the initial discovery was not yet made. |
| Accepted | The issue was not fixed as a result of the remediation. The Customer was informed of the risks associated with it. |
| Resolved | The issue was fixed and does not present a risk to the system. |

## Findings

A secure code review and static security analysis can produce a wide range of findings, which may include but are not limited to:

- Overconfidence in a node (or node provider)
- Failure to account for a blockchain branching out
- Incorrect validation of ENS records
- Weak authentication via message signing
- Unsafe private key storage
- XSS/SQL injections from the blockchain data
- Misuse of checksum addresses
- Blockchain data inconsistency
- Incorrect integration with a smart contract and/or blockchain network
- Usage of wrong data types
- Deprecated, vulnerable, or outdated Web 3 libraries

To ensure consistency and completeness, each finding resulting from a secure code review and static security analysis should include a title, description, status, severity level, associated Common Weakness Enumeration (CWE), and recommendation on how to mitigate the issue.

The weakness classification used by Hacken security engineers contains a list of standardized issues that may be identified during the secure code review process. While some of these issues may have a higher severity level than what is currently considered industry norms, security engineers at Hacken believe this approach helps to promote good security practices and ensure a healthy Web 3 ecosystem.

---

# Assessment Report

This is a document that contains all the findings from the application code review and security analysis. Its content should include the following:

- The assessment scope, conditions, assumptions, limitations, and other relevant information.
- A list of issues and vulnerabilities found during the review with recommendations on how to address them.
- An overview of the system created by the security engineers.

---

# Limitations

While this methodology is designed to identify specific risks and vulnerabilities in the application through a thorough code review and security analysis, it is important to note that it does not make any statements or warranties regarding the overall security of the application.

To ensure the security of a decentralized application, it is strongly recommended to not rely solely on this methodology. We advise conducting several independent audits and implementing a public bug bounty program to further identify and address potential security issues.
