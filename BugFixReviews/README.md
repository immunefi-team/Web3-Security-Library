Bugfix Reviews
--------------------
These are real world cases of bug fixes reported through Immunefi. To learn more about smart contract vulnerabilities theory check: [Vulnerabilities](../Vulnerabilities/README.md)

- [2023](#2023)
  - [July 2023](#july-2023)
    - [Yield Protocol Logic Error](#yield-protocol-logic-error)
  - [June 2023](#june-2023)
    - [Silo Finance Logic Error](#silo-finance-logic-error)
    - [DFX Finance Rounding Error](#dfx-finance-rounding-error)
  - [May 2023](#may-2023)
    - [Enzyme Finance Missing Privilege Check](#enzyme-finance-missing-privilege-check)
  - [February 2023](#february-2023)
    - [Beanstalk Logic Error](#beanstalk-logic-error)
    - [Balancer Logic Error](#balancer-logic-error)
  - [January 2023](#january-2023)
    - [Moonbeam, Astar, And Acala Library Truncation Bugfix Review — $1m Payout](#moonbeam-astar-and-acala-library-truncation-bugfix-review--1m-payout)
- [2022](#2022)
  - [December 2022](#december-2022)
    - [88MPH Theft Of Unclaimed MPH Rewards Bugfix Review](#88mph-theft-of-unclaimed-mph-rewards-bugfix-review)
  - [November 2022](#november-2022)
    - [Mt Pelerin Double Transaction Bugfix Review](#mt-pelerin-double-transaction-bugfix-review)
  - [September 2022](#september-2022)
    - [Aurora Improper Input Sanitization Bugfix Review](#aurora-improper-input-sanitization-bugfix-review)
    - [Aurora Withdrawal Logic Error Bugfix Review](#aurora-withdrawal-logic-error-bugfix-review)
  - [July 2022](#july-2022)
    - [Moonbeam Missing Call Check ](#moonbeam-missing-call-check-)
    - [Balancer DoS](#balancer-dos)
    - [Two Novel Crypto Wallet Exploits, Explained](#two-novel-crypto-wallet-exploits-explained)
    - [Synthetix Logic Error Bugfix Review](#synthetix-logic-error-bugfix-review)
  - [June 2022](#june-2022)
    - [Port Finance Logic Error Bugfix Review](#port-finance-logic-error-bugfix-review)
    - [Sense Finance Access Control Issue Bugfix Review](#sense-finance-access-control-issue-bugfix-review)
    - [Aurora Inflation Spend Bugfix Review: $6m Payout](#aurora-inflation-spend-bugfix-review-6m-payout)
  - [May 2022](#may-2022)
    - [Wormhole Uninitialized Proxy Bugfix Review](#wormhole-uninitialized-proxy-bugfix-review)
  - [March 2022](#march-2022)
    - [Redacted Cartel Custom Approval Logic Bugfix Review](#redacted-cartel-custom-approval-logic-bugfix-review)
    - [Optimism Infinite Money Duplication](#optimism-infinite-money-duplication)
  - [February 2022](#february-2022)
    - [Polygon Consensus Bypass](#polygon-consensus-bypass)
    - [APWine Incorrect Check of Delegations](#apwine-incorrect-check-of-delegations)
    - [Notional Double Counting Free Collateral](#notional-double-counting-free-collateral)
  - [January 2022](#january-2022)
    - [Cronos Theft of Transactions Fees](#cronos-theft-of-transactions-fees)
- [2021](#2021)
  - [December 2021](#december-2021)
    - [Bitswift Unlimited Mint](#bitswift-unlimited-mint)
    - [Polygon Lack of Balance Check](#polygon-lack-of-balance-check)
  - [November 2021](#november-2021)
    - [Enzyme Finance Price Oracle Manipulation](#enzyme-finance-price-oracle-manipulation)
    - [Harvest Finance Uninitialized Proxies](#harvest-finance-uninitialized-proxies)
  - [October 2021](#october-2021)
    - [Polygon Double-Spend](#polygon-double-spend)
    - [RocketPool and Lido Front-running](#rocketpool-and-lido-front-running)
  - [September 2021](#september-2021)
    - [Belt finance logic error](#belt-finance-logic-error)
    - [OpenZeppelin Bugfix Review](#openzeppelin-bugfix-review)
  - [August 2021](#august-2021)
    - [Tidal Finance Logic Error](#tidal-finance-logic-error)
    - [xDai Stake Arbitrary Call Method](#xdai-stake-arbitrary-call-method)
    - [Teller uninitialized proxy](#teller-uninitialized-proxy)
  - [July 2021](#july-2021)
    - [Alchemix access control](#alchemix-access-control)
    - [MCDex Insufficient Validation](#mcdex-insufficient-validation)
    - [PancakeSwap Logic Error](#pancakeswap-logic-error)
    - [Cream Finance](#cream-finance)
  - [June 2021](#june-2021)
    - [Pods Finance](#pods-finance)
    - [Mushrooms Finance Logic Error](#mushrooms-finance-logic-error)
    - [SharedStake Insider Exploit](#sharedstake-insider-exploit)
    - [Zapper Arbitrary Call Data](#zapper-arbitrary-call-data)
    - [88mph Function Initialization](#88mph-function-initialization)
    - [PancakeSwap Content Injection](#pancakeswap-content-injection)
  - [May 2021](#may-2021)
    - [Bitswift Race Condition](#bitswift-race-condition)
    - [Charger Particles Griefing](#charger-particles-griefing)
    - [Mushrooms finance Theft of Yield](#mushrooms-finance-theft-of-yield)
    - [Fei Protocol Flashloan Vulnerability](#fei-protocol-flashloan-vulnerability)
    - [Sovryn loan vulnerability](#sovryn-loan-vulnerability)
  - [April 2021](#april-2021)
    - [Fei Protocol Vulnerability](#fei-protocol-vulnerability)
  - [March 2021](#march-2021)
    - [PancakeSwap lottery vulnerability](#pancakeswap-lottery-vulnerability)
  - [February 2021](#february-2021)
    - [ArmorFi postmortem](#armorfi-postmortem)

# 2023

## July 2023
### [Yield Protocol Logic Error]()

The vulnerability involved a potential exploit that could allow an attacker to drain the base tokens from a pool by manipulating the token balance of a contract.

- Vulnerability type: Logic

## June 2023
### [Silo Finance Logic Error](https://medium.com/immunefi/silo-finance-logic-error-bugfix-review-35de29bd934a)

The bug could manipulate the interest rate to borrow more funds than should have been allowed by the system.

- Vulnerability type: Logic

### [DFX Finance Rounding Error](https://medium.com/immunefi/dfx-finance-rounding-error-bugfix-review-17ba5ffb4114)

Rounding error with EURS token due to the non-standard decimal value of two.

- Vulnerability type: Logic 

## May 2023
### [Enzyme Finance Missing Privilege Check](https://medium.com/immunefi/enzyme-finance-missing-privilege-check-bugfix-review-ddb5e87b8058)

This critical bug could have led to the draining of Enzyme's Vault.

- Vulnerability type: Missing Privilege Check

## February 2023
### [Beanstalk Logic Error](https://medium.com/immunefi/beanstalk-logic-error-bugfix-review-4fea17478716)

This critical logic error allowed theft of assets from the accounts that were approved for the Beanstalk contract.

- Vulnerability type: Logic

### [Balancer Logic Error](https://medium.com/immunefi/balancer-logic-error-bugfix-review-74f5edca8b1a)

This high severity bug allowed liquidity providers to submit duplicate claims and drain all the Merkle Orchad's assets from the Vault.

- Vulnerability type: Logic

## January 2023

### [Moonbeam, Astar, And Acala Library Truncation Bugfix Review — $1m Payout](https://medium.com/immunefi/moonbeam-astar-and-acala-library-truncation-bugfix-review-1m-payout-41a862877a5b)

The bug, which was found within Frontier — the Substrate pallet that provides core Ethereum compatibility features within the Polkadot ecosystem–impacted Moonbeam, Astar Network, and Acala. The estimated potential damage from the vulnerability amounted to approximately $200m across the three projects, which was swiftly prevented

- Vulnerability type: Minting new valid but depegged wrapped tokens.

# 2022

## December 2022

### [88MPH Theft Of Unclaimed MPH Rewards Bugfix Review](https://medium.com/immunefi/88mph-theft-of-unclaimed-mph-rewards-bugfix-review-1dec98b9956b)

Allowed users to steal most of the 88MPH tokens generated from yield contract by depositing an asset and withdrawing the vested 88mph tokens immediately.

- Vulnerability type: Theft of funds.

## November 2022

### [Mt Pelerin Double Transaction Bugfix Review](https://medium.com/immunefi/mt-pelerin-double-transaction-bugfix-review-503838db3d70)

The bug could have allowed users to drain contract funds.

- Vulnerability type: Theft of funds.

## September 2022

### [Aurora Improper Input Sanitization Bugfix Review](https://medium.com/immunefi/aurora-improper-input-sanitization-bugfix-review-a9376dac046f)

Improper impot sanitazion that allowed a bad actor to steal funds using a worthless NEP-141.

- Vulnerability type: Improper Input Sanitization

### [Aurora Withdrawal Logic Error Bugfix Review](https://medium.com/immunefi/aurora-withdrawal-logic-error-bugfix-review-c5b4e30a9160)
We need Aurora to execute a burn function on NEAR and wait to withdraw the assets in Ethereum. How do we create a transaction looks like Aurora did it?

- Vulnerability type: Logic, Bridge

## July 2022

### [Moonbeam Missing Call Check ](https://medium.com/immunefi/moonbeam-missing-call-check-bugfix-review-6279d609bdc5 )

Missing call check vulnerability that allows direct theft of native assets.

Vulnerability Type: Missing call check, theft of funds.

- Vulnerability type: Missing Call Check

### [Balancer DoS](https://medium.com/immunefi/balancer-dos-bugfix-review-8a8ba5d971bf )
Potentially exploitable Denial of Service scenario by emptying double entry-point ERC-20 tokens through Balancer’s flash loans.

- Vulnerability type: DoS

### [Two Novel Crypto Wallet Exploits, Explained](https://medium.com/immunefi/two-novel-crypto-wallet-exploits-explained-98e74e50d13f )
Unciphered unveiled three novel exploits impacting popular (and once-popular) crypto wallets Electrum Bitcoin Wallet, Trezor One, and Ethereumwallet.com.

- Vulnerability type: hardware

### [Synthetix Logic Error Bugfix Review](https://medium.com/immunefi/synthetix-logic-error-bugfix-review-40da0ead5f4f )

Logic vulnerability in the fee reclamation and rebate features in Synthetix.

- Vulnerability type: logic

## June 2022

### [Port Finance Logic Error Bugfix Review](https://medium.com/immunefi/port-finance-logic-error-bugfix-review-29767aced446 )

A malicious user could have withdrawn all their obligation collaterals without paying off their full debt.

- Vulnerability type: logic

### [Sense Finance Access Control Issue Bugfix Review](https://medium.com/immunefi/sense-finance-access-control-issue-bugfix-review-32e0c806b1a0 )

Missing access control issue in the onSwap() function of the Sense Balancer pool that could have allowed a malicious actor to update the oracle data of the Space AMM contract

- Vulnerability type: access control

### [Aurora Inflation Spend Bugfix Review: $6m Payout](https://medium.com/immunefi/aurora-infinite-spend-bugfix-review-6m-payout-e635d24273d )

The vulnerability consisted of an infinite spend bug that, if exploited by a malicious user, could have led to a direct loss of 70k ETH and $200m in other assets.

- Vulnerability type: infinite spend

## May 2022

### [Wormhole Uninitialized Proxy Bugfix Review](https://medium.com/immunefi/wormhole-uninitialized-proxy-bugfix-review-90250c41a43a )

Upgradeable proxy implementation self-destruct bug that helped prevent a potential lockup of user funds

- Vulnerability type: upgradeable proxy

## March 2022

### [Redacted Cartel Custom Approval Logic Bugfix Review](https://medium.com/immunefi/redacted-cartel-custom-approval-logic-bugfix-review-9b2d039ca2c5)

The vulnerability would have allowed a malicious attacker to assign a user’s allowance to themselves, enabling the attacker to steal that user’s funds.

- Vulnerability type: Logic and allowance.
  
### [Optimism Infinite Money Duplication](https://medium.com/immunefi/optimism-infinite-money-duplication-bugfix-review-daa6597146a0)

The bug would have allowed an attacker to replicate money continuously on any chain using a vulnerability found in OVM 2.0 (Optimism Virtual Machine)

- Vulnerability type: Logic, OVM(EVM equivalent)

## February 2022

### [Polygon Consensus Bypass](https://medium.com/immunefi/polygon-consensus-bypass-bugfix-review-7076ce5047fe)

Consensus bypass vulnerability that would have allowed an attacker to decrease the total staking power, allowing a consensus (⅔ threshold) bypass that could potentially have allowed an attacker to drain all the funds from the deposit manager, engage in unlimited withdrawals, DoS, and more.

- Vulnerability type: PoS Consensus bypass

### [APWine Incorrect Check of Delegations](https://medium.com/immunefi/apwine-incorrect-check-of-delegations-bugfix-review-7e401a49c04f)

In the PT tokens, one condition wasn’t checked during the burn of those tokens which could lead to the theft of the yield from the protocol after the two periods.

- Vulnerability type: Logic error

### [Notional Double Counting Free Collateral](https://medium.com/immunefi/notional-double-counting-free-collateral-bugfix-review-28b634903934)

Free collateral miscalculation and overpricing by a factor of two could allow a bad actor to drain almost all liquidity.

- Vulnerability type: Logic error - Miscalculation

## January 2022

### [Cronos Theft of Transactions Fees](https://medium.com/immunefi/cronos-theft-of-transactions-fees-bugfix-postmortem-b33f941b9570)

The vulnerability that could allow stealing the fees of the current block in Cronos Blockchain

- Vulnerability type: theft of yield
 
# 2021
## December 2021

### [Bitswift Unlimited Mint](https://medium.com/immunefi/bitswift-unlimited-mint-bugfix-postmortem-147a1e57dca9)

A front-end critical vulnerability that could allow minting an infinite amount of tokens.

- Vulnerability type: Insecure front-end, mint.

### [Polygon Lack of Balance Check](https://medium.com/immunefi/polygon-lack-of-balance-check-bugfix-postmortem-2-2m-bounty-64ec66c24c7d)

The vulnerability consisted of a lack of balance/allowance check in the `transfer()` function of Polygon’s MRC20 contract and would have allowed an attacker to steal all MATIC from the contract.

- Type of vulnerability: Lack of balance check.

## November 2021

### [Enzyme Finance Price Oracle Manipulation](https://medium.com/immunefi/enzyme-finance-price-oracle-manipulation-bug-fix-postmortem-4e1f3d4201b5)

Vulnerability Type: flash loan/oracle price manipulation.

### [Harvest Finance Uninitialized Proxies](https://medium.com/immunefi/harvest-finance-uninitialized-proxies-bug-fix-postmortem-ea5c0f7af96b)

The Dedaub team filed a submission via Immunefi for uninitialized implementation contracts for Uniswap V3 vault proxies. The contracts in scope held a total of $6.4M in Uniswap V3 positions at the time of the submission.

- Vulnerability Type: Uninitialized Proxies, Access control.

## October 2021

### [Polygon Double-Spend](https://medium.com/immunefi/polygon-double-spend-bug-fix-postmortem-2m-bounty-5a1db09db7f1)

The vulnerability allowed an attacker to exit their burn transaction from the bridge multiple times, up to 223 times. There were around ~$850M at risk. Having just $100k to launch the attack with would result in $22.3M in loss!

- Vulnerability Type: Bridge manipulation.

### [RocketPool and Lido Front-running](https://medium.com/immunefi/rocketpool-lido-frontrunning-bug-fix-postmortem-e701f26d7971)

The vulnerability allowed a malicious node operator included in Lido or RocketPool to steal user deposits frontrunning the deposit.

- Vulnerability Type: Frontrunning

## September 2021

### [Belt finance logic error](https://medium.com/immunefi/belt-finance-logic-error-bug-fix-postmortem-39308a158291)

A logic error caused one of the contracts to think it had less money than it did, resulting in excess shares being issued for new deposits.

- Vulnerability Type: Logic Error

### [OpenZeppelin Bugfix Review](https://medium.com/immunefi/openzeppelin-bug-fix-postmortem-66d8c89ed166)

Critical reentrancy vulnerability in OpenZeppelin’s TimelockController, where the “executor” was able to hijack the controller and set the delay to 0, remove the existing “proposers”, set themselves as the “proposer” and take over the Timelock and the contracts associated with it.

- Vulnerability Type: Re-entrancy, Access control

## August 2021

### [Tidal Finance Logic Error](https://medium.com/immunefi/tidal-finance-logic-error-bug-fix-postmortem-3607d8b7ed1f)

The logic error permitted a malicious user to claim more rewards from staking than they were entitled to.

- Vulnerability Type: Logic Error - Excess rewards

### [xDai Stake Arbitrary Call Method](https://medium.com/immunefi/xdai-stake-arbitrary-call-method-bug-postmortem-f80a90ac56e3)

The bug allowed a potentially malicious hacker to gain access to funds in a contract.

- Vulnerability Type: Arbitrary call method

### [Teller uninitialized proxy](https://medium.com/immunefi/teller-bug-fix-postmorten-and-bug-bounty-launch-b3f67a65c5ac)

The beacon proxy was not initialized and could have been initialized by anyone, including a hypothetical malicious attacker.

- Vulnerability Type: Uninitialized proxy

## July 2021

### [Alchemix access control](https://medium.com/immunefi/alchemix-access-control-bug-fix-debrief-a13d39b9f2e0)

Any user could have called setWhitelist() to give an attacker the ability to call the harvest function.

- Vulnerability Type: Access control

### [MCDex Insufficient Validation](https://medium.com/immunefi/mcdex-insufficient-validation-bug-fix-postmortem-182fc6cab899)

A critical vulnerability in MCDEX’s broker contract that would have allowed a malicious user to drain that contract of ETH

- Vulnerability Type: 

### [PancakeSwap Logic Error](https://medium.com/immunefi/pancakeswap-logic-error-bug-fix-postmortem-f2d02adb6983)

Due to insufficient validation, a malicious user could have claimed the same winning lottery ticket at least 255 times in a single transaction.

- Vulnerability Type: Logic Error - insufficient validation

### [Cream Finance](https://medium.com/immunefi/cream-finance-insufficient-validation-bug-fix-postmortem-1ec7248e8865)

A malicious user drains Cream’s liquidity mining rewards contract using the front-end and different wallets.

- Vulnerability Type: Front-end - Insufficient Validation

## June 2021

### [Pods Finance](https://medium.com/immunefi/pods-finance-bug-fix-postmortem-61a576897ebd)

This logic error allows for theft of yield or abuse of the rewards system. A bad actor was able to claim rewards owed to other users and drain the entire contract.

- Vulnerability Type: Logic Error - Improper Validation

### [Mushrooms Finance Logic Error](https://medium.com/immunefi/mushrooms-finance-logic-error-bug-fix-postmortem-780122821621)

A logic error leading to a flash loan attack vector.

- Vulnerability Type: Logic Error, Flash loan

### [SharedStake Insider Exploit](https://medium.com/immunefi/sharedstake-insider-exploit-postmortem-17fa93d5c90e)

This vulnerability allowed the beneficiary of the time-locked funds to transfer out those funds before those funds were scheduled to be released.

- Vulnerability Type: Arbitrary call

### [Zapper Arbitrary Call Data](https://medium.com/immunefi/zapper-arbitrary-call-data-bug-fix-postmortem-d75a4a076ae9)

Using the arbitrary call an attacker could call “transferFrom” and since there was no validation of the data provided, the contract will be forced to transfer all the LP tokens from any victim to the attacker.

- Vulnerability Type: Arbitrary call

### [88mph Function Initialization](https://medium.com/immunefi/88mph-function-initialization-bug-fix-postmortem-c3a2282894d3)

The `init()` function was missing an onlyOwner modifier and also there was no initializer to prevent a re-initialization. So `init()` function was unprotected and was callable multiple times.

Vulnerability Type: Logic Error, Access Control

### [PancakeSwap Content Injection](https://medium.com/immunefi/pancakeswap-content-injection-bug-fix-postmortem-e9058cfc7451)

Web content injection vulnerability that would have allowed a malicious user to inject any arbitrary text on PancakeSwap’s website.

- Vulnerability Type: Content injection

## May 2021

### [Bitswift Race Condition](https://medium.com/immunefi/bitswift-race-condition-bug-fix-postmortem-588184b8b43e)

The race condition vulnerability would have allowed a malicious user to repeatedly claim the same voucher, which entitles a user to some amount of crypto tokens.
(Race condition).

- Vulnerability type: 

### [Charger Particles Griefing](https://medium.com/immunefi/charged-particles-griefing-bug-fix-postmortem-d2791e49a66b)

The vulnerability was a griefing/denial of service attack against the protocol that would have allowed a malicious user to create a system where bribes had to be paid for a user to buy or sell an NFT.

- Vulnerability Type: Griefing, Denial of Service (DoS)

### [Mushrooms finance Theft of Yield](https://medium.com/immunefi/mushrooms-finance-theft-of-yield-bug-fix-postmortem-16bd6961388f)

Theft of Yield using an MEV attack with flash bots.

- Vulnerability Type: MEV, Theft of yield

### [Fei Protocol Flashloan Vulnerability](https://medium.com/immunefi/fei-protocol-flashloan-vulnerability-postmortem-7c5dc001affb)

Flash loan-driven market manipulation vulnerability permits a threat actor to drain 60.000 ETH from the contract.

- Vulnerability Type: Flashloan/oracle price manipulation.

### [Sovryn loan vulnerability](https://medium.com/immunefi/sovryn-loan-vulnerability-postmortem-ffaf4d1d688f)

The critical vulnerability consisted of a failure to validate that the receiver of the proceeds of a collateralized loan was the same entity as the borrower, meaning a malicious user could request a loan based on unused collateral from another user.

- Vulnerability Type: Logic - No validation.

## April 2021

### [Fei Protocol Vulnerability](https://medium.com/immunefi/fei-protocol-vulnerability-postmortem-483f9a7e6ad1)

Assuming a situation where the FEI price is below the peg, a malicious user could purchase FEI, pushing the price not just back to the 1:1 peg, but above the peg, receiving some amount of FEI as a buy reward in the process. The user could then drip the FEI back into the Uniswap pool via a transfer (not a swap), which bypasses the burn penalty, and finally, convert the FEI to wETH with a swap. As a result, the attacker receives a wETH from the pool without having (net) sold any FEI.

- Vulnerability Type: Logic Error

## March 2021

### [PancakeSwap lottery vulnerability](https://medium.com/immunefi/pancakeswap-lottery-vulnerability-postmortem-and-bug-4febdb1d2400)

A user could see the lottery draw transaction, compute the winning lottery number, buy the right ticket during the draw, and front-run with a high gas fee to win the lottery. PancakeSwap fixed the vulnerability by updating its contract to include protections against buying using the multibuy method during the drawing phase.

- Vulnerability Type: Front-running.

## February 2021

### [ArmorFi postmortem](https://medium.com/immunefi/armorfi-bug-bounty-postmortem-cf46eb650b38)

A single Dollar worth of coverage could have enabled a malicious attacker to withdraw far more assets than available. Because the exploit allows them to get 10^18 as much as they purchased.

- Vulnerability Type: Logic Error
