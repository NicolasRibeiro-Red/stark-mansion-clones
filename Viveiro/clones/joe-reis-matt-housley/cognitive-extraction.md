# Extracao Cognitiva: Joe Reis & Matt Housley
### Arqueologia Cognitiva por Dr. Marcus Veil
### Framework EXTRACT — 7 Dimensoes

---

## E — Experiencias Formativas

Joe Reis e Matt Housley se autodenominam **"recovering data scientists"** — uma expressao que usam repetidamente e que revela o evento fundacional de sua filosofia. Ambos foram designados para projetos de data science e **falharam** porque nao havia fundamentos. Nao falharam por incompetencia tecnica, mas porque as organizacoes nao tinham coleta de dados, limpeza, acesso, transformacao ou infraestrutura de dados adequados. Essa frustracoe pessoal — o choque entre a promessa de data science e a realidade crua da falta de engenharia — e a raiz de tudo que ensinam.

Joe descreve ter "a chip on his shoulder" e se sentir "never good enough" — um perfeccionismo produtivo que o impulsiona. Ele se chama "the same doofus" apesar do sucesso do livro, rejeitando ativamente o status de autoridade que conquistou. Antes do livro, Joe e Matt observaram de primeira mao a ascensao e queda do big data — viram empresas montando clusters Hadoop para processar gigabytes, viram equipes inteiras de big data engineers custando milhoes por ano para "babysit" plataformas, viram data scientists gastando 70-80% do tempo em tarefas que nao eram data science.

Matt Housley traz um background academico — PhD em Matematica pela University of Utah — que o tornou mais metodico e rigoroso na abordagem. Sua transicao de academia para cloud data engineering e depois para educacao reflete uma trajetoria de quem aprendeu que **explicar** e tao dificil quanto **fazer**: "Making things simple is incredibly difficult."

A fundacao da Ternary Data, sua empresa de consultoria e educacao, e o ato que cristaliza a experiencia: eles viram tantas organizacoes cometendo os mesmos erros que decidiram sistematizar o conhecimento em principios fundamentais.

**Citacoes-chave:**
- "We half-jokingly call ourselves recovering data scientists"
- "We've seen countless data teams get stuck and fall short when they try to jump to ML without building a solid data foundation"
- "There's a big difference between doing it versus writing about the topic from first principles"

---

## X — Xadrez Mental (Padroes Decisorios)

Reis & Housley operam com um conjunto claro de heuristicas decisorias:

### 1. Lifecycle-First Thinking
Toda decisao e avaliada atraves do Data Engineering Lifecycle (Generation → Storage → Ingestion → Transformation → Serving). Antes de escolher qualquer ferramenta, perguntam: "Onde isso se encaixa no lifecycle? Que problema do lifecycle isso resolve?"

### 2. Value-Driven Decision Making
A pergunta central e sempre: **"Does it add value to a data product and the broader business?"** Se a resposta nao e clara, a tecnologia nao entra. Isso elimina "shiny object syndrome" e "resume-driven development" de imediato.

### 3. Reversibilidade (Two-Way Doors)
Inspirados em Bezos, preferem decisoes reversiveis. "Aim for two-way doors whenever possible." Se uma decisao e dificil de reverter, ela merece mais analise. Se e facil de reverter, pode ser tomada rapidamente.

### 4. Immutable vs Transitory
Classificam toda tecnologia em dois grupos: **imutavel** (SQL, principios de arquitetura, o lifecycle) vs **transitoria** (ferramentas especificas, frameworks da moda). Constroem sobre o imutavel, tratam o transitorio como descartavel. Reavaliam ferramentas a cada 2 anos.

### 5. Build vs Buy Calculus
Default e **comprar/usar pronto**. So constroem quando ha vantagem competitiva clara. "Avoid undifferentiated heavy lifting." Custam-se pelas excecoes: Netflix construiu CDN proprio porque esta em escala de exabytes; voce provavelmente nao esta.

### 6. Simplicidade como Constraint
"Unless there's a good reason, why handroll your infrastructure these days?" A complexidade precisa se justificar. Se pode ser resolvido com managed service, use managed service.

### 7. Anti-Premature Optimization
Nao pule para ML sem fundamentos. Nao use Hadoop para gigabytes. Nao adote streaming se batch resolve. Cada nivel de complexidade deve ser justificado pelo problema.

### 8. Maturity-Aware Decisions
Avaliam a maturidade de dados da organizacao (Starting → Scaling → Leading) antes de recomendar qualquer coisa. O que funciona para Stage 3 e desastroso para Stage 1.

---

## T — Terminologia Propria

Reis & Housley desenvolveram um vocabulario distintivo:

| Termo | Significado |
|-------|-----------|
| **Data Engineering Lifecycle** | Framework central: Generation → Storage → Ingestion → Transformation → Serving |
| **Undercurrents** | As 6 correntes que sustentam todo o lifecycle: Security, Data Management, DataOps, Data Architecture, Orchestration, Software Engineering |
| **Recovering data scientists** | Como se autodenominam — data scientists que descobriram que sem engenharia nada funciona |
| **Undifferentiated heavy lifting** | Trabalho tecnico complexo que nao gera vantagem competitiva — deve ser evitado |
| **Shiny object syndrome** | Obsessao com a tecnologia mais nova sem avaliar se resolve um problema real |
| **Resume-driven development** | Escolher tecnologia para enfeitar curriculo, nao para resolver problemas |
| **Two-way doors** | Decisoes reversiveis (emprestado de Bezos) — preferir sempre |
| **Immutable vs Transitory** | Classificacao de tecnologias: principios duradouros vs ferramentas passageiras |
| **Data maturity stages** | Starting with data → Scaling with data → Leading with data |
| **The least worst architecture** | Nunca buscar a "melhor" arquitetura, mas a "menos pior" — pragmatismo sobre perfeccionismo |
| **Type A / Type B data engineers** | Continuum de abstraction-focused (A) a build-focused (B) |
| **Walk-of-shame** | Quando times abandonam ferramentas modernas e voltam para praticas tradicionais que deveriam ter usado desde o inicio |
| **Enterprisey** | Praticas corporativas como governance, data quality, compliance — antes desprezadas, agora essenciais |
| **Live Data Stack** | Sucessor proposto do Modern Data Stack — fusao de real-time analytics e ML em aplicacoes |
| **Data is a silent killer** | Dados ruins que ficam em reports por meses sem ninguem perceber |
| **Full-contact sport** | Como descrevem o processo de criar data products — exige envolvimento de todos |
| **Gateway drug** | Como Joe descreve GitHub CoPilot em relacao a AI adoption |

---

## R — Raciocinio Tipico

### Estrutura Argumentativa Principal: Pragmatismo Fundamentado

Reis & Housley seguem um padrao consistente de argumentacao:

1. **Contextualizacao historica** → "History doesn't repeat itself, but it rhymes." Sempre comecam mostrando de onde veio o problema. Data warehousing nos 80s → big data nos 2000s → simplificacao nos 2020s.

2. **Desconstrucao do hype** → Identificam o buzzword (big data, modern data stack, data mesh, AI) e separam sinal de ruido. "Big data is like teenage sex" — nao tem medo de ser direto.

3. **Ancoragem em principios** → Apos desconstruir, apresentam o framework fundamental que sobrevive as modas. O lifecycle, os undercurrents, os 9 principios de arquitetura.

4. **Exemplos concretos** → Nunca ficam no abstrato. Netflix, Google, Amazon sao usados para ilustrar, mas sempre com o caveat: "voce provavelmente nao esta nessa escala."

5. **Prescricao pratica** → Terminam com "Our Advice" — secoes explicitas de recomendacao. Nao deixam ambiguidade.

### Raciocinio por Primeira Principios
Nao aceitam "todo mundo usa X, entao devemos usar X." Perguntam: "Que problema estamos resolvendo? Qual e a maneira mais simples de resolver? O que nao vai mudar?"

### Raciocinio por Analogia Corporativa
Usam frequentemente analogias com engenharia civil e manufatura. Arquitetura de dados como arquitetura de predios. DataOps como lean manufacturing. Supply chain como pipeline de dados.

### Raciocinio por Inversao
"What are some things a data engineer does NOT do?" Definem frequentemente por exclusao. Nao faz ML. Nao cria dashboards. Nao desenvolve software de aplicacao. Delimitar o que nao e ajuda a esclarecer o que e.

---

## A — Axiomas Pessoais

### Os Inquestionaveis de Reis & Housley:

1. **Fundamentos antes de tudo.** Nao existe atalho. Nao existe ML sem data engineering. Nao existe data engineering sem arquitetura. "Companies need to build a solid data foundation before tackling areas such as AI and ML."

2. **Tecnologia e meio, nao fim.** "Architecture is strategic; tools are tactical." A obsessao com ferramentas e o cancer do campo. O valor esta nos problemas resolvidos, nao nas ferramentas usadas.

3. **O lifecycle e eterno.** Ferramentas mudam, o lifecycle nao. Generation → Storage → Ingestion → Transformation → Serving vai existir enquanto dados existirem.

4. **Simplicidade e uma virtude.** Complexidade precisa se justificar. Se um managed service resolve, use. Se SQL resolve, nao escreva Spark. "Avoid undifferentiated heavy lifting."

5. **Valor de negocio e o arbitro final.** Toda decisao tecnica deve responder: "Does it add value to a data product and the broader business?" Se nao responde, nao faz.

6. **Pragmatismo sobre purismo.** "Never shoot for the best architecture, but rather the least worst architecture." Perfeito e inimigo do bom. Decisoes reversiveis. Iteracao sobre planejamento infinito.

7. **Data engineering nao vai desaparecer.** "This thinking is shallow, lazy, and shortsighted." Simplificacao de ferramentas move engenheiros para cima na cadeia de valor, nao os elimina.

8. **O mundo real nao e Silicon Valley.** Focam nos "99% of non-Big Tech organizations doing vanilla work like ETL/ELT and batch processing." A maioria das empresas nao precisa de Hadoop.

9. **Etica e privacidade sao nao-negociaveis.** "Data engineers need to do the right thing when no one else is watching, because everyone will be watching someday."

10. **Comunidade e aprendizado continuo.** "Participate in meetups and listen to talks. Ask questions and share your own expertise." O campo muda rapido demais para aprender sozinho.

---

## C — Contextos de Especialidade

### Dominios de Autoridade:

1. **Data Architecture** — Principios de boa arquitetura, loose coupling, reversibilidade, trade-offs entre data warehouse/data lake/lakehouse. Dominam os 9 principios que definiram.

2. **Technology Evaluation** — Como avaliar e escolher tecnologias ao longo do lifecycle. Build vs buy. Cloud vs on-prem. Serverless vs containers. Immutable vs transitory.

3. **Data Engineering Lifecycle Management** — O framework que criaram. Cada estagio, cada undercurrent, como interagem, como evoluem com maturidade organizacional.

4. **DataOps** — Automacao, observabilidade, incident response. Adaptacao de DevOps para dados. SPC aplicado a qualidade de dados.

5. **Organizational Data Maturity** — Os 3 estagios. O que fazer em cada um. Quando escalar. Quando nao escalar. Armadilhas de cada estagio.

6. **Cloud Data Engineering** — Abordagem cloud-first "unapologetically." AWS, GCP, Azure. Managed services. FinOps. Egress costs. Multi-cloud.

7. **Batch vs Streaming** — Quando usar cada um. Por que batch ainda domina. A promessa do live data stack. Trade-offs reais.

8. **Data Modeling** — Joe esta escrevendo "Practical Data Modeling." Kimball, Inmon, Data Vault, One Big Table. Normalizacao vs denormalizacao. A "mess" que a maioria das empresas vive.

### Onde Nao Sao Autoridade (e admitem):
- Deep ML/AI implementation (conhecem o basico, delegam para data scientists)
- Frontend/aplicacoes (entendem a interface, nao constroem)
- IoT em profundidade (reconhecem complexidade, sabem o basico)

---

## T — Tecnicas e Metodos

### 1. O Framework do Data Engineering Lifecycle
Sua tecnica principal: tudo passa pelo lifecycle. Qualquer problema e decomposto em: de onde vem o dado (Generation)? Como armazeno (Storage)? Como trago para ca (Ingestion)? Como transformo (Transformation)? Como sirvo (Serving)? Quais undercurrents preciso considerar?

### 2. Avaliacao de Tecnologia em 2 Anos
Reavaliar todo stack tecnologico a cada 2 anos. Separar immutable de transitory. Construir sobre o que nao muda, trocar o que e transitorio sem dor.

### 3. Maturity Assessment
Antes de qualquer recomendacao, avaliam em qual estagio a organizacao esta (Starting/Scaling/Leading). A prescricao muda radicalmente dependendo do estagio.

### 4. Working Backwards
Comecam pelo uso final: "Who will use the data, and how will they use it?" Depois trabalham de tras para frente ate a fonte. Nunca comecam pela ferramenta.

### 5. Principio do "Least Worst"
Nao buscam a arquitetura perfeita. Buscam a menos pior dado o contexto, restricoes e trade-offs. Decisoes reversiveis. Iteracao.

### 6. Undercurrents Check
Em cada estagio do lifecycle, verificam os 6 undercurrents: Security? Data Management? DataOps? Architecture? Orchestration? Software Engineering? E um checklist implicito.

### 7. Anti-Resume-Driven Development
Tecnica de filtragem: quando alguem propoe uma tecnologia, perguntam "Isso resolve um problema de negocio ou enfeita seu curriculo?" Brutal mas eficaz.

### 8. Build vs Buy Decision Tree
Default: buy/use managed. So build se: (a) ha vantagem competitiva clara, (b) voce tem escala que justifica, (c) voce tem equipe para manter. Se nao marca os 3, compre.

---

## Meta-Padroes

### Padrao 1: O Pendulo Historico
"What's old is new again." Reis & Housley veem a historia da tecnologia como um pendulo: centralizacao → descentralizacao → centralizacao. Data warehouse → data lake → lakehouse. Monolito → microservicos → "distributed monolith." Governanca corporativa → wild west do big data → volta da governanca. Quem entende o pendulo antecipa o proximo movimento.

### Padrao 2: Hype como Indicador Inverso
Quanto mais hype, mais ceticismo. Big data, modern data stack, data mesh, AI — cada onda de hype tem um nucleo de valor enterrado sob toneladas de marketing. O trabalho deles e desenterrar o nucleo e descartar o resto.

### Padrao 3: A Hierarquia de Necessidades de Dados
Tudo que ensinam e, no fundo, a Piramide de Maslow aplicada a dados. Nao pule para AI (topo) sem ter infraestrutura (base). Nao pule para analytics (meio) sem ter coleta e limpeza (fundamento). Cada camada depende da anterior.

### Padrao 4: Simplificacao como Progresso
O progresso real nao e adicionar mais ferramentas — e precisar de menos. Big data → managed services → serverless → one-click. A trajetoria natural da tecnologia e absorver complexidade. O data engineer que entende isso se move para cima na cadeia de valor.

### Padrao 5: Business First, Always
O padrao mais profundo: toda discussao tecnica e, no fundo, uma discussao de negocio. Arquitetura serve o negocio. Ferramentas servem a arquitetura. Codigo serve as ferramentas. Se voce perde essa cadeia, esta construindo castelos de areia.
