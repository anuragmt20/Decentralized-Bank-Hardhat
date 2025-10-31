```markdown
# Decentralized Multi-Owner Bank

A decentralized multi-owner banking system built with Solidity and Hardhat. Users can create shared accounts, deposit Ether, request withdrawals, approve others' withdrawal requests, and withdraw funds only after enough approvals. It behaves like a simple on-chain multisig wallet.

## Features

- Create shared bank accounts, max 4 owners
- Each wallet can hold up to 3 accounts
- Deposit Ether into shared accounts
- Request withdrawals, requires co-owner approval
- Prevents self-approval
- Tracks approvals per withdrawal
- Withdraw executes only after required approvals
- Events emitted for deposits, requests, approvals, withdrawals
- View all accounts owned by a wallet

## How It Works

- Validates unique owners per account
- Only account owners can interact with that account
- Checks balance before withdrawal
- Uses `call` for safe transfers
- Clears pending withdrawal request after execution

## Stack

| Component  | Tool |
|-----------|------|
| Blockchain | Solidity |
| Local Dev | Hardhat |
| Frontend | HTML, CSS, JS |
| Wallet | MetaMask |
| Interaction | Ethers.js |

## Project Structure

```
/contracts
  BankAccount.sol
/scripts
  deploy.js
/test
  bank.test.js
/frontend
  index.html
  script.js
hardhat.config.js
README.md
```

## Setup

Install dependencies:

```bash
npm install
```

Compile contracts:

```bash
npx hardhat compile
```

Run tests:

```bash
npx hardhat test
```

Start local blockchain:

```bash
npx hardhat node
```

Deploy locally:

```bash
npx hardhat run scripts/deploy.js --network localhost
```

After deployment, copy the contract address into `frontend/script.js`.

## Frontend Usage

- Connect MetaMask
- Create a shared account by entering co-owner addresses
- View accounts owned by your wallet
- Use UI to call:
  - deposit
  - requestWithdraw
  - approveWithdraw
  - withdraw

## Notes

- Educational project, not audited
- Do not use on mainnet with real funds
- Strong portfolio example for:
  - Multisig logic
  - Secure Ether handling
  - Hardhat + test flow
  - Ethers.js frontend integration
```
