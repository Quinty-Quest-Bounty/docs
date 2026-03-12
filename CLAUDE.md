# docs (Quinty Documentation)

Mintlify documentation site for Quinty — a decentralized bounty/quest platform on Base.

## Quick Start

```bash
npx mintlify dev     # Preview locally (port 3000)
npx mintlify broken-links  # Check for broken links
```

## Architecture

```
├── docs.json               # Mintlify nav config (tabs, groups, pages)
├── index.mdx               # Hero page
├── quickstart.mdx          # 5-min onboarding
├── essentials/              # Core concepts (why, how, architecture)
├── guides/                  # User guides (post bounty, submit, quest, withdraw)
├── smart-contracts/         # Contract docs (overview, bounty, quest, reputation, addresses)
├── agents/                  # Agent documentation (overview, quickstart, auth, API, ERC-8004, drafts)
├── api-reference/           # Backend API + Indexer GraphQL
├── development/             # Local setup + repo structure
├── images/                  # Asset folder
└── logo/                    # Logo assets
```

## Key Patterns

- **MDX format** with YAML frontmatter (`title`, `description`)
- **Active voice, second person** ("you")
- **Sentence case** for headings
- **Tables** for reference data, **Mermaid** for flow diagrams
- **Brand color**: `#0EA885` (emerald green)

## Navigation Tabs

1. Documentation — Getting Started, Essentials, Development
2. Smart Contracts — Contract docs and addresses
3. Agents — Agent overview, quickstart, auth, API, ERC-8004, drafts
4. Guides — User-facing how-tos
5. API Reference — Backend API, Indexer GraphQL

## Current Branch: `feat/agent-docs`

### Completed
- Full Agents section (6 pages): overview, quickstart, authentication, API reference, ERC-8004 identity, drafting bounties
- ERC-8004 registry addresses added to smart-contracts/addresses page
- docs.json updated with Agents tab
