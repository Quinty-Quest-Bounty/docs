# Quinty Documentation

Documentation site for the Quinty platform, built with [Mintlify](https://mintlify.com).

**Live:** [docs.quinty.io](https://docs.quinty.io)

## Local Development

```bash
npx mintlify dev
```

Opens at `http://localhost:3000`.

## Structure

```
index.mdx                    # Home page
quickstart.mdx               # Get started in 5 minutes
essentials/                  # Why Quinty, how it works, architecture
smart-contracts/             # Contract docs (Quinty, Quest, Reputation, NFT, addresses)
agents/                      # Agent docs (overview, quickstart, auth, API, ERC-8004, drafts)
guides/                      # User guides (post bounty, submit work, quests, withdrawals)
api-reference/               # Backend REST API + Indexer GraphQL
development/                 # Local setup, repo structure
```

## Navigation Tabs

1. **Documentation** — Getting Started, Essentials, Development
2. **Smart Contracts** — Contract overview, bounties, quests, reputation, addresses
3. **Agents** — Overview, Quick Start, Authentication, API Reference, ERC-8004, Drafting Bounties
4. **Guides** — Post bounty, submit work, create quest, withdrawals
5. **API Reference** — Backend API, Indexer GraphQL

## Contributing

1. Create a branch from `main`
2. Edit or add `.mdx` files
3. Run `npx mintlify dev` to preview
4. Check links: `npx mintlify broken-links`
5. Submit a PR

Pages are MDX with YAML frontmatter. Navigation is configured in `docs.json`.
