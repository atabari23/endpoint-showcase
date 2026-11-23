# Test-bot swarm report (excerpt)

Run of 20 November 2026 on the live site, with real money (1 share per trade). This is the report the bot wrote itself, unedited except: the site address is removed, and the long trade-by-trade timeline and change log are cut. `mills` = thousandths of a US dollar (USDC).

## Summary

8 bots (test1, test2, test3, test4, test5, test6, test7, test8) traded on the LIVE site  on 4 market(s) for 10.1 minutes (planned 10).

They made 266 trades, about 26.4 a minute (5 of them selling back at the end). Fewest by one bot: 28 (test6); most: 40 (test3).

Strategies: 2 random, 3 follower, 3 fader (test1 fader, test2 fader, test3 random, test4 follower, test5 follower, test6 follower, test7 random, test8 fader).

Reactions: 156 trades were made because a bot's page showed another trader's move (median 6.9 s from seeing the move to the trade's answer, worst 16.7 s); 0 seen moves were skipped. Longest chain: 15 trades.

The site's price guard refused 7 trade(s) because another trade moved the price first (nothing was placed; the bot re-priced and tried again). This is the site working as designed.

Net spending (buys minus sale proceeds): 0 mills in total; test1 -36, test2 -186, test3 -73, test4 249, test5 26, test6 273, test7 -29, test8 -224.

Shares bought in this run and still held at the end: 0.

Limits: 1 share a trade; a buy quoted at most 1000 mills; net spending at most 1000 mills per account and 8000 mills per run; at most 150 trades per account. Each bot waits at least about 10 s between its own trades; bots moved market every 120 s (seed 3145837003).

Findings: 2 broken (S2), 4 works, but slow or shaky (S3), 16 note (S5).

The run finished normally.

## Accounts

| Account | Balance start → end (mills) | Trades | Net spending (mills) | Shares still held | Checks passed / failed |
|---|---|---|---|---|---|
| test1 | 4976 → 5012 | 30 | -36 | none | 96 / 0 |
| test2 | 4975 → 5161 | 32 | -186 | none | 101 / 0 |
| test3 | 4952 → 5025 | 40 | -73 | none | 126 / 0 |
| test4 | 5072 → 4823 | 32 | 249 | none | 102 / 0 |
| test5 | 4049 → 4023 | 34 | 26 | none | 108 / 0 |
| test6 | 4974 → 4701 | 28 | 273 | none | 90 / 0 |
| test7 | 4976 → 5005 | 40 | -29 | none | 126 / 0 |
| test8 | 5026 → 5250 | 30 | -224 | none | 97 / 0 |

## Bots

What each bot did. A random bot trades on its own timer; a follower buys what it sees rising (selling the other side first if it holds it); a fader does the opposite. Money only moves between the bots and the market maker, so one bot's gain is not another's loss. Net result: gained = it got back more than it paid.

| Bot | Strategy | Trades | Buys / sells | Reactions made | Others reacted to it | Price-guard refusals | Net result (mills) |
|---|---|---|---|---|---|---|---|
| test1 | fader | 30 | 15 / 15 | 23 | 5 | 0 | gained 36 |
| test2 | fader | 32 | 16 / 16 | 27 | 14 | 0 | gained 186 |
| test3 | random | 40 | 20 / 20 | 0 | 31 | 0 | gained 73 |
| test4 | follower | 32 | 16 / 16 | 30 | 15 | 2 | lost 249 |
| test5 | follower | 34 | 17 / 17 | 30 | 21 | 2 | lost 26 |
| test6 | follower | 28 | 14 / 14 | 23 | 17 | 1 | lost 273 |
| test7 | random | 40 | 20 / 20 | 0 | 34 | 1 | gained 29 |
| test8 | fader | 30 | 15 / 15 | 23 | 19 | 1 | gained 224 |

## Reactions

A reaction is a trade a follower or fader made because its page showed a price rise. 156 reactions were made; 0 seen moves were skipped (a limit left nothing allowed to do), 0 ended refused by the price guard after the retries, 0 failed. Delay from "the page showed the move" to "the reaction trade answered": median 6.9 s, worst 16.7 s (it includes each bot's wait of at least 10 s after its own last trade). 0 reacted to a move no swarm trade explains (on the live site, a real person). Rows: the bot that reacted; columns: whose trade it reacted to.

| Reacting bot | test1 | test2 | test3 | test4 | test5 | test6 | test7 | test8 |
|---|---|---|---|---|---|---|---|---|
| test1 | 0 | 0 | 6 | 0 | 0 | 0 | 13 | 4 |
| test2 | 0 | 0 | 5 | 0 | 5 | 6 | 7 | 4 |
| test4 | 1 | 0 | 6 | 0 | 6 | 4 | 7 | 6 |
| test5 | 0 | 6 | 7 | 6 | 0 | 7 | 0 | 4 |
| test6 | 0 | 4 | 0 | 5 | 6 | 0 | 7 | 1 |
| test8 | 4 | 4 | 7 | 4 | 4 | 0 | 0 | 0 |

The longest chain has 15 trades on will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff:

1. test8 (fader) sold 1 YES for 512 mills at 18:38:18.8 (trade 374; YES 52.5% → 50.0%).

2. At 18:38:17.5 test6's page showed NO 47.5¢ → 50.0¢ (test8's sell of YES); 11.3 s later test6 (follower) bought 1 NO for 537 mills at 18:38:28.8 (trade 378; NO 52.5% → 55.0%).

3. At 18:38:27.5 test5's page showed NO 52.5¢ → 55.0¢ (test6's buy of NO); 9.4 s later test5 (follower) sold 1 NO for 537 mills at 18:38:36.9 (trade 383; NO 55.0% → 52.5%).

4. At 18:38:35.5 test6's page showed YES 45.0¢ → 47.5¢ (test5's sell of NO); 6.7 s later test6 (follower) sold 1 NO for 512 mills at 18:38:42.2 (trade 385; NO 52.5% → 50.0%).

5. At 18:38:42.0 test5's page showed YES 47.5¢ → 50.0¢ (test6's sell of NO); 9.7 s later test5 (follower) bought 1 YES for 512 mills at 18:38:51.7 (trade 389; YES 50.0% → 52.5%).

6. At 18:38:50.1 test6's page showed YES 50.0¢ → 52.5¢ (test5's buy of YES); 6.6 s later test6 (follower) bought 1 YES for 537 mills at 18:38:56.7 (trade 393; YES 52.5% → 55.0%).

7. At 18:38:55.1 test5's page showed YES 52.5¢ → 55.0¢ (test6's buy of YES); 10.1 s later test5 (follower) sold 1 YES for 537 mills at 18:39:05.1 (trade 400; YES 55.0% → 52.5%).

8. At 18:39:05.1 test6's page showed NO 45.0¢ → 47.5¢ (test5's sell of YES); 7.1 s later test6 (follower) sold 1 YES for 512 mills at 18:39:12.2 (trade 405; YES 52.5% → 50.0%).

9. At 18:39:12.1 test5's page showed NO 47.5¢ → 50.0¢ (test6's sell of YES); 7.2 s later test5 (follower) bought 1 NO for 512 mills at 18:39:19.4 (trade 409; NO 50.0% → 52.5%).

10. At 18:39:19.1 test6's page showed NO 50.0¢ → 52.5¢ (test5's buy of NO); 8.7 s later test6 (follower) bought 1 NO for 537 mills at 18:39:27.8 (trade 414; NO 52.5% → 55.0%).

11. At 18:39:27.7 test5's page showed NO 52.5¢ → 55.0¢ (test6's buy of NO); 7.6 s later test5 (follower) sold 1 NO for 537 mills at 18:39:35.3 (trade 419; NO 55.0% → 52.5%).

12. At 18:39:35.2 test6's page showed YES 45.0¢ → 47.5¢ (test5's sell of NO); 6.0 s later test6 (follower) sold 1 NO for 512 mills at 18:39:41.2 (trade 421; NO 52.5% → 50.0%).

13. At 18:39:41.2 test5's page showed YES 47.5¢ → 50.0¢ (test6's sell of NO); 8.5 s later test5 (follower) bought 1 YES for 512 mills at 18:39:49.7 (trade 427; YES 50.0% → 52.5%).

14. At 18:39:49.7 test6's page showed YES 50.0¢ → 52.5¢ (test5's buy of YES); 4.8 s later test6 (follower) bought 1 YES for 537 mills at 18:39:54.5 (trade 431; YES 52.5% → 55.0%).

15. At 18:39:54.2 test5's page showed YES 52.5¢ → 55.0¢ (test6's buy of YES); 8.7 s later test5 (follower) sold 1 YES for 537 mills at 18:40:03.0 (trade 435; YES 55.0% → 52.5%).

## By strategy

Average price paid is what a buy cost on average; average received is what a sale paid on average (mills for one share).

| Strategy | Bots | Trades | Share of all trades | Net result (mills) | Average paid / received (mills) |
|---|---|---|---|---|---|
| random | 2 | 80 | 30% | gained 102 | 511 / 513 |
| follower | 3 | 94 | 35% | lost 548 | 528 / 516 |
| fader | 3 | 92 | 35% | gained 446 | 504 / 514 |

## Price-guard refusals

When another trade moves the price between a bot's quote and its trade, the site refuses the trade (422 SLIPPAGE\_EXCEEDED) and places nothing. That is the site working as designed, so each market gets one note with the count, not a finding per refusal. The bot then re-prices and tries again (a sell up to 3 tries, a buy up to 2). 7 in all.

| Market | Refusals | By account |
|---|---|---|
| will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr | 1 | test5 1 |
| will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff | 4 | test4 1, test6 1, test7 1, test8 1 |
| will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t | 1 | test4 1 |
| will-j-j-bms-report-that-the-phase-3-librexia-af-trial-met-its-primary-efficacy | 1 | test5 1 |

## Markets

| Market | Trades | Price start → end | Highest / lowest during the run | Biggest one-trade move | Bots that visited | Most trades in 10 min | Burst flag expected |
|---|---|---|---|---|---|---|---|
| will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr | 64 | YES 50.0% → 50.0%; NO 50.0% → 50.0% | YES 55.0% / 45.0%; NO 55.0% / 45.0% | 2.5 points (test3's buy of NO, trade 130) | test2, test3, test4, test5, test6, test8 | 64 | yes |
| will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff | 60 | YES 50.0% → 50.0%; NO 50.0% → 50.0% | YES 55.0% / 45.0%; NO 55.0% / 45.0% | 2.5 points (test1's buy of YES, trade 137) | test1, test4, test5, test6, test7, test8 | 60 | yes |
| will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t | 72 | YES 50.0% → 50.0%; NO 50.0% → 50.0% | YES 57.4% / 45.0%; NO 55.0% / 42.6% | 2.5 points (test8's buy of YES, trade 138) | test1, test3, test4, test6, test7, test8 | 72 | yes |
| will-j-j-bms-report-that-the-phase-3-librexia-af-trial-met-its-primary-efficacy | 70 | YES 50.0% → 50.0%; NO 50.0% → 50.0% | YES 52.5% / 47.5%; NO 52.5% / 47.5% | 1.2 points (test7's buy of NO, trade 129) | test1, test2, test3, test5, test7, test8 | 70 | yes |

## Who saw what

For each trade, each other bot on that market's page: seen (and how long after the trade's answer), superseded (another trade on the market answered first, and this page had not shown the price 2 s after it), too small to see (the shown price did not change), or missed (not seen within 10 s). In all: 248 seen, 1 superseded, 0 too small to see, 1 missed; median lag 0.0 s, worst 0.1 s.

| Market | Seen | Superseded | Too small to see | Missed | Median lag | Worst lag |
|---|---|---|---|---|---|---|
| will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr | 61 | 0 | 0 | 0 | 0.0 s | 0.1 s |
| will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff | 54 | 1 | 0 | 0 | 0.0 s | 0.1 s |
| will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t | 67 | 0 | 0 | 0 | 0.0 s | 0.1 s |
| will-j-j-bms-report-that-the-phase-3-librexia-af-trial-met-its-primary-efficacy | 66 | 0 | 0 | 1 | 0.0 s | 0.1 s |

## Prices each page showed

Every price each page showed (2222 samples, 1090 stretches of one price on one page) checked against the prices the market really went through (its opening prices, then each swarm trade's answer). OK: a price that was current then (a page may lag 2 s). Stale: a real price still shown more than 3 s after a newer one existed. Went back: the page showed an older price after already showing a newer one, with no trade causing it. Phantom: a price the market was never at during the run (on the live site: someone else may have traded). Rounded twice: an ok price shown 0.1 off because the page's last update came from the prices route, which rounds to 4 decimals first (247,475 ppm shows as 24.8%, not 24.7%). In all: 1090 ok (0 of them rounded twice), 0 stale, 0 went back, 0 phantom, 0 someone else.

| Market | Samples | Stretches | OK | Rounded twice | Stale | Went back | Unmatched (someone else) | Worst stale |
|---|---|---|---|---|---|---|---|---|
| will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t | 564 | 292 | 292 | 0 | 0 | 0 | 0 | — |
| will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr | 576 | 266 | 266 | 0 | 0 | 0 | 0 | — |
| will-j-j-bms-report-that-the-phase-3-librexia-af-trial-met-its-primary-efficacy | 564 | 286 | 286 | 0 | 0 | 0 | 0 | — |
| will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff | 518 | 246 | 246 | 0 | 0 | 0 | 0 | — |

Every price every page showed was one the market was really at, shown on time.


## Findings

### S2: Broken

- **The page did not load** (test6; /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff (step: arrive)). Expected: The page loads within 30 seconds. What happened: /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff did not load.
- **A bot step stopped with an error** (test6; /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff (step: crash)). Expected: Each bot step finishes or logs what it could not do. What happened: test6: PlayStop: The page did not load

### S3: Works, but slow or shaky

- **A market is listed as open after its close time** (test1; /markets/will-bristol-myers-squibb-report-that-sotyktu-deucravacitinib-beat-placebo-on-sr (step: market-past-close will-bristol-myers-squibb-report-that-sotyktu-deucravacitini)). Expected: A market stops being listed as open once its close time has passed. What happened: will-bristol-myers-squibb-report-that-sotyktu-deucravacitinib-beat-placebo-on-sr closed for trading at 2026-11-15T23:59:00.000Z but its status is still "open". The site refuses trades on it (MARKET\_NOT\_OPEN); the bot skipped it. (seen in 6 runs since 2026-11-20)
- **The price moved between quote and trade** (test2; \[b64\] (step: check-response)). Expected: The trade's proceeds equals the quote the bot read. What happened: The quote was 494 mills; the trade's proceeds was 506 mills (within the 1% guard). (seen in 2 runs since 2026-11-20)
- **The price moved between quote and trade** (test8; /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff (step: check-response)). Expected: The trade's cost equals the quote the bot read. What happened: The quote was 512 mills; the trade's cost was 488 mills (within the 1% guard).
- **A bot did not see another bot's trade move the price** (test1,test2,test3,test4,test5,test6,test7,test8; \[b64\] (step: who-saw-what:\[b64\])). Expected: Every bot on \[b64\] shows a new price within 10 s of another bot's trade. What happened: On \[b64\]: 1 missed, 66 seen, 0 superseded, 0 too small to see.

### S5: Note

- **A request to another site failed** (test1; (other site) (step: network)). Expected: Every request the page makes succeeds. What happened: GET /logo-api/overview failed (net::ERR\_BLOCKED\_BY\_ORB) on page /markets. (code net::ERR\_BLOCKED\_BY\_ORB, seen 5 times this run, seen in 7 runs since 2026-11-20)
- **The page logged a warning** (test1; /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff (step: console)). Expected: No errors or warnings in the browser console. What happened: The width(-1) and height(-1) of chart should be greater than 0, (seen 24 times this run, seen in 4 runs since 2026-11-20)
- **A request to another site failed** (test1; (other site) (step: network)). Expected: Every request the page makes succeeds. What happened: GET /logo-api/overview failed (net::ERR\_BLOCKED\_BY\_ORB) on page /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff. (code net::ERR\_BLOCKED\_BY\_ORB, seen 31 times this run, seen in 7 runs since 2026-11-20)
- **The page logged a warning** (test7; \[b64\] (step: console)). Expected: No errors or warnings in the browser console. What happened: The width(-1) and height(-1) of chart should be greater than 0, (seen 7 times this run, seen in 4 runs since 2026-11-20)
- **Another bot traded between this bot's quote and its trade** (test3; /markets/will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr (step: check-response)). Expected: With several bots on one market a trade can fill a mill or two off its quote, inside the ticket's 1% guard. What happened: The quote was 512 mills; the trade's proceeds was 537 mills (within the 1% guard). (seen 2 times this run, seen in 2 runs since 2026-11-20)
- **A request to the site failed** (test3; /api/me/balance (step: network)). Expected: Every request the page makes succeeds. What happened: GET /api/me/balance failed (net::ERR\_ABORTED) on page /markets/will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t. (code net::ERR\_ABORTED, seen 2 times this run)
- **A request to the site failed** (test6; /api/markets/:slug/stats (step: network)). Expected: Every request the page makes succeeds. What happened: GET /api/markets/:slug/stats failed (net::ERR\_ABORTED) on page /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff. (code net::ERR\_ABORTED, seen in 2 runs since 2026-11-20)
- **A request to the site failed** (test6; /api/markets/:slug/history (step: network)). Expected: Every request the page makes succeeds. What happened: GET /api/markets/:slug/history failed (net::ERR\_ABORTED) on page /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff. (code net::ERR\_ABORTED, seen in 2 runs since 2026-11-20)
- **Expect a surveillance 'burst' flag for this market; it is review-only** (test1,test2,test3,test4,test5,test6,test7,test8; /markets/will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr (step: burst:will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr)). Expected: The surveillance rule flags a market with more than 20 trades in 10 minutes (server/services/surveillance/detectors.ts). What happened: will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr: up to 64 swarm trades inside 10 minutes. (seen in 2 runs since 2026-11-20)
- **Expect a surveillance 'burst' flag for this market; it is review-only** (test1,test2,test3,test4,test5,test6,test7,test8; /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff (step: burst:will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff)). Expected: The surveillance rule flags a market with more than 20 trades in 10 minutes (server/services/surveillance/detectors.ts). What happened: will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff: up to 60 swarm trades inside 10 minutes. (seen in 2 runs since 2026-11-20)
- **Expect a surveillance 'burst' flag for this market; it is review-only** (test1,test2,test3,test4,test5,test6,test7,test8; /markets/will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t (step: burst:will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t)). Expected: The surveillance rule flags a market with more than 20 trades in 10 minutes (server/services/surveillance/detectors.ts). What happened: will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t: up to 72 swarm trades inside 10 minutes. (seen in 2 runs since 2026-11-20)
- **Expect a surveillance 'burst' flag for this market; it is review-only** (test1,test2,test3,test4,test5,test6,test7,test8; \[b64\] (step: burst:\[b64\])). Expected: The surveillance rule flags a market with more than 20 trades in 10 minutes (server/services/surveillance/detectors.ts). What happened: \[b64\]: up to 70 swarm trades inside 10 minutes.
- **The site's price guard refused trades (expected with several traders)** (test1,test2,test3,test4,test5,test6,test7,test8; /markets/will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr (step: price-guard:will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr)). Expected: When another trade moves the price between a quote and a trade, the site refuses the trade (422 SLIPPAGE\_EXCEEDED) and places nothing. What happened: On will-exelixis-report-that-zanzalintinib-plus-nivolumab-significantly-improved-pr: the site's price guard refused 1 trade(s) because another trade moved the price first; nothing was placed; the bot re-priced and tried again.
- **The site's price guard refused trades (expected with several traders)** (test1,test2,test3,test4,test5,test6,test7,test8; /markets/will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff (step: price-guard:will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff)). Expected: When another trade moves the price between a quote and a trade, the site refuses the trade (422 SLIPPAGE\_EXCEEDED) and places nothing. What happened: On will-vir-biotechnology-report-that-tobevibart-plus-elebsiran-met-the-primary-eff: the site's price guard refused 4 trade(s) because another trade moved the price first; nothing was placed; the bot re-priced and tried again.
- **The site's price guard refused trades (expected with several traders)** (test1,test2,test3,test4,test5,test6,test7,test8; /markets/will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t (step: price-guard:will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t)). Expected: When another trade moves the price between a quote and a trade, the site refuses the trade (422 SLIPPAGE\_EXCEEDED) and places nothing. What happened: On will-eli-lilly-report-that-retatrutide-produced-significantly-more-weight-loss-t: the site's price guard refused 1 trade(s) because another trade moved the price first; nothing was placed; the bot re-priced and tried again.
- **The site's price guard refused trades (expected with several traders)** (test1,test2,test3,test4,test5,test6,test7,test8; \[b64\] (step: price-guard:\[b64\])). Expected: When another trade moves the price between a quote and a trade, the site refuses the trade (422 SLIPPAGE\_EXCEEDED) and places nothing. What happened: On \[b64\]: the site's price guard refused 1 trade(s) because another trade moved the price first; nothing was placed; the bot re-priced and tried again.

