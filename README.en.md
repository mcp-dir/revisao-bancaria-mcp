# Revisão de Contrato Bancário

### Recalculate interest and correction of bank contracts, for AI

**Bank contract review** for AI. Recalculate interest, correction and amounts of contracts and financing with official BACEN indices and rates. Built for revisional actions, no login.

- 💳 **Recalculates contracts** and financing with official BACEN rates
- 📈 **Live official indices**: IPCA, INPC, IGP-M, SELIC, TR (BACEN and IBGE)
- 🧮 **Deterministic calculation**: correction, interest, penalty and fees
- 🔒 **No login, no key**: platform-hosted
- 💬 **Works with any MCP client**: Claude Desktop, ChatGPT, Cursor, VS Code, Cline, Continue

[Versão em português](README.md) · [Full docs (PT-BR)](docs/) · [Agent skill](skills/)

---

## One-click install

### Claude (Web and Desktop)

Anthropic unified MCP installation at `claude.ai/customize/connectors`. **The same link works for Claude Web and Claude Desktop** (just be logged in):

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (if the deeplink does not open): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → paste **Name** `Revisão de Contrato Bancário` and **URL** `https://api.mcp.ai/p_revisao-bancaria`.

### Cursor

[➕ Install Revisão de Contrato Bancário in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=revisaobancaria&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZXZpc2FvLWJhbmNhcmlhIn0=)

### VS Code (Copilot Chat)

[➕ Install Revisão de Contrato Bancário in VS Code](vscode:mcp/install?name=revisaobancaria&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_revisao-bancaria%22%7D)

### ChatGPT, Manus, OpenClaw and 40+ other clients

Works with any MCP client that speaks **MCP over HTTP**. The server URL is always:

```
https://api.mcp.ai/p_revisao-bancaria
```

Per-client details: [INSTALL.md](INSTALL.md).

---

## Example prompts

```
Recalculate this financing with market interest by SELIC
Compare the contract's interest with BACEN's average rate for the period
```

---

## 16 tools available

| Tool | Description |
|---|---|
| `calculo_atualizar` | Atualização monetária / liquidação de débito judicial: corrige parcelas por um índice oficial (IPCA, INPC, IGP-M, SELIC, TR…) e aplica juros, multa e honorários. |
| `calculo_indice` | Consulta de índice oficial: fator de correção acumulado entre duas datas (mês inicial excluído, mês final incluído — convenção BACEN/IBGE). |
| `calculo_salario_minimo` | Salário mínimo nacional vigente de um ano (dinâmico, IPEADATA). |
| `calculo_aluguel` | Aluguéis em atraso (Lei 8.245/91): reajusta o aluguel ao longo do contrato pelo índice, corrige cada mês atrasado até hoje, aplica juros de mora (1% a.m.) e multa moratória. |
| `calculo_pensao` | Pensão alimentícia em atraso (art. |
| `calculo_trabalhista` | Verbas rescisórias / liquidação trabalhista (CLT): saldo de salário, aviso prévio indenizado (Lei 12.506/2011), 13º proporcional, férias proporcionais + 1/3, férias vencidas, multa de 40%/20% do FGTS, com descontos de… |
| `calculo_fgts` | Correção do FGTS (tese TR → INPC/IPCA-E, STF): por depósito calcula a diferença entre corrigir pelo índice de inflação vs pela TR, com juros de 3% a.a. |
| `calculo_dosimetria` | Dosimetria da pena (art. 68 CP, sistema trifásico): pena-base pelas circunstâncias judiciais (art. 59), pena intermediária por atenuantes/agravantes (Súmula 231 STJ), pena definitiva por causas de aumento/diminuição (… |
| `calculo_progressao` | Progressão de regime (LEP art. |
| `calculo_partilha` | Partilha de bens no divórcio por regime (Código Civil): apura a massa partilhável (bens − dívidas conforme o regime) e a quota de cada cônjuge, com torna por desequilíbrio. |
| `calculo_tempo_contribuicao` | Tempo de contribuição (CNIS): soma os vínculos contando concomitância uma vez e converte atividade especial em comum (fatores EC 103/2019, só até 13/11/2019). |
| `calculo_rmi` | RMI — Renda Mensal Inicial (pós-reforma EC 103/2019): média dos salários de contribuição × coeficiente (60% + 2% por ano acima de 20H/15M), com piso (salário mínimo) e teto (INSS). |
| `calculo_revisional` | Revisional de contrato bancário: recalcula o financiamento pela taxa média de mercado do BACEN (busca ao vivo por modalidade+mês) e apura o excedente por parcela (Price ou SAC). |
| `calculo_superendividamento` | Superendividamento (Lei 14.181/2021): % da renda comprometida, mínimo existencial (R$600, parametrizável), renda disponível e capacidade de pagamento de um plano de até 5 anos. |
| `calculo_rmc_rcc` | RMC/RCC — reserva de margem consignável de cartão (INSS, códigos 217/268): limites de 5% e restituição corrigida dos descontos. |
| `calculo_restituicao_inss` | Restituição de descontos indevidos no INSS (fraude associativa, códigos 280/304/310/378): soma as parcelas descontadas corrigidas. |

Details for each tool: [docs/ferramentas.md](docs/ferramentas.md) (PT-BR)

---

## Pricing

Free.

---

## Privacy & data protection

- **Read-only**, no tool changes data at the source.
- **Sub-processors**: Banco Central do Brasil (BACEN SGS), IBGE, IPEADATA, the LLM host you choose (Claude, ChatGPT, Cursor, your own agent). Full list in [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Data returned by the tools is sent to **the LLM host you choose**, a sub-processor outside our control. We recommend plans with training opt-out.

---

## FAQ

**Precisa de login ou chave?**
Não. Funciona out-of-the-box, hospedado pela plataforma. Sem login, sem chave de API.

**De onde vêm os índices?**
De fontes públicas oficiais: BACEN (SGS) e IBGE (SIDRA) para IPCA, INPC, IGP-M, SELIC, TR e salário mínimo. O cálculo é determinístico e reproduzível.

**Serve para uso jurídico?**
Sim, é feito para liquidação, execução e atualização de valores. Ainda assim, confira sempre o memorial de cálculo antes de protocolar.


---

## Support

- 📧 [revisaobancaria@mcp.ai](mailto:revisaobancaria@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/revisao-bancaria-mcp/issues)
- 📄 [docs/](docs/)

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_revisao-bancaria` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
