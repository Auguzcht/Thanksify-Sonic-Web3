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
- [Sonic CLI](https://docs.sonic.com/cli/installation) (if applicable)
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

> This local account will deploy your contracts, allowing you to avoid entering a personal private key.

![chall-0-yarn-generate](https://github.com/scaffold-eth/se-2-challenges/assets/2486142/133f5701-e575-4cc2-904f-cdc83ae86d94)

👩‍🚀 Use `yarn account` to view your deployer account balances.

![chall-0-yarn-account](https://github.com/scaffold-eth/se-2-challenges/assets/2486142/c34df8c9-9793-4a76-849b-170fae7fd0f0)

⛽️ You will need to send ETH to your deployer address with your wallet, or get it from a public faucet of your chosen network.

> Some popular Sepolia faucets are the [Alchemy Faucet](https://sepoliafaucet.com/), [Infura Faucet](https://www.infura.io/faucet/sepolia), and [Google Cloud Faucet](https://cloud.google.com/application/web3/faucet/ethereum/sepolia).

> ⚔️ Side Quest: Keep a 🧑‍🎤 [punkwallet.io](https://punkwallet.io) on your phone's home screen and keep it loaded with testnet eth. 🧙‍♂️ You'll look like a wizard when you can fund your deployer address from your phone in seconds.

🚀 Deploy your NFT smart contract with `yarn deploy`.

> 💬 Hint: You can set the `defaultNetwork` in `hardhat.config.ts` to `sepolia` **OR** you can `yarn deploy --network sepolia`.

---

## Checkpoint 4: 🚢 Ship your frontend! 🚁

> ✏️ Edit your frontend config in `packages/nextjs/scaffold.config.ts` to change the `targetNetwork` to `chains.sepolia` :

![chall-0-scaffold-config](https://github.com/scaffold-eth/se-2-challenges/assets/12072395/ff03bda0-66c6-4907-a9ad-bc8587da8036)

> You should see the correct network in the frontend (http://localhost:3000):

![image](https://github.com/scaffold-eth/se-2-challenges/assets/80153681/50eef1f7-e1a3-4b3b-87e2-59c19362c4ff)

> 🦊 Since we have deployed to a public testnet, you will now need to connect using a wallet you own or use a burner wallet. By default 🔥 `burner wallets` are only available on `hardhat` . You can enable them on every chain by setting `onlyLocalBurnerWallet: false` in your frontend config (`scaffold.config.ts` in `packages/nextjs/`).

![image](https://github.com/scaffold-eth/se-2-challenges/assets/80153681/f582d311-9b57-4503-8143-bac60346ea33)

> 💬 Hint: For faster loading of your transfer page, consider updating the `fromBlock` passed to `useScaffoldEventHistory` in `packages/nextjs/app/transfers/page.tsx` to `blocknumber - 10` at which your contract was deployed. Example: `fromBlock: 3750241n` (where `n` represents its a [BigInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt)). To find this blocknumber, search your contract's address on Etherscan and find the `Contract Creation` transaction line.

🚀 Deploy your NextJS App

```
yarn vercel
```

> You might need to log in to Vercel first by running `yarn vercel:login`. Once you log in (email, GitHub, etc), the default options should work.

> If you want to redeploy to the same production URL you can run `yarn vercel --prod`. If you omit the `--prod` flag it will deploy it to a preview/test URL.

> Follow the steps to deploy to Vercel. It'll give you a public URL.

⚠️ Run the automated testing function to make sure your app passes

```
yarn test
```

#### Configuration of Third-Party Services for Production-Grade Apps.

By default, 🏗 Scaffold-ETH 2 provides predefined API keys for popular services such as Alchemy and Etherscan. This allows you to begin developing and testing your applications more easily, avoiding the need to register for these services.
This is great to complete your **SpeedRunEthereum**.

For production-grade applications, it's recommended to obtain your own API keys (to prevent rate limiting issues). You can configure these at:

- 🔷 `ALCHEMY_API_KEY` variable in `packages/hardhat/.env` and `packages/nextjs/.env.local`. You can create API keys from the [Alchemy dashboard](https://dashboard.alchemy.com/).

- 📃 `ETHERSCAN_API_KEY` variable in `packages/hardhat/.env` with your generated API key. You can get your key [here](https://etherscan.io/myapikey).

> 💬 Hint: It's recommended to store env's for nextjs in Vercel/system env config for live apps and use .env.local for local testing.

---

## Checkpoint 5: 📜 Contract Verification

You can verify your smart contract on Etherscan by running (`yarn verify --network network_name`) :

```
yarn verify --network sepolia
```

> It is okay if it says your contract is already verified. Copy the address of YourCollectable.sol and search it on sepolia Etherscan to find the correct URL you need to submit this challenge.

## Checkpoint 6: 💪 Flex!

👩‍❤️‍👨 Share your public url with a friend and ask them for their address to send them a collectible :)

![gif](https://github.com/scaffold-eth/se-2-challenges/assets/80153681/547612f6-97b9-4eb3-ab6d-9b6d2c0ac769)

## ⚔️ Side Quests

### 🐟 Open Sea

> 🐃 Want to see your new NFTs on Opensea? Head to [Testnets Opensea](https://testnets.opensea.io/)

> 🎫 Make sure you have minted some NFTs on your Vercel page, then connect to Opensea using that same wallet.

![image](https://github.com/scaffold-eth/se-2-challenges/assets/80153681/c752b365-b801-4a02-ba2e-62e0270b3795)

> You can see your collection of shiny new NFTs on a testnet!

(It can take a while before they show up, but here is an example:) https://testnets.opensea.io/assets/sepolia/0x17ed03686653917efa2194a5252c5f0a4f3dc49c/2

---

> 🏃 Head to your next challenge [here](https://github.com/scaffold-eth/se-2-challenges).

> 💬 Problems, questions, comments on the stack? Post them to the [🏗 scaffold-eth developers chat](https://t.me/joinchat/F7nCRK3kI93PoCOk)

## Documentation

Visit our [docs](https://docs.scaffoldeth.io) to learn how to start building with Scaffold-ETH 2.

To know more about its features, check out our [website](https://scaffoldeth.io).

## Contributing to Scaffold-ETH 2

We welcome contributions to Scaffold-ETH 2!

Please see [CONTRIBUTING.MD](https://github.com/scaffold-eth/scaffold-eth-2/blob/main/CONTRIBUTING.md) for more information and guidelines for contributing to Scaffold-ETH 2.