# Changelog

## 25-04-2021

### Added
The following contracts have been deployed across all the major test networks:
- **Rinkeby:** [0xc3F76Ab84f9493B6cd1f8E6E9d24C69F295395Ae](https://rinkeby.etherscan.io/address/0xc3f76ab84f9493b6cd1f8e6e9d24c69f295395ae)
- **Ropsten:** [0x8327931af8ADF326cC1bD1cAb5720A8c9606990c](https://ropsten.etherscan.io/address/0x8327931af8adf326cc1bd1cab5720a8c9606990c)
- **Kovan:** [0xA2869D16B6187DEB70DCfA1A2c6149ADa6D10d3C](https://kovan.etherscan.io/address/0xa2869d16b6187deb70dcfa1a2c6149ada6d10d3c)
- **Goerli:** [0xeB741f8826a3B516C80cA3aD3A5Da3a56B972FA4](https://goerli.etherscan.io/address/0xeb741f8826a3b516c80ca3ad3a5da3a56b972fa4)

Furthermore, the following additions have been implemented:
- Added `1_initial_migration.js` file to the migrations folder;
- Refactored the `truffle-config.js` file with a general dependency on the newly added file `network-config.json`, where all major test networks are defined as well as the Swiss DLT chain;

### Changed
- In the `package.json` I added a couple of new keywords as well as downgraded the `@truffle/hdwallet-provider` to version `1.2.3` due to a recent and still existing bug in the latest Truffle release (see [here](https://stackoverflow.com/questions/66735307/truffle-contract-deployment-failed-invalid-sender));
- The smart contract `SaentisGulden.sol` does not anymore support the extension `ERC20Snapshot` since this is not required in our use case;
- The smart contract `SaentisGulden.sol` does now include a `premint` functionality in the constructor that creates an initial amount of 100'000 tokens for the deployer (no need anymore to separately call `mint` after the deployment);


### Fixed
- Changed naming from `SantisGulden` to `SaentisGulden`;

## 23-04-2021

### Added
- Deployed Säntis Gulden Contract V 1.0 to Rinkeby with the contract address [0x10c35227901F2D1D19067E7c5798CF745e360dBc](https://rinkeby.etherscan.io/address/0x10c35227901f2d1d19067e7c5798cf745e360dbc)
