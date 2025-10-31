
# Decentralized Bank

A decentralized multi-owner banking system built with Solidity and Hardhat. Users can create shared accounts, deposit Ether, request withdrawals, approve withdrawal requests, and withdraw only after enough approvals.

## Features

- Create shared bank accounts, max 4 owners
- Each wallet can hold up to 3 accounts
- Deposit Ether into shared accounts
- Request withdrawals, requires co-owner approval
- Prevent self-approval
- Track approvals per withdrawal
- Withdraw only after approval threshold
- Emits events for all actions
- View accounts owned by a wallet

## How It Works

- Validates unique owners per account
- Only owners can interact with an account
- Checks balance before withdrawal
- Uses `call` for secure transfers
- Clears pending request after execution

## Stack

| Component | Tool |
|---------|------|
| Blockchain | Solidity |
| Dev Env | Hardhat |
| Frontend | HTML, CSS, JS |
| Wallet | MetaMask |
| Interaction | Ethers.js |

## Project Structure

```text
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

Install:

```bash
npm install
```

Compile:

```bash
npx hardhat compile
```

Test:

```bash
npx hardhat test
```

Local blockchain:

```bash
npx hardhat node
```

Deploy:

```bash
npx hardhat run scripts/deploy.js --network localhost
```

Paste deployed address into:

```text
frontend/script.js
```

## Frontend Usage

- Connect MetaMask
- Create shared account with co-owners
- See accounts you own
- Use functions:
  - `deposit`
  - `withdraw`

## Notes

- Educational only, not audited
- Do not use with real funds
- Demonstrates multisig logic, secure Ether handling, Hardhat workflow, Ethers.js integration
