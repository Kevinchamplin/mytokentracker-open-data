<h1 align="center">MyTokenTracker — Open Data</h1>

<p align="center">
  <strong>Free, citable data on what AI costs.</strong><br>
  The daily AI Cost Index, anonymized community usage, and the full model price catalog.
</p>

<p align="center">
  <img alt="License" src="https://img.shields.io/badge/data-CC%20BY%204.0-0D9488">
  <img alt="Updated" src="https://img.shields.io/badge/updated-daily-0D9488">
  <a href="https://mytokentracker.io/state-of-ai"><img alt="State of AI" src="https://img.shields.io/badge/the%20State%20of%20AI-1A1A17"></a>
</p>

---

This repository mirrors the open datasets behind [mytokentracker.io](https://mytokentracker.io),
refreshed **every day** by a GitHub Action that pulls the public
[Data API](https://mytokentracker.io/api/v1/data). Everything here is free to use, share,
and cite under **CC BY 4.0** — just link back so others can find it.

## Datasets (`/data`)

| File | What it is |
|------|------------|
| [`cost-index.json`](data/cost-index.json) · [`.csv`](data/cost-index.csv) | **AI Cost Index** — blended price per million tokens (3:1 input:output) for fixed Frontier and Budget baskets, over time. The S&P 500 of AI prices. |
| [`community.json`](data/community.json) · [`.csv`](data/community.csv) | **Community usage** — anonymized daily aggregate of spend, tokens, and outcomes by provider, model, platform, and use-case. k-anonymity gated. |
| [`models.json`](data/models.json) · [`.csv`](data/models.csv) | **Model price catalog** — current per-million-token prices (input, output, cache, reasoning) for every tracked model. |
| [`schema.json`](data/schema.json) | Field dictionary for every dataset. |

## Use it

Pull a file straight from `raw.githubusercontent.com`, or hit the live API for query
parameters (date ranges, dimensions, filters):

```bash
# Static daily snapshot (this repo)
curl -fsSL https://raw.githubusercontent.com/Kevinchamplin/mytokentracker-open-data/main/data/cost-index.json

# Live + filterable (the API this repo mirrors)
curl "https://mytokentracker.io/api/v1/data/cost-index?index=frontier&from=2026-01-01"
curl "https://mytokentracker.io/api/v1/data/models?provider=openai&format=csv"
```

Discovery + schema: <https://mytokentracker.io/api/v1/data> · <https://mytokentracker.io/api/v1/data/schema>

## How to cite

> Champlin Enterprises. (2026). *MyTokenTracker Open Data* [Data set]. Retrieved from
> https://mytokentracker.io/data

## License

Data is licensed **[CC BY 4.0](LICENSE)** — use it anywhere with attribution and a link
back to [mytokentracker.io](https://mytokentracker.io). The tracking client is published
separately under MIT at [mytokentracker-cli](https://github.com/Kevinchamplin/mytokentracker-cli).
