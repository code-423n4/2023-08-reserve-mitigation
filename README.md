# Reserve - Mitigation Review details

- Total Prize Pool: $17,600 USDC
- [Warden guidelines for C4 mitigation reviews](https://code4rena.notion.site/Guidelines-for-C4-mitigation-reviews-ed10fc5cfbf640bd8dcec66f38b343c4)
- Submit findings [using the C4 form](https://code4rena.com/contests/2023-08-reserve-protocol-mitigation-review/submit)
- Starts August 15, 2023 20:00 UTC
- Ends August 22, 2023 20:00 UTC

## Important note

Each warden must submit a mitigation review for:

- Every High and Medium finding listed as in-scope below, and
- one report for the QA fixes.

For the QA mitigation report:
- Submit any new High or Medium issues introduced by the QA and GAS fixes as a newly-introduced High and Medium risk issue.

**Incomplete mitigation reviews will not be eligible for awards.**

## Findings being mitigated

Mitigations of all High and Medium issues will be considered in-scope and listed here.

- [H-01: Custom redemption might revert if old assets were unregistered](https://github.com/code-423n4/2023-06-reserve-findings/issues/4)
- [H-02: A new era might be triggered despite a significant value being held in the previous era](https://github.com/code-423n4/2023-06-reserve-findings/issues/2)
- [M-01: A Dutch trade could end up with an unintended lower closing price #48](https://github.com/code-423n4/2023-06-reserve-findings/issues/48)
- [M-02: The broker should not be fully disabled by GnosisTrade.reportViolation](https://github.com/code-423n4/2023-06-reserve-findings/issues/47)
- [M-03: In case Distributor.setDistribution use, revenue from rToken RevenueTrader and rsr token RevenueTrader should be distributed](https://github.com/code-423n4/2023-06-reserve-findings/issues/34)
- [M-04: FurnaceP1.setRatio will work incorrect after call when frozen](https://github.com/code-423n4/2023-06-reserve-findings/issues/29)
- [M-06: Oracle timeout at rebalance will result in a sell-off of all RSRs at 0 price](https://github.com/code-423n4/2023-06-reserve-findings/issues/15)
- [M-07: sell reward rTokens at low price because of skiping furnace.melt](https://github.com/code-423n4/2023-06-reserve-findings/issues/13)
- [M-08: stake before unfreeze can take away most of rsr rewards in the freeze period](https://github.com/code-423n4/2023-06-reserve-findings/issues/11)
- [M-09: cancelUnstake lack payoutRewards before mint shares](https://github.com/code-423n4/2023-06-reserve-findings/issues/10)
- [M-10: An oracle deprecation might lead the protocol to sell assets for a low price](https://github.com/code-423n4/2023-06-reserve-findings/issues/8)
- [M-11: Attacker can disable basket during un-registration, which can cause an unnecessary trade in some cases](https://github.com/code-423n4/2023-06-reserve-findings/issues/7)

## Mitigations to be reviewed

### Branch

https://github.com/reserve-protocol/protocol/pull/882 (commit hash 99d9db72e04db29f8e80e50a78b16a0b475d79f3)

### Individual PRs

Wherever possible, mitigations should be provided in separate pull requests, one per issue. If that is not possible (e.g. because several audit findings stem from the same core problem), then please link the PR to all relevant issues in your findings repo.

| URL                                                                                                         | Mitigation of | Purpose                                                                        |
| ----------------------------------------------------------------------------------------------------------- | ------------- | ------------------------------------------------------------------------------ |
| https://github.com/reserve-protocol/protocol/pull/857                                                       | H-01          | Fix redeemCustom                                                               |
| https://github.com/reserve-protocol/protocol/pull/888                                                       | H-02          | Adds governance function to manually push the era forward                      |
| https://github.com/reserve-protocol/protocol/pull/876                                                       | M-01          | Allow settle trade when paused or frozen                                       |
| https://github.com/reserve-protocol/protocol/pull/873 https://github.com/reserve-protocol/protocol/pull/869 | M-02          | Disable dutch auctions on a per-collateral basis, use 4-step dutch trade curve |
| https://github.com/reserve-protocol/protocol/pull/878                                                       | M-03          | Distribute revenue in setDistribution                                          |
| https://github.com/reserve-protocol/protocol/pull/885                                                       | M-04          | Update payout variables if melt fails during setRatio                          |
| https://github.com/reserve-protocol/protocol-private/pull/15                                                | M-06          | Use lotPrice()                                                                 |
| https://github.com/reserve-protocol/protocol-private/pull/7                                                 | M-07          | Refresh before selling rewards, refactor revenue & distro                      |
| https://github.com/reserve-protocol/protocol/pull/857                                                       | M-08          | payoutRewards before freeze and update payoutLastPaid before unfreeze          |
| https://github.com/reserve-protocol/protocol-private/pull/3                                                 | M-09          | Payout rewards during cancelUnstake                                            |
| https://github.com/reserve-protocol/protocol/pull/886                                                       | M-10          | Add oracle deprecation check                                                   |
| https://github.com/reserve-protocol/protocol/pull/857                                                       | M-11          | Change gas reservation policy in AssetRegistry                                 |
| https://github.com/reserve-protocol/protocol/pull/877                                                       | QA            | Document preference for dutch auctions                                         |
| https://github.com/reserve-protocol/protocol/pull/877                                                       | QA            | Claim rewards when unregistering an Asset                                      |
| https://github.com/reserve-protocol/protocol/pull/877                                                       | QA            | Require collateral status remain constant on registration                      |
| https://github.com/reserve-protocol/protocol/pull/872                                                       | QA            | Call useAvailable when setting throttles                                       |
| https://github.com/reserve-protocol/protocol/pull/877                                                       | QA            | Set trade status to CLOSED on contract deployment                              |

## Out of Scope

- [M-05: Lack of claimRewards when manageToken in RevenueTrader](https://github.com/code-423n4/2023-06-reserve-findings/issues/16)
- [M-12: Custom redemption can be used to get more than RToken value, when an upwards depeg occurs](https://github.com/code-423n4/2023-06-reserve-findings/issues/6)

