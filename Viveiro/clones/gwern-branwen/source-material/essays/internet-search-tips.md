# Internet Search Tips - Gwern Branwen

## Filosofia Core
"Your only search guaranteed to fail is the one you never run." Desenvolva habitos sistematicos de busca antes de comecar qualquer query.

## Preparacao Essencial

**Dominio de Sintaxe**
- Domine operadores booleanos e operadores de busca Google
- Use aspas para matches exatos: `"exact phrase"`
- Aplique negacao com hifens: `topic -unwanted`
- Restrinja por dominio: `site:example.com`
- Combine operadores: `(term1 OR term2) -exclusion`

**Ferramentas de Velocidade**
Implemente atalhos para busca instantanea em Google Scholar, Wikipedia, Google:
- Windows: AutoHotkey
- Mac: Quicksilver
- Linux: XMonad, Surfraw

## Workflow de Busca

### Abordagem Inicial
1. Comece com buscas simples titulo + autor
2. Progrida para combinacoes booleanas se necessario
3. Aplique search engines especificos de dominio
4. Escale para tecnicas avancadas apenas quando necessario

### Tecnicas de Manipulacao de Titulo

**Refinamento Iterativo**
- Delete palavras incrementalmente dos titulos
- Remova pontuacao e caracteres especiais
- Divida dois-pontos em frases separadas entre aspas
- Teste variacoes britanicas/americanas
- Tente buscas de subtitulo separadamente

**Ajuste de Metadata**
- Adicione ou remova anos de publicacao
- Busque sobrenomes de autores independentemente
- Tente ordenacoes alternativas de autores

### Busca por Citacoes

Use frases memoraveis e unicas ao inves de excerpts longos. Busque sentencas novas com wording distintivo. Quebre citacoes longas em sub-buscas focando em passagens de inicio e fim.

Priorize "robust quotes" que sobrevivem garbling atraves de transmissao repetida.

## Taticas Especificas de Database

**Google Scholar**
- Cheque links fulltext alem do botao obvio [PDF]
- Procure "soft walls" bloqueando crawlers mas permitindo downloads
- Utilize alertas de citacao e features de artigos relacionados
- Buscas de citacao reversa identificam failures-to-replicate

**Internet Archive**
- Foque buscas com `site:archive.org` no Google
- Explore colecoes menos conhecidas do Archive
- Use feature de wildcard de URL (`URL/*`) para listar todas versoes arquivadas
- Cheque arquivos domain-wide quando URLs especificas falham

**Colecoes Especializadas**
- ERIC para pesquisa educacional
- PubMed para literatura medica
- Wellcome Library para materiais historicos
- HathiTrust para scans de livros
- ProQuest/JSTOR para publicacoes obscuras

## Metodos de Circumvencao de Paywall

**Solucoes Primarias**
- Prepend dominio Sci-Hub: `sci-hub.st/[journal-url]`
- Busque DOI diretamente no LibGen
- Use search engine fulltext Z-Library

**Acesso Institucional**
- Alavanque acesso proxy universitario
- Visite computadores de biblioteca universitaria com login publico
- Explore subscricoes de database de biblioteca publica

**Recursos Secundarios**
- ResearchGate (com ressalvas sobre confiabilidade)
- Academia.edu (estrutura fragil de links)
- Requests por email para autores
- PACER para documentos de tribunal federal US
- Comunidades subreddit: r/Scholar, #icanhazpdf no Twitter

## Estrategias Hard-Target

**Metodo de Citacao Reversa**
Acesse features "cited by" para encontrar versoes relacionadas ou replicacoes posteriores que podem estar mais disponiveis.

**Busca em Compilacoes**
Livros e proceedings de conferencias frequentemente contem papers que nao aparecem em buscas diretas. Busque titulo do volume/livro para localizar papers constituintes.

**Navegacao em Nivel de Issue**
Consulte indices de conteudo de journals diretamente quando papers misteriosamente desaparecem de resultados de busca.

**Otimizacao de Date Range**
Restrinja buscas a ±4 anos ao redor de datas suspeitas de publicacao.

**Exploracao de Jargao**
Identifique terminologia tecnica em snippets de busca. Papers discutindo conceitos similares podem usar terminologia completamente diferente - consulte artigos de review quando buscas standard falham.

## Protocolo de Preservacao de Documentos

### Passos Imediatos Pos-Encontro
1. Evite hosts nao confiaveis (LG, SH, URLs temporarias NBER, Scribd)
2. Edite scans: crop, threshold, binarize, OCR
3. Adicione metadata compreensiva (titulo, autor, DOI, ano, keywords)
4. Extraia page ranges relevantes de obras compiladas

### Hosting de Longo Prazo
- Hospede copias publicas, especialmente materiais dificeis de encontrar
- Use formato PDF sobre alternativas
- Upload para multiplas locacoes (LibGen, sites pessoais, servicos de arquivo)
- Linke paginas especificas com parametro URL `#page=N`
- Compartilhe em Wikipedia, Reddit, Twitter para boostar discoverability

## Heuristicas Taticas

**Principio do Golden Mean**
Mire buscas gerando centenas ao inves de milhares de resultados. Poucos resultados indicam over-specification; muitos sugerem necessidade de filtragem.

**Estrategia Gradient Ascent**
Versoes mais longas e menos polidas tipicamente indicam proximidade de originais. Siga versoes piores - geralmente estao mais proximas da verdade.

**Loop de Refinamento de Busca**
Comece amplamente, observe resultados inesperados, identifique anomalias, explore dicas de hits nao obvios, progressivamente estreite escopo.

**Estrategia de Paciencia**
Papers embargados se tornam disponiveis em meses. Configure lembretes ao inves de abandonar buscas. Persistencia frequentemente compensa quando tentativas iniciais falham.

## Principios de Documentacao

Inclua titulos de pagina em links para auxiliar buscas futuras quando URLs se tornam meaningless. Limpe URLs antes de arquivar - remova parametros de tracking (`?utm_source=`, `?rss=1`), evite variantes mobile.
