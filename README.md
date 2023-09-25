# x/vesting

## Abstract

This page presents comprehensive details regarding the Vesting Module offered by Evmos. The functionality of this module empowers users to transform their accounts into clawback vesting accounts, allowing the reception of tokens from a designated funder. Additionally, it provides the funder with the capability to stipulate specific vesting and locking schedules, and to clawback unvested tokens.
This module is a rearrangement of the original [x/vesting](https://github.com/evmos/evmos/tree/main/x/vesting) that makes no use of the Evmos's custom [EthAccount](https://github.com/evmos/evmos/blob/6fda63866715b248bbd03c13461163a58de48c09/proto/ethermint/types/v1/account.proto#L14) to allows the module to be compatible with any other non-EVM Cosmos SDK chain.

## Clawback Vesting Accounts

### Overview

Vesting accounts, defined in the x/vesting module, are a new type implementing the Cosmos SDK [VestingAccount interface](https://docs.cosmos.network/main/modules/auth/vesting#vesting-account-types). This new type allows users to convert their account into a clawback vesting account. This account type can receive tokens from a particular address, called the funder, which are released according to the defined lockup and vesting schedules. The funder of the account can claw back unvested tokens at any time. The clawback can also be enforced through a governance proposal for any account that opts in to this when converting to a vesting account.

