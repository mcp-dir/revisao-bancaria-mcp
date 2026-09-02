# Instalação detalhada

Revisão de Contrato Bancário é um servidor MCP remoto. Aponte seu cliente pra `https://api.mcp.ai/p_revisao-bancaria`. Snippets rápidos: [INSTALL.md](../INSTALL.md).

| Cliente | URL | Auth |
|---|---|---|
| Claude Desktop | `https://api.mcp.ai/p_revisao-bancaria` | nenhuma (grátis) |
| Cursor | `https://api.mcp.ai/p_revisao-bancaria` | nenhuma |
| VS Code (Copilot) | `https://api.mcp.ai/p_revisao-bancaria` | nenhuma |

A config JSON é a mesma em todos: só a URL, sem headers.

## Desinstalar

Remova o bloco `mcpServers.revisaobancaria` (ou `servers.revisaobancaria` no VS Code) do config do cliente e reinicie.
