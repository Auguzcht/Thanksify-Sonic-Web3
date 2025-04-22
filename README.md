# 🪙 Thanksify

## A Web3 Experimental Platform Built on Sonic

![Sonic Platform](https://img.shields.io/badge/Platform-Sonic-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Experimental-orange)

Thanksify is a backend-focused Web3 testbed built on the Sonic platform, designed to explore token creation, minting mechanics, and smart contract development. This minimalist prototype serves as a powerful sandbox for deploying and interacting with blockchain technologies in a controlled environment.

## 🚀 Features

- **Token Creation & Minting** - Deploy your own tokens with custom parameters
- **Smart Contract Development** - Test and deploy various smart contract implementations
- **Web3 Experimentation** - Explore blockchain concepts in a focused environment
- **Contract Hot Reload** - Your code auto-adapts as you edit smart contracts
- **Testnet Deployment** - Easy deployment to Sonic testnet for real-world testing

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **Solidity** | Smart contract language for writing blockchain logic |
| **Hardhat** | Development environment for compiling, testing and deploying |
| **Sonic Platform** | High-performance execution layer for contract operations |
| **Ethers.js** | JavaScript library for interacting with Ethereum blockchain |
| **Node.js** | Runtime environment for executing deployment scripts |

## 🧪 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v16+)
- [Hardhat](https://hardhat.org/getting-started/)
- [MetaMask](https://metamask.io/) or another Web3 wallet

### Installation

1. Clone the repository:
   ```bash
   https://github.com/Auguzcht/Thanksify-Sonic-Web3.git
   cd thanksify
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

### Development Workflow

1. **Start your local blockchain network**:
   ```bash
   npm run chain
   ```

2. **Compile Contracts**:
   ```bash
   npx hardhat compile
   ```

3. **Deploy your contracts locally**:
   ```bash
   npm run deploy
   ```
   
4. **Run Tests**:
   ```bash
   npx hardhat test
   ```

5. **Mint Tokens**:
   Edit the `mint.js` script in `/scripts` to specify amount and recipient, then:
   ```bash
   npx hardhat run scripts/mint.js --network sonic
   ```

### Deploying to Testnet

1. **Configure your network**:
   Update `hardhat.config.js` with your preferred testnet settings

2. **Generate a deployer address** (optional):
   ```bash
   npm run generate
   ```
   This creates a unique deployer address and saves the mnemonic locally.

3. **Fund your deployer address**:
   Send testnet tokens to your deployer address using a faucet

4. **Deploy to the Sonic testnet**:
   ```bash
   npm run deploy --network sonic
   ```

5. **Verify your contract** (if applicable):
   ```bash
   npm run verify --network sonic
   ```

## 🔍 Debug and Testing

### Local Testing with Burner Wallets

For local development, you can use burner wallets to test your application:

1. Run your local chain and deploy contracts
2. Open a new incognito window to automatically generate a new burner wallet
3. Use the local faucet to fund the burner wallet
4. Test minting and transfers between different addresses

### Contract Verification

After deploying to a public testnet, verify your contract to allow others to interact with it:

```bash
npm run verify --network sonic
```

## 📚 Documentation

For more detailed information, check out these resources:
- [Sonic Platform Documentation](https://docs.sonic.com)
- [Hardhat Tutorials](https://hardhat.org/tutorial)
- [Solidity Documentation](https://docs.soliditylang.org/)

## 🔄 Contribution Guidelines

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## ⚠️ Important Notes

- This project is experimental and intended for educational purposes
- When deploying to production, obtain your own API keys for any third-party services
- For local testing, use burner wallets rather than connecting your primary wallets
- Always verify your contracts on the blockchain explorer after deployment

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙌 Acknowledgements

- **BitSkwela** – For empowering blockchain education and supporting local dev talent
- **Sonic** – For providing a blazing-fast platform for Web3 experimentation and deployment
- **Ethereum Community** – For continuous innovation in the Web3 space
- **Scaffold-ETH** – For inspiration on Web3 development patterns and practices
