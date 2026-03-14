# Exemplos METACOG-EVOLUTION

## Casos de Uso do Framework METACOG-EVOLUTION 2.0

---

## EXEMPLO 1: Evolucao com Sistema Dual

### Cenario
Otimizar um classificador de leads que plateou em 78% de accuracy.

### Execucao

**FASE 0: META-PREPARACAO**

```
AVALIACAO INICIAL:

Complexidade: ALTA (classificacao multi-criterio)
Dados de validacao: 50 test cases
Budget: 10 geracoes

DECISAO INICIAL:
- Sistema: 1 (Fast Evolution) para G0-G2
- Island Populations: ATIVAS
- Objetivos Pareto: Task Performance (40%), Efficiency (20%),
                   Robustness (20%), Hallucination Resistance (20%)
```

**FASE 1: SISTEMA 1 (Fast Evolution) - G0 a G2**

```
GERACAO 0 (Ancestral):
- Fitness: 64/100
- Task Performance: 31/50 (62%)
- Modo: Sistema 1 (rapido, exploratório)

GERACAO 1:
- Variantes testadas: 6 (3 por ilha)
- Exploitation Island: ADD_DETAIL, ADD_CONSTRAINT
- Exploration Island: RESTRUCTURE, SIMPLIFY
- Hybrid Island: Crossover semantico

- Melhor fitness: 71/100 (+7)
- Sistema: 1 (continuar explorando)

GERACAO 2:
- Fitness melhorou 9% (acima de 5% threshold)
- Diversidade populacional: 0.22 (saudavel)
- Melhor fitness: 78/100 (+7)

META-MONITOR: "Melhoria rapida detectada. Considerar switch para Sistema 2."
```

**FASE 2: SISTEMA 2 (Deliberative) - G3+**

```
GERACAO 3:
- Sistema: 2 (deliberativo)
- Razao: fitness > 75%, variance < 0.15

MUDANCAS NO MODO SISTEMA 2:
- Test cases: Completo (50 casos vs 5 amostras)
- VERIFY: Aplicado a top 3 variantes
- Analise: Profunda de cada variante

- Fitness: 83/100 (+5)
- Hallucination Resistance: 91/100 (verificado)

GERACAO 4:
- ADD_EXAMPLE aplicado (baseado em Stone Throw prediction)
- Predicao: +8% | Resultado: +9% (erro: 11%)
- Fitness: 91/100 (+8)

CONVERGENCIA: Top 3 variantes dentro de 4 pontos (91, 89, 87)
```

**RESULTADO FINAL**

```
CHAMPION: Variante 4.2
- Fitness Pareto: [91, 85, 88, 94]
  - Task Performance: 91/100
  - Efficiency: 85/100
  - Robustness: 88/100
  - Hallucination Resistance: 94/100

MELHORIA: 64 -> 91 (+27 pontos, +42%)
GERACOES: 5 (abaixo do esperado 6-8)

DYNAMICS SUMMARY:
- Sistema 1 usado em G0-G2 (exploracao)
- Sistema 2 usado em G3-G4 (refinamento)
- Switch ocorreu no momento certo
- Stone Throw error medio: 14% (calibrado)
```

---

## EXEMPLO 2: Island Populations em Acao

### Cenario
Clone cognitivo com diversidade genetica muito baixa apos 3 geracoes.

### Problema Detectado

```
META-COGNITION MONITOR ALERT:

Geracao 3 - PREMATURE CONVERGENCE RISK

Metricas:
- Exploitation Island std dev: 0.04 (MUITO BAIXO)
- Exploration Island std dev: 0.08 (BAIXO)
- Hybrid Island std dev: 0.06 (BAIXO)
- Fitness: 71/100 (abaixo do target 85)

DIAGNOSTICO: Populacao muito homogenea mas fitness ainda baixo.
             Risco de estar preso em otimo local.
```

### Intervencao do Island Population Controller

```
ISLAND POPULATION REPORT - Emergency Intervention

SITUACAO ATUAL:
- Todas as ilhas convergiram para variantes similares
- Best fitness: 71/100 (precisa de 85+)
- Genetic diversity: CRITICAL

ACOES EXECUTADAS:

1. EXPLORATION ISLAND RESET
   - Injetados 3 novos variantes com mutacoes radicais
   - Mutation types: RESTRUCTURE (2), SIMPLIFY (1)
   - Selection rate reduzida para 20% (mais diversidade)

2. MIGRATION FORCADA
   - Top 1 de Exploitation migrado para Hybrid
   - Random 1 de Exploration injetado em Exploitation
   - Objetivo: quebrar homogeneidade

3. PARAMETER ADJUSTMENT
   - Exploration mutation_intensity: 3 -> 4
   - Exploration selection_rate: 30% -> 20%
   - Global crossover focus: inter-island prioritizado

RESULTADOS APOS 2 GERACOES:

Geracao 5:
- Exploitation std dev: 0.12 (recuperado)
- Exploration std dev: 0.28 (excelente)
- Hybrid std dev: 0.15 (bom)
- Best fitness: 79/100 (+8)

Variante de Exploration com estrutura inovadora
migrou para Hybrid e produziu crossover de 84/100.
```

---

## EXEMPLO 3: Stone Throw Calibration

### Cenario
Modelo preditivo com alto erro (35%) precisa calibracao.

### Stone Throw Experiment Log

```
STONE THROW CALIBRATION - 5 Geracoes

PREDICTION REGISTRY (Pre-Calibration):

| Gen | Mutation | Predicted | Actual | Error |
|-----|----------|-----------|--------|-------|
| G1 | ADD_EXAMPLE | +12% | +14% | 17% |
| G1 | RESTRUCTURE | +10% | +5% | 50% |
| G2 | ADD_DETAIL | +8% | +7% | 12% |
| G2 | SIMPLIFY | +6% | -2% | 133% |
| G3 | ADD_CONSTRAINT | +5% | +4% | 20% |

ERRO MEDIO INICIAL: 35%

PATTERNS DESCOBERTOS:

Pattern 1: RESTRUCTURE Over-Predicted
- Observation: RESTRUCTURE predicted +10% avg, actual +4% avg
- Root cause: Disrupts existing example formatting
- Adjustment: Reduce RESTRUCTURE base by 6%

Pattern 2: SIMPLIFY Context-Dependent
- Observation: +6% on long prompts, -3% on short prompts
- Root cause: Short prompts already optimized, SIMPLIFY removes essential
- Adjustment: Add conditional - SIMPLIFY only if tokens > 250

Pattern 3: ADD_EXAMPLE Consistently Under-Predicted
- Observation: Predicted +11%, actual +13% average
- Root cause: Examples have multiplicative effect on complex tasks
- Adjustment: Increase ADD_EXAMPLE base by 2%, add complexity multiplier

MODEL UPDATE:

def predict_mutation_impact_v2(mutation, context):

    base = calibrated_base_v2[mutation.type]

    # Pattern 1: RESTRUCTURE adjustment
    if mutation.type == 'RESTRUCTURE':
        base *= 0.6  # Reduced from 1.0

    # Pattern 2: SIMPLIFY conditional
    if mutation.type == 'SIMPLIFY':
        if context.prompt_tokens < 250:
            return Prediction(-2, LOW)  # Likely regression
        else:
            base *= 1.2  # Boost for long prompts

    # Pattern 3: ADD_EXAMPLE boost
    if mutation.type == 'ADD_EXAMPLE':
        base += 2  # Base increase
        if context.task_complexity == 'HIGH':
            base *= 1.3  # Complexity multiplier

    return Prediction(base, calculate_confidence(mutation, context))

POST-CALIBRATION RESULTS:

| Gen | Mutation | Predicted | Actual | Error |
|-----|----------|-----------|--------|-------|
| G4 | ADD_EXAMPLE | +14% | +15% | 7% |
| G4 | RESTRUCTURE | +4% | +3% | 25% |
| G5 | SIMPLIFY (long) | +7% | +8% | 12% |
| G5 | ADD_CONSTRAINT | +4% | +4% | 0% |

ERRO MEDIO POS-CALIBRACAO: 11% (melhoria de 69%)
```

---

## EXEMPLO 4: Pareto Multi-Objective

### Cenario
Otimizar prompt para 4 dimensoes simultaneas.

### Pareto Frontier Evolution

```
PARETO OPTIMIZATION - Customer Service Clone

OBJETIVOS:
1. Task Performance: Resolver queries corretamente
2. Efficiency: Minimizar tokens/resposta
3. Robustness: Consistency across query types
4. Hallucination Resistance: Nao inventar policies

GERACAO 0 (Ancestral):
Pareto: [65, 40, 55, 70]

GERACAO 3 (Evolving):
Pareto Frontier com 4 solucoes nao-dominadas:

| Variant | Task | Efficiency | Robust | Halluc | Notes |
|---------|------|------------|--------|--------|-------|
| 3.1 | 85 | 60 | 75 | 82 | Balanced |
| 3.2 | 78 | 85 | 70 | 78 | Efficient |
| 3.3 | 90 | 50 | 80 | 88 | High quality |
| 3.4 | 82 | 70 | 88 | 85 | Robust |

GERACAO 5 (Final):
Pareto Frontier refinado:

| Variant | Task | Efficiency | Robust | Halluc | Trade-off |
|---------|------|------------|--------|--------|-----------|
| 5.1 | 92 | 65 | 82 | 90 | Best overall |
| 5.2 | 85 | 88 | 78 | 85 | Most efficient |
| 5.3 | 88 | 72 | 91 | 88 | Most robust |

RECOMENDACAO:
- Para producao geral: 5.1 (melhor balanco)
- Para alto volume: 5.2 (mais eficiente)
- Para casos criticos: 5.3 (mais robusto)

Usuario escolhe ponto no Pareto Frontier baseado em prioridades.
```

---

## EXEMPLO 5: Meta-Cognition Adaptation

### Cenario
Evolucao detecta plateau e adapta parametros.

### Meta-Cognition Monitor Log

```
META-COGNITION LOG - Generations 3-6

=== GERACAO 3 ===
Status: PROGRESSING
Fitness: 72 -> 76 (+4, 5.5%)
Sistema: 1
Parametros: mutation_rate=0.60, intensity=2
Acao: Nenhuma mudanca necessaria

=== GERACAO 4 ===
Status: PROGRESSING
Fitness: 76 -> 79 (+3, 3.9%)
Sistema: 1
Parametros: mutation_rate=0.60, intensity=2
Acao: Nenhuma mudanca necessaria

=== GERACAO 5 ===
Status: PLATEAU DETECTED
Fitness: 79 -> 80 (+1, 1.3%)
Sistema: 1
Parametros: mutation_rate=0.60, intensity=2

DIAGNOSTICO:
- Melhoria < 2% por 2 geracoes (threshold)
- Diversidade: 0.09 (baixa)
- Mutacoes beneficas: 22% (abaixo de 30%)

ADAPTACOES APLICADAS:
1. mutation_rate: 0.60 -> 0.75 (+0.15)
2. intensity: 2 -> 3 (+1)
3. Trigger: Migration forcada entre ilhas
4. Mutation mix: Adicionar RESTRUCTURE (25%)

=== GERACAO 6 ===
Status: RECOVERING
Fitness: 80 -> 86 (+6, 7.5%)
Sistema: 1 (mantido para exploracao)
Parametros: mutation_rate=0.75, intensity=3

RESULTADO: Adaptacao bem-sucedida.
           Saida do plateau com +6 pontos.

META-OBSERVATION:
"Aumento de mutation_rate + intensity em plateaus
consistentemente resulta em breakthrough dentro de
1-2 geracoes. Pattern confirmado em 4 de 5 casos."
```

---

## METRICAS DE SUCESSO DO METACOG-EVOLUTION

### Comparacao com TOT-EVOLUTION 1.0

| Metrica | TOT 1.0 | METACOG 2.0 | Melhoria |
|---------|---------|-------------|----------|
| Geracoes ate convergencia | 6.2 avg | 4.8 avg | -23% |
| Fitness final medio | 85.3 | 91.2 | +7% |
| Taxa de plateau | 35% | 12% | -66% |
| Prediction error | N/A | 14% | Novo |
| Hallucination rate | N/A | 4% | Novo |

### KPIs do Framework

- **Plateau Recovery Rate**: 88% (recupera de plateaus em 2 gens)
- **System Switch Accuracy**: 82% (switch no momento certo)
- **Island Diversity Maintenance**: 91% (diversidade saudavel)
- **Stone Throw Calibration**: 86% (predicoes dentro de 20%)
- **Pareto Frontier Quality**: 4.2 solucoes medias (vs 1.0 no TOT)

---

## QUANDO USAR CADA CAPACIDADE

### Sistema Dual
- **Sistema 1**: Inicio de evolucao, alta incerteza, exploracao
- **Sistema 2**: Perto do target, refinamento, verificacao

### Island Populations
- **Exploitation**: Quando tem variante promissora para refinar
- **Exploration**: Quando preso em otimo local
- **Hybrid**: Quando quer combinar melhores traits

### Stone Throw
- **Sempre**: Registrar predicoes antes de mutacoes
- **Calibrar**: Quando error > 25%
- **Patterns**: Documentar para futuras evolucoes

### Pareto Optimization
- **Sempre**: Para problemas multi-objetivo
- **Trade-offs**: Quando nao ha solucao unica otima
- **Usuario escolhe**: Apresentar frontier para decisao

---

**Framework mantido por:** Equipe METACOG-EVOLUTION
**Ultima atualizacao:** 2025-12-16
**Versao dos exemplos:** 1.0
