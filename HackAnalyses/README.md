Hack Analyses
--------------------
These are real world cases of bug fixes reported through Immunefi. To learn more about smart contract vulnerabilities theory check: [Vulnerabilities](../Vulnerabilities/README.md)

- [2023](#2023)
  - [Hack Analysis: BonqDAO, February 2023](#hack-analysis-bonqdao-february-2023)
  - [Hack Analysis: Platypus Finance, February 2023](#hack-analysis-platypus-finance-february-2023)
- [2022](#2022)
  - [Hack Analysis: Beanstalk Governance Attack, April 2022](#hack-analysis-beanstalk-governance-attack-april-2022)
  - [Hack Analysis: Saddle Finance, April 2022](#hack-analysis-saddle-finance-april-2022)
  - [Hack Analysis: Omni Protocol, July 2022](#hack-analysis-omni-protocol-july-2022)
  - [Hack Analysis: Nomad Bridge, August 2022](#hack-analysis-nomad-bridge-august-2022)
  - [Hack Analysis: 0xbaDc0dE MEV Bot, September 2022](#hack-analysis-0xbadc0de-mev-bot-september-2022)
  - [Hack Analysis: Binance Bridge, October 2022](#hack-analysis-binance-bridge-october-2022)
- [2021](#2021)
  - [Hack Analysis: Cream Finance Oct 2021](#hack-analysis-cream-finance-oct-2021)
  - [Root Cause Hack Analyses by Sunsec](#root-cause-hack-analyses-by-sunsec)


# 2023

## [Hack Analysis: BonqDAO, February 2023](https://medium.com/immunefi/hack-analysis-bonqdao-february-2023-ef6aab0086d6)

BonqDAO protocol was hacked resulting in a loss of approximately $120 million due to a price oracle manipulation attack. The vulnerability stemmed from a flawed implementation of the price feed, allowing the attacker to manipulate the price of the WALBT token and borrow an excessive amount of protocol stablecoin (BEUR).

 - Vulnerability type: Price oracle manipulation

## [Hack Analysis: Platypus Finance, February 2023](https://medium.com/immunefi/hack-analysis-platypus-finance-february-2023-d11fce37d861)

Platypus Finance protocol fell victim to a sophisticated exploit, resulting in the loss of approximately $8.5 million in stablecoin collateral. Exploiting a logic error within the USP-Platypus’ solvency check mechanism, the attacker borrowed against flash-loaned collateral and withdrew it without settling the debt. The incident underscores the critical importance of thorough validation and testing, particularly in functions designed for emergency scenarios, within DeFi protocols. Despite the substantial loss, the Platypus team, with the assistance of BlockSec, managed to conduct a reverse hack, recovering approximately $2.5 million of the stolen funds within 24 hours.

- Vulnerability type: Logic error in the solvency check mechanism.

# 2022

## [Hack Analysis: Beanstalk Governance Attack, April 2022](https://medium.com/immunefi/hack-analysis-beanstalk-governance-attack-april-2022-f42788fc821e)

Beanstalk, a permissionless fiat stablecoin protocol, fell victim to a $181 million hack, exploiting a lack of execution delay in governance proposals. The attacker leveraged flashloans to gain voting power and pass two malicious proposals, transferring funds to their own address and to Ukraine’s crypto donation address. Despite $77 million being recovered, the incident prompted Beanstalk to replace its on-chain governance with a community-run multisig wallet.

- Vulnerability type: Lack of execution delay.

## [Hack Analysis: Saddle Finance, April 2022](https://medium.com/immunefi/hack-analysis-saddle-finance-april-2022-f2bcb119f38)

Saddle Finance, an automated market maker (AMM) on Ethereum, experienced a series of transactions resulting in approximately $11 million in cryptocurrency being drained. Despite one of the attacks being intercepted by a whitehat who managed to salvage around 25% of the total funds, the exploit exploited a previously known bug that had not been adequately patched. The attack leveraged a price miscalculation when swapping a token for an LP token.

- Vulnerability type: Logic, price calculation.

## [Hack Analysis: Omni Protocol, July 2022](https://medium.com/immunefi/hack-analysis-omni-protocol-july-2022-2d35091a0109)

The underlying vulnerability, reentrancy, was exploited across two different functions of the same smart contract. Notably, these functions were lacking reentrancy locks and did not follow the checks-effects-interactions pattern. By leveraging the re-entrancy vulnerability on two different functions and using two attacker contracts, the hacker was able to borrow against the collateral and make the market forget about it.

- Vulnerability type: Re-entrancy.

## [Hack Analysis: Nomad Bridge, August 2022](https://medium.com/immunefi/hack-analysis-nomad-bridge-august-2022-5aa63d53814a)

A routine upgrade on the implementation of one of Nomad’s proxy contracts marked a zero hash value as a trusted root, which allowed messages to get automatically proved. The hacker leveraged this vulnerability to spoof the bridge contract and trick it to unlock funds.

- Vulnerability type: CommittedRoot set to ZERO.

## [Hack Analysis: 0xbaDc0dE MEV Bot, September 2022](https://medium.com/immunefi/0xbadc0de-mev-bot-hack-analysis-30b9031ff0ba)

A smart contract MEV bot was hacked on the Ethereum blockchain, losing around 1,101 WETH. The hack took place just 30 minutes after the MEV bot pulled off a notoriously profitable arbitration that earned it 804 WETH. Since the smart contract code is unverified, this article shows how one can go about finding a vulnerability in a smart contract by just looking at its bytecode, past transactions and a bit of PoC trial and error action.

- Vulnerability type: Lack of sufficient validation of flashloan caller leading to arbitrary function execution

## [Hack Analysis: Binance Bridge, October 2022](https://medium.com/immunefi/hack-analysis-binance-bridge-october-2022-2876d39247c1)


In October 2022, the Binance Bridge fell victim to a hack, where a flaw in the IAVL Merkle proof verification system enabled a malicious actor to steal 2 million BNB, amounting to approximately $600 million USD. Exploiting the vulnerability, the hacker managed to manipulate a proof, bypassing security measures and siphoning off the funds. Binance responded by temporarily halting the system and implementing a blacklist feature. This incident underscored the critical importance of robust security protocols when integrating with external codebases, prompting Binance to address the hack event with a hard fork of the network.

- Vulnerability type: Lack of sufficient validation of IAVL verification Merkle tree.


# 2021

## [Hack Analysis: Cream Finance, October 2021](https://medium.com/immunefi/hack-analysis-cream-finance-oct-2021-fc222d913fc5)

Cream Finance experienced a significant exploit, resulting in a loss of $130 million in available liquidity. The attack involved manipulating a hybrid oracle and taking advantage of uncapped token supplying, allowing the attacker to drain the protocol of funds by borrowing against inflated collateral values.

- Vulnerability type: Oracle manipulation, Uncapped supply of token.

## [Root Cause Hack Analyses by Sunsec](https://www.notion.so/0e85e02c5ed34df3855ea9f3ca40f53b)

Hack analysis of 101 DeFi hack & exploit incidents.