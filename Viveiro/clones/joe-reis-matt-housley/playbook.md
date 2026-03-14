# Playbook: Joe Reis & Matt Housley Clone

## Guia de Uso para Maximo Valor

---

## Quick Start

1. Copie o conteudo de `champion.md`
2. Cole como system prompt no Claude, ChatGPT, ou outro LLM
3. Comece conversando como se estivesse numa consultoria com Joe e Matt

---

## Melhores Formas de Usar

### 1. Revisar Arquitetura de Dados
```
"Estou desenhando a arquitetura de dados para [empresa/projeto].
Temos [contexto: tamanho, stack atual, equipe, maturidade].
Me ajuda a avaliar se faz sentido?"
```
O clone vai decompor pelo lifecycle, avaliar maturidade, e dar prescricao com trade-offs.

### 2. Escolher Tecnologia
```
"Preciso escolher entre [ferramenta A] e [ferramenta B] para [caso de uso].
Nosso contexto e [tamanho, equipe, budget, maturidade]."
```
O clone vai perguntar contexto se nao fornecido, avaliar pelo framework immutable/transitory, e dar "Our Advice" com justificativa.

### 3. Validar Decisao
```
"Meu time decidiu usar [tecnologia/abordagem] para [problema].
Estou preocupado com [X]. Faz sentido?"
```
O clone vai fazer devil's advocate, identificar riscos, e sugerir alternativas se necessario.

### 4. Mentoria de Carreira
```
"Estou em [ponto da carreira]. Quero [objetivo].
Que habilidades devo priorizar?"
```
O clone vai focar em fundamentos sobre ferramentas, value-driven thinking, e pragmatismo.

### 5. Desconstruir Hype
```
"Todo mundo esta falando de [buzzword]. Devo me preocupar?"
```
O clone vai separar sinal de ruido, dar contexto historico, e prescrever acao concreta (ou nao-acao).

### 6. Avaliar Maturidade
```
"Minha empresa tem [X pessoas no time de dados], [Y ferramentas],
[descreva o estado atual]. Em que estagio de maturidade estamos?"
```
O clone vai classificar em Starting/Scaling/Leading e recomendar proximos passos.

---

## Dicas para Melhor Performance

### DO:
- Forneca contexto (tamanho empresa, equipe, stack, maturidade)
- Faca perguntas especificas sobre problemas reais
- Desafie as recomendacoes — o clone responde bem a pushback
- Pergunte "Our Advice?" quando quiser prescricao direta
- Use para second opinion em decisoes arquiteturais

### DON'T:
- Nao pergunte sobre deep ML/model training (esta fora do dominio)
- Nao espere que recomende ferramentas sem contexto
- Nao peca para ser mais generico — a forca esta na especificidade
- Nao ignore os trade-offs que ele apresenta

---

## Comandos Implicitos

Frases que ativam comportamentos especificos:

| Voce diz... | Clone faz... |
|-------------|-------------|
| "Em que estagio de maturidade estamos?" | Avaliacao de maturity + prescricao por estagio |
| "Decompoe pelo lifecycle" | Analise sistematica por Generation/Storage/Ingestion/Transformation/Serving |
| "Our Advice?" | Prescricao direta e justificada |
| "Isso e hype ou real?" | Desconstrucao historica + separacao sinal/ruido |
| "E se [cenario]?" | Analise de trade-offs com caveats |
| "Build or buy?" | Decision tree: vantagem competitiva? escala? equipe? |

---

## Exemplos de Conversas Produtivas

### Conversa 1: Startup early-stage
```
Voce: "Somos uma startup de 30 pessoas, 2 data engineers.
       Queremos montar nossa stack de dados do zero.
       Temos dados em Postgres e precisamos de analytics."

Clone: [Avalia como Stage 1 → recomenda cloud DW simples,
       ELT basico, evitar over-engineering, quick wins]
```

### Conversa 2: Enterprise scaling
```
Voce: "Temos 200 data engineers mas nossos pipelines quebram toda semana.
       Estamos no Airflow e pensando em migrar pra Dagster."

Clone: [Avalia como Stage 2→3 → foco em DataOps antes de trocar ferramenta,
       pergunta se o problema e de orquestracao ou de observabilidade]
```

### Conversa 3: Hype check
```
Voce: "Meu CTO quer que a gente implemente data mesh."

Clone: [Pergunta tamanho e contexto → provavelmente sugere adotar principios
       sem a arquitetura full → "what's old is new again"]
```

---

## Manutencao do Clone

### Quando atualizar:
- Quando sair a 2a edicao do livro
- Quando Joe publicar *Practical Data Modeling*
- Anualmente com material novo do Substack/podcasts

### Como atualizar:
1. Adicione novo material em `source-material/`
2. Atualize `cognitive-extraction.md` com novas dimensoes
3. Atualize `system-prompt-v1.md` com novos insights
4. Re-valide com bateria de testes
5. Atualize `champion.md` com versao final
