# Crypto Staking Platform Database

## Project Overview
This project contains the schema design and SQL queries for a **Crypto Staking Platform**. The platform facilitates user registration, wallet management, staking packages, reward distributions, referral systems, and ledger management. It is designed with robust database triggers to automate key financial updates, such as income from staking and referral bonuses, ensuring efficient management of staking-related activities.

## Key Features
- **User Management:** The platform supports user registration with roles, status management, and referral tracking.
- **Wallet System:** Each user has a wallet that tracks various balances, including available funds, reserved balances, and income from multiple sources such as staking returns (ROI), referral bonuses, and reward incomes.
- **Staking Packages:** Users can purchase staking packages with predefined amounts and return-on-investment (ROI) rates. The platform supports managing multiple staking packages and automates ROI income tracking.
- **Referral System:** A referral system tracks both the referring and referred users, automatically updating referral bonuses.
- **Income Management:** The platform calculates and records ROI, level income, referral bonuses, and rewards directly into the user's wallet.
- **Rewards:** Users can earn rewards by achieving certain business targets. Reward distributions are tracked and recorded in both the user’s wallet and a reward ledger.
- **Ledger System:** Each financial transaction, including credit, debit, and balance updates, is recorded in a ledger for transparency and audit purposes.
- **Automated Triggers:** The platform uses MySQL triggers to automate wallet updates whenever income is generated from staking, referrals, or rewards.

## Database Design
The database includes the following key tables:

### 1. **User Table**
Stores user information including username, email, password, role, and referral details. Users can refer other users, and this referral hierarchy is captured in the system.

### 2. **Wallet Table**
Each user has an associated wallet to track balances for staking, referral income, rewards, and more. Triggers automatically update these balances.

### 3. **Packages Table**
Stores information about staking packages, including package name, amount, duration, and ROI rates.

### 4. **User Membership Table**
Tracks user subscriptions to staking packages and records key data such as package start dates, status, and ROI distribution dates.

### 5. **ROI Income Table**
Stores daily ROI income for users based on their active staking packages.

### 6. **User Referral Table**
Tracks the parent-child relationship for user referrals and logs referral income.

### 7. **Levels Table**
Defines levels in the platform, with each level associated with a certain point threshold.

### 8. **Level Income Table**
Stores information about income earned based on different levels, tracking the hierarchy of users and associated income.

### 9. **Rewards and User Reward Tables**
Stores information about platform rewards and tracks which users have received specific rewards.

### 10. **Ledger Table**
Records all transactions related to the wallet, including credits, debits, opening and closing balances, and income types.

## Triggers
The platform uses several MySQL triggers to automate processes:
- **After User Insert:** Automatically creates a wallet for a new user.
- **After ROI Income Insert:** Automatically updates the wallet with staking income.
- **After Referral Insert:** Automatically updates the wallet with referral income.
- **After Reward Insert:** Automatically updates the wallet with rewards earned.



