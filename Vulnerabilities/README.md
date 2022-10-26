
# Vulnerabilies
(WIP)

This is the therory behind the vulnerabilities, if you are interested in learning the real world examples check: [BugFixReviews](../BugFixReviews/README.md). 

- [Vulnerabilies](#vulnerabilies)
- [Logic](#logic)
  - [- Bad Arithmetics](#--bad-arithmetics)
  - [- Integer underflow/overflow](#--integer-underflowoverflow)
- [Re-entrancy](#re-entrancy)
- [Uninitialized](#uninitialized)
- [- Contracts](#--contracts)
  - [- Proxies](#--proxies)
- [Code injection via delegatecall [WIP]](#code-injection-via-delegatecall-wip)
- [Access Control](#access-control)
   - [- Unprotected functions](#--unprotected-functions)
   - [- Signature Verification](#--signature-verification)
   - [- Authentication with tx.origin](#--authentication-with-txorigin)
   - [- Reusing msg.value](#--reusing-msgvalue)
- [Wrong implementation of standards](#wrong-implementation-of-standards)
- [Flashloans](#flashloans)
- [Oracle manipulation](#oracle-manipulation)
- [Unchecked call return value](#unchecked-call-return-value)
- [Transaction reorganization (MEV)](#transaction-reorganization-mev)
- [Bad Randomness](#bad-randomness)
- [Resources:](#resources)

# Logic

## - Bad Arithmetics
- Assumptions using external functions

This can have a lot of variations, this case of calling an external function is very interesting: [ValueDeFi Incident](https://peckshield.medium.com/valuedefi-incident-incorrect-weighted-constant-product-invariant-calculation-1bbaa220a02b)

- Decimal assuptions

For example, ERC20 decimals errors, the common value used for decimals is 18, but tokens like USDT and USDC have only 6.

## - Integer underflow/overflow
This happens when you go below the minimum value (underflow) or exceed the maximum value (overflow) and the value will be considered 0.

Solidity has different value types, for integers you can use `int` (negative and positive values) and `uint` (just positive ones) and their size variations in steps of 8 for example: `int8` 2\**8 different values,`int16`, `int24`... `int256` 2\**256 values

Since `version 0.8.0` Solidity automatically reverts on integer overflow and underflow instead of circling the value back to zero.

Resources: [Consensys Insecure Arithmetic](https://consensys.github.io/smart-contract-best-practices/attacks/insecure-arithmetic/), [Solidity Docs Integers](https://docs.soliditylang.org/en/v0.8.11/types.html#integers)

# Re-entrancy
Reentrancy is when a program’s execution can be interrupted and re-run from a particular point, a vulnerability made famous in the DAO hack. One way this vulnerability could manifest is if a bank’s wire system only checked an account’s balance at the beginning of the wire, as opposed to also checking the balance when the wire is about to be sent, in order to ensure sufficient funds. This could lead to a reentrancy attack that calls the send function multiple times to send more funds than are available in the account.

In other words, this is an issue of temporality where a send function can be called before a check balance function is called.

In smart contracts, a function will make an external call, which if not done just correctly will allow an untrusted called contract to perform a re-entrancy attack on the original contract.

Resources: [Consensys](https://consensys.github.io/smart-contract-best-practices/attacks/reentrancy/), [SecuRing](https://medium.com/securing/reentrancy-attack-in-smart-contracts-is-it-still-a-problem-50db3e2042ae)

# Uninitialized
## - Contracts 

## - Proxies

# Code injection via delegatecall [WIP]
First of all, you need to understand what is `delegatecall` this function is a variant of message call but  [SolidityDocs delegatecall](https://docs.soliditylang.org/en/v0.8.16/introduction-to-smart-contracts.html?highlight=delegatecall#delegatecall-callcode-and-**libraries**)

# Access Control
## - Unprotected functions
- Default Visibility
  One of this common examples 
## - Signature Verification

## - Authentication with tx.origin
Never use `tx.origin` for authorization. 

If for example you create a contract wallet with that authorization system, someone can trick you into sending Ether to an attack contract and that contract can call your unsafe wallet and drain all the funds because is checking the `tx.origin` instead of the `msg.sender`. Check the code of this example [here](https://docs.soliditylang.org/en/develop/security-considerations.html#tx-origin)

## - Reusing msg.value
The particularity with `msg.value` is that his value remains fixed during the whole function call. Do not use `msg.value` inside a loop.

Resources: [TrustChain](https://medium.com/@TrustChain/ethereum-msg-value-reuse-vulnerability-5afd0aa2bcef), [TrailOfBits](https://blog.trailofbits.com/2021/12/16/detecting-miso-and-opyns-msg-value-reuse-vulnerability-with-slither/)

# Wrong implementation of standards
Information about standards: [Ethereum docs](https://ethereum.org/en/developers/docs/standards/tokens/), [OpenZeppelin docs](https://docs.openzeppelin.com/contracts/2.x/tokens)

Let's say that these standards are almost bulletproof, however, the most insignificant change can lead to critical vulnerabilities.

As an example, I'm going back to the spring of 2021 when a lot of projects decided to add a "transfer fee" to their tokens, this can be seen as an insignificant change but, most of the contracts weren't ready to handle these tokens. The common issue here was that someone could drain the pool staking and unstaking several times leading to miscalculations. This article [Watchpug SafeDollar postmortem](https://watchpug.medium.com/safedollar-exploit-root-cause-analysis-4b7ec6357a6d) provides an example.

# Flashloans

# Oracle manipulation

# Unchecked call return value

# Transaction reorganization (MEV)

# Bad Randomness

# Resources:
- [Consensys Smart Contract Best Practices Attacks](https://consensys.github.io/smart-contract-best-practices/attacks/)
- [Consensys Smart Contract Best Practices Development Recommendations](https://consensys.github.io/smart-contract-best-practices/development-recommendations/)
- [SWC Registry, Smart Contract Weakness Classification and Test Cases](https://swcregistry.io/)
- [List of Security Vulnerabilities](https://github.com/runtimeverification/verified-smart-contracts/wiki/List-of-Security-Vulnerabilities)
- [Secureum Audit Findings 101](https://secureum.substack.com/p/audit-findings-101)
- [Secureum Audit Findings 201](https://secureum.substack.com/p/audit-findings-201)
- [DeFiVulnLabs - Collection of Vulnerable Code Snippets](https://github.com/SunWeb3Sec/DeFiVulnLabs)