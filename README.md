# Foundry Template with 5ireChain configuration 

_**Please read the full README before using this template.**_

- [Overview 5ireChain configuration](#overview)
  - [`foundry.toml`](#foundrytoml)
- [Deploy and verify contract](#Command)



## Overview

This template is designed to be a simple but powerful configuration for Foundry projects, that aims to help you follow Solidity and Foundry [best practices](https://book.getfoundry.sh/tutorials/best-practices)

### `foundry.toml`

The `foundry.toml` config file comes with:

- A `fmt` configuration.
- A `default`, `lite`, `rpc_endpoints`, `etherscan` profiles for 5ireChain.



### Test Structure

The test structure is configured to follow recommended [best practices](https://book.getfoundry.sh/tutorials/best-practices).
It's strongly recommended to read that document, as it covers a range of aspects.
Consequently, the test structure is as follows:

- The core protocol deploy script is `script/Deploy.sol`.
  This deploys the contracts and saves their addresses to storage variables.
- The tests inherit from this deploy script and execute `Deploy.run()` in their `setUp` method.
  This has the effect of running all tests against your deploy script, giving confidence that your deploy script is correct.
- Each test contract serves as `describe` block to unit test a function, e.g. `contract Increment` to test the `increment` function.


### Command

Note: 
+ You need to set the `ETHERSCAN_API_KEY` environment variable to your Etherscan API key and `PRIVATE_KEY` to your wallet private key.

+ Make sure your wallet has enough balance to pay for the gas fees.



## Testnet 

```bash
forge script script/Deploy.s.sol --rpc-url 5ireTestnet src/Counter.sol:Counter --legacy --broadcast --verify
```

## Mainnet
```bash
forge script script/Deploy.s.sol --rpc-url 5ireMainnet src/Counter.sol:Counter --legacy --broadcast --verify
```
