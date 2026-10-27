# Testing data

There are no files to download. All data is synthetic and already loaded on the deployed app: 10,000 customers of a
fictional Indian marketplace, 5 categories, 200 products and 12 months of history up to 1 Dec 2026.

Press **Reset** on the live engine view before you start. Everyone shares one world, so if a scenario shows FAIL,
press Reset again.

| Try | Where | What you should see |
|---|---|---|
| A Sure Thing gets No Offer | https://offers.uselattice.app, Saving margin | Agent stage: `claude-opus-5-5 chose No Offer`, with its reason. The blue panel: Sure Thing, 48.2% chance of buying with no offer. |
| A Customer a discount moves gets one | same, Saving margin | Offer: 7.0% off fashion, up to ₹100. Valuation: that option is best, worth ₹10. |
| Three Not nows pause Offers | same, Hard limits | Checks: stopped by the Fatigue Pause, paused until 11 Dec. |
| Validation rejects a rule-breaking proposal | same, Safety net | Validation failed: `pct=40 > 25 (margin_floor_pct)`. The Fallback's offer goes out instead. |
| The Caption Check blocks invented urgency | same, Safety net | The caption "Hurry, 30% off tonight only!" fails on the number, the deadline and the urgency. |
| A Rule change flips a Decision | same, Marketer controls | After about 60 s: the same customer's offer drops from 7% to 5% off fashion. |
| `/start`, then `/offers` | Telegram, @apkartbot | Customer buttons, then an Offer Card with Claim, Not now and Stop. Cards go out between 09:00 and 21:00 simulated time; if nothing comes, press +1 hour on https://offers-console.uselattice.app until it is 09:00. |

To rebuild the same world locally: `uv run offer-engine generate --customers 10000 --seed 7`, then
`uv run offer-engine lift fit`.
