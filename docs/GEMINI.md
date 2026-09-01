# FlyRank ML Internship — Project & Agent Knowledge Hub

Bem-vindo ao repositório do **FlyRank ML Internship** (`Applied Search Intelligence: Google Search Ranking & Discoverability`).

---

## 🧭 Router de Skills para Agentes (Antigravity & AGY CLI)

Antes de iniciar qualquer tarefa neste repositório, consulte a tabela abaixo e carregue exatamente **uma** skill relevante em `skills/` (mais `skills/flyrank/flyrank-data/SKILL.md` sempre que manipular dados):

| Tarefa / Objetivo | Carregar Skill Principal | Skill Complementar (Dados) |
|---|---|---|
| **Direcionamento geral do agente / boas práticas** | [`skills/directing-your-ai-assistant/SKILL.md`](skills/directing-your-ai-assistant/SKILL.md) | — |
| **Enquadramento de problema de ML (ML-02, ML-03)** | [`skills/framing-ml-problems/SKILL.md`](skills/framing-ml-problems/SKILL.md) | [`skills/flyrank/flyrank-data/SKILL.md`](skills/flyrank/flyrank-data/SKILL.md) |
| **Contrato de dados & Validação de Completeness (ML-04)** | [`skills/writing-data-contracts/SKILL.md`](skills/writing-data-contracts/SKILL.md) | [`skills/flyrank/flyrank-data/SKILL.md`](skills/flyrank/flyrank-data/SKILL.md) |
| **Consultas SQL em grandes volumes (DuckDB/BigQuery)** | [`skills/querying-big-datasets/SKILL.md`](skills/querying-big-datasets/SKILL.md) | [`skills/flyrank/flyrank-data/SKILL.md`](skills/flyrank/flyrank-data/SKILL.md) |
| **Auditoria de Sinais & Testes de EDA (ML-06)** | [`skills/auditing-signals/SKILL.md`](skills/auditing-signals/SKILL.md) | [`skills/flyrank/flyrank-data/SKILL.md`](skills/flyrank/flyrank-data/SKILL.md) |
| **Baseline de regras & Fila Ranqueada (ML-07)** | [`skills/building-baselines/SKILL.md`](skills/building-baselines/SKILL.md) | [`skills/flyrank/flyrank-data/SKILL.md`](skills/flyrank/flyrank-data/SKILL.md) |
| **Treinamento & Comparação Honesta de Modelos (ML-08)** | [`skills/training-honest-models/SKILL.md`](skills/training-honest-models/SKILL.md) | [`skills/flyrank/flyrank-data/SKILL.md`](skills/flyrank/flyrank-data/SKILL.md) |
| **Caça a Vazamentos (Leakage) & Validação Cruzada (ML-09)**| [`skills/hunting-leakage-and-validating/SKILL.md`](skills/hunting-leakage-and-validating/SKILL.md) | [`skills/flyrank/flyrank-data/SKILL.md`](skills/flyrank/flyrank-data/SKILL.md) |
| **Escrita de Claims Honestas / Métricas sem Viés** | [`skills/writing-honest-claims/SKILL.md`](skills/writing-honest-claims/SKILL.md) | — |
| **Elaboração de Artigo / Research Paper (ML-11, W7)** | [`skills/writing-research-papers/SKILL.md`](skills/writing-research-papers/SKILL.md) | — |
| **Deploy do Paper como Página Estática** | [`skills/deploying-static-pages/SKILL.md`](skills/deploying-static-pages/SKILL.md) | — |
| **Contexto de Domínio FlyRank & SEO AI Visibility** | [`skills/flyrank/flyrank-context/SKILL.md`](skills/flyrank/flyrank-context/SKILL.md) | — |

---

## 🛡️ Diretrizes de Integridade & Completeness

1. **Contratos de Dados Rígidos (`writing-data-contracts`)**:
   - Defina sempre o grão (*grain*) da linha (ex: `(site_id, page_id, week)`).
   - Verifique ausência de duplicidade via queries de contagem.
   - Avalie completude/missingness por categoria e por janela temporal.
2. **Prevenção de Vazamento de Dados (*Data Leakage*)**:
   - Features devem pertencer estritamente à janela temporal pré-predição.
   - Proibido usar rótulos derivados ou flags de regras de produto em features.
   - Use `GroupKFold` pelo identificador de grupo (`client_id` / `site_id`) ou divisão temporal, nunca divisão aleatória pura.
3. **Métricas Honestas**:
   - Sempre imprima a taxa base (*base rate*) junto a qualquer métrica de precisão / ROC-AUC / F1.
   - Exija holdout selado documentado antes de relatar ganhos.
4. **Privacidade e Proteção de Dados (`DATA_USE.md`)**:
   - Nunca comite datasets brutos nem exiba dados confidenciais de clientes.

---

## ⚙️ Ambiente & Execução Rápida

- **Ambiente Virtual**: `.venv` (Python 3.11 gerenciado por `uv`).
- **Ativação**: `.\.venv\Scripts\activate`
- **Execução do Pipeline Completo**:
  ```powershell
  .\.venv\Scripts\python scripts/run_all.py
  ```
- **Notebooks de Trabalho**: Localizados em `work/notebooks/` (w01 até w07 e capstone).
- **Documentação de Referência**: Localizada em `docs/` (`data-dictionary.md`, `ml-core-foundation-framework.md`, `ml-intern-dataset-and-lane-guide.md`).
