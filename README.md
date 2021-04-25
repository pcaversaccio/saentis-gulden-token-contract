# Saentis Gulden's ERC-20 Smart Contract
This is Säntis Gulden's ERC-20 smart contract, whose tokens are used as vouchers in their ecosystem.

## Changelog
See the created `CHANGELOG` file in this repository.

## Installation
### 1. Install the Truffle Framework
We use the Truffle framework for the compilation, testing, and deployment. Please follow their [guide](https://www.trufflesuite.com/truffle) to install the framework on your computer.

### 2. Getting Started
Run `npm i` in order to install the necessary [OpenZeppelin node modules](https://www.npmjs.com/package/@openzeppelin/contracts) as well as further required dependencies.

## Compilation
To compile the contract, it is important that you have installed the project correctly, as we use external dependencies and contracts. Use the following command to compile the contracts: 
```
truffle compile
```

## Deployment
### Local Deployment With Ganache
To deploy the contract on your local Ganache blockchain, you must first install the software on your computer. Follow the installation [guide](https://www.trufflesuite.com/ganache).

Once you installed the local blockchain, you can create a workspce. This is described [here](https://www.trufflesuite.com/docs/ganache/workspaces/creating-workspaces).
> *Note:* We have observed that Truffle and Ganache do not use the same default RPC configuration. The easiest way to align is to adjust Ganache's server hostname, port, and network ID with Truffle's configurations (check the file `truffle-config.js`).

Once you are setup, just run: 
```
truffle migrate --network development
```

### Rinkeby
To deploy the smart contract to Rinkeby, you need to preconfigure first some things:
1. Create a secret.json file.
2. Create a MetaMask Wallet and paste the respective seedphrase into secrets.json. Make sure you got some ETH. Get some at https://faucet.rinkeby.io/.
3. Create a new Infura project at https://infura.io/ and copy the project key into secrets.json.
4. Create a Etherscan account and copy the API key to secrets.json.

Now run the following command:
```
truffle migrate --network rinkeby
```

If the deployment was successful, you will get the final deployment result:

![Deployment Result](/assets/RinkebyDeploymentResult.png)

Copy the contract address and verify the contract right away so that you can interact with it. Run the following command:
```
truffle run verify SaentisGulden@CONTRACT-ADDRESS --network rinkeby
```

If the verification was successful, you will see the result:
```bash
Verifying SantisGulden@0x10c35227901F2D1D19067E7c5798CF745e360dBc
Pass - Verified: https://rinkeby.etherscan.io/address/0x10c35227901F2D1D19067E7c5798CF745e360dBc#contracts
Successfully verified 1 contract(s).
```

For more information, see [here] (https://github.com/rkalis/truffle-plugin-verify).

## Interaction
If you deployed the smart contract succefully, you are now able to interact with it.

### Local Interaction with the Truffle CLI
To start the Truffle JavaScript console, please run:
```
truffle develop
```

In the console, you can create an instance of the provided contract by typing:
```
let i = await SantisGulden.deployed()
```

You can use the instance variable to call functions like symbol:
```
i.symbol()
```

### Rinkeby
Go to the corresponding Etherscan link, e.g. https://rinkeby.etherscan.io/address/CONTRACT-ADDRESS#code. You are able to invoke READ and WRITE functions on the contract.

## Test Deployments
The smart contract `SaentisGulden.sol` has been deployed across all the major test networks:
- **Rinkeby:** [0xc3F76Ab84f9493B6cd1f8E6E9d24C69F295395Ae](https://rinkeby.etherscan.io/address/0xc3f76ab84f9493b6cd1f8e6e9d24c69f295395ae)
- **Ropsten:** [0x8327931af8ADF326cC1bD1cAb5720A8c9606990c](https://ropsten.etherscan.io/address/0x8327931af8adf326cc1bd1cab5720a8c9606990c)
- **Kovan:** [0xA2869D16B6187DEB70DCfA1A2c6149ADa6D10d3C](https://kovan.etherscan.io/address/0xa2869d16b6187deb70dcfa1a2c6149ada6d10d3c)
- **Goerli:** [0xeB741f8826a3B516C80cA3aD3A5Da3a56B972FA4](https://goerli.etherscan.io/address/0xeb741f8826a3b516c80ca3ad3a5da3a56b972fa4)

## References
[1] https://docs.openzeppelin.com/contracts/4.x/erc20
[2] https://github.com/rkalis/truffle-plugin-verify
[3] https://www.trufflesuite.com/ganache
[4] https://www.trufflesuite.com/truffle