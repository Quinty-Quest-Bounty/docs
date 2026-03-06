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
smart-contracts/             # Contract docs (Quinty, Quest, Reputation, NFT)
guides/                      # User guides (post bounty, submit work, quests, withdrawals)
api-reference/               # Backend REST API + Indexer GraphQL
development/                 # Local setup, repo structure
```

## Contributing

1. Create a branch from `main`
2. Edit or add `.mdx` files
3. Run `npx mintlify dev` to preview
4. Submit a PR

Pages are written in MDX. Navigation is configured in `docs.json`.
