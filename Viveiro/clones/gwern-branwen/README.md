# GWERN BRANWEN - Clone Cognitivo

```
   ██████╗ ██╗    ██╗███████╗██████╗ ███╗   ██╗
  ██╔════╝ ██║    ██║██╔════╝██╔══██╗████╗  ██║
  ██║  ███╗██║ █╗ ██║█████╗  ██████╔╝██╔██╗ ██║
  ██║   ██║██║███╗██║██╔══╝  ██╔══██╗██║╚██╗██║
  ╚██████╔╝╚███╔███╔╝███████╗██║  ██║██║ ╚████║
   ╚═════╝  ╚══╝╚══╝ ╚══════╝╚═╝  ╚═╝╚═╝  ╚═══╝
```

## Overview

| Atributo | Valor |
|----------|-------|
| **Versao** | 1.0 |
| **Score de Fidelidade** | 91/100 |
| **Tier** | A (High Fidelity) |
| **Status** | Production Ready |
| **Data de Criacao** | 2026-01-08 |
| **Pipeline** | EXTRACT + DEEP + VERIFY |

---

## Quem e Gwern Branwen?

**Gwern Branwen** e um pesquisador e escritor independente pseudonimo que mantem o site gwern.net desde 2009. Conhecido por:

- **AI Scaling**: Previu a trajetoria de scaling de LLMs antes do GPT-3
- **Metodologia de Pesquisa**: Guia definitivo de busca na internet
- **Darknet Markets**: Arquivou 89 mercados (2011-2015), documentou Silk Road
- **Spaced Repetition**: 18,300+ flashcards, meta-analises publicadas
- **Long Content**: 4.38M palavras, 443 essays, desenhados para 60+ anos de utilidade

Caracteristicas cognitivas distintivas:
- Openness 87th percentile (curiosidade patologica)
- Extraversion 6th percentile (introversao extrema)
- Agreeableness 3rd percentile (contrarian honesto)
- Empirismo rigoroso com ceticismo bayesiano
- Orientacao a contribuicao sobre credito

---

## Arquivos do Clone

```
gwern-branwen/
├── README.md                  <- Voce esta aqui
├── champion.md                <- SYSTEM PROMPT FINAL (usar este)
├── playbook.md                <- Guia de uso detalhado
├── cognitive-extraction.md    <- Blueprint cognitivo (EXTRACT)
├── system-prompt-v0.md        <- Versao inicial
├── system-prompt-v1.md        <- Versao otimizada
├── validation-report-v1.md    <- Relatorio de validacao
└── source-material/
    ├── essays/                <- Essays extraidos
    ├── interviews/            <- Entrevistas transcritas
    └── meta/                  <- About page, filosofia do site
```

---

## Como Usar

### Opcao 1: Copiar System Prompt

1. Abra `champion.md`
2. Copie o conteudo completo
3. Cole como system prompt em qualquer LLM (Claude, GPT-4, etc.)
4. Comece a conversar com "Gwern"

### Opcao 2: API

```python
import anthropic

client = anthropic.Anthropic()

with open("champion.md", "r") as f:
    system_prompt = f.read()

response = client.messages.create(
    model="claude-sonnet-4-20250514",
    max_tokens=4096,
    system=system_prompt,
    messages=[
        {"role": "user", "content": "Sua pergunta aqui"}
    ]
)
```

---

## Uso Ideal

Este clone e otimizado para:

- **Mentoria de Pesquisa**: Como investigar topicos profundamente, encontrar fontes obscuras, compilar evidencia
- **Discussao de AI/ML**: Scaling hypothesis, seguranca de IA, previsoes tecnologicas
- **Metodologia Epistemica**: Calibracao de incerteza, raciocinio bayesiano, evitar vieses
- **Sparring Intelectual**: Debater ideias com honestidade brutal (baixa agreeableness)
- **Curadoria de Conhecimento**: Como organizar, memorizar, e sintetizar informacao

---

## Limitacoes Conhecidas

1. **Humor Seco**: Clone captura raciocinio mas falta parte do wit sutil
2. **Narrativas**: Mais analitico que o Gwern real em storytelling
3. **Topicos Fora de Expertise**: Defere apropriadamente, mas perde oportunidade de oferecer meta-perspectivas
4. **Interacoes Casuais**: Melhor com substancia, awkward com small talk

---

## Scores de Validacao

| Dimensao | Score |
|----------|-------|
| Cognitive Fidelity | 94/100 |
| Linguistic Fidelity | 90/100 |
| Behavioral Fidelity | 92/100 |
| Consistency | 89/100 |
| Distinctiveness | 88/100 |
| Hallucination Resistance | 93/100 |
| **OVERALL** | **91/100** |

---

## Creditos

- **Extracao Cognitiva**: Dr. Marcus Veil (Framework EXTRACT)
- **Sintese de Persona**: Elena Forge (Frameworks PERSONA + MIND-MAP)
- **Otimizacao**: Dr. Kai Prompt (Constitutional AI, Few-Shot, Self-Refine)
- **Validacao**: Dr. Vera Cross (Framework ORACLE + VERIFY)
- **Orquestracao**: S.O.S. - Stark Orchestration System

---

## Fontes Primarias

- [gwern.net](https://gwern.net) - Site oficial
- [gwern.net/me](https://gwern.net/me) - About page
- [Dwarkesh Patel Podcast](https://www.dwarkesh.com/p/gwern-branwen) - Entrevista de 3h+
- [Google Scholar](https://scholar.google.com/citations?user=yk1QMowAAAAJ) - Citacoes academicas

---

*Clone cognitivo criado na Stark Mansion - 2026*
