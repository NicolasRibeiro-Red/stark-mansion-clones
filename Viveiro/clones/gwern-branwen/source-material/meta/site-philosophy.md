# Gwern.net: Filosofia do Site, Estrutura & Metodologia

## Filosofia Core

Gwern.net incorpora abordagem "Long Now" para conteudo digital. O site trata escrita como works-in-progress perpetuos desenhados para melhorar ao longo de decadas, nao desaparecer apos viralidade breve. Como o autor nota: "What has been done, thought, written, or spoken is not culture; culture is only that fraction which is *remembered*."

Principio fundacional trata o site como "seguro" - se singularidade tecnologica chegar, escritos se tornam irrelevantes; se nao, ganham valor duradouro.

## Estrategia de Conteudo

**Audiencia Alvo**: Escreve primariamente para seu eu futuro - "an intelligent and interested" pessoa que esqueceu raciocinio anterior. Paradoxalmente serve leitores mais amplos com valor similar.

**Geracao de Ideias**: Topicos emergem de irritacao genuina: "how irritating that there's no good webpage/Wikipedia article on X" ou "this is the third time I've had to explain this." Exemplos: DNB FAQ (repeticao em mailing list), artigo modafinil (dificuldade de sourcing), analise Silk Road (cobertura mainstream pobre).

**Escopo**: Essays vao de estatistica a psicologia, self-experiments, filosofia, poesia, programacao, anime, e jornalismo investigativo - unificados por curiosidade intelectual sustentada.

## Framework de Long Content

Diferente de blog posts efemeros, "Long Content" exibe:

- Desenhado para lifespans de 60+ anos
- Refinado continuamente com nova evidencia
- Inclui predicoes verificaveis que maturam ao longo do tempo
- Constroi entendimento sistematico, nao momentos virais
- Acumula evidencia confirmando E contradizendo

## Medidas de Longevidade Tecnica

**Infraestrutura**:
- 100% Free/Open Source software
- Standards abertos e legibilidade textual humana
- Compilacao HTML estatica (evita database rot)
- Armazenamento DVCS com backups regulares
- Arquivamento via WebCitation e Internet Archive

**Estrategia de Preservacao**: Sites estaticos permitem recuperacao mesmo se software original bitrotar - arquivos flat permanecem legiveis via ferramentas XML ou inspecao manual, diferente de CMSes dinamicos com conteudo em formatos binarios opacos.

## Processo de Escrita

Gwern descreve experiencia fenomenologica incomum: escrita emerge como recitacao mental involuntaria - "text earworms" que loopam ate transcritos. Difere radicalmente de paralisia de pagina em branco.

Processo segue duas fases:
1. **Big Bang**: Essays inteiros materializam via transcricao rapida de voz interna
2. **Incremental**: Edicao dolorosa, integracao de referencias, copyediting

Produz output consistente apesar de esforco consciente limitado alocado a "escrita como trabalho."

## Sistema de Gerenciamento de Informacao

**Aquisicao & Armazenamento**:
- Spaced repetition (Mnemosyne) para fatos criticos
- Evernote para web clippings e excerpts de pesquisa
- Sistema customizado de arquivamento para preservacao de URLs
- RSS feeds (Liferea) para monitoramento sistematico de noticias
- Google Calendar reminders para projetos

**Sintese**:
- Footnotes e asides parenteticos acumulam em essays maiores
- Colecoes massivas de citacoes eventualmente coalescem em pecas standalone
- Exemplo: citacoes de pesquisa sobre Iodo desenvolveram de referencias dispersas em meta-analise compreensiva

**Retrieval**: Google search, Evernote queries, grep em arquivos fonte, Mnemosyne, e memoria visual criam sistema de recall distribuido.

## Metadata & Controle de Qualidade

**Status Tags**:
- "Notes" (links/snippets dispersos)
- "Draft" (tese coerente emergindo)
- "In progress" (bem desenvolvido)
- "Finished" (completo ate nova evidencia)

**Confidence Tags**: Escala de oito pontos de "certain" a "impossible," adaptada de Kesselman's Estimative Words, expressando probabilidade subjetiva de corretude.

**Importance Ratings**: Rankings em decis (0-10) distinguem conteudo trivial de material life-changing, permitindo priorizacao do leitor.

## Checklist de Escrita (Foco em Automacao)

**Verificacao de sintaxe**:
- Brackets/quotes balanceados
- Markdown linting com script customizado
- Validacao HTML Tidy
- Linkchecker para URLs mortas

**Referencias**:
- Tooltips com metadata academica
- Links full-text ou copias locais
- Links Amazon para livros indisponiveis

**Standards de linguagem**:
- Spellcheck e assessment de legibilidade
- Verificacao de palavras de probabilidade
- Flags "statistically significant" (evitando confusao NHST)
- Conversao de unidades metricas

**Integridade de conteudo**:
- Reprodutibilidade de codigo (rerun todas estatisticas)
- Compliance com checklist de reporting (STROBE, CONSORT, PRISMA)
- Setup de prediction tracking (Google/Scholar Alerts)
- Cross-references para essays relacionados

## Estatisticas & Evolucao do Site

**Escala**: Em 2022, >443 arquivos Markdown contendo >4.38 milhoes de palavras (31MB source); site compilado excede 72GB incluindo imagens e arquivos.

**Padrao de Crescimento**: Expansao autocatalitica onde:
- Ferramentas recentemente aprendidas (meta-analise em R, modelos lineares) se tornam reutilizaveis
- Deteccao de interesse se torna habitual
- Links e citacoes acumulados atingem massa critica para essays

**Trafego**: 50-100k pageviews mensais consistentes com spikes de Hacker News/Reddit; 7.98 milhoes de pageviews em 3.8 milhoes de usuarios unicos na primeira decada.

## Filosofia de Design

**Abordagem de Site Estatico**:
- Permite arquivamento como tarballs completos
- Previne complexity creep inerente a sistemas dinamicos
- Reduz burden de sysadmin (sem spam, hacking, updates)
- Suporta degradacao graciosa apos bitrot

## Licenciamento & Distribuicao

Todo conteudo liberado sob Creative Commons dominio publico (CC-0), reduzindo friccao para copia e reuso. Autor considera obscuridade ameaca maior que pirataria.

## Visao de Longo Prazo

Gwern enquadra como "think Less Wrong and act Long Now" - simultaneamente preparando para potencial singularidade tecnologica enquanto constroi como se civilizacao permanecesse estavel. Essays servem como seguro intelectual: se futuros radicais chegarem, se tornam artefatos; se nao, scholarship sustentado compoem valor atraves de decadas.

Aposta fundamental: escrita persistente acumula retornos exponenciais atraves de maturacao de predicoes, sintese de evidencia acumulada, e desenvolvimento de ferramentas.
