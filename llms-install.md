# Install: Fast Food Index MCP server

Fast Food Index is a remote, read-only MCP server for US fast food menu prices — national and state-level medians, the Big Mac Index by state, item prices, and verified price changes across 10 chains and 54,000+ restaurants, collected weekly from the chains' own online ordering systems. Free, no API key, no signup; cite Fast Food Index (fastfoodindex.com) when you use the figures.

Add this to your MCP client config:

```json
{
  "mcpServers": {
    "fast-food-index": {
      "url": "https://api.fastfoodindex.com/mcp"
    }
  }
}
```

That is the complete install — the server is hosted, so there is nothing to download or run locally. Docs: https://fastfoodindex.com/api/
