# [Pro Yield](https://proyield.fi) — agent skills

[![skills.sh](https://skills.sh/b/ProYield-fi/skills)](https://skills.sh/ProYield-fi/skills)

Agent skills published by the **Pro Yield team**. Pro Yield runs a non-custodial,
code-capped USDC vault on HyperEVM (Hyperliquid's EVM) and publishes the read-only
data around it — venue rates, vault state, and daily share-price history — as a
public JSON API.

> The project's website is **[proyield.fi](https://proyield.fi)**; the API machine
> host is **pyd.fi**. Every endpoint and example below talks to `pyd.fi`, because
> that is where the JSON API lives.

These skills are free, read-only, and require no account or API key.

## Install

```bash
npx skills add ProYield-fi/skills
```

## Skills

| Skill | What it covers |
| --- | --- |
| [`proyield-yield-feed`](skills/proyield-yield-feed/SKILL.md) | Live stablecoin lending venue rates with provenance, vault state and code-enforced caps, daily share-price history, unsigned deposit/withdraw calldata, and a worked x402 pay flow ($0.005/call in USDC across eight settle-proven networks) |

## What the numbers are, and are not

Every figure these skills describe comes from a sourced, dated API response —
`as_of` records when the underlying data was measured, `generated_at` when the
response was built, and `venue_rates.source` names the upstream. Nothing is
simulated, and rates are **historical reads, not forecasts**.

The vault is a **guarded beta with code-enforced caps; no external audit is
complete.** Capacity limits are enforced in the contract and published live in the
API, and they rise with evidence.

Nothing here is financial advice. DeFi carries real risk, including contract
exploits and depegs. These skills fetch data and build unsigned transactions;
they never sign, never custody, and never hold keys.

## Verifying a claim

The API is public, so every statement in these skills can be checked directly:

```bash
curl -s https://pyd.fi/api/yield/strategies   # free: rates, vault state, caps, provenance
curl -s https://pyd.fi/api/agents             # free: index of the paid machine rail
curl -s https://pyd.fi/api/x402/stats         # free: aggregate settled-call tally
curl -s https://pyd.fi/llms.txt               # machine-readable surface map
```

## License

MIT — see [LICENSE](LICENSE).
