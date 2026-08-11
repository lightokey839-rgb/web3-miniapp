# Telegram Task Rewards 🚀

A full-stack **Web3 Telegram Mini App** that lets communities create tasks, reward users, manage referrals, review submissions, and track rewards from a powerful admin dashboard.

Built as a production-oriented monorepo with a React frontend and Fastify/Prisma backend.

## ✨ Features

### 👤 User Experience

* Complete Telegram-based authentication
* Task discovery and completion
* Reward points and transaction history
* Referral system with referral tracking
* User profile and connected accounts
* Solana wallet management
* SOL withdrawal request system
* Leaderboard
* Task reminders
* Responsive Web3-focused interface

### 🎯 Task System

Supports community growth campaigns including:

* Telegram channel/link tasks
* Official website tasks
* X (Twitter) account linking
* X-related task categories
* Referral tasks
* Automated website timer verification
* Manual task submission and review

### 🛡️ Admin Dashboard

Admins can manage the entire reward ecosystem:

* 📊 Dashboard
* 👥 User management
* 🎯 Task creation and management
* 📝 Submission review
* 🎁 Reward management
* 💰 Reward settings
* 🤝 Referral tracking
* 💸 Withdrawal management
* 🔐 Admin access management

### 💰 Rewards & Withdrawals

The platform includes a database-backed reward system with:

* User point balances
* Reward transactions
* Configurable reward settings
* SOL wallet addresses
* Withdrawal requests
* Withdrawal queue
* Processing/completion states
* Failed-withdrawal refunds
* Admin withdrawal review

> **Note:** SOL withdrawals currently use an admin-controlled payout workflow. Automated on-chain transaction broadcasting is not implemented yet.

## 🧱 Tech Stack

### Frontend

* React
* TypeScript
* Vite
* Tailwind CSS
* Telegram Mini App APIs

### Backend

* Node.js
* Fastify
* TypeScript
* Prisma ORM
* PostgreSQL
* Vitest

### Infrastructure

* Docker
* Docker Compose
* npm Workspaces

## 📁 Project Structure

```text
taskapp/
├── apps/
│   ├── web/
│   │   ├── src/
│   │   └── ...
│   │
│   └── server/
│       ├── prisma/
│       ├── src/
│       └── ...
│
├── DEPLOYMENT.md
├── PHASE7_REPORT.md
├── PHASE8_REPORT.md
├── PHASE9_REPORT.md
├── docker-compose.yml
├── package.json
└── README.md
```

## ⚙️ Getting Started

### Requirements

* Node.js
* PostgreSQL
* Git
* Telegram Bot
* Internet connection for Prisma setup

### Installation

Clone the repository:

```bash
git clone https://github.com/lightokey839-rgb/web3-taskapp-.git
cd web3-taskapp-
```

Install dependencies:

```bash
npm install
```

### Backend

Configure the environment variables using the example file:

```bash
cd apps/server
```

Create your environment file from:

```text
apps/server/.env.example
```

Then generate Prisma:

```bash
npm run db:generate
```

Run migrations:

```bash
npm run db:migrate
```

Optional seed:

```bash
npm run db:seed
```

Start the backend:

```bash
cd ../..
npm run dev:server
```

### Frontend

In another terminal:

```bash
cp apps/web/.env.example apps/web/.env
npm run dev:web
```

For additional configuration details, see:

* `apps/web/README.md`
* `apps/server/README.md`
* `DEPLOYMENT.md`

## 🔐 Admin Dashboard

Add your Telegram numeric user ID to:

```text
ADMIN_TELEGRAM_IDS
```

in the backend environment configuration.

After authentication, open:

```text
/#/admin
```

The admin dashboard provides access to users, tasks, referrals, rewards, submissions, and withdrawals.

## 🔄 Application Flow

```text
Telegram User
      │
      ▼
Telegram Mini App
      │
      ▼
React + TypeScript Frontend
      │
      ▼
Fastify API
      │
      ▼
Prisma ORM
      │
      ▼
PostgreSQL
      │
      ├── Users
      ├── Tasks
      ├── Rewards
      ├── Referrals
      ├── Wallets
      └── Withdrawals
```

## 🧪 Testing

The backend contains automated tests covering important business and security logic, including:

* Telegram authentication
* Referral codes
* Solana address validation
* PKCE
* Token encryption
* Task services
* Admin services

Frontend automated tests are not currently included.

## 🚧 Current Limitations

This project is actively developed. Some integrations are intentionally incomplete:

* SOL payouts currently require an admin to execute the transaction manually.
* X OAuth follows the implemented OAuth 2.0 PKCE flow but should be tested against a real X developer application before production use.
* X task actions currently use manual review rather than automated verification.
* The frontend does not currently have an automated test suite.

These limitations are documented rather than hidden so the repository accurately represents the current state of the project.

## 🗺️ Roadmap

* [x] Telegram authentication
* [x] Task management
* [x] Rewards system
* [x] Referral system
* [x] Admin dashboard
* [x] PostgreSQL + Prisma backend
* [x] Solana wallet support
* [x] SOL withdrawal queue
* [x] X OAuth 2.0 PKCE integration
* [x] Website task verification
* [ ] Automated Solana payouts
* [ ] Automated frontend testing
* [ ] Additional social platform integrations
* [ ] Production deployment

## 🎯 Use Cases

This platform can be adapted for:

* Web3 community growth
* Token launches
* Airdrop campaigns
* Telegram communities
* NFT projects
* Marketing campaigns
* Referral campaigns
* Community engagement programs

## 👨‍💻 Developer

Built by **Light**.

Focused on building Web3 websites, Telegram bots, Telegram Mini Apps, community tools, and reward systems.

GitHub:
https://github.com/lightokey839-rgb

## 📄 License

This project is currently provided as a portfolio project. Add an appropriate open-source license before distributing the code for public reuse.
