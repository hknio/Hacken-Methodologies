# Token Economy Review Methodology
Release: Version 0.1

## Table of Contents
- [Document](#document)
- [Part 1. Background to Tokenomics](#part-1-background-to-tokenomics)
- [Part 2. Structural Analysis](#part-2-structural-analysis)
- [Part 3. Allocation and Distribution](#part-3-allocation-and-distribution)
- [Part 4. Code Compliance and Verification](#part-4-code-compliance-and-verification)
- [Part 5. Scoring & Rating](#part-5-scoring--rating)
- [Glossary](#glossary)

---

# Document
| Field | Description |
|-------|-------------|
| Name | Token Economy Review Methodology |
| Creators | Hacken OU |
| Subject | Tokenomics; token security analysis; token supply; token economy; |
| Description | A systematic approach to evaluate and analyze token economies, combining quantitative and qualitative methods to assess sustainability, security, and effectiveness of tokenomics designs. |
| Contributor | Luciano Ciattaglia \| VP of Services, Hacken OU |
| Date | Nov 1st, 2024 |
| Rights | Hacken OU |

---


# Part 1. Background to Tokenomics

## Overview

### Executive summary
The Tokenomics Audit Methodology presents a comprehensive framework for evaluating token economies in blockchain projects. It combines qualitative structural analysis with quantitative simulation techniques to provide an objective assessment of tokenomic designs with the following key features:

- Systematic approach to token economy evaluation
- Standardized scoring system (AAA to D rating scale)
- Code compliance and verification
- Actionable recommendations framework

Hacken's token economy report aims to:
- **Assess Economic Robustness:** Evaluate whether the project token economy is designed to be sustainable and resilient.
- **Identify Optimization Opportunities:** Pinpoint areas within the economy that can be enhanced for better performance.
- **Project Token Appreciation:** Analyze allocation, vesting schedules, and financial projections to estimate potential token value growth.

### Introduction
The emergence of Web3 and tokenized economies has created a need for robust methodologies to evaluate and audit token economic systems. Traditional financial audit approaches, while valuable, fail to capture the unique dynamics of token economies, which combine elements of game theory, monetary policy, and distributed systems.

This methodology addresses this gap by providing a structured approach to tokenomics auditing, incorporating lessons learned from both successful and failed token projects. It builds upon academic research in token economics while maintaining practical applicability for real-world implementations.

<br />

# Part 2. Structural Analysis

## Objective
Auditor's guideline to evaluate the project's value creation and incentives, retention strategies, and agents involved to ensure that the token economy is robust and avoids destructive feedback loops.

## 1. Token Utilities
- **Value Creation**: Review how the project generates real utility and economic productivity. Examine if the service provision and market creation mechanisms add genuine value to users and incentivize long-term engagement.
  - <u>Core Utilities</u>: Essential functions of the token, such as accessing services, products, and features within the ecosystem.
  - <u>Transaction and Interaction Utility</u>: Usage of the token for dApp fees, payments, or interactions, which drive real demand and engagement.
  - <u>Governance and Voting Access</u>: Granting token holders rights to participate in governance, adding value by involving users in project decisions.

- **Value Retention**: Investigate mechanisms in place for value retention, such as locking mechanisms, staking requirements, vesting schedules, and burning practices. Ensure these components support token stability and reduce the likelihood of short-term market volatility.
  - <u>Staking and Yield Mechanisms</u>: Requirements and rewards for staking, which incentivize holding and limit supply while providing returns.
  - <u>Burning Mechanisms</u>: Processes that reduce circulating supply to help counter inflation and support long-term token value.

## 2. Economic Agents
- **Agent Roles**: Identify key roles such as investors, validators, liquidity providers, and users. Assess each role's impact on the ecosystem and incentives for participation.
- **Contributions and Dependencies**: Determine how each agent type contributes to the economy and if any dependencies could impact stability.
- **Incentive Alignment**: Check that incentives promote behaviors aligned with long-term project goals, balancing stability and growth.

<br />

# Part 3. Allocation and Distribution

## Objective
To review token allocation and vesting schedules to ensure fair distribution and maintain market stability. This section examines the distribution mechanisms, holder patterns, and vesting implementations to prevent token concentration and market manipulation.

## Token Distribution Analysis

### Holders Analysis
Token holder analysis provides insights into distribution patterns and potential centralization risks. The review begins by examining the current token holders through on-chain data. This includes examining wallet clusters to identify related addresses and potential whale formation. 

Address categorization helps identify different holder types: active traders, long-term holders, smart contracts, and exchange wallets. A time-based analysis of holder behavior reveals accumulation or distribution patterns that may affect future price stability.

The analysis must identify:
1. Distribution among different holder categories
2. Concentration in top wallets
3. Average holding periods

### Token Distribution Model
The token distribution model analysis examines the initial and ongoing token allocation structure. This includes reviewing the allocation percentages, recipient categories, and distribution mechanisms.

The analysis examines:
1. Team allocation (suggested range: 15-20%)
2. Development fund (suggested range: 10-15%)
3. Marketing and partnerships (suggested range: 5-10%)
4. Community incentives (suggested range: 20-30%)
5. Public sale (suggested range: 20-30%)
6. Protocol reserves (suggested range: 10-15%)

Each allocation category requires specific vesting parameters and usage restrictions. The development fund, for instance, should have clear governance mechanisms for fund deployment. Team allocations need longer vesting periods with cliffs to ensure long-term commitment.

### Vesting Schedule Implementation
Vesting schedule analysis ensures the gradual release of tokens to prevent market disruption. The implementation review includes examining smart contract mechanics and schedule parameters.

Vesting schedules should include:
1. Lock period duration for each allocation category
2. Token release frequency and amounts
3. Cliff periods before initial unlocks
4. Governance controls for schedule modifications

### Market Impact Analysis
The market impact analysis examines how token distribution affects market dynamics. This includes reviewing historical data and projecting future impacts of token unlocks.

The analysis examines:
1. Volume (24H)
2. Market Capitalization
3. Historical price impact of previous unlocks
4. Circulating Supply

<br />

# Part 4. Code Compliance and Verification
**Objective**: Ensure that the tokenomics model is accurately and securely implemented in the code, confirming that each designed feature functions as intended to support the project’s economic goals.

## Scope of Review
The audit scope should be outlined to establish boundaries for code compliance assessment within the tokenomics model. Components under review, such as smart contracts, governance mechanisms, and dependency management, are defined, with exclusions noted for areas that do not directly impact tokenomics (e.g., external application interfaces).

## Compliance Standards and Benchmarks
- **Standards Reference** 
A standard reference is provided to relevant industry standards or frameworks, such as OWASP for security or specific blockchain standards (e.g., ERC-20, ERC-721, ERC-1155). These references ensure that the code aligns with industry-recognized practices in security and functionality.

- **Benchmark Criteria**
Baseline criteria, including minimum performance levels or security thresholds, are specified to ensure consistent evaluation across all areas. These benchmarks support the assessment by defining fundamental requirements for secure and stable tokenomics functionality.

## Required Documentation
Documentation supports the audit by providing auditors with information necessary to verify each part of the tokenomics implementation. Access to detailed documentation allows auditors to assess whether the code meets the project’s economic requirements and intended design.

1. **Developer Documentation**  
   Developer documentation explains each function’s purpose, parameters, and dependencies within the tokenomics model. This helps auditors confirm that the code aligns with the intended design.

2. **Functional Requirements**  
   Functional requirements outline the expected behaviors and outputs for each component in the tokenomics model. These requirements help auditors confirm that the implemented functions meet the project’s defined objectives, such as handling transaction fees, staking mechanisms, and governance processes.

3. **Flow Diagrams and Netspecs**  
   Flow diagrams and network specifications (netspecs) illustrate how data and operations move through the tokenomics system. These visual aids support auditors in understanding complex interactions within the code, allowing them to trace processes, such as minting, burning, and reward distribution.

With this documentation, auditors can cross-reference the code with the tokenomics model to check functionality, performance, and compliance with the intended design.

## Key Evaluation Points

- **Token Utility Validation**: Confirm that core utilities like transaction fees, governance rights, and staking mechanisms are accurately implemented and functional in the code.
- **Reward and Penalty Mechanisms**: Verify that rewards (e.g., staking returns) and penalties (e.g., unstaking fees) align with the specified tokenomics design.
- **Burning Mechanisms**: Ensure that any token burn functions operate as intended and trigger under the specified conditions.
- **Supply Control Functions**: Check for correct implementation of functions that adjust supply, such as minting, vesting, or vesting release.
- **Security and Access Controls**: Assess the security of key functions and confirm that only authorized entities can execute sensitive actions, such as updates to economic parameters.

<br />

# Part 5. Scoring & Rating

## Scoring Criteria

### Structural Analysis (Weighted 40%)

1. **Token Utilities**
   - Does the token have essential functions in the ecosystem, such as access to services or products?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points
   - Is the token used for transactions, fees, or other interactions within the platform?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points
   - Does the token provide governance rights to holders, involving them in decision-making?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points
   - Are there incentive structures (e.g., validators, fees) to encourage positive user behavior?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points
   - Are transaction costs balanced to enhance user engagement without discouraging participation?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points

2. **Value Retention**
   - Do staking or yield mechanisms incentivize holding tokens and limiting supply?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points
   - Is there a burn mechanism in place to reduce circulating supply and counter inflation?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points
   - Are minting and burning mechanisms clearly defined and implemented as intended?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points

3. **Economic Agents**
   - Are key roles (investors, validators, users) clearly identified and defined within the ecosystem?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points
   - Are economic agents' contributions and dependencies balanced to avoid over-reliance on any one group?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points
   - Are incentives aligned with project goals, promoting long-term stability and growth?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points

### Allocation and Distribution (Weighted 35%)

1. **Holders Analysis**
   - Is the distribution of token holders diversified to prevent concentration of control?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points

2. **Market Metrics**
   - Are the 24-hour volume, market capitalization, and circulating supply healthy and stable?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points

3. **Token Generation Event (TGE)**
   - Is TGE information (transaction hash, vesting schedule, distribution) verified and transparent?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points
   - Are all parties involved in the TGE identified to maintain transparency?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points
   - Are existing tokens distinguished from planned tokens for clear understanding of future supply?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points

4. **Vesting Schedules**
   - Are vesting schedules structured to prevent excessive sell pressure?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points

5. **Distribution Patterns**
   - Is the allocation model designed to avoid pump-and-dump dynamics and prevent concentrated control?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points

### Code Compliance and Verification (Weighted 25%)

1. **Utility Validation**
   - Are core utilities (transaction fees, governance rights, staking) implemented as designed in the code?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points

2. **Reward and Penalty Mechanisms**
   - Are reward and penalty mechanisms correctly implemented according to the tokenomics design?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points

3. **Burning Mechanisms**
   - Is the burning function operational and correctly triggered under specified conditions?
     - Yes: 2 points
     - No: -2 points
     - Not Applicable: 0 points

4. **Supply Control Functions**
   - Are supply control functions (e.g., minting, vesting release) correctly implemented and functional?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points

5. **Security and Access Controls**
   - Are security measures and access restrictions in place for sensitive actions?
     - Yes: 3 points
     - No: -3 points
     - Not Applicable: 0 points

## Formulas for Weighted Scores

Each category score is calculated based on the points from each question within that category, adjusted by the category's weight.

### Formula for Each Category Score:
Category Score = (Total Points Scored / Total Possible Points) x 5 x Category Weight

Where:
- Total Points Scored = Sum of points based on answers (Yes, No, Not Applicable)
- Total Possible Points = Maximum potential points for all questions in the category

## Calculating the Overall Rating

1. Calculate Each Category Score using the formula provided.
2. Sum Weighted Scores to get the total score:
   Total Score = SA Score + AD Score + CCV Score
   - SA: Structural Analysis
   - AD: Allocation and Distribution
   - CCV: Code Compliance and Verification

3. Assign an Overall Rating based on the Total Score:
   - AAA (4.5 - 5): Outstanding tokenomics structure with no significant weaknesses
   - AA (4.0 - 4.4): Strong structure with minor areas for improvement
   - A (3.5 - 3.9): Solid structure, though moderate improvements are needed
   - BBB (3.0 - 3.4): Adequate, with some notable weaknesses
   - BB (2.5 - 2.9): Somewhat weak, with several areas needing enhancement
   - B (2.0 - 2.4): Significant issues present; improvement needed
   - C (1.0 - 1.9): Very weak, likely unsustainable without substantial changes
   - D (0 - 0.9): Fails to meet basic standards; unsustainable in its current form

## Example Calculation

Let's say an auditor reviews a token project and assigns the following points:

1. Structural Analysis (SA) (Weighted 40%)
   - Total Points Scored: 20
   - Total Possible Points: 25
   - Calculation: SA Score = (20 / 25) x 5 x 0.4 = 1.6

2. Allocation and Distribution (AD) (Weighted 35%)
   - Total Points Scored: 18
   - Total Possible Points: 24
   - Calculation: AD Score = (18 / 24) x 5 x 0.35 = 1.313

3. Code Compliance and Verification (CCV) (Weighted 25%)
   - Total Points Scored: 15
   - Total Possible Points: 20
   - Calculation: CCV Score = (15 / 20) x 5 x 0.25 = 0.938

### Total Score Calculation
Total Score = SA Score + AD Score + CCV Score
= 
1.6 + 1.313 + 0.938 = 3.85

### Assigning the Rating
Based on the Total Score of 3.85, the project would receive an A rating (3.5 - 3.9), indicating a solid structure with some areas for moderate improvement.

<br />

# Glossary

| Term | Definition |
|------|------------|
| Total Supply | The maximum number of tokens the blockchain can issue.<br>- Available or Circulating Quantity: Number of tokens already issued and available at a given time.<br>- Total Quantity: The maximum number of tokens that will eventually reach circulation. |
| Vesting periods | The vesting period locks developers' tokens for a set length of time, protecting investors from perpetrators of pump-and-dump scams. |
| Staking and Mining | Mechanisms within the tokenomics model where:<br>- Staking involves holding tokens to support network security or participate in governance, often in exchange for rewards.<br>- Mining refers to the process of validating and adding transactions to the blockchain, typically earning new tokens as a reward. |
| Token Burns | A deflationary mechanism used by cryptocurrency platforms to permanently remove tokens from circulation, helping to counteract inflation and support long-term token value. |
| ICO (Initial Coin Offering) | A fundraising method for new cryptocurrency projects where tokens are sold to early investors. |
| TVL (Total Value Locked) | The total amount of assets locked within a protocol. |
| Utility | Utility refers to the benefits a token offers to the token holders. |
| Market Cap and Fully Diluted Valuation (FDV) | While the market cap is for the current circulating tokens, FDV deals with the maximum ones. If token A has a maximum supply of 15 and trades at $3, its FDV will be $45. |
