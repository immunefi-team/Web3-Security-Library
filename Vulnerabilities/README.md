
# Vulnerabilies
(WIP)

This is the therory behind the vulnerabilities, if you are interested in learning the real world examples check: [BugFix Reviews](../BugFixReviews/README.md). 

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
- [Use of components with known vulnerabilities](#use-of-components-with-known-vulnerabilities)
- [Blockchain Bridges](#blockchain-bridges)
- [Research Papers](#research-papers)
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

Resources: [Consensys](https://consensys.github.io/smart-contract-best-practices/attacks/reentrancy/), [SecuRing](https://medium.com/securing/reentrancy-attack-in-smart-contracts-is-it-still-a-problem-50db3e2042ae), [Historical Collection of Reentrancy Attacks](https://github.com/pcaversaccio/reentrancy-attacks)

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

When a borrower uses a platform's smart contract to obtain a loan without providing collateral, this is referred to as a "Flash loan."

A flash loan attack happens when a hacker borrows a lot of assets that don’t require collateral, manipulates the price of a cryptocurrency asset on one exchange, and then sells it very rapidly on another.

An example is C.R.E.A.M. Finance flash loan attack. To know more, read: "[C.R.E.A.M. Finance Post Mortem: Flash Loan Exploit Oct 27](https://medium.com/cream-finance/post-mortem-exploit-oct-27-507b12bb6f8e)" resulted in a loss of ~$130M USD.

# Oracle manipulation

# Unchecked call return value

# Transaction reorganization (MEV)

# Bad Randomness

Bad Randomness arises when the attacker can predict the result of a random number. Depending on the circumstances, this may result in certain security risks.

Currently, two techniques are frequently employed to obtain randomness: using **block variables** or **oracles**.

#### 1. Block variables

The most frequently used block variables are `block.difficulty`, `blockhash`, `block.number`, and `block.timestamp`. Randomness generated by block data limits the possibility of regular users to predict that random number, but not to miners.

When they have mined a block, the miners are not required to broadcast it, they can also discard it. This process is called "selective packing". Until they achieve the desired outcome, miners will continue to produce randomness; once they do, they will broadcast a block.

For randomness that isn't a part of the core application, block variables are a good option.

#### 2. Oracles

An example of an oracle is [ChainLink](https://chain.link/). There are oracles specifically built to generate random number seeds that are then used by other applications to generate randomness.

This comes with some risks, such as being dependent on a third-party to provide you a random number seed and being sure that the oracle doesn't get corrupted. Even if you create your own oracle, your application will always depend on the integrity of it (check [Oracle manipulation](#oracle-manipulation)).

That said, oracles are the most reliable way to have strong randomness.

# Use of components with known vulnerabilities
- Smart contracts may have been created using an obsolete compiler with known flaws
- Libraries with known vulnerabilities have been imported
- Code reuse: for their apps, many programmers reuse code. To put it another way, if the copied code has flaws, so does the smart contract it was pasted into.

# Blockchain Bridges:

- [The Dark Side of DeFi Cross-chain Bridge Hacks](https://quantstamp.com/blog/the-dark-side-of-defi-cross-chain-bridge-hacks)

# Research Papers:

- [SoK: Not Quite Water Under the Bridge: Review of Cross-Chain Bridge Hacks](https://arxiv.org/pdf/2210.16209.pdf)
- [A Review on Cryptocurrencies Security](https://www.researchgate.net/publication/352343090_A_Review_on_Cryptocurrencies_Security)

# Resources:
- [Consensys Smart Contract Best Practices Attacks](https://consensys.github.io/smart-contract-best-practices/attacks/)
- [Consensys Smart Contract Best Practices Development Recommendations](https://consensys.github.io/smart-contract-best-practices/development-recommendations/)
- [SWC Registry, Smart Contract Weakness Classification and Test Cases](https://swcregistry.io/)
- [List of Security Vulnerabilities](https://github.com/runtimeverification/verified-smart-contracts/wiki/List-of-Security-Vulnerabilities)
- [Secureum Audit Findings 101](https://secureum.substack.com/p/audit-findings-101)
- [Secureum Audit Findings 201](https://secureum.substack.com/p/audit-findings-201)
- [DeFiVulnLabs - Collection of Vulnerable Code Snippets](https://github.com/SunWeb3Sec/DeFiVulnLabs)
