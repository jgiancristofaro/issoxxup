# issoxxup

A simple dark-themed web app that answers "Is SOXX up today?" with a giant smiley or frowny face.

## Stack

Single static `index.html` — no build step, no dependencies.

## Data Source

Yahoo Finance v8 chart API via [corsproxy.io](https://corsproxy.io):
```
https://query1.finance.yahoo.com/v8/finance/chart/SOXX?interval=5m&range=1d&includePrePost=true
```
- `regularMarketPrice` vs `chartPreviousClose` for the main up/down determination
- Post-market price is extracted from the `timestamps`/`indicators.quote[0].close` arrays using `currentTradingPeriod.post.start` as the cutoff
- After-hours row auto-hides during regular trading hours

## Deployment

- **Repo:** https://github.com/jgiancristofaro/issoxxup
- **Live:** https://jgiancristofaro.github.io/issoxxup/
- Hosted on GitHub Pages from the `master` branch root
- Push to `master` to deploy

## Workflow

- Work locally in `dev` branch, preview by opening `index.html` directly in browser
- Merge to `master` and push when ready to deploy
