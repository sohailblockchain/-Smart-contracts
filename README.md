# DeFi Smart Contracts Suite

A collection of Solidity-based smart contracts implementing wrapped assets, ERC20 tokens, oracle-integrated minting, and a collateral-backed token model.

This repository demonstrates core DeFi primitives including:

- Wrapped token mechanics
- ERC20 asset ecosystem
- Chainlink-style oracle integration
- Collateralized mint/burn logic
- Mock price feeds for testing

---

## 📦 Contracts Overview

### 1️⃣ WrappedToken.sol

Implements a wrapped ERC20 token mechanism.

Features:
- Wrap native ERC20 tokens into WTKN
- Mint wrapped tokens 1:1
- Unwrap to retrieve underlying asset
- Secure transferFrom pattern

Use Case:
Token bridging, asset abstraction, liquidity wrapping.

---

### 2️⃣ ROI / BDOLA / EMP Tokens

Standard ERC20 tokens built with OpenZeppelin.

Tokens:
- ROI Token (ROI)
- BDOLA Token (BDOLA)
- Empress Token (EMP)

Each token:
- Mints fixed initial supply
- Uses OpenZeppelin ERC20 standard
- Production-ready inheritance pattern

---

### 3️⃣ DOLA.sol

Collateral-backed ERC20 token with oracle pricing.

Key Mechanics:

- Uses Chainlink-style price feeds
- Requires BDOLA collateral
- Calculates mint requirement based on ROI oracle price
- Supports burn to redeem collateral

Core Functions:

- mint(uint256 amount)
- burn(uint256 amount)
- getROIValue()
- getBDOLAValue()

Architecture:

User  
  ↓  
Provides BDOLA collateral  
  ↓  
DOLA contract checks ROI oracle price  
  ↓  
Mints DOLA based on collateral ratio  

This simulates a simplified stablecoin / synthetic asset mechanism.

---

### 4️⃣ MockPriceFeed.sol

Implements Chainlink AggregatorV3Interface.

Used for:
- Testing oracle-dependent logic
- Simulating price updates
- Local development

Returns:
- Configurable price
- Timestamp data
- Version metadata

---

## 🧠 Architecture

User Wallet
      ↓
ERC20 Tokens (ROI / BDOLA / EMP)
      ↓
DOLA (Collateralized Token)
      ↓
Oracle Layer (AggregatorV3Interface / MockPriceFeed)
      ↓
Price-Based Mint & Burn Logic

---

## 🏗️ Tech Stack

- Solidity ^0.8.x
- OpenZeppelin ERC20
- Chainlink Aggregator Interface
- Hardhat / Foundry compatible structure
- DeFi token primitives

---

## 🚀 DeFi Concepts Implemented

- Wrapped asset design
- ERC20 token standard
- Oracle-based pricing
- Collateralized minting
- Token burning mechanics
- Price feed abstraction
- Smart contract modularity

---

## 🔐 Security Considerations

- Uses OpenZeppelin standard ERC20 implementation
- Solidity 0.8.x overflow protections
- Requires allowance for transferFrom
- Mint and burn logic depend on oracle pricing
- Price feeds should be validated in production

---

## 📈 Use Cases

- Stablecoin simulation
- Synthetic asset protocol
- Oracle-integrated token systems
- DeFi educational framework
- Collateralized token experiments

---

## ⚙️ Future Improvements

- Add liquidation mechanics
- Add collateral ratio enforcement
- Add multi-collateral support
- Integrate real Chainlink feeds
- Add access control roles
- Add unit tests

---

## 👨‍💻 Author

Sohail Ahmed  
Senior Blockchain Engineer | Solidity | DeFi Systems
