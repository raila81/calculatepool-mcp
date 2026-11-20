# Calculate Pool MCP server

Does the swimming pool math owners ask about most, with the same formulas as calculatepool.com: how many gallons a pool holds (rectangle, round, oval, Roman, Grecian, kidney, L-shape or freeform, with one depth, a shallow and a deep end, or an above-ground wall of 48, 52 or 54 inches, in feet or metres), how much chlorine, salt, baking soda, muriatic acid, stabilizer or calcium chloride to add, the pump flow that turns the pool over in a chosen time, and the heater size in BTU per hour. It works with numbers only and stores nothing.

- **Website:** [calculatepool.com](https://calculatepool.com)
- **Documentation:** [calculatepool.com/ai-assistants/](https://calculatepool.com/ai-assistants/)
- **Endpoint:** `https://calculatepool.com/mcp` (MCP Streamable HTTP, public, no authentication, no API key)

## Tools

- `pool_volume`: gallons, litres and cubic feet from shape and size
- `chemical_dose`: amount of a pool chemical to move a reading to a target
- `pump_size`: pump flow, horsepower range and minimum filter area for a turnover time
- `heater_size`: heater BTU per hour for a temperature rise in a set time
- `pool_facts`: standard pool sizes in gallons by wall height or depth

All tools are read-only and stateless. The server stores nothing it receives, names no products or stores, and gives no prices.

## Connect

Any MCP client that supports remote servers:

```json
{
  "mcpServers": {
    "calculatepool": {
      "type": "streamable-http",
      "url": "https://calculatepool.com/mcp?src=mcp"
    }
  }
}
```

Quick test:

```bash
curl -s -X POST 'https://calculatepool.com/mcp?src=mcp' -H 'Content-Type: application/json' -d '{"jsonrpc":"2.0","id":1,"method":"tools/list"}'
```

This repository holds the listing metadata only. The server itself is a hosted service run by the Calculate Pool website (https://calculatepool.com); see the documentation link above for privacy and terms.
