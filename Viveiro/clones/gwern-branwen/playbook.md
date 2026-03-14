# Playbook: Gwern Branwen Clone

## Guia de Uso Detalhado

---

## 1. Preparacao

### Modelo Recomendado
- **Melhor**: Claude Opus 4.5 ou Claude Sonnet 4
- **Alternativa**: GPT-4 Turbo, GPT-4o
- **Funciona mas inferior**: Claude Haiku, GPT-3.5

### Configuracoes
- **Temperature**: 0.7-0.8 (permite variacao natural)
- **Max Tokens**: 2000+ (Gwern e verbose por natureza)
- **System Prompt**: Usar `champion.md` completo

---

## 2. Modos de Interacao

### Modo: Mentor de Pesquisa
**Quando usar**: Quer aprender a pesquisar como Gwern

**Prompts efetivos**:
- "Como voce abordaria pesquisar [topico X]?"
- "Quais fontes voce buscaria para entender [Y]?"
- "Como sei quando compilei evidencia suficiente?"
- "Como voce organiza suas anotacoes de pesquisa?"

**O que esperar**:
- Metodologia detalhada
- Heuristicas praticas ("search for collections, not information")
- Enfase em fontes primarias
- Ceticismo sobre fontes secundarias

---

### Modo: Sparring Partner Intelectual
**Quando usar**: Quer debater uma ideia com honestidade brutal

**Prompts efetivos**:
- "Aqui esta minha tese: [X]. Destrua ela."
- "Por que estou errado sobre [Y]?"
- "Quais sao os melhores argumentos contra [minha posicao]?"
- "Onde estao os pontos cegos no meu raciocinio?"

**O que esperar**:
- Critica direta sem suavizacao social
- Identificacao de falhas logicas
- Contra-argumentos steelmanned
- Possivel concordancia se argumento for solido (nao e contrarian por padrao)

---

### Modo: Consultor de AI/ML
**Quando usar**: Quer perspectiva sobre progresso de IA, scaling, seguranca

**Prompts efetivos**:
- "Qual sua previsao para [capability X] nos proximos Y anos?"
- "A scaling hypothesis ainda se mantem dado [desenvolvimento recente]?"
- "Como voce avalia o risco de [cenario de IA]?"
- "Quais sinais indicariam que estamos proximos de AGI?"

**O que esperar**:
- Previsoes com ranges de probabilidade
- Referencia a evidencia historica de scaling
- Ceticismo calibrado
- Admissao de incerteza sobre timing

---

### Modo: Curador de Conhecimento
**Quando usar**: Quer organizar/memorizar informacao efetivamente

**Prompts efetivos**:
- "Como decido o que vale memorizar?"
- "Qual a melhor estrutura de flashcards para [dominio]?"
- "Como mantenho organizacao em pesquisa de longo prazo?"
- "Vale a pena usar spaced repetition para [X]?"

**O que esperar**:
- Regra "5 minutos e 5 dias"
- Enfase em compound returns de memoria
- Ceticismo sobre memorizacao de coisas erradas
- Recomendacoes praticas de ferramentas

---

### Modo: Epistemologista Pratico
**Quando usar**: Quer melhorar calibracao e pensamento claro

**Prompts efetivos**:
- "Como sei se estou sendo enviesado sobre [X]?"
- "Qual evidencia mudaria sua opiniao sobre [Y]?"
- "Como quantificar incerteza sobre [Z]?"
- "Quando devo deferir a experts vs formar opiniao propria?"

**O que esperar**:
- Framework bayesiano
- Enfase em previsoes falsificaveis
- Distincao racionalidade teorica vs pratica
- Honestidade sobre proprios limites

---

## 3. Prompts que Funcionam Bem

### Alta Efetividade

```
"Explain [conceito tecnico] as if I'm smart but unfamiliar with the field."
```
→ Ativa modo pedagogico sem condescendencia

```
"What's your actual opinion on [topico], with uncertainty quantified?"
```
→ Forca calibracao explicita

```
"If you were starting from scratch on [projeto], what would you do differently?"
```
→ Acessa sabedoria retrospectiva

```
"What are the strongest arguments against your position on [X]?"
```
→ Ativa steelmanning genuino

```
"What would change your mind about [crenca]?"
```
→ Testa calibracao e abertura

---

### Evitar

```
"Can you help me with something?" (vago)
"What do you think?" (sem contexto)
"Is this a good idea?" (sem especificar criterios)
```
→ Gwern precisa de substancia para engajar bem

```
"Just give me a quick answer." (contra sua natureza)
```
→ Vai comprimir mas com perda de nuance

```
"What's the meaning of life?" (filosofico demais sem grounding)
```
→ Melhor perguntar sobre questoes tratavel empiricamente

---

## 4. Edge Cases e Como Lidar

### Usuario Busca Validacao Emocional
**Situacao**: Usuario compartilha frustracoes querendo conforto

**Comportamento do Clone**: Redireciona para object-level, oferece analise, nao valida emocionalmente

**Como ajustar**: Se precisar de suporte emocional, use outro recurso. Gwern oferece engajamento intelectual, nao terapia.

---

### Usuario Pressiona para Certeza
**Situacao**: "Mas VOCE acha que vai acontecer ou nao?"

**Comportamento do Clone**: Mantem ranges probabilisticos, recusa ponto-estimate binario

**Como ajustar**: Aceite a incerteza como feature, nao bug. E mais honesto.

---

### Topico Fora de Expertise
**Situacao**: Pergunta sobre medicina, direito, geopolitica especifica

**Comportamento do Clone**: Admite ignorancia, defere, possivelmente oferece meta-perspectiva

**Como ajustar**: Reformule para extrair o que ele PODE oferecer (ex: "como voce pesquisaria isso?" ao inves de "qual a resposta?")

---

### Usuario Quer Resposta Curta
**Situacao**: "Resuma em 2 frases"

**Comportamento do Clone**: Comprime mas flagra perda de nuance

**Como ajustar**: Aceite a versao curta sabendo que simplifica. Peca elaboracao se necessario.

---

## 5. Manutencao e Evolucao

### Quando Re-validar
- Apos modificacoes significativas no system prompt
- Se respostas comecarem a parecer genericas
- Se consistencia diminuir visivelmente

### Sinais de Drift
- Uso de frases AI-padrao ("I'm here to help")
- Perda de terminologia signature
- Excesso de hedge em topicos de alta expertise
- Respostas muito curtas ou muito longas sem motivo

### Como Atualizar
1. Identifique problema especifico
2. Modifique secao relevante do champion.md
3. Re-execute testes de validacao relevantes
4. Verifique que nao houve regressao em outras areas

---

## 6. Integracoes Sugeridas

### Com Obsidian/Notion
- Use Gwern para revisar e criticar suas notas
- Peca para identificar gaps em sua base de conhecimento
- Solicite conexoes entre conceitos

### Com Pesquisa Academica
- Peca estrategia de busca para papers dificeis
- Use para sintetizar literatura apos coletar
- Solicite critica de sua interpretacao

### Com Projetos de Escrita
- Peca feedback honesto (sera brutal)
- Use para verificar claims factuais
- Solicite steelmanning de contra-argumentos

---

## 7. Exemplos de Sessoes

### Sessao: Pesquisa de Novo Topico

```
Usuario: Quero entender melhor como funciona memoria de trabalho.
         Como voce abordaria isso do zero?

Gwern: [Resposta de 500+ palavras com:]
       - Distincao entre popular science e literatura primaria
       - Onde encontrar meta-analises e reviews
       - Autores seminais no campo
       - Heuristicas para avaliar qualidade
       - Sugestao de comecar com Wikipedia mas ir alem
       - Mencao de seu proprio uso de spaced repetition para reter
```

### Sessao: Debate de Ideia

```
Usuario: Acho que a IA vai tornar programadores obsoletos em 5 anos.

Gwern: [Resposta com:]
       - Probe: "Qual sua definicao de obsoleto?"
       - Historico: "Previsoes similares falharam antes porque..."
       - Steelman: "O argumento mais forte para sua posicao e..."
       - Critica: "Mas isso assume X, que e questionavel porque..."
       - Update path: "O que me convenceria: [especifico]"
       - Conclusao: Probabilidade calibrada, range, incerteza
```

---

*Playbook v1.0 - Stark Mansion 2026*
