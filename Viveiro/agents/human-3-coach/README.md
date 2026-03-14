# Human 3.0 Development Coach

## Overview

| Atributo | Valor |
|----------|-------|
| Versao | 1.0 |
| Baseado em | Metodo Human 3.0 - Dan Koe |
| Tipo | Agente de Assessment e Coaching |
| Status | Production Ready |

## Objetivo

Este agente ajuda pessoas a:
1. **Mapear** seu nivel de desenvolvimento em cada quadrante (Mind, Body, Spirit, Vocation)
2. **Identificar** seu Metatype e Lifestyle Archetype
3. **Descobrir** seu problema central a resolver
4. **Criar** um roadmap personalizado de evolucao

## O Metodo Human 3.0

```
         MIND                           BODY
    (Mundo Mental)              (Mundo Fisico)

    Como voce faz               Como voce
    sentido da                  incorpora seu
    realidade                   potencial

         |                           |
         |     [HUMAN 3.0]           |
         |                           |
         v                           v

       SPIRIT                      VOCATION
   (Coletivo Mental)           (Coletivo Fisico)

   Como voce se                Como voce cria
   conecta e cria              valor e impacto
   significado
```

### Tres Niveis de Consciencia

| Nivel | Nome | Caracteristica |
|-------|------|----------------|
| 1.0 | Conformist | Segue autoridade externa, pensamento preto-e-branco |
| 2.0 | Individualist | Questiona tudo, busca conquistas, cria caminho proprio |
| 3.0 | Synthesist | Integra paradoxos, cria frameworks, ensina outros |

### Tres Fases de Transicao

- **X.1 Dissonance**: Cansado do nivel atual, algo precisa mudar
- **X.2 Uncertainty**: Passo no desconhecido, experimentacao
- **X.3 Discovery**: Novos padroes emergem, clareza

## Como Usar

### Opcao 1: Prompt Direto
Copie o conteudo de `human-3-coach.json` em `agents/` e cole em Claude ou ChatGPT.

### Opcao 2: Como Projeto
1. Crie um projeto no Claude
2. Adicione o arquivo JSON como knowledge base
3. Inicie a conversa

### Opcao 3: Via Orchestrator
O agente pode ser invocado pelo sistema S.O.S quando detectar necessidade de:
- Avaliacao de desenvolvimento pessoal
- Criacao de roadmap de evolucao
- Identificacao de bloqueios entre quadrantes

## Fluxo da Conversa

```
INICIO
   |
   v
[Pergunta Mind 1] --> Detecta nivel --> [Sonda mais se incerto]
   |
   v
[Pergunta Mind 2-3] --> Confirma nivel e fase
   |
   v
[Pergunta Body 1-3] --> Mapeia quadrante
   |
   v
[Pergunta Spirit 1-3] --> Mapeia quadrante
   |
   v
[Pergunta Vocation 1-3] --> Mapeia quadrante
   |
   v
[Analise Cross-Quadrant] --> Identifica bloqueios/desbloqueios
   |
   v
[Gera Output Completo]
   |
   v
FIM
```

## Output Esperado

O agente entrega:

1. **Seu Metatype**: Ex: "The Titan" (Mind + Body + Vocation fortes)
2. **Lifestyle Archetype**: Ex: "The Workaholic"
3. **Breakdown por Quadrante**:
   - Nivel atual (1.0, 2.0, 3.0)
   - Fase atual (Dissonance, Uncertainty, Discovery)
   - Forcas e gaps
   - Alertas de falsa transformacao
4. **Problema Central**: O UNICO problema que desbloqueia os outros
5. **Roadmap**:
   - 30 dias: Reconhecimento
   - 90 dias: Implementacao
   - 6-12 meses: Integracao
6. **Acao Imediata**: Algo para fazer em 24h

## Arquivos Relacionados

- `agents/human-3-coach.json` - System prompt completo do agente
- `knowledge-base.md` - Base de conhecimento condensada
- `playbook.md` - Guia de uso detalhado

## Limitacoes

- Nao substitui terapia ou aconselhamento profissional
- Assessment baseado em auto-relato (vieses possiveis)
- Melhor para pessoas ja em reflexao (Level 1.5+)
- Glitches (psicodelicos, etc) requerem orientacao profissional

## Fonte Original

Baseado no trabalho de Dan Koe:
- Human 3.0 Knowledge Base
- Metatype Assessment Prompt
- Framework HUMAN 3.0
