# Cap Models

Uma camada unificada de engenharia de ML/AI que automatiza e padroniza o ciclo completo de desenvolvimento de modelos — operável tanto por humanos via CLI quanto por agentes de IA via MCP/API.

## Visão Geral

```
                  Cap Models
                     │
         ┌───────────┴───────────┐
         ↓                       ↓
      CLI humana            AI Agents
     `cap ...`         Claude Code / Codex
         │                       │
         └───────────┬───────────┘
                     ↓
                 Core Toolkit
```

> **Uma única camada de engenharia de ML que pode ser operada tanto por desenvolvedores quanto por agentes de IA.**

## Ciclo de Vida Coberto

```
Dados
 ↓
Inspeção / Validação
 ↓
Preparação
 ↓
Treinamento
 ↓
Avaliação
 ↓
Experimentos
 ↓
Benchmark
 ↓
Versionamento de Modelos
 ↓
Inferência
 ↓
Deploy
 ↓
Monitoramento
```

## Interface CLI

A CLI é a interface para humanos:

```bash
cap init                          # Inicializa um projeto ML
cap data inspect                  # Inspeção de dados
cap data validate                 # Validação de schemas e qualidade
cap dataset prepare               # Preparação e transformação
cap train                         # Treinamento de modelos
cap eval                          # Avaliação de modelos
cap experiment compare            # Comparação de experimentos
cap benchmark                     # Benchmark de performance
cap model register                # Registro e versionamento
cap predict                       # Inferência em batch
cap infer serve                   # Servidor de inferência
cap pipeline run                  # Execução de pipelines
```

## Interface para Agentes (MCP)

As mesmas capacidades são disponibilizadas como tools estruturadas via MCP:

```
inspect_dataset()        → Métricas, schema, anomalias
validate_dataset()       → Regras de qualidade, tipos, nulos
prepare_dataset()        → Limpeza, encoding, splitting
train_model()            → Treino com hiperparâmetros
evaluate_model()         → Métricas, relatórios, plots
compare_experiments()    → Ranking e diffs entre runs
register_model()         → Versionamento e registry
run_pipeline()           → Orquestração end-to-end
```

## Arquitetura

```
cap-models/
├── src/
│   └── cap_models/
│       ├── cli/              # Interface CLI (Click/Typer)
│       ├── core/             # Lógica central
│       │   ├── data/         # Inspeção, validação, preparação
│       │   ├── training/     # Treinamento e experimentos
│       │   ├── evaluation/   # Avaliação e benchmarks
│       │   ├── registry/     # Versionamento e registro
│       │   ├── inference/    # Servimento e batch
│       │   └── pipeline/     # Orquestração
│       ├── mcp/              # Tools MCP para agentes
│       └── integrations/     # MLflow, DVC, W&B, etc.
├── tests/
└── pyproject.toml
```

## Princípios

- **CLI e MCP como duas faces da mesma moeda** — toda funcionalidade acessível por ambos
- **Core centralizado** — zero lógica duplicada entre interfaces
- **Ecossistema, não substituto** — integra com MLflow, DVC, W&B ao invés de competir
- **Observabilidade embutida** — logs, métricas e rastreabilidade desde o início
- **Agent-friendly** — output estruturado (JSON) para consumo direto por LLMs

## Stack

| Camada | Tecnologias |
|--------|-------------|
| CLI | Python, Click/Typer |
| Core | Python, Pandas, Scikit-learn |
| MCP | Model Context Protocol, FastMCP |
| Integrações | MLflow, DVC, W&B, Docker |
| Testes | Pytest, coverage |
| Build | pyproject.toml, uv/pip |

## Objetivos do Projeto

Além de ser uma ferramenta útil, este projeto explora na prática:

- **Python** — engenharia de software moderna
- **ML** — ciclo completo de modelos
- **MLOps** — versionamento, experimentos, deploy
- **Software Engineering** — arquitetura limpa, testes, CI
- **AI Agents** — integração via MCP
- **MCP** — Model Context Protocol como interface para agentes

## Getting Started

```bash
# Clonar
git clone <repo-url>
cd cap-models

# Instalar
pip install -e .

# Inicializar um projeto
cap init

# Inspecionar dados
cap data inspect data/dataset.csv

# Rodar um pipeline completo
cap pipeline run --config pipeline.yaml
```

## Status

Em desenvolvimento. O toolkit está sendo construído do zero para explorar a integração entre engenharia de ML e agentes de IA.
