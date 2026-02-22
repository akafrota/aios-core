# Integração n8n — Frota Mídias

Este documento descreve como o n8n está integrado ao projeto Frota Mídias AIOS e como configurá-lo.

## Variáveis de ambiente

No seu `.env` (nunca commitar credenciais):

```bash
# n8n (automação de workflows)
N8N_API_KEY=sua_api_key_aqui
N8N_WEBHOOK_URL=https://seu-n8n.com/webhook/...
```

- **N8N_API_KEY:** API key da sua instância n8n (Settings → API no n8n).
- **N8N_WEBHOOK_URL:** URL base do n8n ou URL de um webhook específico para disparar workflows.

## Ferramenta MCP n8n no AIOS

O AIOS já inclui a definição da ferramenta n8n em:

- `.aios-core/infrastructure/tools/mcp/n8n.yaml`

Operações suportadas (validadores e helpers):

- **execute_workflow** — Executar um workflow por `workflow_id`; opcionalmente `data` e `wait_for_completion`.
- **create_workflow** — Criar workflow (name, nodes, connections).
- **create_credential** / **update_credential** — Gerenciar credenciais.

Para os agentes usarem o n8n via MCP:

1. Configure o servidor **n8n-mcp** no seu cliente MCP (ex.: Docker MCP gateway ou `.claude/mcp.json`).
2. Informe a URL da instância n8n e, se necessário, a API key no catálogo MCP.
3. Agentes que declaram a ferramenta `n8n` poderão chamar esses fluxos.

## Sentidos da integração

| Direção    | Como |
|-----------|------|
| **AIOS → n8n** | Task ou script no AIOS chama a API do n8n ou envia POST para `N8N_WEBHOOK_URL` (ex.: ao fechar uma story ou passar em quality gate). |
| **n8n → AIOS** | No n8n, use o nó **HTTP Request** ou **Execute Command** para chamar um webhook do projeto que rode o CLI AIOS (ex.: `npx aios-pro workflow run ...`) ou um script que invoque o AIOS. |

## Checklist de preparação

- [ ] Instância n8n rodando (local ou servidor).
- [ ] API key criada no n8n.
- [ ] `.env` com `N8N_API_KEY` e `N8N_WEBHOOK_URL`.
- [ ] n8n-mcp registrado no MCP (Docker gateway ou config do IDE).
- [ ] Documentar neste arquivo quais workflows existem e o que cada um faz (quando criar).

---

*Frota Mídias — Integração n8n.*
