# MiniSocial Smart Contract

MiniSocial is a simple social media-style Ethereum smart contract that allows users to publish and retrieve messages on the blockchain. Each message is stored with the author's address, enabling a decentralized, transparent, and immutable message board.

## Features

- **Publish Messages**: Users can publish messages that are stored on the blockchain along with their Ethereum address.
- **Retrieve Messages**: Users can retrieve a specific message by index.
- **Total Message Count**: The contract tracks the total number of messages published.

## Prerequisites

- **MetaMask**: Used for Ethereum account management and signing transactions.
- **Remix IDE**: A web-based Ethereum IDE to compile, deploy, and interact with the contract.
- **Sepolia Test Network**: The contract is deployed and tested on the Sepolia test network using SepoliaETH.

## Contract Overview

### `Post` Structure

The `Post` structure holds each message with the following attributes:

- `message` (string): The content of the message.
- `author` (address): The Ethereum address of the user who published the message.

### Functions

1. **publishPost(string memory _message)**
   - Publishes a new message to the blockchain.
   - Stores the message and the address of the user (`msg.sender`) who called the function.
   
2. **getPost(uint index) public view returns (string memory, address)**
   - Retrieves a specific post by index from the blockchain.
   - Returns the message and the author's address.
   
3. **getTotalPosts() public view returns (uint)**
   - Returns the total number of posts that have been published.

## Deployment and Testing Instructions

1. **Open Remix IDE**: Go to [Remix IDE](https://remix.ethereum.org/).
2. **Create the Contract File**: In the Remix file explorer, create a new file named `MiniSocial.sol` and paste in the contract code.
3. **Compile**: Go to the "Solidity Compiler" tab and click "Compile MiniSocial.sol".
4. **Deploy**: 
   - Go to the "Deploy & Run Transactions" tab.
   - Select the **Injected Web3** environment to connect Remix to MetaMask.
   - Ensure MetaMask is connected to the Sepolia test network.
   - Click **Deploy** and confirm the transaction in MetaMask.

### Testing the Functions

1. **publishPost**:
   - In the "Deployed Contracts" section, enter a custom message (e.g., "Hello from user1!") into the `publishPost` function and click **transact**.
   - Repeat with different messages or MetaMask accounts to simulate different users.

2. **getPost**:
   - Enter an index (starting from `0` for the first post) in the `getPost` function field and click **call**.
   - Verify that the returned message and address match the expected values.

3. **getTotalPosts**:
   - Click on `getTotalPosts` to retrieve the current count of posts.

