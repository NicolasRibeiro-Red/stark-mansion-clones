# SETUP - Como Configurar a Stark Mansion

## Pre-requisitos

- **Claude Code** (CLI da Anthropic) instalado
- **Python 3.8+** (para extracao de PDFs)

---

## Passo 1: Colocar a pasta no seu computador

Copie a pasta `Stark Mansion` para qualquer lugar no seu computador.
Exemplo: `C:\Users\SEU-USUARIO\Stark Mansion\` ou `~/Stark Mansion/`

---

## Passo 2: Abrir no Claude Code

```bash
cd "caminho/para/Stark Mansion"
claude
```

O Claude vai detectar o `CLAUDE.md` automaticamente e se comportar como o orquestrador.

---

## Passo 3: Instalar dependencia para PDFs (opcional)

Se voce quiser usar PDFs como material fonte:

```bash
pip install PyMuPDF
```

---

## O que voce pode fazer imediatamente

### Conversar com um clone existente
```
"Falar com Naval Ravikant"
"Falar com Alex Hormozi"
"Falar com Robert Greene"
```
O sistema vai ler o `champion.md` do clone e assumir a persona.

### Criar um novo clone
```
"Clone de [nome da pessoa]"
```
O sistema vai guiar voce pelo pipeline de 7 fases.

### Usar um clone como system prompt no ChatGPT/API
1. Abra `Viveiro/clones/[nome]/champion.md`
2. Copie o conteudo
3. Cole como "System Prompt" ou "Custom Instructions" no ChatGPT, Claude, ou qualquer LLM

---

## Estrutura da Pasta

```
Stark Mansion/
├── CLAUDE.md          <- Instrucoes do sistema (o cerebro)
├── CONTRATO.md        <- Arquitetura tecnica detalhada
├── README.md          <- Overview geral
├── SETUP.md           <- Voce esta aqui
│
├── agents/            <- 15 agentes especializados (JSON)
├── frameworks/        <- 6 frameworks metodologicos
├── swipe-files/       <- Exemplos reais de referencia
│
└── Viveiro/
    └── clones/        <- 39 clones cognitivos prontos
        ├── alex-hormozi/
        ├── naval-ravikant/
        ├── gary-halbert/      <- NOVO (Mestre do Copy)
        ├── eugene-schwartz/   <- NOVO (Mestre do Copy)
        └── ... (34 outros)
```

---

## Configuracoes Opcionais (para usuarios avancados)

### Habilitar extracao automatica de PDFs
Se quiser que o Claude extraia PDFs automaticamente (como skill):

1. Crie a pasta `.claude/skills/pdf-extractor/scripts/` dentro de Stark Mansion
2. Crie um arquivo `pdf_extractor.py` com um script de extracao usando PyMuPDF
3. Configure no `.claude/settings.local.json`

### Habilitar pesquisa web
Para que o Claude possa pesquisar sobre pessoas automaticamente:
- O WebSearch ja funciona nativamente no Claude Code
- Para pesquisas mais avancadas, configure MCPs como Exa ou Apify

---

## FAQ

**P: Preciso de API key do Claude?**
R: Sim, voce precisa ter o Claude Code configurado com sua conta Anthropic.

**P: Funciona com ChatGPT?**
R: Os clones (champion.md) funcionam em QUALQUER LLM como system prompt.
O pipeline automatizado (7 fases) funciona melhor no Claude Code.

**P: Posso criar clones de qualquer pessoa?**
R: Sim, desde que tenha material de referencia (livros, entrevistas, artigos).
Quanto mais material, melhor o clone.

**P: Como usar um clone no dia-a-dia?**
R: Copie o champion.md e use como system prompt no seu LLM preferido.
Ou use "Falar com [nome]" direto no Claude Code.
