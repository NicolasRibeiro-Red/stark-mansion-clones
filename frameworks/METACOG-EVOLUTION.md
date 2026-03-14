# FRAMEWORK METACOG-EVOLUTION

## Sistema de Otimização Evolutiva com Meta-Cognição

---

## O QUE É METACOG-EVOLUTION?

**METACOG-EVOLUTION** é a evolução do TOT-EVOLUTION que integra:

- **Meta-cognição** - O sistema observa e ajusta seu próprio processo
- **Anti-alucinação** - Framework VERIFY integrado
- **Island Populations** - Múltiplas populações evolutivas isoladas
- **Otimização Pareto** - Multi-objetivo com 4 dimensões
- **Parâmetros Adaptativos** - Auto-ajuste baseado em feedback
- **Stone Throw Protocol** - Calibração do modelo mental

### Evolução do Framework

```
TOT-EVOLUTION 1.0          →    METACOG-EVOLUTION 2.0
─────────────────────────────────────────────────────────
Darwinismo puro            →    Darwinismo + Consciência
Fitness único              →    Pareto multi-objetivo
Parâmetros fixos           →    Parâmetros adaptativos
População única            →    Island Populations
Sem verificação            →    Framework VERIFY integrado
Mutação estatística        →    Stone Throw calibrado
Sistema único              →    Sistema Dual (1 e 2)
```

### Analogia Central: Stone Throw

```
Imagine lançar pedras em um lago:
├── Pedras diferentes (tamanho, composição) = Mutações diferentes
├── Força do lançamento = Intensidade da mutação
├── Ângulo de lançamento = Direção da mudança
├── Splash = Impacto imediato no fitness
├── Ripples = Efeitos secundários nas métricas
├── Alvo = Objetivo Pareto-optimal
└── Calibração = Ajustar modelo mental para acertar mais
```

---

## OS 5 PILARES DO METACOG-EVOLUTION

### PILAR 1: SISTEMA DUAL DE PROCESSAMENTO

Inspirado na teoria de Kahneman (Sistema 1 e 2):

```
┌─────────────────────────────────────────────────────────────┐
│                    SISTEMA DUAL                              │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│  SISTEMA 1: FAST EVOLUTION          SISTEMA 2: DELIBERATIVE │
│  ─────────────────────────          ───────────────────────  │
│  • Rápido e intuitivo               • Lento e analítico      │
│  • Heurísticas conhecidas           • Análise profunda       │
│  • Exploração do espaço             • Refinamento preciso    │
│  • Gerações iniciais (G0-G2)        • Gerações finais (G3+)  │
│  • 3-5 test cases                   • Todos test cases       │
│  • Alta diversidade                 • Alta precisão          │
│  • Tolerante a erros                • VERIFY rigoroso        │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

#### Quando Usar Cada Sistema

```python
def select_system(context):
    """
    Seleciona Sistema 1 ou 2 baseado no contexto
    """

    # SISTEMA 1 (Fast) quando:
    if context.generation < 3:
        return SYSTEM_1  # Exploração inicial

    if context.fitness_variance > 0.3:
        return SYSTEM_1  # Alta diversidade, explorar mais

    if context.time_pressure == "high":
        return SYSTEM_1  # Precisa de resultados rápidos

    # SISTEMA 2 (Deliberative) quando:
    if context.fitness_variance < 0.1:
        return SYSTEM_2  # Convergindo, refinar

    if context.top_fitness > 0.85:
        return SYSTEM_2  # Perto do ótimo, precisão

    if context.hallucination_risk == "high":
        return SYSTEM_2  # Precisa verificação

    # Default: alternar baseado em performance
    return SYSTEM_2 if context.generation % 2 == 0 else SYSTEM_1
```

#### Transição Entre Sistemas

```
Fase Exploratória (SISTEMA 1)
├── G0: População inicial via mutação
├── G1: Alta diversidade, muitas variantes
├── G2: Seleção natural, top 50%
│
↓ Trigger: fitness_variance < 0.15 OR top_fitness > 0.80
│
Fase de Refinamento (SISTEMA 2)
├── G3: Análise profunda de survivors
├── G4: VERIFY em variantes promissoras
├── G5+: Convergência para Pareto-optimal
```

---

### PILAR 2: META-COGNIÇÃO EVOLUTIVA

O sistema observa e ajusta seu próprio processo:

#### Meta-Monitor Evolutivo

```
META-MONITOR
│
├── OBSERVAÇÃO
│   ├── Fitness atual vs gerações anteriores
│   ├── Diversidade populacional
│   ├── Taxa de mutações benéficas
│   └── Padrões de sucesso/falha
│
├── DIAGNÓSTICO
│   ├── Evolução está progredindo?
│   ├── População muito homogênea?
│   ├── Plateau detectado?
│   └── Risco de ótimo local?
│
├── AJUSTE
│   ├── Modificar mutation_rate
│   ├── Alterar mutation_intensity
│   ├── Triggerar migração inter-ilhas
│   └── Mudar de Sistema 1 para 2
│
└── APRENDIZADO
    ├── Quais mutações funcionam melhor?
    ├── Quais combinações são efetivas?
    └── Atualizar heurísticas para próxima evolução
```

#### Perguntas do Meta-Monitor

```markdown
A cada geração, o Meta-Monitor avalia:

**PROGRESSO**
□ "A fitness melhorou vs geração anterior?"
□ "Taxa de melhoria está diminuindo?"
□ "Estamos no caminho do target?"

**DIVERSIDADE**
□ "População está muito homogênea?"
□ "Há variantes radicalmente diferentes?"
□ "Diversidade genética é suficiente?"

**EFICIÊNCIA**
□ "Quantas mutações foram benéficas?"
□ "Quantas foram neutras?"
□ "Quantas foram prejudiciais?"

**RISCO**
□ "Alguma regressão grave?"
□ "Risco de ótimo local?"
□ "Precisa de exploração radical?"

**CALIBRAÇÃO**
□ "Previsões de fitness estão corretas?"
□ "Modelo mental precisa ajuste?"
□ "Stone Throw está calibrado?"
```

---

### PILAR 3: ISLAND POPULATIONS

Três populações evolutivas isoladas com estratégias diferentes:

```
┌──────────────────────────────────────────────────────────────┐
│                    ISLAND POPULATIONS                         │
├──────────────────────────────────────────────────────────────┤
│                                                               │
│  ISLAND A: EXPLOITATION     ISLAND B: EXPLORATION             │
│  ────────────────────────   ─────────────────────             │
│  • Foco: Refinamento        • Foco: Diversidade               │
│  • Selection rate: 70%      • Selection rate: 30%             │
│  • Mutation intensity: 1    • Mutation intensity: 3           │
│  • Mutações suaves          • Mutações radicais               │
│  • Preserva bons genes      • Descobre novos padrões          │
│                                                               │
│                 ISLAND C: HYBRID                              │
│                 ──────────────────                            │
│                 • Foco: Crossover inter-ilhas                 │
│                 • Selection rate: 50%                         │
│                 • Mutation intensity: 2                       │
│                 • Combina traits das outras ilhas             │
│                 • Ponto de encontro genético                  │
│                                                               │
└──────────────────────────────────────────────────────────────┘
```

#### Configuração das Ilhas

```python
island_config = {
    'exploitation': {
        'name': 'Exploitation Island',
        'emoji': 'A',
        'strategy': 'refinement',
        'selection_rate': 0.70,    # Top 70% sobrevive
        'mutation_rate': 0.50,     # 50% mutação vs crossover
        'mutation_intensity': 1,   # 1 operador por mutação
        'mutation_types': ['add_detail', 'add_constraint', 'add_validation'],
        'focus': 'Aperfeiçoar variantes promissoras'
    },
    'exploration': {
        'name': 'Exploration Island',
        'emoji': 'B',
        'strategy': 'diversity',
        'selection_rate': 0.30,    # Apenas top 30% sobrevive
        'mutation_rate': 0.80,     # 80% mutação
        'mutation_intensity': 3,   # 3 operadores por mutação
        'mutation_types': ['restructure', 'simplify', 'change_tone', 'add_example'],
        'focus': 'Descobrir padrões não-óbvios'
    },
    'hybrid': {
        'name': 'Hybrid Island',
        'emoji': 'C',
        'strategy': 'crossover',
        'selection_rate': 0.50,    # Top 50% sobrevive
        'mutation_rate': 0.30,     # Mais crossover
        'mutation_intensity': 2,
        'crossover_types': ['semantic', 'multi_point', 'trait_based'],
        'focus': 'Combinar melhores traits de A e B'
    }
}
```

#### Protocolo de Migração

```
MIGRAÇÃO INTER-ILHAS
│
├── Frequência: A cada 3 gerações
│
├── Volume: Top 1 de cada ilha migra
│
├── Direção:
│   ├── A → C (exploitation para hybrid)
│   ├── B → C (exploration para hybrid)
│   └── C → A e B (hybrid distribui)
│
└── Objetivo:
    ├── Trocar material genético
    ├── Evitar convergência prematura
    └── Combinar exploration e exploitation
```

```
Gen 0:   [A: 6] [B: 6] [C: 6]
Gen 1:   [A: 6] [B: 6] [C: 6]
Gen 2:   [A: 6] [B: 6] [C: 6]
         ↓ MIGRAÇÃO ↓
Gen 3:   [A: 6+1] [B: 6+1] [C: 6+2]
         (top de A→C, B→C, C→A e C→B)
Gen 4:   [A: 7] [B: 7] [C: 8]
Gen 5:   ...
```

---

### PILAR 4: OTIMIZAÇÃO PARETO MULTI-OBJETIVO

Quatro dimensões de fitness simultâneas:

```
┌──────────────────────────────────────────────────────────────┐
│                    PARETO OPTIMIZATION                        │
├──────────────────────────────────────────────────────────────┤
│                                                               │
│  DIMENSÃO 1: TASK PERFORMANCE (40%)                          │
│  ────────────────────────────────────                        │
│  • Accuracy nos test cases                                   │
│  • Qualidade das respostas                                   │
│  • Completude da tarefa                                      │
│                                                               │
│  DIMENSÃO 2: EFFICIENCY (20%)                                │
│  ──────────────────────────────                              │
│  • Token count do prompt                                     │
│  • Latência de processamento                                 │
│  • Complexidade cognitiva                                    │
│                                                               │
│  DIMENSÃO 3: ROBUSTNESS (20%)                                │
│  ────────────────────────────                                │
│  • Consistency across inputs                                 │
│  • Estabilidade sob variação                                 │
│  • Edge case handling                                        │
│                                                               │
│  DIMENSÃO 4: HALLUCINATION RESISTANCE (20%)                  │
│  ────────────────────────────────────────                    │
│  • VERIFY score                                              │
│  • Taxa de claims verificáveis                               │
│  • Calibração de confiança                                   │
│                                                               │
└──────────────────────────────────────────────────────────────┘
```

#### Cálculo de Dominância Pareto

```python
def pareto_fitness(variant, test_cases):
    """
    Calcula fitness multi-objetivo
    """
    return {
        'task_performance': evaluate_accuracy(variant, test_cases),
        'efficiency': evaluate_efficiency(variant),
        'robustness': evaluate_consistency(variant, test_cases),
        'hallucination_resistance': verify_score(variant)
    }

def is_pareto_dominant(a, b):
    """
    a domina b se:
    - Melhor em pelo menos 1 objetivo
    - Não pior em nenhum objetivo
    """
    dominated = all(a[k] >= b[k] for k in a)
    strictly_better = any(a[k] > b[k] for k in a)
    return dominated and strictly_better

def get_pareto_frontier(population):
    """
    Retorna conjunto de soluções não-dominadas
    """
    frontier = []
    for variant in population:
        dominated = False
        for other in population:
            if is_pareto_dominant(other.fitness, variant.fitness):
                dominated = True
                break
        if not dominated:
            frontier.append(variant)
    return frontier
```

#### Visualização do Pareto Frontier

```
Task Performance
     ↑
100% │    ★ A        ★ B
     │        ★ C
 80% │              ★ D
     │
 60% │                    ★ E
     │
 40% │
     └────────────────────────→ Efficiency
         40%   60%   80%  100%

Pareto Frontier: A, B, C, D (não-dominados)
Dominated: E (dominado por D em ambas dimensões)
```

---

### PILAR 5: STONE THROW PROTOCOL

Protocolo de experimentação sistemática para calibrar o modelo mental:

```
┌──────────────────────────────────────────────────────────────┐
│                    STONE THROW PROTOCOL                       │
├──────────────────────────────────────────────────────────────┤
│                                                               │
│  1. DEFINIR ALVO (Target)                                    │
│     • Métricas de sucesso específicas                        │
│     • Objetivos Pareto e pesos                               │
│     • Threshold de aceitação                                 │
│                                                               │
│  2. CATALOGAR PEDRAS (Variáveis)                             │
│     • Lista de mutações disponíveis                          │
│     • Parâmetros ajustáveis                                  │
│     • Combinações possíveis                                  │
│                                                               │
│  3. CALIBRAR LANÇAMENTO (Baseline)                           │
│     • Baseline measurement                                   │
│     • Modelo preditivo inicial                               │
│     • Hipóteses sobre impacto                                │
│                                                               │
│  4. LANÇAR PEDRA (Execute)                                   │
│     • Aplicar mutação específica                             │
│     • Registrar parâmetros exatos                            │
│     • Prever resultado antes de medir                        │
│                                                               │
│  5. MEDIR IMPACTO (Measure)                                  │
│     • Splash: Mudança imediata em fitness                    │
│     • Ripples: Efeitos secundários                           │
│     • Sink: Permanência da mudança                           │
│                                                               │
│  6. VALIDAR MODELO (Calibrate)                               │
│     • Comparar previsão vs resultado                         │
│     • Calcular erro de predição                              │
│     • Atualizar modelo mental                                │
│                                                               │
│  7. ITERAR (Repeat)                                          │
│     • Usar modelo atualizado                                 │
│     • Prever próximo resultado                               │
│     • Reduzir erro progressivamente                          │
│                                                               │
└──────────────────────────────────────────────────────────────┘
```

#### Métricas de Impacto

```python
def measure_impact(baseline, result):
    """
    Mede impacto de uma mutação (Stone Throw)
    """
    return {
        'splash': {
            # Impacto imediato no fitness primário
            'value': result.fitness - baseline.fitness,
            'magnitude': abs(result.fitness - baseline.fitness)
        },
        'ripples': {
            # Efeitos secundários em outras métricas
            'efficiency_delta': result.efficiency - baseline.efficiency,
            'robustness_delta': result.robustness - baseline.robustness,
            'verify_delta': result.verify_score - baseline.verify_score
        },
        'sink': {
            # Permanência (medida em gerações futuras)
            'generations_retained': count_trait_retention(result),
            'offspring_inheritance': calculate_inheritance_rate(result)
        }
    }
```

#### Calibração do Modelo Preditivo

```python
def calibrate_model(predictions, results):
    """
    Calibra modelo preditivo com base em erros
    """
    errors = []
    for pred, res in zip(predictions, results):
        error = abs(pred.expected_fitness - res.actual_fitness)
        errors.append({
            'mutation_type': pred.mutation_type,
            'predicted': pred.expected_fitness,
            'actual': res.actual_fitness,
            'error': error,
            'error_pct': error / pred.expected_fitness * 100
        })

    # Calcular erro médio por tipo de mutação
    mutation_errors = {}
    for e in errors:
        mt = e['mutation_type']
        if mt not in mutation_errors:
            mutation_errors[mt] = []
        mutation_errors[mt].append(e['error_pct'])

    # Atualizar modelo
    for mt, errs in mutation_errors.items():
        avg_error = sum(errs) / len(errs)
        model.update_confidence(mt, avg_error)

    return model
```

#### Dashboard Stone Throw

```
┌──────────────────────────────────────────────────────────────┐
│                 STONE THROW DASHBOARD                         │
├──────────────────────────────────────────────────────────────┤
│                                                               │
│  ALVO ATUAL:                                                  │
│  • Task Performance: 90%+                                    │
│  • Efficiency: 80%+                                          │
│  • Robustness: 85%+                                          │
│  • Hallucination Resistance: 95%+                            │
│                                                               │
│  ÚLTIMO LANÇAMENTO:                                          │
│  ├── Pedra: ADD_VALIDATION + RESTRUCTURE                     │
│  ├── Força: Intensity 2                                      │
│  ├── Previsão: +8% fitness                                   │
│  ├── Resultado: +6% fitness                                  │
│  └── Erro: 25% (modelo precisa ajuste)                       │
│                                                               │
│  CALIBRAÇÃO DO MODELO:                                       │
│  ├── ADD_EXAMPLE: Erro médio 14%                             │
│  ├── ADD_CONSTRAINT: Erro médio 40%  ← PRECISA AJUSTE        │
│  ├── RESTRUCTURE: Erro médio 12%                             │
│  └── ADD_VALIDATION: Erro médio 18%                          │
│                                                               │
│  PRÓXIMA AÇÃO RECOMENDADA:                                   │
│  ├── Baseado no modelo: ADD_EXAMPLE                          │
│  ├── ROI esperado: +12% fitness                              │
│  └── Confiança: 85%                                          │
│                                                               │
└──────────────────────────────────────────────────────────────┘
```

---

## PROCESSO COMPLETO METACOG-EVOLUTION

### FASE 0: META-PREPARAÇÃO

```markdown
Antes de iniciar evolução:

1. **Avaliar Complexidade**
   - Espaço de soluções é grande?
   - Tem dados de validação suficientes?
   - Qual é o budget de iterações?

2. **Selecionar Modo Inicial**
   - Complexidade alta → Sistema 1 (explorar)
   - Complexidade baixa → Sistema 2 (refinar)
   - Incerto → Sistema 1 primeiro

3. **Configurar Island Populations**
   - Definir tamanho de cada ilha
   - Configurar parâmetros por ilha
   - Estabelecer protocolo de migração

4. **Definir Objetivos Pareto**
   - Quais dimensões importam?
   - Quais são os pesos relativos?
   - Qual é o target mínimo por dimensão?

5. **Inicializar Stone Throw**
   - Definir alvo
   - Catalogar mutações disponíveis
   - Estabelecer baseline preditivo
```

### FASE 1: INICIALIZAÇÃO CONSCIENTE

```markdown
## FASE 1: INICIALIZAÇÃO

### 1.1 Prompt Ancestral + VERIFY Check

Antes de começar evolução:
□ Aplicar SELF-FAMILIARITY ao prompt base
□ Identificar claims que podem alucinhar
□ Calcular SUScore inicial
□ Documentar limitações conhecidas

### 1.2 Test Cases + Uncertainty Mapping

Para cada test case:
□ Calcular SUScore do expected output
□ Identificar casos de alta incerteza
□ Ajustar peso se incerteza alta
□ Documentar riscos por caso

### 1.3 Island Populations Setup

□ Criar população inicial em cada ilha
□ Verificar diversidade genética
□ Configurar migration controller
□ Estabelecer métricas de monitoramento

### 1.4 Baseline Multi-Objetivo

Avaliar ancestral em todas dimensões:
□ Task Performance: __/100
□ Efficiency: __/100
□ Robustness: __/100
□ Hallucination Resistance: __/100
□ Pareto Fitness: [__, __, __, __]
```

### FASE 2: EVOLUÇÃO META-MONITORADA

```markdown
## FASE 2: LOOP EVOLUTIVO

for generation in range(max_generations):

    ### 2.1 META-CHECK (início de cada geração)
    □ Sistema atual (1 ou 2) ainda é apropriado?
    □ Parâmetros precisam ajuste?
    □ Migração inter-ilhas necessária?

    ### 2.2 VARIAÇÃO (por ilha)
    for island in [exploitation, exploration, hybrid]:
        □ Aplicar operadores conforme estratégia da ilha
        □ Documentar genealogia de cada variante
        □ Registrar hipóteses (Stone Throw)

    ### 2.3 AVALIAÇÃO PARETO
    for variant in all_variants:
        □ Calcular fitness em 4 dimensões
        □ Determinar dominância Pareto
        □ Atualizar Pareto Frontier

    ### 2.4 SELEÇÃO NATURAL (por ilha)
    for island in islands:
        □ Aplicar selection_rate da ilha
        □ Preservar elite (melhor da geração anterior)
        □ Cullar bottom performers

    ### 2.5 META-ANÁLISE (fim de cada geração)
    □ Comparar previsões vs resultados (Stone Throw)
    □ Atualizar modelo preditivo
    □ Ajustar parâmetros adaptativos
    □ Decidir: continuar ou convergência?

    ### 2.6 MIGRAÇÃO (a cada 3 gerações)
    if generation % 3 == 0:
        □ Top 1 de cada ilha migra para outras
        □ Verificar diversidade pós-migração
```

### FASE 3: VERIFICAÇÃO PROFUNDA

```markdown
## FASE 3: VERIFY EM VARIANTES TOP

Para top 5 variantes do Pareto Frontier:

### 3.1 VERIFY Completo (6 etapas)
□ V - Validate Familiarity
□ E - Evaluate Uncertainty (SUScore)
□ R - Review Two-Pass
□ I - Iterate Chain-Query para spans incertos
□ F - Flag Confidence em todo output
□ Y - Yield apenas claims verificados

### 3.2 Uncertainty Mapping
□ Gerar mapa de incerteza para cada variante
□ Identificar áreas de risco
□ Documentar claims não verificáveis

### 3.3 Calibração de Confiança
□ Verificar correlação confiança × acurácia
□ Ajustar flags se descalibrado
□ Recalcular Hallucination Resistance
```

### FASE 4: FINALIZAÇÃO CONSCIENTE

```markdown
## FASE 4: ENTREGA

### 4.1 Champion Selection (Pareto-optimal)
□ Identificar variantes no Pareto Frontier
□ Apresentar trade-offs ao usuário
□ Recomendar champion baseado em prioridades

### 4.2 Meta-Relatório Evolutivo
□ Documentar dinâmica evolutiva
□ Quais mutações foram mais efetivas?
□ Como Island Populations performaram?
□ Qual foi a calibração final do Stone Throw?

### 4.3 Documentação de Limitações
□ Áreas de incerteza no champion
□ Edge cases não testados
□ Riscos conhecidos

### 4.4 Uncertainty Map do Champion
□ Visualização de confiança por seção
□ Claims que requerem verificação
□ Sugestões para usuário
```

---

## PARÂMETROS ADAPTATIVOS

### Auto-Ajuste de Mutation Rate

```python
def adaptive_mutation_rate(history):
    """
    Ajusta mutation_rate baseado em performance
    """
    current_rate = config.mutation_rate

    # Detectar plateau
    if fitness_plateau(history, window=2):
        # Fitness não melhorou significativamente
        current_rate += 0.15  # Mais exploração
        log("Plateau detectado: aumentando mutation_rate")

    # Detectar melhoria rápida
    elif rapid_improvement(history, threshold=0.10):
        # Fitness está subindo bem
        current_rate -= 0.10  # Menos perturbação
        log("Melhoria rápida: diminuindo mutation_rate")

    # Clamp para range válido
    return clamp(current_rate, min=0.30, max=0.90)

def fitness_plateau(history, window=2):
    """
    True se melhoria < 2% nas últimas `window` gerações
    """
    if len(history) < window + 1:
        return False

    recent = history[-window:]
    improvement = (recent[-1].best_fitness - recent[0].best_fitness)
    return improvement < 0.02

def rapid_improvement(history, threshold=0.10):
    """
    True se melhoria > threshold na última geração
    """
    if len(history) < 2:
        return False

    improvement = history[-1].best_fitness - history[-2].best_fitness
    return improvement > threshold
```

### Auto-Ajuste de Mutation Intensity

```python
def adaptive_mutation_intensity(history, current_intensity):
    """
    Ajusta número de operadores por mutação
    """
    if fitness_plateau(history, window=3):
        # Plateau prolongado: mutações mais radicais
        return min(current_intensity + 1, 4)

    elif fitness_regression(history):
        # Regressão: mutações mais conservadoras
        return max(current_intensity - 1, 1)

    return current_intensity
```

### Tabela de Ajustes

| Condição | Mutation Rate | Mutation Intensity | Ação |
|----------|---------------|-------------------|------|
| Plateau (2+ gens) | +0.15 | +1 | Explorar mais |
| Melhoria rápida (>10%) | -0.10 | -1 | Explorar menos |
| Alta diversidade | -0.05 | = | Já tem diversidade |
| Baixa diversidade | +0.10 | +1 | Precisa diversidade |
| Regressão | = | -1 | Ser conservador |

---

## INTEGRAÇÃO COM VERIFY

### VERIFY em Cada Etapa

```
METACOG-EVOLUTION + VERIFY
│
├── FASE 0: Meta-Preparação
│   └── VERIFY: Avaliar familiaridade com domínio
│
├── FASE 1: Inicialização
│   ├── VERIFY: Check no prompt ancestral
│   └── VERIFY: Uncertainty map nos test cases
│
├── FASE 2: Evolução
│   ├── VERIFY: SUScore em variantes promissoras
│   └── VERIFY: Two-Pass em top performers
│
├── FASE 3: Verificação Profunda
│   ├── VERIFY: 6 etapas completas em top 5
│   ├── VERIFY: ICQ para spans incertos
│   └── VERIFY: Confidence flags obrigatórios
│
└── FASE 4: Finalização
    ├── VERIFY: Champion com todas verificações
    └── VERIFY: Uncertainty map na documentação
```

### Hallucination Resistance como Dimensão Pareto

```python
def calculate_hallucination_resistance(variant):
    """
    Dimensão Pareto: resistência a alucinações
    """
    # Aplicar VERIFY
    verify_result = verify_framework.evaluate(variant)

    # Componentes
    familiarity_score = verify_result.familiarity  # 0-100
    suscore_inverse = 100 - (verify_result.suscore * 100)  # 0-100
    two_pass_score = verify_result.two_pass_accuracy  # 0-100
    calibration_score = verify_result.confidence_calibration  # 0-100

    # Média ponderada
    resistance = (
        familiarity_score * 0.25 +
        suscore_inverse * 0.25 +
        two_pass_score * 0.30 +
        calibration_score * 0.20
    )

    return resistance
```

---

## AGENTES DO METACOG-EVOLUTION

### Ecossistema de Agentes

```
┌──────────────────────────────────────────────────────────────┐
│                    AGENTES METACOG-EVOLUTION                  │
├──────────────────────────────────────────────────────────────┤
│                                                               │
│  ORQUESTRAÇÃO                                                │
│  ├── Clone Orchestrator - Coordenação geral                  │
│  └── Meta-Cognition Monitor - Observa e ajusta processo      │
│                                                               │
│  EVOLUÇÃO                                                    │
│  ├── TOT-Evolution Optimizer - Executa loop evolutivo        │
│  ├── Island Population Controller - Gerencia 3 ilhas         │
│  └── Stone Throw Experimenter - Calibra modelo mental        │
│                                                               │
│  VERIFICAÇÃO                                                 │
│  ├── Hallucination Detector - Framework VERIFY               │
│  └── Validation Engineer - ORACLE + VERIFY                   │
│                                                               │
│  REFINAMENTO                                                 │
│  └── Evolution Specialist - EVOLVE+ framework                │
│                                                               │
└──────────────────────────────────────────────────────────────┘
```

### Fluxo de Trabalho Entre Agentes

```
1. Clone Orchestrator recebe solicitação
   │
2. Meta-Cognition Monitor avalia:
   ├── Complexidade → Sistema 1 ou 2?
   ├── Objetivos → Dimensões Pareto?
   └── Configuração → Parâmetros iniciais
   │
3. TOT-Evolution Optimizer executa:
   ├── Loop evolutivo principal
   └── Coordena com Island Population Controller
   │
4. Island Population Controller:
   ├── Gerencia 3 ilhas
   ├── Controla migração
   └── Monitora diversidade
   │
5. Stone Throw Experimenter:
   ├── Registra previsões
   ├── Compara com resultados
   └── Calibra modelo preditivo
   │
6. Hallucination Detector (VERIFY):
   ├── Aplica 6 etapas em top variantes
   ├── Gera uncertainty maps
   └── Calcula Hallucination Resistance
   │
7. Validation Engineer certifica:
   ├── ORACLE expandido com VERIFY
   └── Certificação final
   │
8. Evolution Specialist refina (se necessário):
   └── EVOLVE+ para polish final
   │
9. Entrega:
   ├── Champion Pareto-optimal
   ├── Uncertainty map
   └── Meta-relatório
```

---

## MÉTRICAS E KPIs

### Métricas de Processo

| Métrica | Definição | Baseline | Target |
|---------|-----------|----------|--------|
| Gerações até convergência | Iterações necessárias | 4-6 | 3-5 |
| Taxa de melhoria por geração | Δ fitness por gen | +5-15% | +10-20% |
| Diversidade populacional | Std dev de fitness | 0.1-0.2 | 0.15-0.25 |
| Erro de predição (Stone Throw) | Previsão vs resultado | N/A | < 20% |
| Migração efetiva | % de migrantes que sobrevivem | N/A | > 50% |

### Métricas de Resultado

| Métrica | Definição | Baseline | Target |
|---------|-----------|----------|--------|
| Task Performance | Accuracy em test cases | Variável | 90%+ |
| Efficiency | Tokens / performance | Variável | Pareto-optimal |
| Robustness | Consistency | Variável | 85%+ |
| Hallucination Resistance | VERIFY score | N/A | 95%+ |
| Pareto Frontier Size | Soluções não-dominadas | 1 | 3-5 |

### Métricas de Meta-Cognição

| Métrica | Definição | Target |
|---------|-----------|--------|
| Plateau Detection Accuracy | % de plateaus corretamente detectados | > 90% |
| System Selection Accuracy | % de vezes que sistema correto foi usado | > 80% |
| Parameter Adaptation Effectiveness | Melhoria após ajuste | > 5% |
| Model Calibration | Correlação previsão × resultado | > 0.8 |

---

## CHECKLIST DE EXECUÇÃO

### Antes de Começar

```markdown
□ Prompt ancestral definido e VERIFY-checked
□ Test cases criados com uncertainty mapping
□ Objetivos Pareto definidos com pesos
□ Island Populations configuradas
□ Stone Throw baseline estabelecido
□ Métricas de sucesso definidas
```

### Durante Evolução

```markdown
□ Meta-Monitor ativo a cada geração
□ Sistema 1/2 alternando conforme necessário
□ Parâmetros adaptativos ajustando
□ Migração inter-ilhas ocorrendo
□ Stone Throw registrando e calibrando
□ VERIFY em variantes promissoras
```

### Após Convergência

```markdown
□ VERIFY completo em Pareto Frontier
□ Champion selecionado e documentado
□ Uncertainty map gerado
□ Meta-relatório criado
□ Limitações documentadas
□ Recomendações para usuário
```

---

## REFERÊNCIAS E INSPIRAÇÕES

### Fundamentos Científicos

1. **Teoria da Evolução** (Darwin) - Variação, seleção, hereditariedade
2. **Dual Process Theory** (Kahneman) - Sistema 1 e 2
3. **Pareto Optimization** - Otimização multi-objetivo
4. **Island Model** (Wright) - Populações isoladas com migração
5. **Meta-Learning** - Aprender a aprender

### Papers Relevantes

1. **EvoAgent** - Multi-agent generation via evolutionary algorithms
2. **EvoPrompt** - Evolutionary prompt optimization
3. **Tree-of-Thoughts** - Deliberative reasoning
4. **Reflexion** - Self-reflection for LLMs
5. **Constitutional AI** - Principles-based optimization

---

**Framework mantido por:** Equipe METACOG-EVOLUTION
**Última atualização:** 2025-12-16
**Versão:** 2.0
**Status:** Production-ready
**Substitui:** TOT-EVOLUTION 1.0
