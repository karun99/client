# Royal Mutton Hub

B2B distributor site for Royal Mutton Hub.

## Structure

- `client/` - Main Next.js application

## MCP server

This application ships a dependency-free [Model Context Protocol](https://modelcontextprotocol.io)
server (`mcp-server/server.mjs`) exposing its core operations to agentic clients.
It speaks JSON-RPC 2.0 over stdio and adds no runtime dependencies.

Add the repository's [`.mcp.json`](.mcp.json) to your MCP client, or run:

```bash
node mcp-server/server.mjs
```

Protocol smoke tests:

```bash
python3 -m unittest discover -s tests -p "test_mcp_server.py" -v
```

See [docs/MCP.md](docs/MCP.md) and [mcp-server/README.md](mcp-server/README.md).


## Quick start & testing

```bash
# run the client
npm install
npm run dev

# verify the MCP server speaks the protocol
python3 -m unittest discover -s tests -p "test_mcp_server.py" -v
```

See [docs/MCP.md](docs/MCP.md) for the exposed tools. All files were generated
(and the application hardened) by the TRL rollout in `mcp-server/`.
