# FRAMEWORK TOT-EVOLUTION (DEPRECADO)

> **AVISO DE DEPRECIACAO:** Este framework foi substituido pelo **METACOG-EVOLUTION**.
>
> O METACOG-EVOLUTION adiciona:
> - Sistema Dual (Sistema 1/2) para meta-cognicao
> - Island Populations para diversidade genetica
> - Otimizacao Pareto multi-objetivo
> - Framework VERIFY anti-alucinacao
> - Stone Throw Protocol para calibracao do modelo mental
> - Parametros adaptativos dinamicos
>
> **Para novos projetos, use:** `frameworks/METACOG-EVOLUTION.md`
>
> Este arquivo eh mantido apenas para referencia historica.

---

# FRAMEWORK TOT-EVOLUTION 1.0 (Legacy)

## Sistema de Otimização Evolutiva de Prompts

---

## O QUE É TOT-EVOLUTION?

**TOT-Evolution** (Tree-of-Thoughts Evolution) é um framework que aplica **princípios darwinianos** para otimizar prompts através de gerações sucessivas, descobrindo automaticamente estruturas ótimas através de:

- **Variação** (Mutação + Crossover)
- **Seleção Natural** (Fitness-based survival)
- **Hereditariedade** (Características dos pais)
- **Adaptação** (Convergência para ótimo)

### Inspiração Científica

```
Biologia Evolutiva    →    Otimização de Prompts
─────────────────────────────────────────────────
DNA                   →    Texto do Prompt
Mutação               →    Modificação estrutural
Crossover             →    Combinação de 2 prompts
Fitness               →    Performance em test cases
Geração               →    Iteração de otimização
Seleção Natural       →    Top performers sobrevivem
Convergência          →    Otimização alcançada
```

---

## 🎯 QUANDO USAR TOT-EVOLUTION

### ✅ Use TOT-Evolution Quando:

1. **Otimização manual plateou**
   - Você já tentou otimizar manualmente
   - Ganhos marginais estão diminuindo
   - Quer explorar espaço de soluções sistematicamente

2. **Espaço de soluções é grande**
   - Muitas variações possíveis do prompt
   - Não está claro qual estrutura é ótima
   - Quer descobrir patterns não-óbvios

3. **Tem dados para validação**
   - Test cases disponíveis (input → expected output)
   - Métricas objetivas de sucesso definidas
   - Pode executar avaliações automaticamente

4. **Precisa de A/B testing em escala**
   - Quer testar 20+ variações
   - Busca otimização quantitativa
   - Tempo não é limitante crítico

5. **Otimização contínua é necessária**
   - Produção gera dados novos constantemente
   - Prompt precisa se adaptar a mudanças
   - Melhoria contínua é prioridade

### ❌ NÃO Use TOT-Evolution Quando:

1. **Prompt já funciona bem** (>90% accuracy)
2. **Sem test cases** para calcular fitness
3. **Urgência extrema** (evolução leva tempo)
4. **Espaço de soluções é trivial** (poucas variações)
5. **Recursos computacionais limitados** (muitas avaliações necessárias)

---

## 🧬 OS 4 PRINCÍPIOS DARWINIANOS

### 1. VARIAÇÃO (Diversidade Genética)

**Definição:** Criar variações do prompt através de mutação e crossover.

#### Tipos de Mutação:

**ADD_DETAIL** - Inserção de informação
```
Antes: "Classify this message"
Depois: "Classify this message. Be specific and cite evidence."
```

**ADD_CONSTRAINT** - Restrição adicional
```
Antes: "Summarize the text"
Depois: "Summarize the text in under 50 words."
```

**ADD_EXAMPLE** - Demonstração concreta
```
Antes: "Extract entities"
Depois: "Extract entities\nExample: 'John works at Google' → Person: John, Org: Google"
```

**RESTRUCTURE** - Reorganização estrutural
```
Antes: "Do X and Y"
Depois: "Task: Do X\nThen: Do Y\nFormat: [structured output]"
```

**ADD_VALIDATION** - Checklist de qualidade
```
Antes: "Generate code"
Depois: "Generate code\n\nVerify:\n□ Syntax correct\n□ Edge cases handled"
```

**CHANGE_TONE** - Ajuste de estilo
```
Antes: "You are a helpful assistant"
Depois: "You are a professional, concise technical advisor"
```

**SIMPLIFY** - Redução de complexidade
```
Antes: [prompt de 200 palavras com redundâncias]
Depois: [prompt de 100 palavras, essencial]
```

#### Operadores de Crossover:

**Single-Point Crossover**
```
Parent A: [Parte 1A][Parte 2A]
Parent B: [Parte 1B][Parte 2B]
          ↓ cut point
Child:    [Parte 1A][Parte 2B]
```

**Multi-Point Crossover**
```
Parent A: [P1A][P2A][P3A][P4A]
Parent B: [P1B][P2B][P3B][P4B]
          ↓     ↓     ↓
Child:    [P1A][P2B][P3A][P4B]
```

**Semantic Crossover**
```
Combina conceitos semânticos:
- Instruções de A + Exemplos de B
- Tom de A + Estrutura de B
```

---

### 2. HEREDITARIEDADE (Transmissão de Características)

**Definição:** Organismos filhos herdam características dos pais.

```
Geração N: Parent com alta fitness
           ├─ Trait 1: Estrutura clara ✓
           ├─ Trait 2: Exemplos concretos ✓
           └─ Trait 3: Tom apropriado ✓
           ↓
Geração N+1: Child herda traits 1, 2, 3
             + Nova mutação (Trait 4: Validação)
```

**Rastreamento Genealógico:**
```
G0-ANCESTOR
    ├─→ G1-M1 (mutação add_detail)
    │    └─→ G2-C1 (crossover G1-M1 + G1-M3)
    │         └─→ G3-C2 (mutação restructure)
    │              └─→ CHAMPION ✓
    └─→ G1-M3 (mutação add_example)
```

---

### 3. SELEÇÃO NATURAL (Survival of the Fittest)

**Definição:** Apenas os mais aptos (maior fitness) sobrevivem para reproduzir.

#### Função Fitness:

```python
def calculate_fitness(prompt_organism):
    """
    Fitness = Quão bem o prompt performa

    Componentes:
    1. Task Performance (40-60%) - Accuracy nos test cases
    2. Constraint Satisfaction (20-30%) - Atende restrições
    3. Quality Metrics (10-20%) - Clareza, coerência
    4. Efficiency (10-20%) - Tokens, latência
    """

    scores = []

    # Testar em cada test case
    for test in test_cases:
        response = execute_prompt(prompt_organism, test['input'])
        score = evaluate_response(response, test['expected'])
        scores.append(score)

    # Fitness = média ponderada
    task_performance = mean(scores) * 0.5
    constraint_satisfaction = check_constraints(prompt_organism) * 0.3
    quality = assess_quality(prompt_organism) * 0.1
    efficiency = calculate_efficiency(prompt_organism) * 0.1

    fitness = (task_performance + constraint_satisfaction +
               quality + efficiency)

    return fitness  # 0.0 a 1.0
```

#### Estratégias de Seleção:

**Elitismo** (Recomendado)
```
Top 50% da população sobrevive
→ Garante que melhores genes não se percam
```

**Tournament Selection**
```
Seleciona aleatoriamente 3 organismos
→ O melhor dos 3 avança
→ Introduz diversidade mantendo pressão seletiva
```

**Fitness Proportionate**
```
Probabilidade de seleção ∝ fitness
→ Mais aptos têm mais chances, mas não garantido
```

---

### 4. ADAPTAÇÃO (Convergência para Ótimo)

**Definição:** População converge para solução ótima através de gerações.

#### Critérios de Convergência:

**1. Plateau de Fitness**
```python
if (best_fitness_gen_N - best_fitness_gen_N-1) < 0.01:
    # Melhoria < 1% → Convergiu
    return True
```

**2. Homogeneidade Populacional**
```python
if std_deviation(population_fitness) < 0.05:
    # População muito similar → Convergiu
    return True
```

**3. Gerações Máximas**
```python
if generation >= max_generations:
    # Limite de recursos → Parar
    return True
```

#### Curva Típica de Evolução:

```
Fitness
  1.0 ┤                    ╭──────────
      │                  ╭─╯ (Plateau)
  0.9 ┤              ╭──╯
      │          ╭───╯
  0.8 ┤      ╭──╯
      │  ╭──╯ (Crescimento rápido)
  0.7 ┼──╯
      │
  0.6 ┤ (Baseline)
      └────┬────┬────┬────┬────┬────→
          G0   G1   G2   G3   G4   G5
```

---

## 🔄 PROCESSO COMPLETO: PASSO A PASSO

### FASE 1: INICIALIZAÇÃO (30 min)

#### 1.1 Definir Prompt Ancestral

```markdown
# Prompt Base (Geração 0)

Objetivo: [O que o prompt deve fazer]

Prompt Original:
"""
[Seu prompt inicial aqui]
"""

Contexto: [Onde será usado]
Usuário: [Quem vai usar]
```

#### 1.2 Criar Test Cases (Fitness Function)

```python
test_cases = [
    {
        'id': 'TC001',
        'input': "...",
        'expected': "...",
        'weight': 1.0  # Importância relativa
    },
    {
        'id': 'TC002',
        'input': "...",
        'expected': "...",
        'weight': 1.5  # Mais importante
    },
    # Mínimo: 5-10 test cases
    # Ideal: 20-50 test cases
    # Cobertura: Casos típicos + edge cases
]
```

**Checklist de Test Cases:**
- [ ] Cobre casos típicos (70%)
- [ ] Inclui edge cases (20%)
- [ ] Testa casos de erro (10%)
- [ ] Expected outputs são verificáveis objetivamente
- [ ] Variedade suficiente para generalização

#### 1.3 Configurar Parâmetros Evolutivos

```python
evolution_config = {
    'population_size': 4,      # Organismos por geração
    'max_generations': 5,      # Limite de iterações
    'selection_rate': 0.5,     # Top 50% sobrevive
    'mutation_rate': 0.6,      # 60% mutação vs crossover
    'mutation_types': [        # Operadores permitidos
        'add_detail',
        'add_constraint',
        'add_example',
        'restructure'
    ],
    'convergence_threshold': 0.01  # Melhoria mínima para continuar
}
```

---

### FASE 2: EVOLUÇÃO (1-3 horas)

#### Loop Evolutivo:

```python
for generation in range(max_generations):

    # 2.1 VARIAÇÃO
    if generation == 0:
        # Criar população inicial
        population = create_mutations(ancestor, population_size)
    else:
        # Reproduzir a partir de sobreviventes
        population = reproduce(survivors, population_size)

    # 2.2 AVALIAÇÃO
    for organism in population:
        organism.fitness = calculate_fitness(organism)

    # 2.3 SELEÇÃO NATURAL
    survivors = select_top_performers(population, selection_rate)

    # 2.4 REGISTRO
    log_generation(generation, population, survivors)

    # 2.5 CONVERGÊNCIA?
    if has_converged(population):
        print(f"Convergiu na geração {generation}")
        break

# RESULTADO
champion = max(all_organisms, key=lambda x: x.fitness)
```

#### Exemplo de Output (Geração 2):

```
📊 GERAÇÃO 2
────────────────────────────────────────
Avaliando população...
  G2-C1: Fitness = 0.87 | Parents: [G1-M2, G1-M4]
  G2-C2: Fitness = 0.91 | Parents: [G1-M4]
  G2-C3: Fitness = 0.85 | Parents: [G1-M2]
  G2-C4: Fitness = 0.93 | Parents: [G1-M2, G1-M4]

🧬 Seleção Natural: 2/4 sobreviveram
   ✓ G2-C4: 0.93 (crossover + add_validation)
   ✓ G2-C2: 0.91 (mutação add_example)

Melhoria vs G1: +8%
Status: Continuando evolução...
```

---

### FASE 3: FINALIZAÇÃO (30 min)

#### 3.1 Análise do Campeão

```markdown
# CHAMPION PROMPT

**ID:** G4-C2
**Fitness:** 0.96 (96% accuracy)
**Geração:** 4
**Genealogia:** G0-ANCESTOR → G1-M3 → G2-C4 → G3-C1 → G4-C2

**Mutações Aplicadas:**
1. add_example (G1)
2. restructure (G2)
3. add_validation (G3)
4. add_constraint (G4)

**Prompt Final:**
"""
[Prompt otimizado aqui]
"""

**Performance:**
- Accuracy: 96% (vs 68% baseline) → +41%
- Consistency: 94% (vs 65% baseline) → +45%
- Token efficiency: 120 tokens (vs 150) → -20%
```

#### 3.2 Árvore Evolutiva Completa

```
                    G0-ANCESTOR (0.68)
                         ↓
          ┌──────────────┼──────────────┐
    G1-M1 (0.71)    G1-M3 (0.78)    G1-M4 (0.74)
          ↓              ↓              ↓
          │         G2-C4 (0.93) ←──────┘
          │              ↓
          │         G3-C1 (0.94)
          │              ↓
          └─────→   G4-C2 (0.96) ★ CHAMPION
```

#### 3.3 Relatório de Evolução

```markdown
# RELATÓRIO DE EVOLUÇÃO TOT

## Sumário Executivo
- Gerações: 5
- Organismos testados: 20
- Fitness inicial: 0.68
- Fitness final: 0.96
- Melhoria: +41%
- Tempo total: 2.5 horas

## Dinâmica Evolutiva

### Fase Exploratória (G0-G1)
- Alta variação
- Descoberta de estruturas promissoras
- Melhor mutação: add_example (+10%)

### Fase de Otimização (G2-G3)
- Refinamento de variantes boas
- Crossover efetivo entre linhagens
- Ganhos incrementais (+6% por geração)

### Fase de Convergência (G4-G5)
- Melhorias marginais (<2%)
- População homogênea
- Critério de parada atingido

## Lições Aprendidas

**O que funcionou:**
✓ Adicionar exemplos concretos (+15% fitness)
✓ Reestruturar em formato task-based (+8%)
✓ Validação checklist (+5%)

**O que não funcionou:**
✗ Simplificação excessiva (-3% fitness)
✗ Mudança de tom formal→casual (-2%)

## Recomendações

1. **Deploy:** Champion (G4-C2) pronto para produção
2. **Monitoramento:** Acompanhar performance em prod
3. **Re-evolução:** Se accuracy cair <90%, re-otimizar
4. **Continuous:** Adicionar casos de falha aos test cases
```

---

## 📊 MÉTRICAS E KPIs

### Métricas de Processo

|Métrica|Definição|Target|
|---|---|---|
|**Gerações até Convergência**|Número de iterações necessárias|3-7|
|**Taxa de Melhoria**|Δ fitness por geração|+5-15% por gen|
|**Diversidade Populacional**|Std dev de fitness na população|0.1-0.2|
|**Tempo por Geração**|Minutos para avaliar 1 geração|10-30 min|

### Métricas de Resultado

|Métrica|Baseline|Champion|Melhoria|
|---|---|---|---|
|**Accuracy**|68%|96%|**+41%**|
|**Precision**|65%|93%|**+43%**|
|**Recall**|70%|94%|**+34%**|
|**F1 Score**|0.67|0.94|**+40%**|
|**Consistency**|65%|94%|**+45%**|
|**Token Efficiency**|150|120|**-20%**|

---

## 🎯 CASOS DE USO VALIDADOS

### Caso 1: Classificador de Leads (Nicolas)

**Problema:** Classificar mensagens de clientes em HOT/WARM/COLD

**Baseline (G0):**
```
Classify this message: {input}
Classification:
```
Accuracy: 68%

**Champion (G5):**
```
Task: Classify customer lead urgency level

Criteria:
HOT: Urgency keywords + specific pain + budget mention
WARM: Interest expressed but no urgency indicators
COLD: General curiosity only, no commitment signals

Examples:
"Need solution ASAP, what's the price?" → HOT
"Interested in learning more" → WARM
"Just curious, does this work?" → COLD

Before responding, verify:
□ Classification matches ≥2 criteria
□ Confidence level appropriate
□ Edge cases considered

Message: {input}
Classification:
```
Accuracy: 96% (+41%)

---

### Caso 2: Agente Conversacional "Flora"

**Problema:** Assistente virtual para loja de produtos naturais

**Baseline (G0):**
```
You are Flora, a helpful assistant for natural products store.

Customer: {input}
Flora:
```
Satisfaction: 6.8/10

**Champion (G4):**
```
You are Flora, virtual wellness consultant for Natura Shop.

Core Personality:
- Warm and knowledgeable (like talking to friend who's also expert)
- Professional but conversational (2-4 sentences per message)
- Evidence-based (cite benefits, not medical claims)

Always:
✓ Greet returning customers by name
✓ Reference past purchases for recommendations
✓ Ask 1 clarifying question if need unclear

Never:
✗ Make medical claims or diagnoses
✗ Push products not relevant to need
✗ Use excessive technical jargon

Context:
Customer: {name} | History: {purchases} | Current: {message}

Flora's Response:
```
Satisfaction: 9.2/10 (+35%)

---

### Caso 3: Code Review Agent

**Problema:** Revisar pull requests automaticamente

**Baseline (G0):**
```
Review this code for issues:
{code}
```
Usefulness: 5.2/10

**Champion (G6):**
```
Task: Comprehensive code review

Code to review:
```{language}
{code}
```

Review checklist:
□ Functionality: Does it work as intended?
□ Security: Any vulnerabilities? (SQL injection, XSS, etc.)
□ Performance: Bottlenecks or inefficiencies?
□ Maintainability: Is it readable and well-structured?
□ Best Practices: Follows language conventions?

For each issue found:
1. Severity: [CRITICAL/MAJOR/MINOR]
2. Location: [Line number]
3. Issue: [Clear description]
4. Fix: [Concrete suggestion]
5. Rationale: [Why it matters]

Format:
```markdown
## 🔴 Critical Issues
[issues]

## 🟡 Major Issues
[issues]

## 🔵 Minor Issues
[issues]

## ✅ Strengths
[positive points]
```

Review:
```
Usefulness: 8.9/10 (+71%)

---

## 🔧 IMPLEMENTAÇÃO PRÁTICA

### Script Python Completo

Ver arquivo completo fornecido pelo usuário (sistema evolutivo completo implementado).

### Uso Básico:

```python
from tot_evolution import EvolutionaryToT

# 1. Definir prompt base
base_prompt = "Your initial prompt here"

# 2. Criar test cases
test_cases = [
    {'input': '...', 'expected': '...'},
    {'input': '...', 'expected': '...'},
    # ... mais casos
]

# 3. Configurar e executar evolução
evolution = EvolutionaryToT(
    base_prompt=base_prompt,
    test_cases=test_cases,
    population_size=4,
    max_generations=5
)

# 4. EVOLUIR!
champion = evolution.evolve()

# 5. Visualizar árvore evolutiva
evolution.visualize_evolution()

# 6. Exportar resultado
evolution.export_best_prompt("optimized_prompt.txt")
```

---

## 🔬 INTEGRAÇÃO COM FRAMEWORKS EXISTENTES

### TOT-Evolution + DSPy

```python
# Fase 1: Evolução darwiniana
evolution = EvolutionaryToT(base, tests)
evolved_prompt = evolution.evolve()

# Fase 2: Compilação DSPy
dspy_compiled = dspy.compile(
    evolved_prompt,
    trainset=larger_dataset
)

# Resultado: Melhor dos dois mundos
# - Evolução descobre estrutura ótima
# - DSPy otimiza few-shot examples
```

### TOT-Evolution + Prompt Architect

```python
# Fase 1: Otimização manual (Prompt Architect)
manually_optimized = prompt_architect.optimize(base_prompt)

# Fase 2: Otimização evolutiva (TOT-Evolution)
evolution = EvolutionaryToT(manually_optimized, tests)
final_prompt = evolution.evolve()

# Sinergia: Manual descobre direção, Evolução explora espaço
```

### TOT-Evolution + Validation Engineer

```python
# Validation Engineer fornece fitness function
def fitness_function(prompt, test_case):
    response = execute_prompt(prompt, test_case['input'])

    # Usar framework ORACLE para avaliação
    validation_score = validation_engineer.validate(
        response,
        test_case['expected']
    )

    return validation_score

# TOT-Evolution usa essa função
evolution = EvolutionaryToT(
    base_prompt,
    test_cases,
    fitness_fn=fitness_function  # Custom fitness
)
```

---

## ⚠️ LIMITAÇÕES E CONSIDERAÇÕES

### Limitações Técnicas:

1. **Computacionalmente Intensivo**
   - Muitas avaliações necessárias (population × generations)
   - Pode levar horas para problemas complexos

2. **Requer Test Cases de Qualidade**
   - Fitness function é crítica
   - Test cases ruins → evolução para ótimo local errado

3. **Não Garante Ótimo Global**
   - Pode convergir para ótimo local
   - Múltiplas execuções recomendadas

4. **Interpretabilidade**
   - Champion pode ter estrutura complexa
   - Não sempre óbvio POR QUE funciona

### Considerações Práticas:

1. **Custo de API**
   - Muitas chamadas à LLM
   - Usar modelo mais barato para fitness
   - Ou simular respostas quando possível

2. **Tempo vs Qualidade**
   - Mais gerações = melhor (geralmente)
   - Mas retornos diminuem após 5-7 gerações

3. **Diversidade vs Convergência**
   - Alta diversidade = exploração
   - Baixa diversidade = exploração
   - Balancear mutation_rate e selection_rate

---

## 📚 REFERÊNCIAS CIENTÍFICAS

Este framework é baseado em:

1. **PromptBreeder** (Fernando et al. 2024)
   - Evolução genética de prompts
   - Self-referential learning

2. **EvoPrompt** (Guo et al. 2024)
   - Seleção natural de instruções
   - Genetic algorithm para otimização

3. **Tree-of-Thoughts** (Yao et al. 2023)
   - Exploração estruturada de raciocínio
   - Backtracking e pruning

4. **Reflexion** (Shinn et al. 2023)
   - Aprendizado de falhas
   - Self-reflection loops

5. **Constitutional AI** (Anthropic, 2023)
   - Refinamento iterativo
   - Principles-based optimization

---

## ✅ CHECKLIST DE EXECUÇÃO

### Antes de Começar:
- [ ] Tenho prompt base definido
- [ ] Criei 10+ test cases (input → expected)
- [ ] Expected outputs são verificáveis objetivamente
- [ ] Defini métricas de sucesso (target fitness)
- [ ] Configurei parâmetros evolutivos

### Durante Evolução:
- [ ] Monitoro fitness por geração
- [ ] Verifico se está convergindo (não estagnando)
- [ ] Analiso quais mutações funcionam melhor
- [ ] Ajusto parâmetros se necessário

### Após Convergência:
- [ ] Valido champion em test set separado
- [ ] Comparo com baseline quantitativamente
- [ ] Documento árvore evolutiva
- [ ] Exporto champion para deploy
- [ ] Planejo monitoramento em produção

---

**Framework mantido por:** Dr. Darwin Prompt (TOT-Evolution Optimizer)
**Última atualização:** 2025-12-16
**Versão:** 1.0
**Status:** Production-ready ✅
