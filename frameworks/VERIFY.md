# FRAMEWORK VERIFY

## Sistema de Prevenção e Detecção de Alucinações

---

## O QUE É O FRAMEWORK VERIFY?

**VERIFY** é um framework anti-alucinação de 6 etapas que valida o modelo mental da IA antes, durante e após a geração de respostas. O objetivo é reduzir drasticamente a taxa de alucinações através de verificação sistemática.

### O Acrônimo VERIFY

```
V - Validate Familiarity    (Validar familiaridade com conceitos)
E - Evaluate Uncertainty    (Avaliar incerteza semântica)
R - Review Two-Pass         (Revisar em duas passadas)
I - Iterate Chain-Query     (Iterar com perguntas encadeadas)
F - Flag Confidence         (Sinalizar níveis de confiança)
Y - Yield Verified Output   (Entregar output verificado)
```

### Por Que VERIFY é Necessário?

```
Problema: LLMs alucinam quando:
├── Falta familiaridade com o conceito
├── Generalizam de padrões superficiais
├── Não reconhecem limites de conhecimento
├── Confiam demais em padrões estatísticos
└── Não verificam claims antes de outputar

Solução VERIFY:
├── Pré-detecção de áreas de incerteza
├── Quantificação de confiança por claim
├── Verificação iterativa antes do output
├── Transparência sobre limitações
└── Calibração contínua do modelo mental
```

---

## OS 6 PASSOS DO VERIFY

### PASSO 1: VALIDATE FAMILIARITY (Pré-Geração)

**Objetivo:** Antes de responder, avaliar se o modelo tem familiaridade genuína com os conceitos envolvidos.

#### Técnica: SELF-FAMILIARITY Check

```markdown
Antes de gerar resposta, pergunte internamente:

1. **Reconhecimento Conceitual**
   - "Reconheço este conceito de múltiplas fontes?"
   - "Posso definir este termo sem ambiguidade?"
   - "Já vi este padrão em contextos variados?"

2. **Profundidade de Conhecimento**
   - "Sei apenas o nome ou entendo mecanismos?"
   - "Posso explicar o 'porquê' além do 'o quê'?"
   - "Conheço exceções e edge cases?"

3. **Fonte de Conhecimento**
   - "Isso vem de dados de treinamento robustos?"
   - "É conhecimento comum ou especializado?"
   - "Há risco de confusão com conceitos similares?"
```

#### Scoring de Familiaridade

```
Score 90-100: ALTA FAMILIARIDADE
  - Múltiplas fontes convergentes
  - Conhecimento profundo e mecanístico
  - Pode explicar com exemplos variados
  → Proceder com confiança

Score 70-89: FAMILIARIDADE MODERADA
  - Conhecimento superficial a médio
  - Algumas lacunas identificáveis
  → Proceder com cautela, sinalizar incertezas

Score 50-69: FAMILIARIDADE BAIXA
  - Reconhece termo mas conhecimento vago
  - Alto risco de generalização incorreta
  → Declarar limitação, buscar confirmação

Score < 50: FAMILIARIDADE INSUFICIENTE
  - Não reconhece ou conhecimento fragmentado
  → NÃO responder como se soubesse, admitir desconhecimento
```

#### Template de Validação

```markdown
## FAMILIARITY CHECK

Conceito: [nome do conceito]

□ Reconhecimento: [SIM/PARCIAL/NÃO]
□ Profundidade: [ALTA/MÉDIA/BAIXA/NENHUMA]
□ Múltiplas fontes: [SIM/NÃO]
□ Mecanismo entendido: [SIM/PARCIAL/NÃO]

**Score de Familiaridade:** __/100

**Decisão:**
- [ ] Proceder com confiança
- [ ] Proceder com cautela
- [ ] Sinalizar incerteza explicitamente
- [ ] Admitir desconhecimento
```

---

### PASSO 2: EVALUATE UNCERTAINTY (Durante Geração)

**Objetivo:** Quantificar incerteza em palavras e spans semanticamente importantes.

#### Técnica: SUScore (Substantive-word Uncertainty Score)

```markdown
Identificar e avaliar incerteza em:

1. **Palavras Substantivas**
   - Substantivos (nomes, entidades, conceitos)
   - Verbos principais (ações, processos)
   - Numerais (quantidades, datas, estatísticas)
   - Adjetivos qualificativos (características específicas)

2. **Spans de Alto Risco**
   - Afirmações factuais específicas
   - Citações ou atribuições
   - Dados numéricos precisos
   - Relações causais
   - Previsões ou projeções
```

#### Cálculo do SUScore

```python
def calculate_suscore(text):
    """
    SUScore = Média ponderada de incerteza por palavra substantiva

    Para cada palavra substantiva:
    - uncertainty = P(palavra estar incorreta)
    - weight = importância semântica (0.5 a 2.0)

    SUScore = Σ(uncertainty × weight) / Σ(weight)

    Interpretação:
    - SUScore < 0.1: Baixa incerteza (confiável)
    - SUScore 0.1-0.3: Incerteza moderada (verificar)
    - SUScore > 0.3: Alta incerteza (flags necessárias)
    """

    substantive_words = extract_substantive(text)

    total_uncertainty = 0
    total_weight = 0

    for word in substantive_words:
        uncertainty = estimate_uncertainty(word)
        weight = semantic_importance(word)
        total_uncertainty += uncertainty * weight
        total_weight += weight

    return total_uncertainty / total_weight if total_weight > 0 else 0
```

#### Uncertainty Map

```
Texto: "Einstein publicou a teoria da relatividade geral em 1915"

UNCERTAINTY MAP:
┌─────────────────────────────────────────────────────────────┐
│ Einstein      │ [LOW]  │ Entidade bem conhecida           │
│ publicou      │ [LOW]  │ Fato estabelecido                │
│ teoria da     │ [LOW]  │ Conceito bem definido            │
│ relatividade  │                                           │
│ geral         │ [LOW]  │ Distinção clara de especial      │
│ 1915          │ [LOW]  │ Data bem documentada             │
└─────────────────────────────────────────────────────────────┘

SUScore: 0.05 (Baixa incerteza - claim verificável)
```

```
Texto: "A empresa XYZ faturou R$500 milhões em 2024"

UNCERTAINTY MAP:
┌─────────────────────────────────────────────────────────────┐
│ empresa XYZ   │ [MED]  │ Entidade específica - verificar  │
│ faturou       │ [LOW]  │ Verbo comum                      │
│ R$500 milhões │ [HIGH] │ Valor numérico específico        │
│ 2024          │ [MED]  │ Ano recente - dados podem variar │
└─────────────────────────────────────────────────────────────┘

SUScore: 0.45 (Alta incerteza - verificação necessária)
```

---

### PASSO 3: REVIEW TWO-PASS (Verificação)

**Objetivo:** Gerar rascunho primeiro, depois verificar cada afirmação factual.

#### Processo Two-Pass

```
PASS 1: GERAÇÃO (Draft)
├── Gerar resposta completa
├── Não se preocupar com verificação ainda
├── Capturar todo o conteúdo relevante
└── Marcar internamente spans para verificar

PASS 2: VERIFICAÇÃO (Review)
├── Identificar cada claim factual
├── Para cada claim:
│   ├── É verificável?
│   ├── É consistente internamente?
│   ├── Contradiz conhecimento estabelecido?
│   └── Precisa de qualificação?
├── Corrigir ou qualificar claims problemáticos
└── Remover claims não verificáveis
```

#### Template Two-Pass

```markdown
## PASS 1: DRAFT

[Resposta gerada sem filtro]

---

## PASS 2: REVIEW

**Claims identificados:**

| # | Claim | Tipo | Status | Ação |
|---|-------|------|--------|------|
| 1 | [claim] | Factual | ✓ Verificado | Manter |
| 2 | [claim] | Factual | ? Incerto | Qualificar |
| 3 | [claim] | Factual | ✗ Duvidoso | Remover |
| 4 | [claim] | Opinião | N/A | Sinalizar como opinião |

**Correções aplicadas:**
- Claim 2: Adicionado "aproximadamente"
- Claim 3: Removido por falta de suporte

---

## OUTPUT FINAL

[Resposta revisada e verificada]
```

#### Checklist de Verificação

```markdown
Para cada claim factual, verificar:

□ **Consistência Interna**
  - Não contradiz outras partes da resposta
  - Logicamente coerente

□ **Consistência Externa**
  - Alinha com conhecimento estabelecido
  - Não contradiz fatos amplamente aceitos

□ **Especificidade Apropriada**
  - Números/datas são aproximados quando necessário
  - Generalização indicada quando aplicável

□ **Fonte Implícita**
  - Conhecimento comum vs. especializado
  - Contemporâneo vs. histórico

□ **Qualificação Necessária**
  - Precisa de "aproximadamente"?
  - Precisa de "tipicamente"?
  - Precisa de "segundo X"?
```

---

### PASSO 4: ITERATE CHAIN-QUERY (Validação Profunda)

**Objetivo:** Para spans de alta incerteza, gerar perguntas de validação e respondê-las iterativamente.

#### Técnica: ICQ (Iterative Chain-Query)

```markdown
Para cada span com SUScore > 0.3:

1. **Gerar Pergunta de Validação**
   - Transformar span em pergunta verificável
   - Focar no aspecto mais incerto

2. **Responder Pergunta**
   - Usar conhecimento disponível
   - Ser honesto sobre limitações

3. **Atualizar Span**
   - Se confirmado: manter
   - Se contradito: corrigir ou remover
   - Se inconclusivo: qualificar
```

#### Exemplo ICQ

```markdown
## ICQ PROCESS

**Span Original:** "O ChatGPT foi lançado em dezembro de 2022"

**SUScore:** 0.25 (moderado)

---

**Query 1:** "Em que mês de 2022 o ChatGPT foi lançado?"

**Response:** "O ChatGPT foi lançado em 30 de novembro de 2022,
tornando-se publicamente disponível. Dezembro de 2022 seria
tecnicamente incorreto, embora muito próximo."

**Decisão:** Corrigir para "novembro de 2022" ou "final de 2022"

---

**Span Atualizado:** "O ChatGPT foi lançado em novembro de 2022"

**SUScore Novo:** 0.08 (baixo - verificado)
```

#### Loop ICQ

```python
def icq_validation(spans):
    """
    Iterative Chain-Query para validação profunda
    """
    for span in spans:
        if span.suscore > 0.3:  # Alta incerteza

            # Gerar pergunta
            query = generate_validation_query(span)

            # Responder
            response = answer_query(query)

            # Avaliar
            if response.confirms(span):
                span.status = "VERIFIED"
            elif response.contradicts(span):
                span.status = "CORRECTED"
                span.text = response.correction
            else:
                span.status = "QUALIFIED"
                span.text = add_qualifier(span.text)

            # Recalcular
            span.suscore = recalculate_suscore(span)

            # Iterar se ainda incerto
            if span.suscore > 0.3:
                span = icq_validation([span])[0]

    return spans
```

---

### PASSO 5: FLAG CONFIDENCE (Sinalização)

**Objetivo:** Adicionar indicadores explícitos de confiança ao output final.

#### Níveis de Confiança

```
[HIGH] - Alta confiança
  - Fatos bem estabelecidos
  - Múltiplas fontes convergentes
  - Conhecimento amplamente aceito
  - SUScore < 0.1

[MEDIUM] - Confiança moderada
  - Fatos prováveis mas não 100% certos
  - Algumas fontes, não universalmente confirmado
  - Conhecimento especializado
  - SUScore 0.1-0.3

[LOW] - Baixa confiança
  - Incerteza significativa
  - Fontes limitadas ou conflitantes
  - Extrapolação de padrões
  - SUScore 0.3-0.5

[SPECULATIVE] - Especulativo
  - Não há dados suficientes
  - Inferência ou estimativa
  - Pode estar incorreto
  - SUScore > 0.5
```

#### Formato de Flags

```markdown
## Opção 1: Inline Flags

"A teoria da relatividade geral [HIGH] foi publicada por Einstein
em 1915 [HIGH]. Estima-se que cerca de 10.000 cientistas [LOW]
trabalharam em extensões da teoria desde então [SPECULATIVE]."

---

## Opção 2: Seção de Confiança

**Resposta:**
A teoria da relatividade geral foi publicada por Einstein em 1915.
Estima-se que cerca de 10.000 cientistas trabalharam em extensões
da teoria desde então.

**Níveis de Confiança:**
- "teoria da relatividade geral foi publicada por Einstein em 1915" - [HIGH]
- "10.000 cientistas" - [LOW] (estimativa aproximada)
- "trabalharam em extensões desde então" - [SPECULATIVE]

---

## Opção 3: Notas de Rodapé

A teoria da relatividade geral¹ foi publicada por Einstein em 1915¹.
Estima-se que cerca de 10.000² cientistas trabalharam em extensões
da teoria desde então³.

¹ [HIGH] Fato histórico bem documentado
² [LOW] Número aproximado, fonte incerta
³ [SPECULATIVE] Inferência sem dados precisos
```

#### Quando Usar Cada Flag

```markdown
USE [HIGH] quando:
- Definições de conceitos amplamente aceitas
- Fatos históricos documentados
- Conhecimento científico estabelecido
- Informações verificáveis e verificadas

USE [MEDIUM] quando:
- Fatos prováveis mas com margem de erro
- Estatísticas com variação
- Conhecimento especializado não universal
- Informações de fontes limitadas

USE [LOW] quando:
- Estimativas ou aproximações
- Informações de memória incerta
- Dados que podem ter mudado
- Generalizações com exceções

USE [SPECULATIVE] quando:
- Inferências ou extrapolações
- Previsões ou projeções
- Opinões apresentadas como possibilidades
- Quando genuinamente não sabe
```

---

### PASSO 6: YIELD VERIFIED OUTPUT (Entrega)

**Objetivo:** Entregar output final apenas com claims verificados e transparência sobre limitações.

#### Estrutura do Output Verificado

```markdown
## OUTPUT VERIFICADO

### Resposta Principal
[Conteúdo verificado com flags de confiança]

### Declaração de Limitações
- Áreas onde conhecimento é limitado
- Claims que não puderam ser verificados
- Possíveis fontes de erro

### Uncertainty Map (se solicitado)
[Visualização de incerteza por span]

### Recomendações
- Claims que usuário deve verificar independentemente
- Fontes sugeridas para confirmação
```

#### Checklist de Yield

```markdown
Antes de entregar output:

□ Todos os claims passaram por Two-Pass?
□ Spans de alta incerteza passaram por ICQ?
□ Flags de confiança aplicados?
□ Limitações declaradas?
□ Output é útil apesar das qualificações?

Se TODOS ✓: Entregar
Se algum ✗: Revisar antes de entregar
```

#### Template de Output Final

```markdown
## RESPOSTA VERIFICADA

[Conteúdo principal com [FLAGS] inline ou referenciados]

---

## SOBRE ESTA RESPOSTA

**Nível Geral de Confiança:** [HIGH/MEDIUM/LOW]

**Claims de Alta Confiança:**
- [lista de claims [HIGH]]

**Claims que Requerem Verificação:**
- [lista de claims [MEDIUM] ou [LOW]]

**Limitações Conhecidas:**
- [áreas onde conhecimento é incerto]

**Sugestões:**
- [o que o usuário pode fazer para verificar]
```

---

## APLICAÇÃO DO VERIFY EM CONTEXTOS ESPECÍFICOS

### VERIFY para Clones Cognitivos

```markdown
Ao gerar respostas como clone:

1. **VALIDATE FAMILIARITY**
   - "A pessoa original realmente tem esta opinião?"
   - "Isso está documentado nas fontes extraídas?"
   - "Estou inferindo ou reproduzindo?"

2. **EVALUATE UNCERTAINTY**
   - Marcar opiniões atribuídas como [ATTRIBUTED]
   - Marcar inferências como [INFERRED]
   - Marcar conhecimento confirmado como [DOCUMENTED]

3. **TWO-PASS para Autenticidade**
   - Pass 1: Gerar resposta no estilo do clone
   - Pass 2: Verificar se cada claim é suportado pelas fontes

4. **ICQ para Posições**
   - "A pessoa original realmente disse/pensaria isso?"
   - "Há evidência nas fontes?"

5. **FLAGS específicos para clones**
   - [DOCUMENTED] - Afirmado explicitamente nas fontes
   - [ATTRIBUTED] - Atribuído mas não citação direta
   - [INFERRED] - Inferido do padrão geral
   - [EXTRAPOLATED] - Extrapolação para novo contexto

6. **YIELD com transparência**
   - Distinguir reprodução de inferência
   - Admitir quando extrapolando
```

### VERIFY para Evolução de Prompts

```markdown
Ao avaliar variantes evolutivas:

1. **VALIDATE FAMILIARITY**
   - "Entendo por que esta mutação pode funcionar?"
   - "Tenho dados suficientes para avaliar fitness?"

2. **EVALUATE UNCERTAINTY**
   - Quantificar incerteza na previsão de fitness
   - Identificar variantes de alto risco

3. **TWO-PASS para Fitness**
   - Pass 1: Avaliar fitness inicial
   - Pass 2: Verificar se avaliação é consistente

4. **ICQ para Previsões**
   - "Por que esta variante tem fitness X?"
   - "O que poderia estar errado nesta avaliação?"

5. **FLAGS para Fitness**
   - [MEASURED] - Fitness medido em test cases
   - [ESTIMATED] - Fitness estimado por heurística
   - [PREDICTED] - Fitness previsto por modelo

6. **YIELD com calibração**
   - Reportar incerteza nas métricas
   - Distinguir medição de estimativa
```

---

## MÉTRICAS DO FRAMEWORK VERIFY

### KPIs de Qualidade

| Métrica | Definição | Target |
|---------|-----------|--------|
| **Hallucination Rate** | % de claims incorretos no output | < 5% |
| **Uncertainty Detection** | % de claims incertos corretamente flaggados | > 90% |
| **False Positive Rate** | % de claims corretos marcados como incertos | < 10% |
| **Coverage** | % de claims substantivos avaliados | > 95% |
| **Calibration** | Correlação entre confiança e acurácia | > 0.8 |

### Fórmulas

```python
# Taxa de Alucinação
hallucination_rate = incorrect_claims / total_claims

# Detecção de Incerteza
uncertainty_detection = (
    correctly_flagged_uncertain /
    total_actually_uncertain
)

# Taxa de Falso Positivo
false_positive_rate = (
    incorrectly_flagged_as_uncertain /
    total_actually_certain
)

# Calibração
calibration = correlation(
    confidence_scores,
    accuracy_scores
)
```

---

## INTEGRAÇÃO COM OUTROS FRAMEWORKS

### VERIFY + METACOG-EVOLUTION

```
METACOG-EVOLUTION usa VERIFY para:
├── Avaliar familiaridade com tarefa de otimização
├── Quantificar incerteza em previsões de fitness
├── Verificar claims sobre performance de variantes
├── Calibrar modelo mental do processo evolutivo
└── Garantir transparência sobre limitações
```

### VERIFY + ORACLE (Validation Engineer)

```
ORACLE expandido com VERIFY:
├── O - Originality + VERIFY de claims biográficos
├── R - Reliability + Uncertainty mapping
├── A - Authenticity + Two-Pass verification
├── C - Coverage + ICQ para edge cases
├── L - Limitations + Confidence flags
├── E - Evolution + Calibração contínua
```

### VERIFY + EVOLVE+ (Evolution Specialist)

```
EVOLVE+ usa VERIFY para:
├── Diagnosticar alucinações em clones
├── Refinar claims problemáticos
├── Calibrar confiança de outputs
└── Documentar limitações conhecidas
```

---

## CHECKLIST DE IMPLEMENTAÇÃO VERIFY

### Para Cada Resposta

```markdown
PRÉ-GERAÇÃO
□ SELF-FAMILIARITY check completo
□ Áreas de baixa familiaridade identificadas
□ Decisão sobre prosseguir ou admitir limitação

DURANTE GERAÇÃO
□ SUScore calculado para spans substantivos
□ Uncertainty map gerado
□ Spans de alto risco marcados

PÓS-GERAÇÃO
□ Two-Pass review completo
□ ICQ para spans de alta incerteza
□ Confidence flags aplicados
□ Limitações declaradas

ENTREGA
□ Output verificado e qualificado
□ Transparência sobre incertezas
□ Recomendações para verificação pelo usuário
```

---

## ANTI-PATTERNS A EVITAR

```markdown
❌ NÃO FAZER:

1. Ignorar VERIFY por pressa
   → Qualidade > velocidade para claims factuais

2. Aplicar VERIFY apenas superficialmente
   → Two-Pass real, não teatro

3. Over-flag (marcar tudo como incerto)
   → Calibração é importante

4. Under-flag (não marcar nada)
   → Transparência é obrigatória

5. Usar VERIFY como desculpa para não responder
   → Objetivo é melhorar, não bloquear

6. Ignorar calibração
   → Confidence flags devem correlacionar com acurácia
```

---

## EVOLUÇÃO DO FRAMEWORK

O VERIFY é um framework vivo que deve evoluir:

1. **Calibração Contínua** - Ajustar thresholds baseado em feedback
2. **Novas Técnicas** - Incorporar avanços em detecção de alucinação
3. **Especialização** - Criar variantes para domínios específicos
4. **Automação** - Aumentar automação onde possível

---

**Framework mantido por:** Dr. Verity Check (Hallucination Detector)
**Última atualização:** 2025-12-16
**Versão:** 1.0
**Status:** Production-ready
