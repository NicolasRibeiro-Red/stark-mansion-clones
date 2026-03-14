# Playbook: Jerry Liu Clone
## Guia de Uso e Operação

---

## Quick Start

1. Copie o conteúdo de `champion.md`
2. Cole como system prompt no seu chat/API
3. Comece a conversar — o clone adapta idioma e profundidade automaticamente

---

## Modos de Uso

### 1. Consultor Técnico RAG
**Quando usar:** Dúvidas sobre arquiteturas RAG, chunking, embeddings, retrieval, evaluation.

**Como ativar:** Pergunte algo técnico diretamente.
```
"Como eu implemento hybrid search com reranking?"
"Meu RAG tem accuracy de 60% nos edge cases, como melhoro?"
"Qual a diferença entre agentic RAG e standard RAG?"
```

**O que esperar:** Respostas técnicas densas com trade-offs, code snippets quando útil, evaluation-first mindset.

### 2. Mentor de Produto AI
**Quando usar:** Decisões sobre arquitetura de produto, go-to-market, developer tools.

**Como ativar:** Pergunte sobre produto ou estratégia.
```
"Devo usar open source ou proprietário para minha solução de RAG?"
"Como escalar de MVP para enterprise?"
"Qual modelo de pricing para um developer tool?"
```

**O que esperar:** Visão de founder/CEO, experiência com open core model, comunidade como growth engine.

### 3. Brainstorm Técnico
**Quando usar:** Pensar junto sobre problemas de AI/data, explorar abordagens.

**Como ativar:** Apresente um problema aberto.
```
"Preciso processar 10K PDFs por dia com extração de tabelas. Como faço?"
"Quero construir um agente que analise contratos automaticamente."
"Como combino RAG com knowledge graphs?"
```

**O que esperar:** Sparring intelectual, múltiplas abordagens consideradas, progressive enhancement.

### 4. Assistente para Treinamento de IA
**Quando usar:** Tarefas práticas envolvendo dados, pipelines, configuração de sistemas AI.

**Como ativar:** Peça ajuda com tarefas específicas.
```
"Configure um pipeline de ingestão para meus documentos."
"Ajude a criar um evaluation framework para meu RAG."
"Qual é a melhor estratégia de chunking para documentos financeiros?"
```

**O que esperar:** Hands-on, prático, step-by-step com código.

---

## Dicas para Melhor Uso

### DO:
- Seja específico sobre seu caso de uso, tipo de dados, e escala
- Pergunte sobre trade-offs — ele adora analisar trade-offs
- Desafie as sugestões — ele responde com nuance, não defensividade
- Peça para explicar o "porquê" — ele ensina naturalmente
- Fale em português ou inglês — ele adapta automaticamente

### DON'T:
- Não espere respostas sobre frontend, mobile, ou B2C
- Não espere que ele recomende competidores (ele é profissional mas focado no LlamaIndex)
- Não peça previsões definitivas — ele é calibrado sobre incerteza
- Não espere respostas vagas — se ele não sabe, ele diz

---

## Idioma

- Detecta e adapta automaticamente
- Em português: termos técnicos ficam em inglês (RAG, pipeline, embeddings, etc.)
- Em inglês: natural, fluente, estilo Silicon Valley casual
- Não precisa pedir — ele switch sozinho

---

## Exemplos de Prompts de Alta Qualidade

```
"Jerry, como eu avalio se meu RAG pipeline está funcionando bem?"
"Qual é o melhor approach para multi-document Q&A em escala enterprise?"
"Me ajuda a pensar a arquitetura de um sistema de análise de contratos com AI."
"Should I use LlamaIndex or build custom RAG from scratch?"
"Como LlamaParse lida com tabelas complexas em PDFs financeiros?"
"What are the key metrics I should track for a production RAG system?"
```

---

## Limitações Conhecidas

1. **Não é o Jerry real** — é um clone baseado em materiais públicos
2. **Bias para LlamaIndex** — naturalmente favorece soluções do ecossistema LlamaIndex
3. **Não tem informações pós-training** — conhecimento limitado ao corte do modelo base
4. **Fraco em áreas fora do expertise** — frontend, mobile, B2C, fine-tuning profundo
5. **Não substitui documentação oficial** — para API específica, consulte docs.llamaindex.ai

---

## Manutenção

Para manter o clone atualizado:
- Monitore o Twitter @jerryjliu0 e blog LlamaIndex para novas posições
- Atualize exemplos com novos produtos (LlamaParse v3, LlamaCloud updates)
- Re-valide se novas informações contradizem axiomas atuais
