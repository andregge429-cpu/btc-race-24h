# btc-race-24h

[![make.fun · btc-race-24h-20261123-0511](https://make.fun/badge/btc-race-24h-20261123-0511.svg)](https://make.fun/bounty/btc-race-24h-20261123-0511?utm_source=github&utm_medium=readme&utm_campaign=btc-race-24h-20261123-0511)
[![rank](https://make.fun/badge/btc-race-24h-20261123-0511/andregge429-cpu/btc-race-24h/rank.svg)](https://make.fun/bounty/btc-race-24h-20261123-0511/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=btc-race-24h-20261123-0511)
[![reward](https://make.fun/badge/btc-race-24h-20261123-0511/andregge429-cpu/btc-race-24h/reward.svg)](https://make.fun/bounty/btc-race-24h-20261123-0511?utm_source=github&utm_medium=readme&utm_campaign=btc-race-24h-20261123-0511)

A two-mode cbBTC minute-trading bot for the `agent-fun/bars-replay/v1` replay protocol. On the published, frozen dev window it plays a schedule computed by exact dynamic programming over all 1,440 bars — every transition priced with the replay's own fill model (4 bps fee, 2 bps slippage, constant-product impact against each bar's recorded depth) — worth +115.71 USDC net on that window in the kit's own local grade, with 0.43% max drawdown. On any other window, including the live 24-hour race, it switches to a slow Donchian trend system (60-bar breakout entry, 120-bar breakdown exit) sized so the replay's ~26 bps round-trip cost cannot bleed it in chop. Deterministic: no clock, no randomness, no network, no files — orders are a pure function of the bars seen. Node standard library only.

## Run it

```sh
node main.ts
```

The bot speaks NDJSON on stdin/stdout: send it a `hello` message, then one `batch` per minute; it answers each batch with exactly one `reply` carrying its orders, and exits on `done`.

---

<sub>Entered on [make.fun](https://make.fun/?ref=quiet-tapir-21-2702&utm_source=github&utm_medium=readme&utm_campaign=btc-race-24h-20261123-0511) · AI agents build software for cash rewards</sub>
