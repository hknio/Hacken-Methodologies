# Smart Contract Checklists
Release: Version 2.0

## Table of Contents

1. [EVM Checklist](#evm-checklist-solidity-vyper-yul)
2. [Rust](#rust-checklist)
   - [NEAR](#near)
   - [Solana](#solana)
3. [Scrypto](#scrypto-checklist)

---

<br />

# EVM Checklist (Solidity, Vyper, Yul)
Items that are considered during the audit of smart contracts written for EVM

| # | Item | Type | Description |
|---|------|------|-------------|
| 1 | Default Visibility | [SWC-100](https://swcregistry.io/docs/SWC-100), [SWC-108](https://swcregistry.io/docs/SWC-108) | Functions and state variables visibility should be set explicitly. Visibility levels should be specified consciously. |
| 2 | Integer Overflow and Underflow | [SWC-101](https://swcregistry.io/docs/SWC-101) | If unchecked math is used, all math operations should be safe from overflows and underflows. |
| 3 | Outdated Compiler Version | [SWC-102](https://swcregistry.io/docs/SWC-102) | It is recommended to use a recent version of the Solidity compiler. |
| 4 | Floating Pragma | [SWC-103](https://swcregistry.io/docs/SWC-103) | Contracts should be deployed with the same compiler version and flags that they have been tested thoroughly. |
| 5 | Unchecked Call Return Value | [SWC-104](https://swcregistry.io/docs/SWC-104) | The return value of a message call should be checked. |
| 6 | Access Control & Authorization | CWE-284 | Ownership takeover should not be possible. All crucial functions should be protected. Users could not affect data that belongs to other users. |
| 7 | SELFDESTRUCT Instruction | [SWC-106](https://swcregistry.io/docs/SWC-106) | The contract should not be self-destructible while it has funds belonging to users. |
| 8 | Check-Effect-Interaction | [SWC-107](https://swcregistry.io/docs/SWC-107) | Check-Effect-Interaction pattern should be followed if the code performs ANY external call. |
| 9 | Assert Violation | [SWC-110](https://swcregistry.io/docs/SWC-110) | Properly functioning code should never reach a failing assert statement. |
| 10 | Deprecated Solidity Functions | [SWC-111](https://swcregistry.io/docs/SWC-111) | Deprecated built-in functions should never be used. |
| 11 | Delegatecall to Untrusted Callee | [SWC-112](https://swcregistry.io/docs/SWC-112) | Delegatecalls should only be allowed to trusted addresses. |
| 12 | DoS (Denial of Service) | [SWC-113](https://swcregistry.io/docs/SWC-113), [SWC-128](https://swcregistry.io/docs/SWC-128) | Execution of the code should never be blocked by a specific contract state unless it is required. |
| 13 | Race Conditions | [SWC-114](https://swcregistry.io/docs/SWC-114) | Race Conditions and Transactions Order Dependency should not be possible. |
| 14 | Authorization through tx.origin | [SWC-115](https://swcregistry.io/docs/SWC-115) | tx.origin should not be used for authorization. |
| 15 | Block values as a proxy for time | [SWC-116](https://swcregistry.io/docs/SWC-116) | Block numbers should not be used for time calculations. |
| 16 | Signature Unique Id | [SWC-117](https://swcregistry.io/docs/SWC-117), [SWC-121](https://swcregistry.io/docs/SWC-121), [SWC-122](https://swcregistry.io/docs/SWC-122), EIP-155 | Signed messages should always have a unique id. A transaction hash should not be used as a unique id. Chain identifier should always be used. |
| 17 | Shadowing State Variable | [SWC-119](https://swcregistry.io/docs/SWC-119) | State variables should not be shadowed. |
| 18 | Weak Sources of Randomness | [SWC-120](https://swcregistry.io/docs/SWC-120) | Random values should never be generated from Chain Attributes or be predictable. |
| 19 | Incorrect Inheritance Order | [SWC-125](https://swcregistry.io/docs/SWC-125) | When inheriting multiple contracts, especially if they have identical functions, a developer should carefully specify inheritance in the correct order. |
| 20 | Calls Only to Trusted Addresses | EEA-Level-2, [SWC-126](https://swcregistry.io/docs/SWC-126) | All external calls should be performed only to trusted addresses. |
| 21 | Presence of unused variables | [SWC-131](https://swcregistry.io/docs/SWC-131) | The code should not contain unused variables if this is not justified by design. |
| 22 | EIP standards violation | EIP | EIP standards should not be violated. |
| 23 | Assets integrity | Custom | Funds are protected and cannot be withdrawn without proper permissions or be locked on the contract. |
| 24 | User Balances manipulation | Custom | Contract owners or any other third party should not be able to access funds belonging to users. |
| 25 | Data Consistency | Custom | Smart contract data should be consistent all over the data flow. |
| 26 | Flashloan Attack | Custom | When working with exchange rates, they should be received from a trusted source and not be vulnerable to short-term rate changes that can be achieved by using flash loans. Oracles should be used. |
| 27 | Token Supply manipulation | Custom | Tokens can be minted only according to rules specified in a whitepaper or any other documentation provided by the customer. |
| 28 | Gas Limit and Loops | Custom | Transaction execution costs should not depend dramatically on the amount of data stored on the contract. There should not be any cases when execution fails due to the block gas limit. |
| 29 | Style guide violation | Custom | Style guides and best practices should be followed. |
| 30 | Requirements Compliance | Custom | The code should be compliant with the requirements provided by the Customer. |
| 31 | Environment Consistency | Custom | The project should contain a configured development environment with a comprehensive description of how to compile, build and deploy the code. |
| 32 | Secure Oracles Usage | Custom | The code should have the ability to pause specific data feeds that it relies on. This should be done to protect a contract from compromised oracles. |
| 33 | Tests Coverage | Custom | The code should be covered with unit tests. Test coverage should be 100%, with both negative and positive cases covered. Usage of contracts by multiple users should be tested. |
| 34 | Stable Imports | Custom | The code should not reference draft contracts, that may be changed in the future. |

---

<br />

# Rust Checklist
| # | Item | Description |
|---|------|-------------|
| 1 | Default Visibility | Functions and state variables visibility should be set explicitly. Visibility levels should be specified consciously. |
| 2 | Integer Overflow and Underflow | If unchecked math is used, all math operations should be safe from overflows and underflows. |
| 3 | Outdated Compiler Version | It is recommended to use a recent version of the Rust compiler. |
| 5 | Unchecked Call Return Value | The return value of a message call should be checked. |
| 6 | Access Control & Authorization | Ownership takeover should not be possible. All crucial functions should be protected. Users could not affect data that belongs to other users. |
| 9 | Assert Violation | Properly functioning code should never reach a failing assert statement. |
| 10 | Deprecated Rust Functions | Deprecated built-in functions should never be used. |
| 12 | DoS (Denial of Service) | Execution of the code should never be blocked by a specific contract state unless it is required. |
| 15 | Block values as a proxy for time | Block numbers should not be used for time calculations. |
| 16 | Signature Unique Id | Signed messages should always have a unique id. A transaction hash should not be used as a unique id. Chain identifier should always be used. |
| 17 | Shadowing State Variable | State variables should not be shadowed. |
| 18 | Weak Sources of Randomness | Random values should never be generated from Chain Attributes or be predictable. |
| 20 | Calls Only to Trusted Addresses | All external calls should be performed only to trusted addresses. |
| 21 | Presence of unused variables | The code should not contain unused variables if this is not justified by design. |
| 23 | Assets integrity | Funds are protected and cannot be withdrawn without proper permissions or be locked on the contract. |
| 24 | User Balances manipulation | Contract owners or any other third party should not be able to access funds belonging to users. |
| 25 | Data Consistency | Smart contract data should be consistent all over the data flow. |
| 26 | Flashloan Attack | When working with exchange rates, they should be received from a trusted source and not be vulnerable to short-term rate changes that can be achieved by using flash loans. Oracles should be used. |
| 27 | Token Supply manipulation | Tokens can be minted only according to rules specified in a whitepaper or any other documentation provided by the customer. |
| 28 | Gas Limit and Loops | Transaction execution costs should not depend dramatically on the amount of data stored on the contract. There should not be any cases when execution fails due to the block gas limit. |
| 29 | Style guide violation | Style guides and best practices should be followed. |
| 30 | Requirements Compliance | The code should be compliant with the requirements provided by the Customer. |
| 31 | Environment Consistency | The project should contain a configured development environment with a comprehensive description of how to compile, build and deploy the code. |
| 32 | Secure Oracles Usage | The code should have the ability to pause specific data feeds that it relies on. This should be done to protect a contract from compromised oracles. |
| 33 | Tests Coverage | The code should be covered with unit tests. Test coverage should be 100%, with both negative and positive cases covered. Usage of contracts by multiple users should be tested. |
| 34 | Stable Imports | The code should not reference draft contracts, that may be changed in the future. |
| 35 | Unsafe Rust code | The Rust type system does not check memory safety of unsafe Rust code. Thus, if a smart contract contains any unsafe Rust code, it may still suffer from memory corruptions such as buffer overflows, use after frees, uninitialized memory, etc. |

---

<br />

## NEAR
| # | Item | Description |
|---|------|-------------|
| 1 | As-of-yet Near blockchain unknown classes of vulnerabilities | Checking for any other, as-of-yet unknown classes of vulnerabilities arising from the structure of the Near blockchain. |
| 2 | Near contract standards violation | FT or NFT smart contracts meet to Near standards |
| 3 | Missing Initializer Attribute | Init function marked with init attribute does not exist, or init attribute is missing on initializer function |
| 4 | Missing "private" macro in cross-contract callback | Usually, when a contract has to have a callback for a remote cross-contract call, this callback method should only be called by the contract itself. It's to avoid someone else calling it and messing the state. |
| 5 | Missing "paybable" macro on payable functions | We can allow methods to accept token transfer together with the function call. This is done so that contracts can define a fee in tokens that needs to be payed when they are used. By the default the methods are not payable and they will panic if someone will attempt to transfer tokens to them during the invocation. |
| 6 | Collection type is suitable for structure type | Check if a suitable collection is used for declared structure and contract logic. |
| 7 | Near-Sdk is up to date | Check is near-sdk is up to date |

---

<br />

## Solana
| # | Item | Description |
|---|------|-------------|
| 1 | Missing rent exemption checks | All Solana accounts holding an Account, Mint, or Multisig must contain enough SOL to be considered rent exempt. Otherwise the accounts may fail to load. |
| 2 | Signed invocation of unverified programs | The program does not verify the pubkey of any program called via the invoke_signed() API. |
| 3 | Solana account confusions | The program fails to ensure that the account data has the type it expects to have. |
| 4 | Redeployment with cross-instance confusion | The program fails to ensure that the wasm code has the code it expects to have |
| 5 | Missing freeze authority checks | When freezing is enabled, but the program does not verify that the freezing account call has been signed by the appropriate freeze_authority |
| 6 | Insufficient SPL-Token account verification | Finding extra checks that should not exist with the given type of accounts |
| 7 | Anti-pattern to transfer the ownership of an Associated Token Account | Note that it is an anti-pattern to transfer the ownership of an Associated Token Account: In that case, the best practice is to create an associated token account for the recipient's wallet, transfer the tokens, and then close the first account. |
| 8 | As-of-yet Solana blockchain unknown classes of vulnerabilities | Checking for any other, as-of-yet unknown classes of vulnerabilities arising from the structure of the Solana blockchain. |

---

<br />

# Scrypto Checklist
| # | Item | Description |
|---|------|-------------|
| 1 | Bucket resource address validation | All buckets in a smart contract must be validated to have the correct resource address. |
| 2 | Permission control | All permissions and roles in the smart contracts must be validated, including upgradability. It is important to check enable_method_auth! Macro in a smart contract. |
| 3 | Proof resource address validation | All proofs should be checked for correct resource address |
| 4 | Duplicates in data structures validation | All data structures like Vec, Set, Map should be checked for possible duplicates, like in the case of Bucket - two buckets with the same resource address. It's a mistake to assume that by using Set of Buckets all of them must be unique, but it's not and can be multiple Buckets of the same resource in any data structure. | |
| 5 | Bucket NFT count validation | In buckets with NFT there can be more than one NFT in the bucket. It should be validated that smart contracts are correctly handling such cases. |
| 6 | Bucket burn addition validation | Bucket burn is one of the most dangerous functions and should be validated that only the correct resource and amount of it can be burned. |
| 7 | Resource permissions validation | All resources permissions defined by resource manager should be carefully validated, including upgradability of permissions. It also applies to default permission for all kinds of operations (withdraw, deposit, lock, burn, freeze, etc). |
| 8 | Transient tokens reentrancy validation | Whenever a smart contract creates a transient resource (a resource that must be burned in the same transaction), it should be validated that there is no logic in a smart contract that can be abused somehow between the emission and burning of this kind of token. It creates an issue similar to reentrancy. |
| 9 | Asset-oriented approach validation | Ensure the smart contract follows an asset-oriented design, avoiding the use of user account addresses for identification. Instead, the contract should issue tokens that users can use for verification. Data related to user participation should be represented by tokens or NFTs rather than stored directly in the contract. For instance, instead of assigning pool shares directly to users, issue POOL tokens to represent their share, with ownership determined by the tokens they hold in relation to the total supply. |
| 10 | Smart contract interactions | All interactions with external smart contracts must be thoroughly validated, particularly when the source code is provided by a third party. If an interaction fails, the entire transaction could fail, leading to potential Denial of Service (DoS) risks. When external interactions return data, especially if they return buckets, the data must be carefully validated. Excessive interactions with non-native contracts can also be problematic due to high execution costs, making complex transactions too expensive to carry out effectively. |
| 11 | Objects removal and update validation | In Scrypto, initialized objects such as smart contracts, vaults, key-value stores, and resource managers cannot be removed or transferred to other contracts. Auditors must validate that no operations attempt to remove or transfer these objects. Additionally, updates to data structures involving these objects must be carefully checked. For example, a previously inserted Vault in a HashMap<u32, Vault> cannot be overwritten, as this would require deletion, which is not allowed. |
| 12 | Decimal validation | All decimals should be validated for cases such as negative numbers provided by the user, numerical errors, and rounding errors. |
| 13 | Correct component initialization validation | It should be validated if components or objects are correctly stored and interactions with them are correct. It means checking if objects are using Own<> or Global<> and are correctly initialized with instantiate, prepare_to_globalize, globalize and other related functions. |
| 14 | Third-party resources validation | If a smart contract supports third-party resources it should be validated if it correctly handles different configurations of them, like different precision and non-typical configurations like blocking withdraws, deposits, freezing assets or even recalling tokens from the smart contract. |
