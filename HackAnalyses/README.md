Hack Analyses
--------------------
These are real world cases of bug fixes reported through Immunefi. To learn more about smart contract vulnerabilities theory check: [Vulnerabilities](../Vulnerabilities/README.md)

- [2023](#2023)
  - [Hack Analysis: 0xbaDc0dE MEV Bot, September 2022](#hack-analysis-0xbadc0de-mev-bot-september-2022)
  - [Hack Analysis: Nomad Bridge, August 2022](#hack-analysis-nomad-bridge-august-2022)
  - [Hack Analysis: Beanstalk Governance Attack, April 2022](#hack-analysis-beanstalk-governance-attack-april-2022)
- [2022](#2022)
  - [Hack Analysis: Omni Protocol, July 2022](#hack-analysis-omni-protocol-july-2022)
  - [Hack Analysis: Saddle Finance, April 2022](#hack-analysis-saddle-finance-april-2022)
  - [Hack Analysis: Cream Finance Oct 2021](#hack-analysis-cream-finance-oct-2021)
  - [Root Cause Hack Analyses by Sunsec](#root-cause-hack-analyses-by-sunsec)


# 2023

## [Hack Analysis: 0xbaDc0dE MEV Bot, September 2022](https://medium.com/immunefi/0xbadc0de-mev-bot-hack-analysis-30b9031ff0ba)

A smart contract MEV bot was hacked on the Ethereum blockchain, losing around 1,101 WETH. The hack took place just 30 minutes after the MEV bot pulled off a notoriously profitable arbitration that earned it 804 WETH. Since the smart contract code is unverified, this article shows how one can go about finding a vulnerability in a smart contract by just looking at its bytecode, past transactions and a bit of PoC trial and error action.

- Vulnerability type: Lack of sufficient validation of flashloan caller leading to arbitrary function execution

## [Hack Analysis: Nomad Bridge, August 2022](https://medium.com/immunefi/hack-analysis-nomad-bridge-august-2022-5aa63d53814a)

A routine upgrade on the implementation of one of Nomad’s proxy contracts marked a zero hash value as a trusted root, which allowed messages to get automatically proved. The hacker leveraged this vulnerability to spoof the bridge contract and trick it to unlock funds.

- Vulnerability type: CommittedRoot set to ZERO.

## [Hack Analysis: Beanstalk Governance Attack, April 2022](https://medium.com/immunefi/hack-analysis-beanstalk-governance-attack-april-2022-f42788fc821e)

Beanstalk was the victim of a whopping $181M hack, which leveraged the lack of execution delay to push through a malicious governance proposal.

- Vulnerability type: Lack of execution delay.

# 2022

## [Hack Analysis: Omni Protocol, July 2022](https://medium.com/immunefi/hack-analysis-omni-protocol-july-2022-2d35091a0109)

The underlying vulnerability, reentrancy, was exploited across two different functions of the same smart contract. Notably, these functions were lacking reentrancy locks and did not follow the checks-effects-interactions pattern. By leveraging the re-entrancy vulnerability on two different functions and using two attacker contracts, the hacker was able to borrow against the collateral and make the market forget about it.

- Vulnerability type: Re-entrancy.

## [Hack Analysis: Saddle Finance, April 2022](https://medium.com/immunefi/hack-analysis-saddle-finance-april-2022-f2bcb119f38)

Price miscalculation when swapping a token for an LP token.

- Vulnerability type: Logic, price calculation.

## [Hack Analysis: Cream Finance Oct 2021](https://medium.com/immunefi/hack-analysis-cream-finance-oct-2021-fc222d913fc5)

Analysis of Cream Finance exploit on Oct 2021, resulting in loss of $130m in available liquidity.

- Vulnerability type: Oracle manipulation, Uncapped supply of token.

## [Root Cause Hack Analyses by Sunsec](https://www.notion.so/0e85e02c5ed34df3855ea9f3ca40f53b)

Hack analysis of 101 DeFi hack & exploit incidents.
