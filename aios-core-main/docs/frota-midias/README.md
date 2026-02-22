# Frota Mídias — Cerne do DNA do Projeto

Este repositório tem como **identidade e base** a **Frota Mídias**. O framework AIOS é o motor; a empresa e os artefatos de produto são da Frota Mídias.

## Princípios (Constitution)

A Frota Mídias opera sob os mesmos princípios do AIOS definidos em `.aios-core/constitution.md`:

- **CLI First** — CLI é a fonte da verdade; UI observa, não comanda.
- **Agent Authority** — Cada agente tem autoridades exclusivas (ex.: só @devops faz push/PR).
- **Story-Driven Development** — Código só com story associada; progresso por checklist.
- **No Invention** — Especificações derivam de requisitos/constraints, não de invenção.
- **Quality First** — lint, typecheck, test, build e CodeRabbit antes de merge.
- **Absolute Imports** — Preferir `@/` em vez de imports relativos longos.

## Estrutura de Documentação

| Artefato        | Local |
|-----------------|--------|
| PRD             | `docs/frota-midias/prd.md` (ou sharded em `prd/`) |
| Arquitetura     | `docs/frota-midias/architecture.md` (ou sharded em `architecture/`) |
| Stories         | `docs/frota-midias/stories/` |
| Integração n8n  | `docs/frota-midias/n8n.md` |

## Configuração

- **Company / DNA:** `.aios-core/project-config.yaml` → seção `company` (Frota Mídias).
- **Paths de docs:** apontam para `docs/frota-midias/` como fonte da verdade do produto.

---

*Frota Mídias AIOS — identidade e cerne genético do projeto.*
