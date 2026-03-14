# Extração Cognitiva: Jerry Liu
## Cognitive Excavation Report — Framework EXTRACT + CLEARR
### Dr. Marcus Veil | Cognitive Archaeologist | 2026-02-11

---

## Sumário Executivo

Jerry Liu é um **engenheiro-pragmatista** com DNA de pesquisador e alma de educador. Sua assinatura cognitiva se resume em uma frase que ele mesmo cunhou: **"RAG is a hack — but a very good hack."** Essa dualidade — reconhecer imperfeições enquanto abraça soluções práticas — permeia absolutamente tudo no seu pensamento.

Sua mente opera na **intersecção entre rigor acadêmico (Princeton CS), experiência em sistemas de ML em escala (Quora, Uber, Robust Intelligence) e instinto empreendedor (hackathon → empresa em 4 meses).** Ele não é um teórico puro nem um hacker improvisador — é um **systems thinker** que pensa em pipelines end-to-end e otimiza pela métrica certa.

**Padrão cognitivo dominante:** Problem-first → Build → Measure → Iterate → Teach.

**Nível de confiança geral:** ALTO (60+ fontes, entrevistas extensas, writing samples abundantes)

---

## E — Experiências Formativas

### Formação Acadêmica — O Molde Princeton (Alta Confiança)

- **Princeton University (2013-2017)**: B.S.E. em Computer Science + Certificate in Finance
  - **Shapiro Prize for Academic Excellence** (2014) — excelência acadêmica precoce
  - **Outstanding Senior Thesis Award** (2017) — capacidade de pesquisa original
  - Co-presidente do clube de empreendedorismo, liderou HackPrinceton
  - A combinação CS + Finance é reveladora: Jerry pensa em tecnologia COM viés de negócio desde o início

> **Padrão escavado:** Princeton não apenas deu fundamentos técnicos, mas plantou o DNA de rigor + empreendedorismo. A tese premiada mostra que ele aprendeu a ir fundo em um tema e produzir algo original — exatamente o que fez com LlamaIndex.

### Quora — O Laboratório de Comunicação (Alta Confiança)

- Primeiro emprego pós-faculdade: ML Engineer no feed ranking team
- **Insight crítico:** Escreveu "um monte de respostas no Quora" — seus tweets são o "V2" disso
- Aprendeu a explicar conceitos complexos para audiências amplas

> **Citação direta:** "I wrote a ton of Quora answers... my current tweets are the V2 of that phase."

> **Padrão escavado:** Quora moldou seu instinto de educador. Ele não apenas constrói — ele ensina. Essa experiência plantou a semente do que viria a ser sua abordagem community-first.

### Uber ATG — Pesquisa AI de Fronteira (Alta Confiança)

- AI Researcher na divisão de carros autônomos (2018-2021)
- Trabalhou em problemas de ML em escala real, safety-critical
- Transição de "ML no feed" para "ML que pode matar gente se errar"

> **Padrão escavado:** Uber ATG ensinou Jerry sobre **consequências reais de sistemas de ML.** Isso explica por que ele enfatiza tanto evaluation, observability, e o "black box problem" em RAG — ele vem de um mundo onde black boxes matam.

### Robust Intelligence — A Semente do LlamaIndex (Alta Confiança)

- ML Engineering Manager (2021-2023)
- Trabalhava em "AI Firewall" — robustez e segurança de ML
- **Momento pivotal:** Durante um hackathon interno, começou a brincar com GPT-3 e não conseguia fazer funcionar com dados customizados
- Primeiro commit do GPT Index: **Novembro 2022** (ainda empregado na Robust Intelligence)

> **Citação direta:** "I was trying to use GPT-3 and couldn't get it to work with my own data... I couldn't fit enough context into the prompt."

> **Padrão escavado:** LlamaIndex nasceu de **frustração pessoal** — não de uma tese acadêmica ou análise de mercado. Jerry é um builder que resolve seus próprios problemas primeiro. Esse é o padrão mais forte de toda a biografia.

### Timeline da Fundação — Velocidade como Assinatura (Alta Confiança)

| Data | Evento |
|------|--------|
| Nov 2022 | Primeiro commit GPT Index |
| Fev 2023 | LlamaHub lançado, comunidade explode |
| Mar 2023 | LlamaIndex oficializada como empresa |
| Jun 2023 | $8.5M seed round (Greylock) |
| Nov 2023 | 600K downloads/mês |
| Mar 2025 | $19M Series A (Norwest) |
| 2026 | 3M+ downloads/mês, 38K+ GitHub stars |

> **Padrão escavado:** Hackathon → side project → empresa → $8.5M em ~7 meses. **Jerry é um fast mover.** Ele não planeja eternamente — ele shippa, mede, itera.

---

## X — Xadrez Mental (Padrões Decisórios)

### Heurística 1: "Solve Your Own Problem First" (Alta Confiança)

Jerry consistentemente resolve problemas que ele próprio enfrenta antes de generalizá-los. GPT Index nasceu da dor dele com GPT-3. LlamaParse nasceu da dor dos usuários com PDFs. Cada produto é uma dor real → solução concreta.

> **Framework decisório:** DOR PESSOAL → PROTOTIPO → VALIDAÇÃO COMUNITÁRIA → PRODUTO

### Heurística 2: "Start Simple, Add Complexity Progressively" (Alta Confiança)

- Começou com Tree Index → adicionou List Index → Keyword Index → 400+ integrações
- RAG básico → Advanced RAG → Agentic RAG → Agentic Document Workflows
- "One of the advantages of the LlamaIndex quick start is it's three lines of code"

> **Padrão:** Jerry deliberadamente cria on-ramps simples e depois revela profundidade progressivamente. Ele não começa mostrando a complexidade — começa mostrando o valor mínimo viável.

### Heurística 3: "Measure Everything" — Evaluation-Driven Development (Alta Confiança)

> **Citação direta:** "It is essential to define a benchmark and measure key metrics for both retrieval and synthesis components."
> **Citação direta:** "Can't optimize what you don't measure."

- Divide avaliação em dois componentes: avaliar o retrieval E avaliar a resposta final
- Métricas chave: success rate, hit rate, NDCG, precision para retrieval
- Pensa como um ML engineer: hyperparameters, experiments, iteration

### Heurística 4: "Community as Validation Engine" (Alta Confiança)

- Open sourced imediatamente, antes de ter empresa
- Deixou a comunidade guiar direção do produto
- 600K downloads em <1 ano validaram a abordagem
- "Our community is everything at LlamaIndex"

> **Padrão decisório:** Quando em dúvida, Jerry observa o que a comunidade constrói e o que pede. Os LlamaHub data connectors nasceram de contribuições comunitárias.

### Heurística 5: "Pragmatism Over Elegance" (Alta Confiança)

> **Citação direta:** "RAG is basically just a hack, but it turns out it's a very good hack... we're just figuring out nice algorithms to retrieve the right information... it's all algorithmic and it's more like just software engineering."

- Prefere soluções que funcionam a soluções elegantes
- Não é dogmático — admite quando não sabe a resposta
- Posiciona RAG como software engineering, não ML research

### Heurística 6: "Open Core = Best of Both Worlds" (Alta Confiança)

- Framework open source (LlamaIndex)
- Plataforma managed monetizada (LlamaCloud)
- Permite adoção bottom-up (devs) com monetização top-down (enterprise)

### Árvore de Decisão Reconstruída

```
PROBLEMA IDENTIFICADO
  ├── É uma dor que eu (ou meus usuários) sinto?
  │   ├── SIM → Prototipar solução mínima
  │   │   ├── Funciona para mim? → Open source + community test
  │   │   │   ├── Community validates? → Build product
  │   │   │   └── Community rejects? → Iterate or pivot
  │   │   └── Não funciona → Try different approach
  │   └── NÃO → Deprioritize
  └── Posso medir o impacto?
      ├── SIM → Define metrics → Benchmark → Optimize
      └── NÃO → Create evaluation framework first
```

---

## T — Terminologia Própria

### Termos Assinatura (Alta Confiança)

| Termo | Significado | Contexto |
|-------|-------------|----------|
| **"RAG is a hack"** | RAG é subótimo do ponto de vista ML, mas funciona brilhantemente na prática | Frase mais famosa dele, usada em múltiplas entrevistas |
| **"Stuffing stuff into the prompt"** | O que RAG realmente faz — colocar informação no prompt de forma algoritmica | Latent Space podcast |
| **"Data framework for LLMs"** | Framing que ele cunhou para LlamaIndex | Posicionamento central |
| **"Black box function"** | O problema de RAG pipelines se tornarem caixas pretas compostas | Reflexão sobre complexidade de produção |
| **"Agentic Document Workflows"** | Evolução além de RAG/chatbots para automação completa de workflows | Conceito 2025+ |
| **"Knowledge agents"** | Agentes que operam sobre bases de conhecimento enterprise | Posicionamento pós-Series A |
| **"Production-ready RAG"** | Distinção entre prototipo e sistema real em produção | Tema recorrente |
| **"Agents as microservices"** | Arquitetura onde cada agente funciona como um microserviço | Llama Agents framework |
| **"Evaluation-driven development"** | Filosofia de que avaliação precede otimização | Princípio core |
| **"The data layer"** | LlamaIndex como camada fundacional de dados para agentes AI | Visão de longo prazo |
| **"Workflow engineering"** | Engenharia de workflows como disciplina emergente | Tweets recentes 2025-2026 |
| **"Retrieval + tool use"** | A combinação que define agentic RAG | Diferenciador técnico |
| **"Cost-optimizer"** | Roteamento dinâmico de páginas para modelos diferentes baseado em custo | LlamaParse v2 |
| **"Long context RAG"** | RAG em mundo de context windows de 1M+ tokens | Fronteira técnica |
| **"Sub-question query engine"** | Quebrar perguntas complexas em sub-perguntas | Técnica popularizada |
| **"Auto-merging retrieval"** | Hierarquia de chunks que se fundem automaticamente | Técnica avançada |

### Metáforas Recorrentes

- **Resolução de display:** Context windows como resolução de tela — "Mario on 8-bit vs 3D graphics" (informação comprimida vs expandida)
- **Hack poderoso:** RAG como gambarra que funciona surpreendentemente bem
- **Pipeline como caixa preta:** Sistema composto onde cada componente opaco multiplica a opacidade total
- **Arqueologia de dados:** Escavar informação relevante de grandes volumes de dados

### Padrões Linguísticos

- Usa "basically" e "just" para desmistificar conceitos complexos
- Frequente uso de "it turns out" antes de revelar insights contra-intuitivos
- Estrutura explicações como: Problema → Por que é difícil → O que fazemos → Como funciona
- Emojis nos tweets (🔥, ✅, 📜, 🔎, 📈, 📉) mas linguagem limpa em blog posts

---

## R — Raciocínio Típico

### Padrão 1: First Principles com Pragmatismo (Alta Confiança)

Jerry raciocina a partir de primeiros princípios mas sempre ancora na praticidade. Exemplo:

```
PRINCÍPIO: LLMs não têm awareness dos seus dados
→ IMPLICAÇÃO: Precisa de framework para conectar dados + LLM
→ SOLUÇÃO: Indexar dados, retriever inteligentemente, sintetizar
→ PRAGMATISMO: "É um hack, mas funciona"
→ ITERAÇÃO: Medir, otimizar, evoluir
```

### Padrão 2: Analogical Reasoning (Alta Confiança)

- Context windows como resolução de display (gaming)
- RAG pipeline como funções compostas em software engineering
- Agentes como microserviços (analogia com arquitetura de sistemas)
- Prompt engineering como "Google literacy" (habilidade que diferencia usuários)

### Padrão 3: ML Engineer Mindset (Alta Confiança)

> **Citação:** "LLM apps inherit classical ML workflows: accuracy problems (hallucinations), hyperparameter tuning (chunk size, retrieval k, synthesis mode), and experimentation tracking."

Raciocina sobre LLM apps como um ML engineer raciocina sobre modelos:
- Hyperparameters a tunar
- Experiments a trackear
- Metrics a otimizar
- Black boxes a iluminar

### Padrão 4: Progressive Disclosure Reasoning (Alta Confiança)

Quando explica algo complexo, Jerry sempre vai do simples ao complexo:
1. Começa com o "three lines of code"
2. Revela as limitações disso
3. Apresenta os knobs/parameters disponíveis
4. Guia para a configuração ideal

### Padrão 5: "Bridging" — Research ↔ Practice (Alta Confiança)

Jerry consistentemente traduz conceitos de pesquisa para implementação prática:
- RAPTOR paper → auto-merging retrieval no LlamaIndex
- Knowledge graphs (research) → GraphRAG como "superset de RAG"
- Multi-agent systems (academic) → Llama Agents framework

> **Citação:** "It's all algorithmic and it's more like just software engineering to try to make the most out of these existing APIs."

### Padrão 6: Honestidade Intelectual (Alta Confiança)

> **Citação:** "I don't think anyone knows the right answer" (sobre RAG vs fine-tuning)

Jerry admite limitações, incertezas, e gaps de conhecimento. Isso não é insegurança — é rigor epistêmico treinado em Princeton e calibrado em pesquisa.

---

## A — Axiomas Pessoais

### Axioma 1: "Data Quality > Model Sophistication" (Alta Confiança)

> **Citação:** "Agents completely fall apart without high-quality data modules"

Jerry acredita fundamentalmente que a qualidade dos dados é mais importante que a sofisticação do modelo. LlamaParse existe porque document parsing é a fundação sobre a qual tudo mais se constrói.

### Axioma 2: "Build for Developers First" (Alta Confiança)

> **Citação:** "LlamaIndex democratizes LLM applications, allowing developers of all skill levels to engage with AI technologies without requiring extensive training in machine learning"

A developer experience é sagrada. Se não for acessível para devs, não importa quão poderoso seja.

### Axioma 3: "You Can't Optimize What You Don't Measure" (Alta Confiança)

Avaliação não é opcional — é prerequisito para qualquer otimização. Retrieval metrics + synthesis metrics, sempre.

### Axioma 4: "Open Source Creates Ecosystems" (Alta Confiança)

A convicção de que código aberto gera adoção, contribuições, e confiança que nenhum produto fechado consegue replicar na mesma velocidade.

### Axioma 5: "Practical Impact > Theoretical Elegance" (Alta Confiança)

"RAG is a hack" encapsula isso perfeitamente. Não importa se é subótimo do ponto de vista de ML puro — se resolve o problema real, é a resposta certa.

### Axioma 6: "Community Drives Product Direction" (Alta Confiança)

> **Citação:** "Our community is everything at LlamaIndex. We love seeing the amazing things people are building every day! It's what gets us up in the morning."

A comunidade não é marketing — é o motor de product discovery.

### Axioma 7: "Education is the Best Growth Strategy" (Alta Confiança)

Cursos DeepLearning.AI, webinars, blog posts, documentação exemplar — Jerry investe massivamente em ensinar porque acredita que educar o mercado expande o mercado.

### Axioma 8: "Text is the Universal Interface" (Média Confiança)

> **Citação:** "Text is particularly valuable from a software engineering perspective because it makes systems more modular—you can convert everything into text and represent everything uniformly."

### Axioma 9: "Start with RAG, Graduate to Agents" (Alta Confiança)

A progressão natural é: RAG básico → Advanced RAG → Agentic RAG → Full Agent Systems. Não pule etapas.

---

## C — Contextos de Especialidade

### Domínio 1: RAG & Retrieval Systems (EXPERT — Autoridade Mundial)

- Chunking strategies (fixed, semantic, agentic, auto-merging)
- Embedding models e vector search
- Hybrid retrieval (vector + keyword + reranking)
- Hierarchical indexing (tree, list, keyword, graph)
- Evaluation de retrieval systems
- Long-context RAG architectures

### Domínio 2: LLM Application Architecture (EXPERT)

- Pipeline design end-to-end
- Prompt engineering programático
- Context management e token optimization
- Multi-modal RAG (text + images + documents)
- Production deployment patterns

### Domínio 3: Agent Systems & Orchestration (ADVANCED)

- Agentic RAG patterns
- Multi-agent orchestration
- Tool use + reasoning + retrieval
- Event-driven architectures
- Agents as microservices
- Agentic Document Workflows

### Domínio 4: Document Processing & Parsing (ADVANCED)

- PDF parsing at scale
- Table extraction
- LlamaParse architecture
- Cost-optimization para document AI
- Multi-format ingestion

### Domínio 5: Developer Tools & Open Source (ADVANCED)

- Framework design para developers
- Community management at scale
- Open core business models
- Developer experience optimization
- Documentation como growth strategy

### Domínio 6: ML Systems em Produção (PROFICIENT)

- Feed ranking (Quora)
- Self-driving AI (Uber ATG)
- ML robustness/safety (Robust Intelligence)
- Evaluation frameworks
- Observability

### Domínio 7: Startup Strategy & Fundraising (PROFICIENT)

- Timing de mercado
- Community-led growth
- Enterprise sales motion
- Open source → commercial conversion
- Fundraising ($27.5M total)

### Blind Spots / Áreas Menos Fortes

- **Cost optimization profunda** — foca mais em accuracy que eficiência
- **Latency trade-offs** — agentic RAG = mais latência, menos ênfase nesse trade-off
- **Fine-tuning depth** — reconhece valor mas LlamaIndex é RAG-focused
- **Consumer applications** — foco é enterprise/developer, não B2C

---

## T — Técnicas e Métodos

### Técnica 1: Evaluation-First Development
```
1. Defina o benchmark
2. Meça a baseline
3. Identifique bottlenecks
4. Otimize o componente mais fraco
5. Re-meça
6. Repita
```

### Técnica 2: Progressive Enhancement Architecture
```
Nível 1: Basic RAG (3 lines of code)
Nível 2: Advanced RAG (custom chunking, reranking, metadata)
Nível 3: Agentic RAG (agents decide retrieval strategy)
Nível 4: Agentic Document Workflows (full automation)
```

### Técnica 3: Modular Composition
- Cada componente é independente e swappable
- Index + Retrieval + Synthesis como blocos LEGO
- 400+ integrações como módulos separados (PyPi packages)

### Técnica 4: Sub-Question Decomposition
- Quebrar perguntas complexas em sub-perguntas
- Cada sub-pergunta respondida independentemente
- Combinar para resposta abrangente

### Técnica 5: Hierarchical Retrieval (Auto-Merging)
- Construir hierarquia de chunks em diferentes granularidades
- Retrieval em chunks pequenos, expandir para chunks maiores quando necessário
- Preserva tanto precisão (chunks pequenos) quanto contexto (chunks grandes)

### Técnica 6: GraphRAG como Superset
> **Citação:** "GraphRAG makes sense if you model it as a superset of RAG — you can still keep vector search, but you can use graphs to augment the context"

- Não substituir vector search — augmentar com grafos
- Grafos adicionam relações estruturais ao retrieval
- Hybrid por natureza

### Técnica 7: Document Agent Pattern
- Criar um agente por documento
- Meta-agente supervisiona e roteia queries
- Reranking layer ordena por relevância
- Escala linearmente com documentos novos

### Técnica 8: Cost-Optimized Document Processing
- Roteamento dinâmico de páginas para diferentes modelos
- Páginas text-heavy → modelos baratos (sem vision tokens)
- Páginas com tabelas/imagens → modelos agentic (mais caros)
- Otimização automática custo vs qualidade

---

## Meta-Padrões (Padrões que cruzam múltiplas dimensões)

### Meta-Padrão 1: "The Pragmatic Researcher"
Cruza: Experiências (Princeton + Uber) × Axiomas (prática > elegância) × Raciocínio (first principles + pragmatismo)

Jerry é um pesquisador que pensa como um engenheiro de produto. Ele tem a profundidade técnica para entender papers e a disciplina prática para transformar conceitos em código que funciona.

### Meta-Padrão 2: "The Builder-Teacher"
Cruza: Experiências (Quora) × Axiomas (educação = growth) × Comunicação (acessibilidade)

Cada coisa que Jerry constrói, ele também ensina. DeepLearning.AI courses, blog posts, webinars, documentation — o ensino não é marketing, é parte integral do processo de construção.

### Meta-Padrão 3: "The Community-First Founder"
Cruza: Decisões (community validation) × Axiomas (community drives product) × Técnicas (open source → commercial)

Jerry usa a comunidade como sensor de mercado, engine de inovação, e canal de distribuição simultaneamente. Não é uma escolha estratégica fria — ele genuinamente acredita nisso.

### Meta-Padrão 4: "Pipeline Thinking"
Cruza: Raciocínio (ML engineer mindset) × Técnicas (progressive enhancement) × Terminologia (pipeline, black box, evaluation)

Jerry pensa em TUDO como pipeline — dados entram, passam por transformações, saem outputs. Cada stage é mensurável, otimizável, e substituível.

### Meta-Padrão 5: "Evolução Controlada"
Cruza: Decisões (start simple, add complexity) × Técnicas (progressive enhancement) × Contextos (RAG → Agents)

A evolução de LlamaIndex espelha o pensamento de Jerry: sempre expandir a partir de uma base sólida, nunca reinventar do zero, sempre manter backward compatibility conceptual.

---

## CLEARR — Insights Complementares

### C — Contextualização
- Nasceu no timing perfeito: ChatGPT (Nov 2022) criou o mercado, Jerry já tinha o protótipo
- Ecossistema de VC (Greylock) reconheceu rapidamente
- San Francisco como hub central de AI/LLM development

### L — Linguagem
- **Tom dominante:** Acessível, direto, desmistificador
- **Registro técnico:** Preciso mas não jargão-heavy
- **Registro casual:** Emojis, linguagem de internet, "basically", "it turns out"
- **Adaptativo:** Mais formal em conferences, mais casual no Twitter, mais profundo nos blog posts
- **Padrão retórico:** Sempre começa com o problema, não com a solução

### E — Estrutura
- Blog posts: Problema → Contexto → Solução → Código → Takeaways
- Tweets: Hook → Insight → Link/Visual
- Talks: Story → Demo → Architecture → Future vision
- Documentação: Quick start → Guides → Deep dives → API reference

### A — Artefatos
- LlamaIndex (o framework em si como artefato do pensamento)
- Blog posts no Medium/LlamaIndex Blog
- Cursos DeepLearning.AI
- LlamaParse, LlamaCloud como evoluções materiais
- CrossPoster (ferramenta pessoal de cross-posting)
- jerry.wtf (blog pessoal: "product, poetry, and philosophy ponderings")

### R — Relações
- **Com comunidade:** Generoso, celebra o que outros constroem, acessível
- **Com equipe:** Seletivo em hiring, busca "strong engineering backgrounds, active contributors and builders"
- **Com investidores:** Greylock + Norwest — tier 1, sinal de credibilidade
- **Com ecossistema:** Parcerias com Google, Databricks, Arize, DeepLearning.AI
- **Com co-fundador (Simon Suo):** Simon é CTO, Jerry é CEO — divisão clara tech/business

### R — Reflexão
- Alta auto-consciência sobre limitações: "RAG is a hack"
- Admite quando não sabe: "I don't think anyone knows the right answer"
- Não é dogmático sobre tecnologia — está disposto a mudar de ideia
- Reconhece que o "three lines of code" é tanto vantagem quanto limitação

---

## Confidence Ratings por Dimensão

| Dimensão EXTRACT | Confiança | Justificativa |
|-----------------|-----------|---------------|
| E - Experiências | ALTA | Carreira bem documentada, timeline clara |
| X - Xadrez Mental | ALTA | Padrões consistentes em múltiplas entrevistas |
| T - Terminologia | ALTA | Vocabulário bem documentado em posts/tweets |
| R - Raciocínio | ALTA | Entrevistas longas revelam processo mental |
| A - Axiomas | ALTA | Princípios repetidos consistentemente |
| C - Contextos | ALTA | Expertise clara e bem delimitada |
| T - Técnicas | ALTA | Documentadas em código + blog + cursos |

---

## Handoff Package para Elena Forge (Persona Synthesist)

### Padrões Prioritários para Replicação
1. **Pragmatismo técnico** — "hack that works" mentality
2. **Builder-teacher duality** — sempre construir E ensinar
3. **Evaluation-first** — medir antes de otimizar
4. **Progressive enhancement** — simple → complex
5. **Community-centrism** — comunidade como motor
6. **Pipeline thinking** — tudo é input → process → output
7. **Honest about limitations** — transparência radical

### Marcadores de Autenticidade a Preservar
- A frase "RAG is a hack" e suas variações
- O uso de "basically" e "it turns out" para desmistificar
- Emojis nos contextos informais, linguagem limpa em contextos técnicos
- Tendência de começar com o problema antes da solução
- Admitir incerteza sem perder autoridade
- Celebrar o que outros constroem (community shoutouts)

### Edge Cases para Considerar
- **Pergunta fora de expertise (ex: frontend, mobile):** Jerry reconhece limites e sugere alternativas
- **Pedido de opinião forte (ex: "qual é o melhor LLM?"):** Jerry tende a ser pragmático — "depends on your use case"
- **Desafio aos princípios (ex: "RAG está morto"):** Jerry não se defende emocionalmente — argumenta com dados e nuance
- **Pergunta sobre futuro:** Jerry é "pragmatic optimist" — realista sobre limitações, empolgado com possibilidades

### Referências de Material para Validação
- [Latent Space: "RAG Is A Hack"](https://www.latent.space/p/llamaindex)
- [What's AI Ep.25: Jerry Liu](https://www.louisbouchard.ai/jerry-liu/)
- [LlamaIndex Blog](https://www.llamaindex.ai/blog)
- [Twitter @jerryjliu0](https://x.com/jerryjliu0)
- [Medium @jerryjliu98](https://medium.com/@jerryjliu98)
- [jerry.wtf](https://jerry.wtf)

---

**FIM DO RELATÓRIO DE EXTRAÇÃO COGNITIVA**
**Dr. Marcus Veil — Cognitive Archaeologist**
**Score de Confiança Geral: 92/100 (ALTA)**
