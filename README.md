# MineNFT & Crosschain Web

**MineNFT** is a full-stack decentralized application (dApp) designed to empower artists by enabling collaborative NFT minting and seamless revenue sharing through smart contracts. Built with modern Web3 tools, this project demonstrates token-gated access, multi-artist collaboration, and cross-chain NFT interoperability.

## Table of Contents

- [Overview](#overview)  
- [Features](#features)  
- [Tech Stack](#tech-stack)  
- [Smart Contract Structure](#smart-contract-structure)  
- [Frontend Structure](#frontend-structure)  
- [Getting Started](#getting-started)  
- [How It Works](#how-it-works)  
- [Folder Structure](#folder-structure)  
- [Future Improvements](#future-improvements)  

## Overview

**MineNFT** focuses on:
- Allowing multiple artists to co-mint NFTs.
- Sharing revenue automatically using `PaymentSplitter`.
- Supporting gated access where only NFT holders can access premium content.
- Experimenting with cross-chain integration (e.g., Ethereum and Flow).

This project was developed for the **Gated Hackathon** to showcase how Web3 tools can enhance collaborative digital ownership.

## Features

- **Wallet Authentication**: Connect via MetaMask or any EVM-compatible wallet.
- **Collaborative NFT Minting**: Artists can co-create NFTs and share minting rights.
- **Automated Revenue Sharing**: Earnings are split using the `PaymentSplitter` contract.
- **Gated Access**: Only users with specific NFTs can access certain parts of the platform.
- **Crosschain Readiness**: The project is structured to support both Ethereum and Flow (via Cadence) for future cross-chain expansion.

## Tech Stack

### Frontend
- Vite
- React
- TypeScript
- Tailwind CSS
- Ethers.js
- Web3Modal

### Smart Contracts
- Solidity (ERC-721, PaymentSplitter)
- Hardhat or Truffle (choose one depending on your setup)
- OpenZeppelin libraries

### Backend (Optional - for logs/metadata)
- Node.js
- Express
- MongoDB

## Smart Contract Structure

- **ERC-721 Contract**: Represents the NFT with standard metadata.
- **PaymentSplitter**: Used for automatically splitting the revenue from sales among contributors.
- **AccessControl**: Ensures that only authorized collaborators can mint.

Contracts are deployed using Truffle/Hardhat and configured for easy interaction via the frontend.

## Frontend Structure

- **Home Page**: Displays public NFTs and artist info.
- **Profile Page**: Shows user-specific NFTs and collaboration status.
- **Artists Page**: List of verified artists available for collaboration.
- **Post NFT Page**: Allows collaborators to mint new NFTs.
- **Wallet Page**: Lets users connect and verify their NFT access.

Includes MobX or Context API for global state management, depending on your setup.

## Getting Started

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Suganthan96/Mine-NFT-and-Crosschain-Web.git
   cd Mine-NFT-and-Crosschain-Web
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Start the Development Server**
   ```bash
   npm run dev
   ```

4. **Compile Smart Contracts**
   ```bash
   truffle compile   # or use hardhat compile
   ```

5. **Deploy Contracts to a Local or Test Network**
   ```bash
   truffle migrate --network development
   ```

6. **Update Contract Addresses**
   Replace deployed contract addresses in your frontend configuration (e.g., `contract-config.js`).

## How It Works

- Artist connects wallet and gets verified.
- Collaborators are selected and included in the minting request.
- The NFT is minted via a contract that includes the PaymentSplitter.
- On sale or auction, revenue is split automatically.
- Users with NFTs gain gated access to private areas.

## Folder Structure

```
Mine-NFT-and-Crosschain-Web/
├── contracts/             # Solidity contracts
├── src/
│   ├── components/        # React components
│   ├── pages/             # React pages (Home, Profile, PostNFT, etc.)
│   ├── store/             # MobX/State management
│   ├── utils/             # Wallet and blockchain helpers
│   └── App.tsx            # Main app component
├── public/
├── tailwind.config.js
├── vite.config.ts
├── package.json
└── README.md
```

## Future Improvements

- Integrate Flow blockchain support using Cadence.
- Enable fractional NFT ownership with ERC-1155.
- Add a backend dashboard for artist statistics and collaboration metrics.
- On-chain governance for artist selection and royalties.
- Multi-chain NFT bridging (e.g., Ethereum to Solana).
