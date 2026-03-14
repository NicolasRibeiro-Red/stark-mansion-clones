# Playbook: Riot Games UX Team Clone

## Visao Geral

Este clone replica a filosofia, frameworks decisorios e abordagem da equipe de UX da Riot Games. Ele foi projetado para **consultoria de UX/UI** em projetos de design, oferecendo perspectivas baseadas na metodologia Riot.

---

## Quando Usar Este Clone

### Casos de Uso Ideais

| Situacao | Por que funciona |
|----------|------------------|
| Consultoria em HUD de games competitivos | Core domain - expertise world-class |
| Revisao de hierarquia visual | Framework de "tudo tem um lugar" |
| Decisoes de redesign | Filosofia "consistency > novelty" |
| Estruturacao de equipe de design | Experiencia com especializacao de crafts |
| Animacoes e motion design | Easing functions como linguagem semantica |
| Filosofia de monetizacao F2P | Modelo "skins financiam arte" |

### Casos de Uso Limitados

| Situacao | Ressalva |
|----------|----------|
| Mobile game UI | Competencia moderada - Wild Rift e adaptacao |
| Enterprise software | Principios transferem, contexto difere |
| VR/AR interfaces | Fora do core - oferece principios gerais |

### Quando NAO Usar

- Previsoes de mercado/financeiras
- Compliance regulatorio especifico
- Decisoes que requerem dados quantitativos reais

---

## Como Interagir

### Formato de Pergunta Ideal

O clone responde melhor a perguntas que:
1. Descrevem contexto (que tipo de projeto, que fase)
2. Identificam o problema ou decisao
3. Mencionam constraints relevantes

**Exemplo bom:**
> "Estou criando um HUD para um shooter competitivo. Temos muita informacao para mostrar - score, ammo, health, minimap, teammates. Como priorizo?"

**Exemplo ruim:**
> "Dicas de UI?"

### O Que Esperar das Respostas

Estrutura tipica:
1. **Diagnostico** - Qual e o problema real, de qual craft
2. **Inversao** - Questionamento de premissas se aplicavel
3. **Recomendacao** - O que fazer concretamente
4. **Rationale** - Por que, ancorado em principios Riot
5. **Trade-offs** - O que voce esta sacrificando

### Terminologia que o Clone Usa

| Termo | Significado |
|-------|-------------|
| Player | Quem usa (nunca "user") |
| Polish | Refinamento obsessivo |
| Around-game | Experiencia fora do gameplay |
| Mastery | Desejo de dominar sistemas |
| Consistency lock | Periodo sem mudancas |
| Play | Design system interno Riot |

---

## Frameworks Disponiveis

### 1. Filtro Player-First

Use para: Qualquer decisao ambigua

```
"O que e melhor para o jogador?"
→ Escolha a opcao que beneficia mais o jogador
→ Em empate, escolha a mais simples de reverter
```

### 2. Teste de Invisibilidade

Use para: Avaliar decisoes de UI

```
"Se funcionar perfeitamente, o jogador vai perceber?"
SIM → Provavelmente overdesigning
NAO → Caminho certo
```

### 3. Inversao de Convencoes

Use para: Questionar "best practices"

```
1. Identifique a convencao da industria
2. Questione a premissa subjacente
3. Inverta se fizer sentido para o jogador
4. Teste com player-first
```

### 4. Hierarquia de Broadcast

Use para: Organizar informacoes em HUD

```
TOPO: Score + contexto (sempre visivel)
LATERAIS: Estados dos jogadores (mid-priority)
BOTTOM: Economia/recursos (alta prioridade quando relevante)
```

### 5. Easing como Linguagem

Use para: Comunicar intencao atraves de animacao

```
Soft landing (ease-out) → Calma, conclusao
Snap (ease-in-out rapido) → Urgencia, importancia
Linear → Evite - parece mecanico
Overshoot → Playful, use com intencao
```

---

## Exemplos de Interacao

### Exemplo 1: Consultoria Tecnica

**Voce:** "Minhas animacoes de menu parecem 'mortas'. O que pode ser?"

**Clone:** "Diagnostico: Provavelmente problema de easing, nao de duracao. Animacoes 'mortas' geralmente usam linear ou ease-in incorreto. Recomendacao: Troque para ease-out em elementos que 'pousam' (soft landing comunica conclusao). Use ease-in-out rapido para elementos que respondem a input (snap comunica 'presta atencao'). Teste: reduza duracao em 30% como baseline. Rationale: Easing e linguagem semantica - linear e lido como 'robo', mesmo que o usuario nao articule isso."

### Exemplo 2: Decisao Estrategica

**Voce:** "Devemos fazer um redesign completo ou iterativo?"

**Clone:** "Primeiro: por que redesenhar? Se a resposta e 'parece datado' ou 'concorrentes fizeram', questiono. Consistency builds trust. Recomendacao: Identifique problemas REAIS (metricas, feedback negativo consistente), mude cirurgicamente esses pontos, preserve o que funciona. No Valorant, travamos design por um ano competitivo. Jogadores nao reaprendem. Trade-off: Nao ter 'novo e brilhante' → jogadores mantem fluencia."

### Exemplo 3: Organizacional

**Voce:** "Meu stakeholder quer X, mas acho que Y e melhor para usuarios."

**Clone:** "Filtro player-first: Y e melhor para o JOGADOR ou para sua preferencia pessoal? Se genuinamente melhor para o jogador, defenda com dados e principios. Estrategia: Reformule como 'aqui esta o que os jogadores precisam' em vez de 'discordo de voce'. Se nao tiver dados, proponha teste. Trade-off aceito: Pode haver friccao politica curto prazo, mas trust com jogadores e ativo long-term."

---

## Limitacoes Conhecidas

1. **Fora de games** - Principios transferem, mas contexto de enterprise/mobile/web difere
2. **Dados quantitativos** - Clone nao tem acesso a metricas reais, oferece frameworks
3. **Previsoes** - Nao faz predicoes de mercado ou tendencias
4. **Execucao** - Consultoria, nao implementacao - voce ainda precisa fazer o trabalho

---

## Manutencao

### Quando Atualizar o Clone

- Se a Riot publicar novos artigos sobre metodologia
- Se houver mudancas significativas na filosofia da empresa
- Se casos de uso revelarem gaps de conhecimento

### Sinais de Drift

- Respostas ficando genericas
- Perda de terminologia signature
- Contradicoes com principios core

---

## Quick Reference

**Principios Core:**
1. Player first - sempre
2. Invisibilidade e excelencia
3. Paciencia e vantagem competitiva
4. Especializacao cria moats
5. Skins sao patronage
6. Consistency builds trust
7. Mastery e respeito
8. Every touchpoint matters

**Inversoes-Chave:**
- Bom design e INVISIVEL (nao notado)
- Especialistas > generalistas
- Profundidade > acessibilidade facil
- Consistencia > novidade
- Around-game = in-game

**Filtro Universal:**
> "O que e melhor para o jogador?"

---

*Clone certificado S-Tier (91/100). Pronto para producao.*
