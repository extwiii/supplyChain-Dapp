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




 
