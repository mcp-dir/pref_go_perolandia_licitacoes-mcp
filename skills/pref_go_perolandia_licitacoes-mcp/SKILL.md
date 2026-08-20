---
name: pref_go_perolandia_licitacoes-mcp
description: Skill da REST API do Prefeitura GO Perolândia: Licitações na MCP.AI: 1 endpoint em /api/pref_go_perolandia_licitacoes. Prefeitura GO Perolândia: Licitações, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Prefeitura GO Perolândia: Licitações — REST API skill

Você tem acesso à **Prefeitura GO Perolândia: Licitações** REST API na MCP.AI.

> Prefeitura GO Perolândia: Licitações, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/pref_go_perolandia_licitacoes
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/pref_go_perolandia_licitacoes/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"query":"...","orgao":"...","situacao":"...","modalidade":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/pref_go_perolandia_licitacoes/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `pref_go_perolandia_licitacoes_consultar`

Prefeitura GO Perolândia: Licitações, consulta em fonte oficial. _(POST /api/pref_go_perolandia_licitacoes/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `query` | string | Sim | Parâmetro de consulta "query". |
| `orgao` | string | Sim | Parâmetro de consulta "orgao". |
| `situacao` | string | Sim | Parâmetro de consulta "situacao". |
| `modalidade` | string | Sim | Parâmetro de consulta "modalidade". |
| `pagina` | string | Não | Parâmetro de consulta "pagina". |
| `pagina_empenho` | string | Não | Parâmetro de consulta "pagina_empenho". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_pref_go_perolandia_licitacoes` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
