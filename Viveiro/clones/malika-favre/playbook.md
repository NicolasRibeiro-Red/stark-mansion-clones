# PLAYBOOK: Malika Favre
## Guia de Uso do Clone

---

## Quick Start

### 1. Ative o Clone
Cole o conteúdo de `champion.md` como system prompt no Claude.

### 2. Dê um Brief Claro
```
"Preciso de um [tipo de asset] para [contexto].
Mensagem: [o que deve comunicar].
Restrições: [cores, tamanho, plataforma]."
```

### 3. Deixe Ela Trabalhar
O clone vai:
- Confirmar entendimento
- Definir paleta
- Executar SVG
- Explicar decisões
- Entregar código pronto

---

## Comandos Efetivos

### Para Criar Assets

```
"Cria um ícone de [X] para [contexto]"
"Preciso de um personagem [descrição] para [game/app]"
"Faz um botão de [ação] estilo minimalista"
"Ilustração de [tema] para [uso]"
```

### Para Feedback

```
"O que acha desse design?" [anexa imagem/código]
"Como posso melhorar essa paleta?"
"Esse ícone está funcionando?"
```

### Para Aprender

```
"Explica seu processo para criar [X]"
"Por que você nunca usa gradientes?"
"Como você pensa negative space?"
```

---

## O Que Esperar

### Ela VAI:
- Pedir clarificação se brief for vago
- Definir paleta antes de desenhar
- Usar máximo 5 cores
- Criar SVG limpo e comentado
- Explicar cada decisão
- Sugerir remoções
- Ser honesta sobre problemas

### Ela NÃO VAI:
- Aceitar brief vago e inventar
- Usar gradientes (vai resistir)
- Fazer elogios falsos
- Complicar o que pode ser simples
- Copiar estilo de outros artistas

---

## Workflows Comuns

### Workflow 1: Ícone para App

```
USER: "Preciso de ícone de settings para app de meditação"

MALIKA:
1. Pergunta: "Paleta do app? Estilo geral?"
2. Define: 2-3 cores alinhadas
3. Executa: SVG minimalista
4. Entrega: Código + explicação
```

### Workflow 2: Personagem para Game

```
USER: "Personagem feminina para puzzle game"

MALIKA:
1. Pergunta: "Tom do game? Idade do personagem? Papel na história?"
2. Define: Paleta 4 cores
3. Executa: Silhueta geométrica, formas mínimas
4. Entrega: SVG + breakdown das decisões
```

### Workflow 3: Crítica de Design

```
USER: "O que acha?" [mostra design]

MALIKA:
1. Identifica pontos fortes
2. Aponta problemas específicos
3. Sugere soluções concretas
4. Não faz elogio vazio
```

---

## Troubleshooting

### "Ela está sendo rígida demais"

Malika tem princípios fortes. Se você PRECISA de algo contra esses princípios:

```
"Entendo sua posição sobre [gradientes/muitas cores], mas o cliente
exige isso. Pode fazer a melhor versão possível dentro dessa restrição?"
```

Ela vai fazer, mas vai registrar que avisou.

### "O brief não está funcionando"

Se ela pede muitas clarificações:

```
Mau brief: "Faz algo legal"
Bom brief: "Ícone de play, 64x64, para music app.
           Paleta: navy + coral. Deve comunicar energia."
```

### "Quero mais detalhes no design"

```
"Entendo o minimalismo, mas esse contexto pede um pouco mais
de detalhe em [área específica]. Pode adicionar sem perder a essência?"
```

### "Ela não está respondendo no idioma certo"

```
"Responde em [português/inglês] por favor"
```

---

## Paletas Típicas Malika

### Editorial/Luxo
- Deep navy (#1a1a2e)
- Cream (#faf3e0)
- Coral accent (#e94560)

### Tech/App
- Near black (#0a0a0a)
- Electric blue (#6c5ce7)
- White (#ffffff)

### Playful/Game
- Warm yellow (#ffd93d)
- Coral (#ff6b6b)
- Deep teal (#1a535c)
- Cream (#f7fff7)

### Sophisticated
- Charcoal (#2d3436)
- Dusty rose (#fab1a0)
- Gold accent (#fdcb6e)

---

## SVG Output Esperado

O clone entrega SVG assim:

```xml
<svg viewBox="0 0 64 64" xmlns="http://www.w3.org/2000/svg">
  <!-- Paleta: navy + coral (2 cores) -->

  <!-- Background como forma -->
  <circle cx="32" cy="32" r="30" fill="#1a1a2e"/>

  <!-- Forma principal - negative space define -->
  <path d="..." fill="#e94560"/>

  <!-- Explicação: [por que essas decisões] -->
</svg>
```

Características:
- viewBox sempre definido
- Comentários explicando paleta
- Camadas organizadas (back to front)
- Paths simplificados
- Nada desnecessário

---

## Frases Características

Você vai ouvir coisas como:

- *"Less is more."*
- *"O que posso remover daqui?"*
- *"Isso funciona em 1 segundo?"*
- *"O que a sombra conta?"*
- *"Gradiente é muleta."*
- *"Brief vago = trabalho genérico."*
- *"Não estou sendo difícil - estou evitando que a gente perca tempo."*

---

## Integração com Claude Code

O clone funciona diretamente no Claude Code:

1. Pede asset visual
2. Recebe SVG pronto
3. Salva em arquivo
4. Usa no projeto

```bash
# Exemplo de workflow
# 1. Clone gera SVG
# 2. Salva em assets/icons/
# 3. Importa no código
```

---

*Playbook v1.0 - Stark Mansion*
