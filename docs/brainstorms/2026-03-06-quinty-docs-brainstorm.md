# Brainstorm: Quinty Project Documentation

**Date:** 2026-03-06
**Status:** Complete

## What We're Building

Comprehensive documentation for the Quinty project across all repositories:

1. **Per-repo READMEs** (5 repos + docs) — Concise, explains each repo's role in Quinty
2. **Mintlify docs site** (`docs/`) — Full docs for three audiences: users, developers, evaluators
3. **Mermaid diagrams** — User flows, technical architecture, contract interactions

## Key Decisions

| Decision | Choice |
|----------|--------|
| Target audience | All three: user guide + developer reference + evaluator overview |
| Diagram tool | Mermaid (text-based, renders in Mintlify) |
| Language | English, plain for general, technical where needed |
| Version references | None — document current state only |
| Branch | `feat/quinty-docs` across all repos, PR to main |
| Source of truth | sc-quinty for contracts, addresses, ABIs |
| Domain | docs.quinty.io |
| Existing docs content | Overwrite completely, write from scratch |
| Landing README | Minimal (one paragraph + link to docs) |
| SC function docs | Overview + key functions (not full reference) |
| Social links | GitHub org + Twitter |
| "Why Quinty" angle | Natural — let the project context drive the narrative |

## Quinty System Architecture

```
User (Browser)
  |
  v
fe-quinty (Next.js 15 + React 19 + Privy auth)
  |-- Auth -----------> be-quinty (NestJS + Supabase)
  |-- Wagmi/Viem -----> Smart Contracts (Base Sepolia)
  |                       |-- Quinty.sol (Bounties + escrow)
  |                       |-- Quest.sol (Social quests)
  |                       |-- QuintyReputation.sol (Soulbound badges)
  |                       |-- QuintyNFT.sol (Achievement NFTs)
  |
indexer-quinty (Ponder) --> indexes events --> GraphQL API
landing-quinty (Vite + React) --> marketing site
```

### Smart Contracts (Base Sepolia, Chain ID: 84532)

| Contract | Address | Purpose |
|----------|---------|---------|
| Quinty | `0x034cf0b72BcB1b529a2B0458275E0307CD6b5459` | Multi-winner bounty with escrow |
| Quest | `0x86cc170e725784812A31F548c434e425bc0181B1` | Social quests with verifiers |
| QuintyReputation | `0x3Fc6d21B3AC4E419a2bEe6BeB40E00FfF2bF1014` | Soulbound reputation badges |
| QuintyNFT | `0x6fcd78D8BB923E20B3C657C65f64A20a4a6b9884` | Achievement NFTs |

### Repos

| Repo | Stack | Role |
|------|-------|------|
| sc-quinty | Solidity, Hardhat | Smart contracts, ABIs, deploy scripts |
| fe-quinty | Next.js 15, Wagmi, Privy | Frontend web app |
| be-quinty | NestJS, Supabase | Auth API, user profiles |
| indexer-quinty | Ponder, PostgreSQL | Blockchain event indexer, GraphQL |
| landing-quinty | Vite, React, GSAP | Marketing landing page |
| docs | Mintlify | Documentation site |

## Deliverables

### 1. Per-Repo READMEs

Each README: one-line desc, role in Quinty, tech stack, quick start, env vars, link to docs.
- sc-quinty: Full README (contracts, deploy, test)
- fe-quinty: Full README (pages, auth, contract integration)
- be-quinty: Full README (endpoints, auth flow)
- indexer-quinty: Full README (indexed events, schema)
- landing-quinty: Minimal (one paragraph + tech stack + run command)
- docs: How to run Mintlify locally

### 2. Mintlify Docs Structure

```
docs.json                      # Mintlify config (domain: docs.quinty.io)
index.mdx                     # Hero — what is Quinty
quickstart.mdx                # Get started in 5 minutes

essentials/
  why-quinty.mdx              # Problem + solution
  how-it-works.mdx            # User flow (Mermaid diagrams)
  architecture.mdx            # Technical architecture (Mermaid)

smart-contracts/
  overview.mdx                # Contract system overview
  quinty-bounties.mdx         # Bounty contract: lifecycle, key functions
  quest.mdx                   # Quest contract: lifecycle, key functions
  reputation.mdx              # Reputation + NFT system
  addresses.mdx               # Deployed addresses, chain info

guides/
  post-bounty.mdx             # How to post a bounty (user guide)
  submit-work.mdx             # How to submit to a bounty
  create-quest.mdx            # How to create a quest
  withdrawals.mdx             # How the pull-based withdrawal works

api-reference/
  backend-api.mdx             # be-quinty REST endpoints
  indexer-graphql.mdx          # Ponder GraphQL schema + queries

development/
  local-setup.mdx             # Running the full stack locally
  repo-structure.mdx          # All repos explained
```

### 3. Mermaid Diagrams

1. Bounty lifecycle flow (Open -> Judging -> Resolved / Slashed)
2. Quest lifecycle flow (Created -> Entries -> Verified -> Finalized)
3. System architecture (all repos + their connections)
4. Contract interaction diagram
5. Auth flow (Privy -> Backend -> JWT)
