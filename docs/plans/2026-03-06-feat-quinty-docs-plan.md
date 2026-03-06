---
title: "feat: Comprehensive Quinty Documentation"
type: feat
status: completed
date: 2026-03-06
origin: docs/brainstorms/2026-03-06-quinty-docs-brainstorm.md
---

# feat: Comprehensive Quinty Documentation

## Overview

Write documentation for the entire Quinty project: per-repo READMEs across 6 repositories, a full Mintlify docs site with ~20 pages, and 5 Mermaid diagrams. Target audiences: end users, developers, and project evaluators. (see brainstorm: docs/brainstorms/2026-03-06-quinty-docs-brainstorm.md)

## Problem Statement

The Quinty project spans 6 repositories with no unified documentation. The existing `docs/` repo contains a Mintlify starter template with zero Quinty-specific content. Individual repo READMEs are either missing or outdated. There is no single place to understand what Quinty is, how it works, or how to develop on it.

## Proposed Solution

1. Create branch `feat/quinty-docs` in all 6 repos
2. Write concise READMEs for each repo
3. Overwrite the Mintlify docs site with Quinty-specific content organized into essentials, smart contracts, guides, API reference, and development sections
4. Embed Mermaid diagrams for visual understanding of flows and architecture
5. PR each repo to main

## Implementation Phases

### Phase 1: Branch Setup (all repos)

Create `feat/quinty-docs` branch in each repo:

- [x] `sc-quinty` — `git checkout -b feat/quinty-docs`
- [x] `fe-quinty` — `git checkout -b feat/quinty-docs`
- [x] `be-quinty` — `git checkout -b feat/quinty-docs`
- [x] `indexer-quinty` — `git checkout -b feat/quinty-docs`
- [x] `landing-quinty` — `git checkout -b feat/quinty-docs`
- [x] `docs` — `git checkout -b feat/quinty-docs`

### Phase 2: Per-Repo READMEs

Write README.md for each repo. Structure: one-line description, role in Quinty, tech stack, quick start, env vars, link to full docs.

#### 2a. `sc-quinty/README.md` (Full)
- [x] One-line: Smart contracts for the Quinty bounty and quest platform
- [x] Contract list: Quinty.sol, Quest.sol, QuintyReputation.sol, QuintyNFT.sol
- [x] Deployed addresses table (Base Sepolia)
- [x] Tech stack: Solidity 0.8.28, Hardhat, OpenZeppelin v5.4.0
- [x] Quick start: `npm install`, `npx hardhat compile`, `npx hardhat test`
- [x] Key scripts: deploy, export-abis, setup-contracts
- [x] Env vars: `PRIVATE_KEY`, `BASE_SEPOLIA_RPC_URL`, `BASESCAN_API_KEY`
- [x] Link to docs.quinty.io/smart-contracts

#### 2b. `fe-quinty/README.md` (Full)
- [x] One-line: Frontend web app for Quinty
- [x] Tech stack: Next.js 15, React 19, TypeScript, Wagmi, Privy, Tailwind + shadcn/ui
- [x] Pages: Dashboard, Bounties, Quests, Profile, Reputation, History
- [x] Quick start: `pnpm install`, `pnpm dev`
- [x] Env vars: `NEXT_PUBLIC_PRIVY_APP_ID`, `NEXT_PUBLIC_API_URL`, `NEXT_PUBLIC_TWITTER_CLIENT_ID`, Pinata keys
- [x] Link to docs.quinty.io

#### 2c. `be-quinty/README.md` (Full)
- [x] One-line: Authentication and user management API for Quinty
- [x] Tech stack: NestJS, TypeScript, Supabase, JWT
- [x] Endpoints table: /auth/sync-profile, /auth/me, /auth/profile, /users/wallet/:address, etc.
- [x] Quick start: `npm install`, `npm run start:dev` (port 3001)
- [x] Env vars: `SUPABASE_URL`, `SUPABASE_KEY`, `SUPABASE_SERVICE_ROLE_KEY`, `JWT_SECRET`, `TWITTER_CLIENT_ID/SECRET`
- [x] Link to docs.quinty.io/api-reference

#### 2d. `indexer-quinty/README.md` (Full)
- [x] One-line: Blockchain event indexer for Quinty smart contracts
- [x] Tech stack: Ponder, TypeScript, PostgreSQL
- [x] Indexed contracts: Quinty, Quest, QuintyReputation
- [x] Schema: Bounty, Submission, Quest, QuestEntry, User tables
- [x] Quick start: `pnpm install`, `pnpm dev`
- [x] Env vars: `DATABASE_URL`, `PONDER_RPC_URL_84532`
- [x] Link to docs.quinty.io/api-reference/indexer-graphql

#### 2e. `landing-quinty/README.md` (Minimal)
- [x] One paragraph: Marketing landing page for Quinty
- [x] Tech stack: Vite, React, TypeScript, Tailwind, GSAP
- [x] Quick start: `pnpm install`, `pnpm dev`
- [x] Link to docs.quinty.io

#### 2f. `docs/README.md`
- [x] One-line: Documentation site for Quinty (Mintlify)
- [x] Quick start: `npx mintlify dev`
- [x] How to contribute docs
- [x] Link to docs.quinty.io

### Phase 3: Mintlify Config + Hero Pages

Overwrite existing Mintlify starter content completely. (see brainstorm: key decision "Overwrite completely")

#### 3a. `docs.json` — Mintlify configuration
- [x] Name: Quinty
- [x] Domain: docs.quinty.io
- [x] Colors: teal/green (#0EA885 primary)
- [x] Logo: light + dark variants
- [x] Navigation structure matching brainstorm file tree
- [x] Tabs: Guides, Smart Contracts, API Reference
- [x] Social links: GitHub org + Twitter
- [x] Favicon

#### 3b. `index.mdx` — Hero page
- [x] What is Quinty (one paragraph)
- [x] Key features: escrow bounties, social quests, soulbound reputation
- [x] Quick links to get started, smart contracts, guides
- [x] "Built on Base" callout

#### 3c. `quickstart.mdx` — Get started in 5 minutes
- [x] Connect wallet (Privy)
- [x] Get test ETH from faucet
- [x] Post your first bounty or quest
- [x] Link to app: app.quinty.io

### Phase 4: Essentials Section

#### 4a. `essentials/why-quinty.mdx`
- [x] The problem: freelance/bounty platforms require trust in a middleman
- [x] The solution: smart contract escrow, on-chain reputation
- [x] Key differentiators: trustless, multi-winner, soulbound badges, Base L2

#### 4b. `essentials/how-it-works.mdx`
- [x] Bounty user flow with Mermaid diagram (Diagram 1)
- [x] Quest user flow with Mermaid diagram (Diagram 2)
- [x] Step-by-step for each flow in plain English

#### 4c. `essentials/architecture.mdx`
- [x] System architecture Mermaid diagram (Diagram 3)
- [x] What each component does (table)
- [x] How they connect
- [x] Contract interaction Mermaid diagram (Diagram 4)
- [x] Auth flow Mermaid diagram (Diagram 5)

### Phase 5: Smart Contracts Section

#### 5a. `smart-contracts/overview.mdx`
- [x] Four contracts and their purposes
- [x] How they interact (cross-reference to architecture diagram)
- [x] Security features: pausable, reentrancy guard, pull withdrawals, SafeERC20
- [x] Token support: ETH + whitelisted ERC-20 (USDC)

#### 5b. `smart-contracts/quinty-bounties.mdx`
- [x] Bounty lifecycle: OPEN -> JUDGING -> RESOLVED / SLASHED
- [x] Mermaid state diagram
- [x] Key functions: createBounty, submitToBounty, selectWinners, triggerSlash
- [x] Prize tiers (1-10 winners)
- [x] 1% submission deposit mechanic
- [x] Slash mechanism explained

#### 5c. `smart-contracts/quest.mdx`
- [x] Quest lifecycle: Active -> Verified -> Finalized / Cancelled
- [x] Key functions: createQuest, submitEntry, verifyEntry, finalizeQuest
- [x] Delegated verifiers
- [x] Fixed reward per qualifier

#### 5d. `smart-contracts/reputation.mdx`
- [x] Soulbound NFT system
- [x] Achievement milestones (Solver, Winner, Creator badges)
- [x] Monthly seasons and leaderboards
- [x] On-chain SVG generation
- [x] QuintyNFT badge types

#### 5e. `smart-contracts/addresses.mdx`
- [x] Contract addresses table (Base Sepolia)
- [x] Chain ID: 84532
- [x] RPC URL, block explorer, faucet links
- [x] USDC address
- [x] ABIs: link to sc-quinty/exported-abis/

### Phase 6: Guides Section (User-Facing)

#### 6a. `guides/post-bounty.mdx`
- [x] Step-by-step: connect wallet, fill form, set prizes, set deadlines, fund escrow
- [x] Tips: slash percentage, judging deadline
- [x] What happens after posting

#### 6b. `guides/submit-work.mdx`
- [x] Find a bounty, review requirements
- [x] Submit with IPFS proof + deposit
- [x] What happens during judging
- [x] Getting paid (pull withdrawal)

#### 6c. `guides/create-quest.mdx`
- [x] Create quest with fixed reward per qualifier
- [x] Add verifiers
- [x] Review and approve entries
- [x] Finalize quest

#### 6d. `guides/withdrawals.mdx`
- [x] Pull-based withdrawal explained
- [x] How to check pending balance
- [x] How to withdraw ETH or ERC-20
- [x] Why pull-based (security)

### Phase 7: API Reference Section

#### 7a. `api-reference/backend-api.mdx`
- [x] Base URL and auth (JWT)
- [x] Endpoints table with method, path, description, auth required
- [x] Key endpoints: sync-profile, me, profile update, wallet lookup
- [x] Twitter OAuth callback

#### 7b. `api-reference/indexer-graphql.mdx`
- [x] Ponder GraphQL endpoint
- [x] Schema: Bounty, Submission, Quest, QuestEntry, User
- [x] Example queries: list bounties, get user stats, filter by status
- [x] How the indexer works (event-driven)

### Phase 8: Development Section

#### 8a. `development/local-setup.mdx`
- [x] Prerequisites: Node.js, pnpm, PostgreSQL
- [x] Clone all repos
- [x] Environment variables for each repo
- [x] Start order: contracts -> indexer -> backend -> frontend
- [x] Test contracts: `npx hardhat test`

#### 8b. `development/repo-structure.mdx`
- [x] All 6 repos with description, stack, and key files
- [x] How data flows between repos
- [x] Where to find ABIs, addresses, types

### Phase 9: Mermaid Diagrams

All diagrams embedded inline in their respective .mdx files.

#### Diagram 1: Bounty Lifecycle (in how-it-works.mdx)
```
stateDiagram-v2
  [*] --> OPEN: Creator posts bounty + funds escrow
  OPEN --> JUDGING: Open deadline passes
  JUDGING --> RESOLVED: Creator selects winners
  JUDGING --> SLASHED: Creator misses judging deadline
  RESOLVED --> [*]: Winners withdraw prizes
  SLASHED --> [*]: Submitters receive slash compensation
```

#### Diagram 2: Quest Lifecycle (in how-it-works.mdx)
```
stateDiagram-v2
  [*] --> ACTIVE: Creator posts quest + funds escrow
  ACTIVE --> ACTIVE: Users submit entries
  ACTIVE --> VERIFIED: Creator/verifier approves entries
  ACTIVE --> FINALIZED: Deadline or max qualifiers reached
  ACTIVE --> CANCELLED: No approvals yet
  FINALIZED --> [*]: Unused escrow refunded
```

#### Diagram 3: System Architecture (in architecture.mdx)
```
graph TD
  User[User Browser] --> FE[fe-quinty<br/>Next.js 15]
  FE -->|Privy Auth| BE[be-quinty<br/>NestJS]
  FE -->|Wagmi/Viem| SC[Smart Contracts<br/>Base Sepolia]
  BE -->|Profiles| DB[(Supabase<br/>PostgreSQL)]
  SC --> Q[Quinty.sol]
  SC --> QU[Quest.sol]
  SC --> REP[QuintyReputation.sol]
  SC --> NFT[QuintyNFT.sol]
  SC -->|Events| IDX[indexer-quinty<br/>Ponder]
  IDX -->|GraphQL| IDXDB[(PostgreSQL)]
  Landing[landing-quinty<br/>Vite + React] -->|Links to| FE
```

#### Diagram 4: Contract Interactions (in architecture.mdx)
```
graph LR
  Q[Quinty.sol] -->|recordSubmission<br/>recordWin<br/>recordBountyCreation| REP[QuintyReputation.sol]
  QU[Quest.sol] -->|recordSubmission<br/>recordBountyCreation| REP
  Q -->|authorizeMinter| NFT[QuintyNFT.sol]
  REP -->|mint soulbound badges| REP
```

#### Diagram 5: Auth Flow (in architecture.mdx)
```
sequenceDiagram
  User->>Frontend: Login (email/Google/wallet)
  Frontend->>Privy: Authenticate
  Privy-->>Frontend: Privy token + user data
  Frontend->>Backend: POST /auth/sync-profile
  Backend->>Supabase: Upsert profile
  Backend-->>Frontend: JWT token
  Frontend->>Frontend: Store JWT, load profile
```

### Phase 10: Commit, Push, PR

- [x] Commit all changes in each repo on `feat/quinty-docs`
- [x] Push all branches
- [x] Create PR in each repo to `main`
- [x] PR titles: "docs: comprehensive Quinty documentation"

## File List

### Files to Create/Overwrite

| Repo | File | Action |
|------|------|--------|
| sc-quinty | `README.md` | Overwrite |
| fe-quinty | `README.md` | Overwrite |
| be-quinty | `README.md` | Overwrite |
| indexer-quinty | `README.md` | Overwrite |
| landing-quinty | `README.md` | Overwrite |
| docs | `README.md` | Overwrite |
| docs | `docs.json` | Overwrite |
| docs | `index.mdx` | Overwrite |
| docs | `quickstart.mdx` | Overwrite |
| docs | `essentials/why-quinty.mdx` | Create |
| docs | `essentials/how-it-works.mdx` | Create |
| docs | `essentials/architecture.mdx` | Create |
| docs | `smart-contracts/overview.mdx` | Create |
| docs | `smart-contracts/quinty-bounties.mdx` | Create |
| docs | `smart-contracts/quest.mdx` | Create |
| docs | `smart-contracts/reputation.mdx` | Create |
| docs | `smart-contracts/addresses.mdx` | Create |
| docs | `guides/post-bounty.mdx` | Create |
| docs | `guides/submit-work.mdx` | Create |
| docs | `guides/create-quest.mdx` | Create |
| docs | `guides/withdrawals.mdx` | Create |
| docs | `api-reference/backend-api.mdx` | Create |
| docs | `api-reference/indexer-graphql.mdx` | Create |
| docs | `development/local-setup.mdx` | Create |
| docs | `development/repo-structure.mdx` | Create |

### Files to Delete (old Mintlify starter content)

| Repo | File | Reason |
|------|------|--------|
| docs | `essentials/settings.mdx` | Mintlify template |
| docs | `essentials/navigation.mdx` | Mintlify template |
| docs | `essentials/markdown.mdx` | Mintlify template |
| docs | `essentials/code.mdx` | Mintlify template |
| docs | `essentials/images.mdx` | Mintlify template |
| docs | `essentials/reusable-snippets.mdx` | Mintlify template |
| docs | `ai-tools/` | Entire directory — Mintlify template |
| docs | `api-reference/introduction.mdx` | Mintlify template |
| docs | `api-reference/endpoint/*.mdx` | Mintlify template |
| docs | `api-reference/openapi.json` | Mintlify template |
| docs | `snippets/` | Mintlify template |

## Acceptance Criteria

- [x] All 6 repos have accurate READMEs on `feat/quinty-docs` branch
- [x] Mintlify docs site builds without errors (`npx mintlify dev`)
- [x] All 5 Mermaid diagrams render correctly
- [x] docs.json navigation matches the planned structure
- [x] No version numbers (V2/V3) referenced anywhere
- [x] Contract addresses match sc-quinty/exported-abis/constants.ts
- [x] All internal links between docs pages work
- [x] PRs created in all 6 repos

## Sources & References

### Origin

- **Brainstorm document:** [docs/brainstorms/2026-03-06-quinty-docs-brainstorm.md](docs/brainstorms/2026-03-06-quinty-docs-brainstorm.md)
  - Key decisions: all three audiences, Mermaid diagrams, overwrite existing docs, docs.quinty.io domain, minimal landing README

### Internal References

- Smart contract source of truth: `sc-quinty/contracts/`
- Contract addresses: `sc-quinty/exported-abis/constants.ts`
- Frontend pages: `fe-quinty/src/app/`
- Backend endpoints: `be-quinty/src/auth/auth.controller.ts`
- Indexer schema: `indexer-quinty/ponder.schema.ts`
- Existing Mintlify config: `docs/docs.json`

### External References

- Mintlify docs: https://mintlify.com/docs
- Mermaid syntax: https://mermaid.js.org/
- Base Sepolia explorer: https://sepolia-explorer.base.org
