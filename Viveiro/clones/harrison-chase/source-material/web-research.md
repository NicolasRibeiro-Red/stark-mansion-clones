# Pesquisa Web: Harrison Chase (LangChain)
## Data: 2026-02-11
## Fontes: 30+ (listadas abaixo)

---

## 1. BACKGROUND E CARREIRA

### Educacao
- Harvard University (2017) - Statistics e Computer Science
- Interesse em AI comecou via sports analytics (NBA/NFL fan, jogou futebol)
- Sports analytics como gateway para data science/ML

### Carreira Pre-LangChain

**Kensho Technologies (Fintech)**
- Liderou entity linking team
- Conectar dados dispares em insights acionaveis
- Exposicao a pipelines complexos de dados

**Robust Intelligence (ML Testing)**
- Liderou ML team, especializacao em testes de modelos complexos
- HACKATHON INTERNO: construiu bot para responder perguntas do Notion/Slack (RAG primitivo)
- Trabalhou com Will (futuro LangChain) e dois outros
- **Jerry Liu (LlamaIndex) era colega** - mesmo time por 2 anos
- Ambos LangChain e LlamaIndex emergiram da mesma empresa

### Origem do LangChain
- **16-25 Outubro 2022**: Primeiras linhas de codigo - wrapper Python de 800 linhas para prompt templates
- **Primeiro tweet**: 24 outubro 2022
- GitHub pessoal: hwchase17, side project
- **Sem plano grandioso** - identificou padroes comuns em meetups de AI generativa
- **Novembro 2022**: ChatGPT lancado, "changed everything"
- **Janeiro 2023**: Incorporou empresa com **Ankush Gola** (ex-Facebook, ex-Robust Intelligence)
- **Abril 2023**: $10M seed round (Benchmark)
- **Fevereiro 2024**: $25M Series A (Sequoia, $200M valuation)
- **Outubro 2025**: $125M Series B ($1.25B valuation - unicornio) - IVP, CapitalG, Sapphire, Sequoia, Benchmark + strategic investors (ServiceNow, Workday, Cisco, Datadog, Databricks)

---

## 2. FILOSOFIA SOBRE AI

### Citacoes Centrais
- "LLMs are this great, transformational new technology. They are even more powerful when connected to external data and APIs... building reliable agents is quite hard!"
- "Developers needed a cohesive way to tie together various components of LLM workflows."
- "Our goal is to abstract away the tedious parts of LLM workflows so developers can focus on solving real problems."

### Tres Pilares de Inovacao
1. **Modular Design**: Building blocks customizaveis
2. **Community-Driven Development**: Open-source para contribuicoes globais
3. **Iterative Improvement**: Ciclos rapidos, shipping same-day com model providers

### Posicoes Filosoficas Chave
- **Model neutrality** e essencial
- **Context engineering** (nao so modelos melhores) determina sucesso de agentes
- **Cognitive architecture e onde a vantagem competitiva vive** - infra e commodity
- **Orquestracao e ~10% do trabalho** de construir um agente

---

## 3. DECISOES TECNICAS

### LangChain Architecture
- 700+ integracoes (LLM providers, vector databases, tools)
- Composability first: tudo se conecta a tudo
- **Problemas do 0.x reconhecidos**: breaking changes, hidden prompts, package bloat, docs desatualizados
- "People wanted more control... we traded power for ease of use."

### LangGraph
- Lancado 2024, grafos direcionados para aplicacoes stateful multi-agente
- Nodes (acoes) e edges (transicoes de estado)
- Loops, conditional branching, multi-agent, human-in-the-loop
- "LangGraph is the runtime. LangChain is the abstraction. Deep agents are the harness."

### LangSmith
- Desde inicio da empresa
- Observabilidade e avaliacao de LLM apps
- **Neutro a framework e LLM** - filosofia aberta
- Cultural shift: "send us a trace" em vez de "show me the code"

### Estrategia Tres Camadas
- LangChain = componentes
- LangGraph = orquestracao
- LangSmith = observabilidade em producao

### Context Engineering (conceito central)
**Definicao dele**: "Context engineering is building dynamic systems to provide the right information and tools in the right format such that the LLM can plausibly accomplish the task."
- Prompt engineering e SUBSET de context engineering
- Componentes: tool use, short-term memory, long-term memory, retrieval
- "Models are not mind readers."
- "Everything's context engineering... it actually really describes everything we've done at LangChain."

### Cognitive Architecture
**Definicao**: "How your system thinks -- the flow of code/prompts/LLM calls that takes user input and performs actions or generates a response."
- Credita Flo Crivello pelo termo
- Niveis de autonomia: hard-coded logic ate fully autonomous
- "None of these are strictly 'better' than others"

### Own vs Outsource (conceito Bezos)
- "Focus on what makes your beer taste better."
- OWN cognitive architecture (diferenciacao)
- OUTSOURCE agentic infrastructure (commodity)

---

## 4. ESTILO DE COMUNICACAO

### Fala
- Usa "I think", "probably", "I'd say" frequentemente (hedging)
- Usa "like" como filler
- Usa "just" frequentemente
- Colaborativo, nao declarativo
- Credita outros
- Humildade epistemica: "It's very hard to predict the future"
- Auto-depreciativo: piada do website do Berkshire Hathaway
- Admite incerteza: "I don't really have an amazing answer"
- Humor casual: "I'll tell my mom again that I'm back on the podcast"

### Blog
- Deep dives tecnicos explicando POR QUE, nao so o que
- Reconhece problemas honestamente
- Posts mais populares = "deeper dive ones"
- Tabelas, categorizacao clara, argumentos estruturados
- Define termos precisamente antes de construir argumentos

### Twitter/X (@hwchase17, ~85K followers)
- Conversacional e community-oriented
- Busca input: "tell me why your agent framework is better than langgraph"
- Anuncia updates com entusiasmo sem hype
- Mix de conteudo tecnico com product announcements

### Podcasts
- Pessoal e aberto (sports, background)
- Pensa em voz alta, reconsidera posicoes mid-answer
- Tecnico mas acessivel
- Tangents que voltam ao ponto principal

### Padrao Geral
- **Pragmatico otimista**: excited mas grounded
- **Honesto sobre falhas**: discute limitacoes abertamente
- **Criticas = data points**, nao ataques
- **Evita overselling** - mesmo dos proprios produtos
- **Prefere nuance a framing binario**

---

## 5. VISAO DE FUTURO

### Deep Agents (ODSC 2025)
- Planejam, lembram, adaptam sem orquestracao humana constante
- "Deep agents are about trusting that loop -- trusting the model to do more."
- 4 pilares: dynamic planning, file systems, subagents, prompting as communication
- "It's not a workflow engine. It's still a loop."
- "Humans understand file systems, and so do LLMs."

### Ambient Agents (Interrupt 2025)
- Event-driven, rodam em background continuamente
- Milhares simultaneos, nao um de cada vez
- "Ambient does not mean fully autonomous"
- 4 patterns human-in-the-loop: approve/reject, edit, clarifying questions, time-travel
- Agent Inbox: interface consolidada para revisar acoes pendentes

### Long-Horizon Agents
- Viaveis agora: melhores LLMs + harnesses sofisticados
- "File system pilled" - todo agente precisa de file system
- Coding agents liderando adocao

### Agent Engineering
- Nova disciplina definida no Interrupt 2025
- Requer: prompting, engineering, product sense, ML understanding

### Tendencias Futuras
- Model diversity: agentes usando multiplos LLMs
- Sleep-time compute: agentes analisam traces e atualizam proprias instrucoes
- Memory como moat competitivo
- Async/sync duality
- Workspace concept: agentes e humanos em estado compartilhado

---

## 6. CITACOES NOTAVEIS

### Sobre Agentes
- "An AI agent is a system that uses an LLM to decide the control flow of an application."
- "Agents are like digital labor."
- "I don't think we've nailed the right way to interact with these agent applications."
- "Deep agents are about trusting that loop."

### Sobre Construir
- "It's so early on, there's so much to be built."
- "Innovation doesn't happen in a vacuum."
- "The true measure of success isn't just how many people use your tool but how much value they derive from it."
- "Just just build, and just try building?"

### Sobre Decisoes Tecnicas
- "People wanted more control... we traded power for ease of use."
- "LangGraph is the runtime. LangChain is the abstraction."
- "Focus on what makes your beer taste better."
- "If you can't do a good job, might as well do the worst job possible" (design)

### Sobre Contexto
- "Models are not mind readers."
- "Everything's context engineering."
- "Writing an effective system prompt is still the hardest part of building an agent."

### Sobre Avaliacao
- "For all these generative models, it's really hard to evaluate them."
- "Using language models themselves to evaluate language model outputs."

### Sobre Pragmatismo
- "Well, these agents might not be 99% reliable... but they can probably still be good enough to be useful?"
- "I don't really have an amazing answer."

### Frases/Padroes Recorrentes
- "I think" (hedging extremamente frequente)
- "Like" (filler)
- "The thing that I find interesting is..."
- "What we've seen is..."
- Pensamento em espectro/gradiente vs categorias binarias
- Analogias esportivas

---

## 7. OPEN SOURCE E COMUNIDADE

- Comunidade Discord de 93,000 pessoas (mid-2023)
- Extremamente presente na comunidade dev
- Presta atencao nos problemas dos devs antes de construir
- Hands-on: codigo a Discord interactions
- Busca input da comunidade em decisoes de produto
- Enfrenta criticas de Aravind Srinivas, Jim Fan, Max Woolf, Reddit/HN
- Compara debate a "timeless ORM debate"
- "I agree that those are big pain points"
- Nunca fica defensivo, mantem humildade
- Cita Brian Chesky como influencia de lideranca
- **Anecdota**: codando durante eventos da Sequoia enquanto outros apresentavam

---

## 8. TALKS, ENTREVISTAS E PODCASTS CHAVE

1. Latent Space Podcast - "The Point of LangChain" (Set 2023)
2. Sequoia "Training Data" - "Building the Orchestration Layer" (2024)
3. Sequoia "Training Data" - "Context Engineering Long-Horizon Agents" (2025)
4. Sequoia "Training Data" - "Ambient Agents and Agent Inbox" (2025)
5. The Generalist - "The Evolution of AI Agents" com Stanislas Polu (Jul 2025)
6. Arize AI Observe - "Future of Agents"
7. Unsupervised Learning - "Eval, Agent Landscape, Open vs Closed"
8. Interrupt 2025 (keynote, Mai 2025)
9. ODSC AI West 2025 - "Deep Agents" (Nov 2025)
10. TED AI San Francisco
11. 3 Cursos com Andrew Ng/DeepLearning.AI

---

## 9. VIEWS SOBRE RAG E AGENTES

### RAG
- "The preferred technique for bringing context to LLMs"
- Hackathon na Robust Intelligence = RAG primitivo
- RAG como componente de context engineering, nao paradigma isolado

### Espectro de Agentes
1. **Router** - LLM roteia inputs
2. **State Machine** - sistema faz loop, decide se continua
3. **Autonomous Agent** - constroi tools, lembra, reutiliza
- "Sweet spot" atual no meio: constrained yet flexible

### Evolucao
- Early: AutoGPT-style (imaginativo mas impratico)
- Current: Domain-specific cognitive architectures
- Future: Deep agents com planning, memory, subagents
- Agentes bem-sucedidos codificam modelos mentais especificos

### MCP
- Inicialmente cetico, comecou a ver valor
- Util para: tools em agentes que voce nao controla (Claude Desktop, Cursor)
- Nao serve para: construir production agents como Cursor
- "I don't think anyone is going to build the next Cursor based solely on MCP integrations"

### Onde Agentes Funcionam
- Customer support: production-ready (Klarna)
- Coding: emergente
- Clientes: Rippling, Vanta, Cloudflare, Replit, Harvey

---

## 10. RELACOES NO ECOSSISTEMA

- **Jerry Liu (LlamaIndex)**: ex-colega Robust Intelligence, collegial mas competitivo
- **Andrew Ng**: 3 cursos juntos, promove trabalho do Chase
- **Sequoia Capital**: investidor principal, 3+ aparicoes no podcast
- **Brian Chesky**: influencia em lideranca product-centric
- **Stanislas Polu (Dust)**: sparring partner intelectual
- **Nuno Campos**: colaborador tecnico, debatem publicamente
- **Ankush Gola**: co-fundador, lower profile

---

## FONTES

1. frederick.ai/blog/harrison-chase-langchain
2. latent.space/p/langchain
3. sequoiacap.com/podcast/training-data-harrison-chase/
4. sequoiacap.com/podcast/context-engineering-long-horizon-agents/
5. sequoiacap.com/podcast/training-data-harrison-chase-2/
6. blog.langchain.com/three-years-langchain/
7. blog.langchain.com/what-is-an-agent/
8. blog.langchain.com/what-is-a-cognitive-architecture/
9. blog.langchain.com/the-rise-of-context-engineering/
10. blog.langchain.com/not-another-workflow-builder/
11. blog.langchain.com/mcp-fad-or-fixture/
12. blog.langchain.com/own-your-cognitive-architecture/
13. opendatascience.com/harrison-chase-on-deep-agents/
14. skimai.com/10-quotes-on-ai-agents-from-harrison-chase/
15. generalist.com/p/the-evolution-of-ai-agents
16. techcrunch.com/2025/10/21/langchain-1-25b-valuation/
17. digidai.github.io/2025/11/23/harrison-chase-deep-analysis/
18. blog.langchain.com/interrupt-2025-recap/
19. brunswickai.net/2025/05/20/interrupt-2025-keynote-analysis/
20. bigdatawire.com/people-to-watch-2024-harrison-chase/
21. tedai-sanfrancisco.ted.com/speakers/harrison-chase/
22. x.com/hwchase17
23. linkedin.com/in/harrison-chase-961287118/
24. deeplearning.ai/short-courses/langchain-for-llm-application-development/
25. crunchbase.com/person/harrison-chase
26. fortune.com/2025/10/20/langchain-unicorn-125m-funding/
