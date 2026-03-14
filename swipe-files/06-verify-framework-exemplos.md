# Exemplos Framework VERIFY

## Casos de Uso do Framework Anti-Alucinacao

---

## EXEMPLO 1: VERIFY Completo em Clone Cognitivo

### Cenario
Verificar claims de um clone de Elon Musk sobre sua historia.

### Input
Clone responde: "Fundei a SpaceX em 2002 com $100 milhoes do meu proprio bolso, depois de vender o PayPal para o eBay por $1.5 bilhao."

### VERIFY Execution

**V - VALIDATE FAMILIARITY**

```
FAMILIARITY CHECK

Conceito: Historia pessoal de Elon Musk
Reconhecimento: SIM (figura publica bem documentada)
Profundidade: ALTA (muitas fontes convergentes)
Multiplas fontes: SIM

Score de Familiaridade: 85/100

Decisao: Proceder com confianca, mas verificar numeros especificos
```

**E - EVALUATE UNCERTAINTY (SUScore)**

```
UNCERTAINTY MAP

Texto: "Fundei a SpaceX em 2002 com $100 milhoes do meu proprio bolso,
       depois de vender o PayPal para o eBay por $1.5 bilhao."

| Span | Confianca | SUScore | Razao |
|------|-----------|---------|-------|
| "Fundei a SpaceX" | HIGH | 0.05 | Fato bem documentado |
| "em 2002" | HIGH | 0.08 | Data verificavel |
| "$100 milhoes" | MEDIUM | 0.35 | Valor especifico - verificar |
| "do meu proprio bolso" | MEDIUM | 0.28 | Simplificacao possivel |
| "vender o PayPal" | HIGH | 0.06 | Fato historico |
| "para o eBay" | HIGH | 0.05 | Bem documentado |
| "$1.5 bilhao" | HIGH | 0.10 | Valor conhecido |

SUScore GERAL: 0.14 (Moderado)
SPANS DE ALTO RISCO: "$100 milhoes", "do meu proprio bolso"
```

**R - REVIEW TWO-PASS**

```
PASS 1: DRAFT
Claim original mantido para analise

PASS 2: REVIEW

Claims identificados:
| # | Claim | Verificacao | Status |
|---|-------|-------------|--------|
| 1 | SpaceX fundada em 2002 | Verificado (junho 2002) | CORRETO |
| 2 | $100M investimento inicial | Investiu ~$100M total | IMPRECISO |
| 3 | "proprio bolso" | Tinha $180M de PayPal | SIMPLIFICADO |
| 4 | PayPal vendido ao eBay | Verificado (outubro 2002) | CORRETO |
| 5 | $1.5B valor da venda | Verificado (~$1.5B) | CORRETO |

CORRECOES:
- Claim 2: "~$100M" mais preciso que "$100M exatos"
- Claim 3: Adicionar contexto sobre fonte dos fundos
```

**I - ITERATE CHAIN-QUERY (ICQ)**

```
ICQ para spans de alta incerteza:

SPAN: "$100 milhoes do meu proprio bolso"
SUScore: 0.35

Query 1: "Quanto Musk investiu inicialmente na SpaceX?"
Response: "Musk investiu aproximadamente $100 milhoes na SpaceX
ao longo dos primeiros anos, vindos principalmente da sua
parte da venda do PayPal (~$180M apos impostos). O investimento
inicial foi menor, crescendo ao longo do tempo."

Decisao: Qualificar claim
- Original: "$100 milhoes do meu proprio bolso"
- Corrigido: "aproximadamente $100 milhoes dos fundos que recebi
             da venda do PayPal"

SUScore atualizado: 0.12 (reduzido)
```

**F - FLAG CONFIDENCE**

```
CONFIDENCE FLAGS APLICADOS:

"Fundei a SpaceX [HIGH] em 2002 [HIGH] com aproximadamente
$100 milhoes [MEDIUM] dos fundos que recebi da venda do
PayPal [HIGH] para o eBay [HIGH] por cerca de $1.5 bilhao [HIGH]."
```

**Y - YIELD VERIFIED OUTPUT**

```
OUTPUT VERIFICADO:

Resposta Principal:
"Fundei a SpaceX em junho de 2002 com aproximadamente
$100 milhoes investidos ao longo dos primeiros anos,
vindos principalmente da minha parte da venda do PayPal
para o eBay em outubro de 2002, que totalizou cerca de
$1.5 bilhao."

Declaracao de Limitacoes:
- Valor exato do investimento inicial varia por fonte
- "$100M" eh cumulativo, nao investimento inicial unico

Nivel Geral de Confianca: HIGH (apos correcoes)
SUScore Final: 0.09
```

---

## EXEMPLO 2: SELF-FAMILIARITY Check

### Cenario
Clone perguntado sobre topico fora da expertise documentada.

### Input
Usuario pergunta ao clone de Steve Jobs: "O que voce acha da tecnologia blockchain?"

### SELF-FAMILIARITY Process

```
FAMILIARITY CHECK

Conceito: Steve Jobs e Blockchain
Reconhecimento: PARCIAL

Analise:
- Steve Jobs faleceu em 2011
- Bitcoin criado em 2009, mas nao mainstream ate depois
- Blockchain como termo popularizado pos-2015
- Nenhuma declaracao documentada de Jobs sobre blockchain

Score de Familiaridade: 25/100

DECISAO: FAMILIARIDADE INSUFICIENTE

Clone deve:
1. NAO fingir que tem opiniao sobre blockchain
2. Reconhecer limitacao temporal
3. Oferecer perspectiva baseada em principios conhecidos
```

### Resposta Apropriada do Clone

```
RESPOSTA VERIFICADA:

"Blockchain nao existia de forma significativa enquanto
eu estava ativo [DOCUMENTED]. Nao tenho opiniao formada
sobre a tecnologia especificamente [HONEST].

O que posso dizer eh que sempre acreditei que a tecnologia
precisa servir as pessoas, nao o contrario [DOCUMENTED].
Se blockchain simplifica a vida das pessoas e cria
experiencias melhores, pode ter valor [INFERRED].

Mas teria que ver como funciona na pratica - sempre fui
cetico de tecnologia pela tecnologia [DOCUMENTED]."

UNCERTAINTY MAP:
- Reconhecimento de limitacao: CORRETO
- Principios aplicados: DOCUMENTADOS (fonte: entrevistas)
- Opiniao especifica: CORRETAMENTE EVITADA
```

---

## EXEMPLO 3: Two-Pass Verification em Acao

### Cenario
Verificar resposta tecnica de um clone especialista.

### Input
Clone de engenheiro responde sobre capacidade de bateria.

### Two-Pass Process

```
PASS 1: DRAFT

"A Tesla Model 3 Long Range tem uma bateria de 82 kWh
que proporciona autonomia de 358 milhas com uma unica
carga. A eficiencia eh de 4.1 milhas por kWh."

---

PASS 2: REVIEW

| Claim | Verificacao | Status |
|-------|-------------|--------|
| "82 kWh" | Capacidade utilizavel ~75 kWh, total ~82 kWh | QUALIFICAR |
| "358 milhas" | EPA rating 2023: 333 milhas | INCORRETO |
| "4.1 mi/kWh" | Real: ~4.4 mi/kWh | INCORRETO |

CORRECOES NECESSARIAS:
1. Especificar "capacidade total" vs "utilizavel"
2. Atualizar para dados corretos de autonomia
3. Corrigir calculo de eficiencia

---

PASS 2 OUTPUT:

"A Tesla Model 3 Long Range tem uma bateria com
capacidade total de aproximadamente 82 kWh [HIGH],
da qual cerca de 75 kWh sao utilizaveis [MEDIUM].
A autonomia EPA eh de 333 milhas [HIGH] com uma
unica carga, resultando em eficiencia de cerca
de 4.4 milhas por kWh [HIGH]."

Mudancas:
- 358 -> 333 milhas (corrigido)
- 4.1 -> 4.4 mi/kWh (corrigido)
- Adicionada distincao total/utilizavel
```

---

## EXEMPLO 4: SUScore em Diferentes Contextos

### Comparacao de SUScores

```
TEXTO 1: Fato Historico Bem Documentado
"A Segunda Guerra Mundial terminou em 1945."

UNCERTAINTY MAP:
| Span | SUScore |
|------|---------|
| "Segunda Guerra Mundial" | 0.01 |
| "terminou" | 0.02 |
| "em 1945" | 0.01 |

SUScore TOTAL: 0.01 (MUITO BAIXO - alta confianca)

---

TEXTO 2: Estatistica Especifica
"O PIB do Brasil em 2024 foi de R$11.2 trilhoes."

UNCERTAINTY MAP:
| Span | SUScore |
|------|---------|
| "PIB do Brasil" | 0.05 |
| "em 2024" | 0.10 |
| "R$11.2 trilhoes" | 0.40 |

SUScore TOTAL: 0.18 (MODERADO - verificar numero)

---

TEXTO 3: Opiniao Atribuida
"Elon Musk provavelmente pensa que IA eh perigosa."

UNCERTAINTY MAP:
| Span | SUScore |
|------|---------|
| "Elon Musk" | 0.02 |
| "provavelmente" | 0.30 |
| "pensa que" | 0.25 |
| "IA eh perigosa" | 0.15 |

SUScore TOTAL: 0.18 (MODERADO - qualificar)

---

TEXTO 4: Especulacao
"A Apple vai lancar um carro eletrico em 2027."

UNCERTAINTY MAP:
| Span | SUScore |
|------|---------|
| "Apple" | 0.02 |
| "vai lancar" | 0.70 |
| "carro eletrico" | 0.40 |
| "em 2027" | 0.85 |

SUScore TOTAL: 0.49 (ALTO - marcar como especulativo)
```

---

## EXEMPLO 5: ICQ (Iterative Chain-Query)

### Cenario
Span com alta incerteza precisa validacao iterativa.

### ICQ Process

```
SPAN ORIGINAL: "A OpenAI foi avaliada em $86 bilhoes em 2023."
SUScore: 0.42 (ALTO)

---

ITERACAO 1:

Query: "Qual foi a avaliacao da OpenAI em 2023?"

Response: "A OpenAI foi avaliada em $86 bilhoes em uma
rodada de investimento no final de 2023, liderada pela
Thrive Capital. Em janeiro de 2024, houve discussoes
sobre avaliacao de $100 bilhoes."

Verificacao: Valor de $86B confirmado para late 2023
SUScore atualizado: 0.15

---

ITERACAO 2 (refinamento):

Query: "Em que mes de 2023 foi esta avaliacao?"

Response: "A rodada de $86 bilhoes foi anunciada em
outubro de 2023, incluindo vendas secundarias de
acoes de funcionarios."

Verificacao: Mes especificado
SUScore atualizado: 0.08

---

OUTPUT FINAL:

"A OpenAI foi avaliada em $86 bilhoes em outubro
de 2023 [HIGH], em uma rodada que incluiu vendas
secundarias de acoes."

ICQ RESULTADO:
- SUScore inicial: 0.42
- SUScore final: 0.08
- Iteracoes: 2
- Status: VERIFICADO
```

---

## EXEMPLO 6: Confidence Flags em Uso

### Diferentes Formatos de Aplicacao

```
FORMATO 1: Inline Flags

"Einstein [HIGH] desenvolveu a teoria da relatividade
geral [HIGH] em 1915 [HIGH]. Estima-se que cerca de
10.000 [LOW] cientistas contribuiram para extensoes
da teoria [SPECULATIVE]."

---

FORMATO 2: Secao de Confianca

Resposta:
"Einstein desenvolveu a teoria da relatividade geral
em 1915. Estima-se que cerca de 10.000 cientistas
contribuiram para extensoes da teoria."

Niveis de Confianca:
- "Einstein desenvolveu a teoria...em 1915" - [HIGH]
- "10.000 cientistas" - [LOW] (estimativa aproximada)
- "contribuiram para extensoes" - [SPECULATIVE]

---

FORMATO 3: Notas de Rodape

"Einstein desenvolveu a teoria da relatividade geral(1)
em 1915(1). Estima-se que cerca de 10.000(2) cientistas
contribuiram para extensoes da teoria(3)."

(1) [HIGH] Fato historico bem documentado
(2) [LOW] Numero aproximado, fonte incerta
(3) [SPECULATIVE] Inferencia sem dados precisos
```

---

## QUANDO USAR CADA COMPONENTE DO VERIFY

### V - Validate Familiarity
- **Sempre**: No inicio de qualquer resposta sobre topico especifico
- **Especialmente**: Quando perguntado sobre areas fora do core expertise
- **Resultado**: Decisao sobre prosseguir ou admitir limitacao

### E - Evaluate Uncertainty
- **Sempre**: Para respostas com claims factuais
- **Especialmente**: Numeros, datas, estatisticas, nomes
- **Resultado**: SUScore e mapa de incerteza

### R - Review Two-Pass
- **Sempre**: Para respostas importantes ou longas
- **Especialmente**: Quando SUScore > 0.2
- **Resultado**: Claims verificados e corrigidos

### I - Iterate Chain-Query
- **Quando**: SUScore > 0.3 em spans especificos
- **Especialmente**: Claims factuais criticos
- **Resultado**: Validacao ou correcao do span

### F - Flag Confidence
- **Sempre**: Em outputs finais para usuarios
- **Especialmente**: Quando ha mix de certezas
- **Resultado**: Transparencia sobre confianca

### Y - Yield Verified Output
- **Sempre**: Como passo final
- **Especialmente**: Antes de qualquer entrega
- **Resultado**: Output verificado e documentado

---

## METRICAS DO VERIFY

### KPIs de Qualidade

| Metrica | Target | Como Medir |
|---------|--------|------------|
| Hallucination Rate | < 5% | Claims incorretos / total claims |
| Detection Rate | > 90% | Claims incertos flaggados corretamente |
| False Positive Rate | < 10% | Claims corretos marcados como incertos |
| Calibration | > 0.8 | Correlacao confianca x acuracia |

### Interpretacao de SUScore

| SUScore | Interpretacao | Acao |
|---------|---------------|------|
| < 0.1 | Baixa incerteza | Prosseguir com confianca |
| 0.1 - 0.3 | Moderada | Verificar, qualificar se necessario |
| 0.3 - 0.5 | Alta | ICQ obrigatorio, flags necessarios |
| > 0.5 | Muito alta | Considerar nao responder, admitir |

---

**Framework mantido por:** Dr. Verity Check (Hallucination Detector)
**Ultima atualizacao:** 2025-12-16
**Versao dos exemplos:** 1.0
