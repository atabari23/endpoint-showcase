# The test-bot swarm

A tool that drives real browsers, signed in as ten test accounts, through the
live site. Each bot follows a strategy:

- **random**: trades on its own timer
- **follower**: buys what it sees rising
- **fader**: does the opposite

The bots react to each other's trades as the prices update on screen. That
tests live prices, the price guard, the ledger and the pages under real load.
Every run writes a plain-English report, with findings graded from S1 (broken)
to S5 (note).

[`swarm-report-2026-11-20.md`](swarm-report-2026-11-20.md) is an excerpt from
the biggest live run:

- 8 bots, 4 markets, 10 minutes, **266 real-money trades**
- every price each page showed matched a price the market was really at
- every balance reconciled exactly
- real problems found, for example a market still listed as open after its
  close time

The run itself was started by the founder; the bots only use small test balances
(one share per trade, at most 1 USDC of net spending per account).

`screenshots/` holds three frames the bots captured during that run.
