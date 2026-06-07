# PSCD — live demo

A live, in-browser demo of [PSCD](https://github.com/ruzkypazzy/Pharos-Symbol-Collision-Detector-PSCD-).

**What it does:** checks whether a candidate ERC-20 token symbol is already taken on Pharos Pacific mainnet. Returns CLEAR, COLLISION, or EMPTY.

**How it works:** the page makes fresh JSON-RPC calls to `https://rpc.pharos.xyz` — no backend, no indexer, no caching. Every visit re-queries the chain.

**The flow:**
1. User types a symbol (or clicks a chip) → form pre-fills the "prompt"
2. Click "Check symbol" → a user bubble appears in the agent chat
3. Browser scans blocks via `eth_getLogs` (filtered to Transfer-from-zero events)
4. For each candidate contract, fetches `symbol()` / `name()` / `decimals()` in parallel
5. Agent replies with a CLEAR or COLLISION verdict, plus a "trading card" for each matching token

**Visual style:** *token trading card* — warm cream paper, italic Georgia headings, dashed gold borders, ribbon-stripe headers, a "FOUND ON CHAIN" wax-seal on each collision card. Distinct from the cyber/electric, terminal/hacker, and analytics-dashboard themes of the other demos in this campaign.

**Source:** https://github.com/ruzkypazzy/Pharos-Symbol-Collision-Detector-PSCD-
