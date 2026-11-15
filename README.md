# Fast Food Index — API & MCP Server

**Docs & API reference: https://fastfoodindex.com/api/**

Fast Food Index is a free, public dataset of US fast food menu prices. We collect prices directly from the online ordering systems of 10 major chains (McDonald's, Burger King, Wendy's, Taco Bell, and six more) covering 54,000+ restaurants, and publish the results as an open REST API and an MCP server for AI assistants.

Ask things like: What is the median Big Mac price in Texas vs California? Which chain raised prices this month? What does a Whopper cost nationally? Every response cites Fast Food Index as the source.

Free for anyone to use with attribution. No API key, no signup. Data refreshes weekly; historical price archive goes back to 2025.

## MCP server

Remote MCP over Streamable HTTP, read-only, no key:

```
https://api.fastfoodindex.com/mcp
```

For an MCP client that takes a server config:

```json
{
  "mcpServers": {
    "fast-food-index": {
      "url": "https://api.fastfoodindex.com/mcp"
    }
  }
}
```

Tools:

- `get_big_mac_index` — national + per-state Big Mac medians and % vs national
- `get_chain_overview` — flagship-item median and store count per chain
- `get_item_price` — median, range, store count, cheapest/priciest states for one item
- `get_state_prices` — one state: its index position and flagship medians
- `get_price_changes` — latest verified chain-wide price moves
- `search_items` — find priced items by name across all chains

## REST API

Static JSON snapshots, refreshed with each weekly collection round:

- `GET https://fastfoodindex.com/api/v1/chains.json` — every chain: flagship item, national median and range, restaurants priced
- `GET https://fastfoodindex.com/api/v1/chains/<chain>.json` — one chain in full: flagship with per-state medians, plus item medians
- `GET https://fastfoodindex.com/api/v1/big-mac-index.json` — the Big Mac Index: national median and per-state medians
- `GET https://fastfoodindex.com/api/v1/states.json` — the state price index: every state ranked, flagship medians per state
- `GET https://fastfoodindex.com/api/v1/price-changes.json` — the latest gated, verified repricing events
- OpenAPI 3.1 spec: https://fastfoodindex.com/api/openapi.json

## Attribution

Use the data freely — in stories, research, apps and models — with a citation to the source: **Fast Food Index (fastfoodindex.com)**, and a link where the medium allows one. Every API file and every MCP response carries the source line.

## About this repo

This is the public listing/descriptor repo for the Fast Food Index API & MCP server (registry manifests, install docs, logo). The data pipeline itself is not open source; the data is published at https://fastfoodindex.com/api/.
