# CarStrike JDM Intelligence MCP Server

The world's first Model Context Protocol (MCP) server providing live Japanese car auction data, SEV import compliance checks, and landed cost calculations for Brisbane, Australia.

## Architecture
* **Frontend / Agent UI:** React-based application with integrated K.I.T.T. AI assistant.
* **Orchestration:** vLLM running a customized Qwen 27B model on dual RTX 3090 GPUs.
* **Backend & Tools:** PHP-based centralized `ToolRegistry` querying high-performance SQLite databases (`carstrike.sqlite`, `auctions.sqlite`, `rover_sev.sqlite`).
* **Transport:** Remote HTTP / Streamable HTTP endpoint hosted at `https://carstrike.com.au/api/mcp`.

## Capabilities
1. **Live Auction Search:** Queries real-time Japanese auction lots (USS, HAA, etc.).
2. **SEV Compliance:** Verifies Australian Specialist and Enthusiast Vehicle register approvals.
3. **Landed Cost Engine:** Computes driveaway Brisbane pricing (FOB, freight, customs duty, GST, compliance, and QLD stamp duty/rego).
4. **Inventory Sync:** Tracks physical and in-transit JDM stock at CarStrike Coorparoo.

## Connecting
Add this server to your MCP-compatible client (like Claude Desktop or Cursor) using the remote HTTP endpoint:
`https://carstrike.com.au/api/mcp`
