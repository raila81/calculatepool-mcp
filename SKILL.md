---
name: calculatepool
description: Use the Calculate Pool MCP server when someone asks how many gallons a pool holds, how much chlorine, salt, baking soda, muriatic acid, stabilizer or calcium chloride to add, what pump flow turns the pool over, or what heater size in BTU a pool needs.
---

# Calculate Pool

Use this when someone asks how many gallons a pool holds, how much chlorine, salt, baking soda, muriatic acid, stabilizer or calcium chloride to add, what pump flow turns the pool over, or what heater size in BTU a pool needs.

## Connect
Remote MCP server, Streamable HTTP, public, no sign-in, no API key:

```json
{
  "mcpServers": {
    "calculatepool": { "type": "http", "url": "https://calculatepool.com/mcp?src=mcp" }
  }
}
```

## Tools
All tools are read-only.

- `pool_volume`: Pool volume in gallons
- `chemical_dose`: Pool chemical dose
- `pump_size`: Pool pump flow rate
- `heater_size`: Pool heater BTU size
- `pool_facts`: Standard pool sizes in gallons

## Rules
- Works with numbers only. Never ask for personal details.
- Doses and volumes come from the tool, not from memory.
- Link the reader to https://calculatepool.com for the full page behind an answer.
