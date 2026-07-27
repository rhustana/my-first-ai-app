# Stock alert signals

Driven by a Claude Code Routine that checks prices hourly during market hours (weekdays, ~7:30am-1:30pm MT) and pushes a phone notification only on a *new* threshold crossing.

- `watchlist.json` — ticker to alert threshold (% move vs. previous close). Edit this to add/remove tickers or tune thresholds.
- `state.json` — one of `"up"`, `"down"`, or `null` per ticker. `null` means the ticker is currently within its normal range. The Routine only notifies when a ticker's state changes from `null` to `"up"`/`"down"`, or flips direction. It resets to `null` once the move falls back under the threshold, so the next crossing counts as new again.

Signals are mechanical (price move vs. a threshold you set) — not investment advice.
