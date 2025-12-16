# OrbitSignal

Built for Base

OrbitSignal is a minimal, Base-focused repository intended to validate wallet connectivity, RPC reliability, and basic onchain read operations using official Coinbase tooling.

The project is deliberately simple and reusable, serving as a lightweight signal check for Base-compatible infrastructure rather than a feature-heavy decentralized application.

---

## Why This Repository Exists

OrbitSignal is designed to:
- Confirm Base network accessibility through public RPC endpoints
- Validate wallet onboarding flows via OnchainKit
- Execute deterministic, read-only onchain queries
- Provide clear and reproducible Basescan references on testnet

This makes the repository suitable for repeated validation during development or tooling integration.

---

## Supported Networks

Base Sepolia (testnet)  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Base Mainnet (reference only)  
chainId (decimal): 8453  
Explorer: https://basescan.org  

---

## Application Overview

Primary file: `app/orbitSignal.ts`

At runtime, the application:
- Initializes an OnchainKit provider scoped to the selected Base network
- Renders wallet connection UX using OnchainKit Wallet
- Creates a Viem public client for Base JSON-RPC calls
- Reads:
  - RPC-reported chainId
  - latest block number
  - native ETH balance for a supplied address
- Surfaces explorer URLs for manual inspection

---

## Project Structure

- app/
  - orbitSignal.ts  
    React entry component combining wallet UX with Base read-only RPC calls.

Common supporting files:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env (optional)

---

## Libraries Used

OnchainKit  
Wallet UI components and Base-first primitives  
https://github.com/coinbase/onchainkit  

Viem  
EVM client library for Base JSON-RPC reads  

---

## Installation & Execution

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run the project using a standard React/Vite or Next.js development setup.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

---

## Usage Notes

- Base Sepolia is recommended for validation and testing
- Public RPC endpoints are rate-limited and intended for development use
- Wallet network selection should align with the chosen Base network

---

## License

MIT License

---

## Author

GitHub: https://github.com/yeastybunks 
Public contact (email): yeasty_bunks02@icloud.com  
Public contact (X): https://x.com/slavakydravcev2

---

## Testnet Deployment (Base Sepolia)

**Network:** Base Sepolia  
**chainId (decimal):** 84532  
**Explorer:** https://sepolia.basescan.org  

**Deployed contract #1 address:**  
0x8d6a26697f1a21b1e37f0484b8a0134bbaec8f63

**Deployed contract #2 address:**  
0xebd84d5a7260fc4e366f9d8c3c481dc0e725f2d3

**Basescan deployment and verification links:**  
- Contract #1 address:  
  https://sepolia.basescan.org/address/0x8d6a26697f1a21b1e37f0484b8a0134bbaec8f63
- Contract #2 address:  
  https://sepolia.basescan.org/address/0xebd84d5a7260fc4e366f9d8c3c481dc0e725f2d3
- Contract #1 verification (source code):  
  https://sepolia.basescan.org/0x8d6a26697f1a21b1e37f0484b8a0134bbaec8f63/0#code  
- Contract #2 verification (source code):  
  https://sepolia.basescan.org/0xebd84d5a7260fc4e366f9d8c3c481dc0e725f2d3/0#code  

This deployment is used to validate Base-compatible tooling, account abstraction flows, and onchain read operations in a test environment prior to mainnet usage.

