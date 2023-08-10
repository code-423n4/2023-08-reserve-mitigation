# Reserve - Mitigation Review details
- Total Prize Pool: $17,600 USDC 
- [Warden guidelines for C4 mitigation reviews](https://code4rena.notion.site/Guidelines-for-C4-mitigation-reviews-ed10fc5cfbf640bd8dcec66f38b343c4)
- Submit findings [using the C4 form](https://code4rena.com/contests/2023-08-reserve-mitigation/submit)
- Starts August 15, 2023 20:00 UTC 
- Ends August 22, 2023 20:00 UTC 

## Important note 

Each warden must submit a mitigation review for *every High and Medium finding* from the parent audit that is listed as in-scope for the mitigation review. **Incomplete mitigation reviews will not be eligible for awards.**

## Findings being mitigated

Mitigations of all High and Medium issues will be considered in-scope and listed here.

- [H-01: Custom redemption might revert if old assets were unregistered](https://github.com/code-423n4/2023-06-reserve-findings/issues/4)
- [H-02: A new era might be triggered despite a significant value being held in the previous era](https://github.com/code-423n4/2023-06-reserve-findings/issues/2)
- [M-01: A Dutch trade could end up with an unintended lower closing price #48](https://github.com/code-423n4/2023-06-reserve-findings/issues/48)
- [M-02: The broker should not be fully disabled by GnosisTrade.reportViolation](https://github.com/code-423n4/2023-06-reserve-findings/issues/47)
- [M-03: In case Distributor.setDistribution use, revenue from rToken RevenueTrader and rsr token RevenueTrader should be distributed](https://github.com/code-423n4/2023-06-reserve-findings/issues/34)
- [M-04: FurnaceP1.setRatio will work incorrect after call when frozen](https://github.com/code-423n4/2023-06-reserve-findings/issues/29)
- [M-05: Lack of claimRewards when manageToken in RevenueTrader](https://github.com/code-423n4/2023-06-reserve-findings/issues/16)
- [M-06: Oracle timeout at rebalance will result in a sell-off of all RSRs at 0 price](https://github.com/code-423n4/2023-06-reserve-findings/issues/15)
- [M-07: sell reward rTokens at low price because of skiping furnace.melt](https://github.com/code-423n4/2023-06-reserve-findings/issues/13)
- [M-08: stake before unfreeze can take away most of rsr rewards in the freeze period](https://github.com/code-423n4/2023-06-reserve-findings/issues/11)
- [M-09: cancelUnstake lack payoutRewards before mint shares](https://github.com/code-423n4/2023-06-reserve-findings/issues/10)
- [M-10: An oracle deprecation might lead the protocol to sell assets for a low price](https://github.com/code-423n4/2023-06-reserve-findings/issues/8)
- [M-11: Attacker can disable basket during un-registration, which can cause an unnecessary trade in some cases](https://github.com/code-423n4/2023-06-reserve-findings/issues/7)
- [M-12: Custom redemption can be used to get more than RToken value, when an upwards depeg occurs](https://github.com/code-423n4/2023-06-reserve-findings/issues/6)

[ ⭐️ SPONSORS ADD INFO HERE ]

## Overview of changes

Please provide context about the mitigations that were applied if applicable and identify any areas of specific concern.

## Mitigations to be reviewed

### Branch
[ ⭐️ SPONSORS ADD A LINK TO THE BRANCH IN YOUR REPO CONTAINING ALL PRS ]

### Individual PRs
[ ⭐️ SPONSORS ADD ALL RELEVANT PRs TO THE TABLE BELOW:]

Wherever possible, mitigations should be provided in separate pull requests, one per issue. If that is not possible (e.g. because several audit findings stem from the same core problem), then please link the PR to all relevant issues in your findings repo. 

| URL | Mitigation of | Purpose | 
| ----------- | ------------- | ----------- |
| https://github.com/your-repo/sample-contracts/pull/XXX | H-01 | This mitigation does XYZ | 

## Out of Scope

Please list any High and Medium issues that were judged as valid but you have chosen not to fix.
