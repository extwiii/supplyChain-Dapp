# Supply Chain Dapp

## Part 1: Plan the project with write-ups

### Requirement 1: Project write-up - UML

![Activity Diagram](images/activity_diagram.svg)

![Sequence Diagram](images/sequence_diagram.svg)

![State Diagram](images/state_diagram.svg)

![Data Model](images/data_model.svg)

### Requirement 2: Project write-up - Libraries

- Truffle version: v5.1.20
- OpenZeppelin version: 2.5.0
- Infura
- Metamask

### Requirement 3: Project write-up - IPFS

IPFS implementation is skipped for now.

## Part 2: Write smart contracts

### Requirement 1: Define and implement required interfaces
```
contract AccessControl
contract Base is AccessControl
contract Core is Base
```

* AccessControl - Collection of Contracts: These contracts manages the various addresses and constraints for operations that can be executed only by specific roles.

* Base - SupplyChain.sol: This is where we define the most fundamental code shared throughout the core functionality. This includes our main data storage, constants and data types, plus internal functions for managing these items.

* Core - Ownable.sol: is the contract that controls ownership and transfer of ownership.

### Requirement 2: Build out AccessControl Contracts

* Farmer: The Farmer can harvest coffee beans, process coffee beans, pack coffee palettes, add coffee palettes, ship coffee palettes, and track authenticity.
* Distributor: The Distributor can buy coffee palettes and track authenticity.
* Retailer: The Retailer can receive coffee palettes and track authenticity.
* Consumer: The consumer can buy coffee palettes and track authenticity

### Requirement 3: Build out Base Contract

* Product ID
* Product UPC
* Origination Information
* Origin Actor (e.g. Farmer ID, Farmer Name, )
* Misc. organization information (e.g. Farmer Information)
* Longitude and Latitude of Origin Coordinates (e.g. Farm’s Longitude and Latitude)
* Product notes
* Product price

### Requirement 4: Build out Core Contract

* Ownable - Define an owner for all the contracts.
* Secondary - Allows contract to be transferred owners.

## Part 3: Test smart contract code coverage

### Requirement: Smart contract has associated tests

- harvestItem()
- processItem()
- packItem()
- addItem()
- buyItem()
- shiptItem()
- receiveItem()
- purchaseItem()
- fetchItemBufferOne()
- sfetchItemBufferTwo()

## Part 4: Deploy smart contracts on public test network

### Requirement 1: Deploy smart contract on a public test network

* Add your rinkeby networks inside truffle.js.

```
const HDWallet = require('truffle-hdwallet-provider');

const fs = require('fs');
const mnemonic = fs.readFileSync(".secret").toString().trim();
const infuraKey = fs.readFileSync(".infuraKey").toString().trim();

module.exports = {
  networks: {
    development: {
      host: "127.0.0.1",
      port: 8545,
      network_id: "*" // Match any network id
    },
    rinkeby: {
      provider: () => new HDWallet(mnemonic, `https://rinkeby.infura.io/v3/${infuraKey}`),
      network_id: 4,       // rinkeby's id
      gas: 4500000,        // rinkeby has a lower block limit than mainnet
      gasPrice: 10000000000
    }
  },
};
```

* Create .secret with your secret and .infuraKey with your infuraID

* Run `truffle migrate --reset --network rinkeby`

* Outlook should be similar to `contract_addresses.md`

### Requirement 2: Submit Contract Address

- Please see `contract_addresses.md` file for details

## Part 5: Modify client code to interact with smart contract

### Requirement: Configure client code for each actor

- Submit a product for shipment (farmer to the distributor, distributor to retailer, etc).
- Receive product from shipment.
- Validate the authenticity of the product.

 
