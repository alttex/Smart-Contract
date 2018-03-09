# ALTX Smart-Contract

This repository has the main contracts in ALTTEX platform. There are three main components in this repository including  AlttexToken contract and Crowdsale contracts.
This repository is for testing purposes only, do not use it for real deployment.

# Testnet deployment

We have a functional deployment running on kovan testnet. The deployed contracts are as below.

1. Crowdsale address = [0x6B69C2497a7140D1A929c9c1db9c95F77b5aD778](https://kovan.etherscan.io/address/0x6b69c2497a7140d1a929c9c1db9c95f77b5ad778#readContract)

The abi of Crowdsale contract is available at https://github.com/alttex/Smart-Contract/blob/master/Crowdsale.abi

2. AlttexToken address = [0xb41C6Aa324695dd6F198A1713E4c57AFEd0FD7f0](https://kovan.etherscan.io/address/0xb41c6aa324695dd6f198a1713e4c57afed0fd7f0#readContract)

The abi of AlttexToken contract is available at https://github.com/alttex/Smart-Contract/blob/master/AlttexToken.abi

## Main functions
We describe the main functions of the Alttex contracts as below.
### BuyTokens function
```
    function buyTokens(address beneficiary)
```

`beneficiary` who got the tokens

tokensSumBonus means amount of tokens purchased.

### getTimeBonus function
```
    function getTimeBonus() public view returns (uint256)
```

The function returns bonus value and value depends on time.

### getBonus function
```
    function getBonus(uint256 _value) internal view returns (uint256)
```

The function returns bonus value and value depends on the number of coins bought(_value).

### initialMint function
```
    function initialMint() onlyOwner public
```

The function mints tokens for preSale members.


# Deploy
A user needs to deploy
[Alttex](https://github.com/alttex/Smart-Contract/blob/master/AlttexToken.sol) contract without parameters, after that deploy [Crowdsale](https://github.com/alttex/Smart-Contract/blob/master/Crowdsale.sol) contract with parameters:
`_token = 0xb41C6Aa324695dd6F198A1713E4c57AFEd0FD7f0`,
`_endTime = 1522749600`,
`_wallet = 0xD229e7e74e881fD7e58bf4FBB8320ad9f54Ba800`,
`_TeamAndAdvisors = 0x47CdCdf03574Ed4c5797a4c8bD42B3cE2Cbc014D`,
`_Investors = 0x47CdCdf03574Ed4c5797a4c8bD42B3cE2Cbc014D`,
or with any other user parameters.
Set `saleAgent` equal <address Crowdsale contract> in AltexToken contract.
Then user should send ether and/or tokens to the Crowdsale contract. It can be in a standard way (just `send` or `transfer` ether or tokens to contract address).
