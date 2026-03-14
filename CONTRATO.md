# STARK ORCHESTRATION SYSTEM 2.0 (S.O.S.)
## Contrato de Operacao dos Agentes

---

## IMPORTANTE

Este documento contem detalhes tecnicos do sistema.
Para instrucoes de execucao, veja `CLAUDE.md`.
Para referencia visual rapida, veja a secao WORKFLOW em `CLAUDE.md`.

---

## COMANDOS DO USUARIO

| Comando | Pipeline Ativado | Tempo Estimado |
|---------|------------------|----------------|
| "Clone de [pessoa]" | Marcus → Elena → Kai → Vera → Alexandria | 4-6 horas |
| "Clone s-tier [pessoa]" | Pipeline + Darwin no final | 8-12 horas |
| "Clone verificado [pessoa]" | Pipeline + Verity preventivo | 5-7 horas |
| "Agente para [funcao]" | Elena → Kai → Vera | 2-3 horas |
| "Otimize [prompt]" | Kai (+ Darwin opcional) | 1-2 horas |
| "Valide [X]" | Vera + Verity | 30-60 min |
| "Extraia de [material]" | Marcus | 30-60 min |
| "Evolua [prompt]" | Darwin + equipe meta | 2-4 horas |
| "Documente [X]" | Alexandria | 30-60 min |

---

## ARQUITETURA

```
╔═══════════════════════════════════════════════════════════════════════════╗
║                      CAMADA 0: ROUTER (Claude Code)                        ║
║              Identifica pedido → Roteia → Seleciona modo                   ║
╚═══════════════════════════════════════════════════════════════════════════╝
                                      │
       ┌──────────────────────────────┼──────────────────────────────┐
       ▼                              ▼                              ▼
╔═════════════╗              ╔═════════════════╗              ╔═════════════╗
║   MODO 1    ║              ║     MODO 2      ║              ║   MODO 3    ║
║  SEQUENCIAL ║              ║    PARALELO     ║              ║  STANDALONE ║
║  (Pipeline) ║              ║ (Multi-Persona) ║              ║  (Direto)   ║
╚═════════════╝              ╚═════════════════╝              ╚═════════════╝
```

---

## MODOS DE OPERAÇÃO

### MODO 1: SEQUENCIAL
```
Aria → Marcus → Elena → Kai → Vera → [Zara loop] → Alexandria
```
**Usar para:** Clones cognitivos, agentes complexos

### MODO 2: PARALELO (Multi-Persona)
```
Problema → [Marcus + Elena + Kai] em paralelo → Síntese
```
**Usar para:** Problemas complexos, múltiplas perspectivas

### MODO 3: STANDALONE
```
Pedido específico → Agente direto → Resultado
```
**Usar para:** Otimização, validação, extração, documentação

---

## TABELA DE ROTEAMENTO

| VOCÊ DIZ... | AGENTES ATIVADOS |
|-------------|------------------|
| "Clone de [pessoa]" | Pipeline completo + Verity |
| "Clone verificado [pessoa]" | Pipeline + Verity preventivo |
| "Clone s-tier [pessoa]" | Pipeline + Darwin no final |
| "Agente para [função]" | Elena → Kai → Vera |
| "Otimize [prompt]" | Kai (+ Darwin opcional) |
| "Valide [X]" | Vera + Verity |
| "Evolua [prompt]" | Darwin + equipe meta |
| "Extraia de [material]" | Marcus (+ Verity opcional) |
| "Documente [X]" | Alexandria |
| "Analise paralela [problema]" | Multi-persona SPP |
| "Variantes [prompt]" | Atlas gera 3 versões |
| "Diagnostico [processo]" | Sophia analisa |

---

## OS 12 AGENTES

### TIER 1 - CORE PIPELINE

| Agente | Função | Entrega |
|--------|--------|---------|
| **Dr. Marcus Veil** | Arqueólogo Cognitivo | Blueprint (EXTRACT + CLEARR) |
| **Elena Forge** | Sintetizadora de Persona | System Prompt (PERSONA + DEEP) |
| **Dr. Kai Prompt** | Arquiteto de Prompts | Prompt otimizado (50+ técnicas) |
| **Dr. Vera Cross** | Engenheira de Validação | Score 0-100 (ORACLE + VERIFY) |

### TIER 2 - REFINAMENTO

| Agente | Função | Entrega |
|--------|--------|---------|
| **Dr. Zara Evolve** | Evolução Manual | Clone refinado (EVOLVE+) |
| **Dr. Darwin Prompt** | Evolução Genética | Prompt campeão (7 mutações) |

### TIER 3 - META-SUPPORT

| Agente | Função | Uso Expandido |
|--------|--------|---------------|
| **Dr. Verity Check** | Anti-alucinação | Qualquer fase, preventivo |
| **Dr. Sophia Mind** | Meta-cognição | Análise de qualquer processo |
| **Dr. Atlas Darwin** | Ilhas genéticas | Geração de variantes |
| **Dr. Newton Launch** | Calibração | Predições gerais |

### TIER 4 - INFRAESTRUTURA

| Agente | Função | Entrega |
|--------|--------|---------|
| **Commander Aria Nexus** | Orquestração | Plano de projeto |
| **Alexandria Reed** | Documentação | Playbooks + arquivos |

---

## REFLECTION LOOP

```
                         ┌────────────────┐
                         │ PROMPT/CLONE   │
                         └───────┬────────┘
                                 │
                    ┌────────────┴────────────┐
                    ▼                         ▼
           ┌────────────────┐        ┌────────────────┐
           │ VERITY CHECK   │        │ (bypass se     │
           │ (preventivo)   │        │  fonte segura) │
           └───────┬────────┘        └────────────────┘
                   │
                   ▼
           ┌────────────────┐
           │  VERA CROSS    │
           │  Score: ???    │
           └───────┬────────┘
                   │
    ┌──────────────┼──────────────┬──────────────┐
    │              │              │              │
  <70%          70-84%         85-94%          ≥95%
    │              │              │              │
    ▼              ▼              ▼              ▼
┌────────┐   ┌────────┐    ┌────────┐    ┌────────┐
│REBUILD │   │ REFINE │    │APPROVE │    │ S-TIER │
│(Marcus)│   │ (Zara) │    │ (bom)  │    │(ótimo) │
└────────┘   └───┬────┘    └───┬────┘    └───┬────┘
                 │             │             │
                 ▼             │             │
         [Max 3 loops]         │             │
                 │             │             │
                 └──────► VERA ◄┘             │
                                             │
                              ┌──────────────┘
                              ▼
                    ┌────────────────┐
                    │ DARWIN (opt.)  │
                    │ Busca S-Tier   │
                    └────────────────┘
```

---

## FEEDBACK CRUZADO

```
Vera Cross ←→ Elena Forge    (ajustes de estilo)
Vera Cross ←→ Marcus Veil    (re-extração focada)
Vera Cross ←→ Kai Prompt     (técnicas específicas)
Verity     ←→ Marcus Veil    (remoção de dados falsos)
```

---

## DOCUMENTAÇÃO PROGRESSIVA

Alexandria captura insights em TODAS as fases:
1. Marcus → insights de extração
2. Elena → decisões de síntese
3. Kai → técnicas aplicadas
4. Vera → gaps identificados
5. Zara/Darwin → evolução
6. Final → playbook completo

---

## FLUXOS ESPECIAIS

| Fluxo | Quando Usar | Agentes |
|-------|-------------|---------|
| **Extração Verificada** | Material duvidoso | Marcus + Verity |
| **Clone S-Tier** | Busca perfeição | Pipeline + Darwin |
| **Multi-Perspectiva** | Problema complexo | Paralelo + Sophia |
| **Diagnóstico** | Processo travado | Sophia Mind |
| **Variantes** | Explorar opções | Atlas (3 ilhas) |

---

## ESTRUTURA DO VIVEIRO

```
Viveiro/
├── clones/           # Clones cognitivos
├── agentes/          # Agentes funcionais
├── prompts/          # Prompts otimizados
├── frameworks/       # Novos frameworks
├── playbooks/        # Guias de processo
├── swipe-files/      # Exemplos
├── lab/              # Experimentos
└── meta/             # Análises de processo
    ├── sophia-reports/
    ├── calibrations/
    └── process-logs/
```

---

## CONVENÇÕES

```
CLONES:   nome-pessoa-lowercase     (naval-ravikant)
AGENTES:  funcao-lowercase          (copywriter-persuasivo)
PROMPTS:  acao-objetivo             (gerar-headlines)
LAB:      YYYY-MM-DD-descricao      (2025-12-16-teste)
```

---

## ARQUIVOS POR AGENTE

| Agente | Gera |
|--------|------|
| Marcus | `extraction-report.md`, `cognitive-blueprint.md` |
| Elena | `system-prompt.md`, `persona-profile.md`, `test-suite.md` |
| Kai | `optimized-prompt.md`, `techniques-applied.md` |
| Vera | `validation-report.md`, `fidelity-scores.md` |
| Zara | `evolution-log.md`, `refined-prompt.md` |
| Darwin | `champion-prompt.md`, `genealogy.md`, `variants/` |
| Alexandria | `project-summary.md`, `playbook.md` |

---

## SCORES DE VALIDAÇÃO

| Score | Tier | Ação |
|-------|------|------|
| 95-100% | S-Tier | Indistinguível |
| 85-94% | A-Tier | Aprovado |
| 70-84% | B-Tier | Refinar (Zara) |
| 55-69% | C-Tier | Gaps sérios |
| <55% | F-Tier | Reconstruir (Marcus) |

---

*Baseado em: CrewAI, LangGraph, AutoGen, OpenAI Swarm*
*Padrões: Andrew Ng (Reflection, Tool Use, Planning, Multi-Agent) + SPP*
