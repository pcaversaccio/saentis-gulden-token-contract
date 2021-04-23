# Saentis Gulden Token Contract 

This is Säntis Guldens ERC-20 preset smart contract, whose tokens are used as vouchers in their ecosystem.

## Changelog

See the created changelog file in this repository.

## Installation

### 1. Install truffle framework
We use truffle framework for compilation, test and deployment. Please follow the guides on their website to install the software on your computer:

https://www.trufflesuite.com/truffle

### 2. Install the project

`npm i`

## Compilation

To compile the contract it is important that you installed the project correctly because we use external dependencies and contracts. Use the following command to compile the contracts.

`truffle compile`

## Deployment

### Local with ganache

To deploy the contract to your local ganache blockchain you need to install the software first on your computer. Follow the installation guide on their website:
https://www.trufflesuite.com/ganache

Once you installed the blockchain create a workspce. This is described also on the their website:
https://www.trufflesuite.com/docs/ganache/workspaces/creating-workspaces

> Note: We recognized that truffle and ganache are not using the same default RPC config. Easiest is to adjust the servers hostname, port and network-id in ganache's server configuration to the defintion of truffle.

Once you are setup please run:

`truffle migrate --network development`

### Rinkeby

To deploy the contract to rinkeby you need to preconfigure first some things.

1. Create a secret.json file.
2. Create a MetaMask Wallet and paste the respective seedphrase into secrets.json. Make sure you got some ETH. Get some at https://faucet.rinkeby.io/.
3. Create a new Infura project at https://infura.io/ and copy the project key into secrets.json.
4. Create a Etherscan account and copy the API key to secrets.json.

run the following command:

`truffle migrate --network rinkeby`

If the deployment was successful you will get the final deployment result:

![Deployment Result](/assets/RinkebyDeploymentResult.png)

Copy the contract address and verify the contract right away so that you can interact with it.
Run the following command:

`truffle run verify SantisGulden@CONTRACT-ADDRESS --network rinkeby`

If the verification was successful you will see the result.

Verifying SantisGulden@0x10c35227901F2D1D19067E7c5798CF745e360dBc
Pass - Verified: https://rinkeby.etherscan.io/address/0x10c35227901F2D1D19067E7c5798CF745e360dBc#contracts
Successfully verified 1 contract(s).

For more information check https://github.com/rkalis/truffle-plugin-verify.

## Interaction

If you deployed the smart contract succefully you are able to interact with it.

### Local with the CLI

To start the truffle console please run:

`truffle develop`

Inside the console you are able to create an instance of the deployed contract by typing:

`let i = await SantisGulden.deployed()`

You can use the instance variable to call functions like symbol:

`i.symbol()`

### Rinkeby

Go to https://rinkeby.etherscan.io/address/CONTRACT-ADDRESS#code.
You are able to invoke READ and WRITE functions on the contract.