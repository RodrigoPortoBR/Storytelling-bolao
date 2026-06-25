# Brief Design — Comunicação Mata-Mata & Conversão Clube iFood

**Objetivo:** Converter usuários não-assinantes em Clube iFood aproveitando os 4 pontos de contato abaixo. O gatilho central é o Ranking Mata-Mata que abre em 28/06 com prêmio de **R$1 milhão** para o 1º colocado Clube iFood.

---

## Tela 1 — Ad Placeholder redesenhado
**Referência:** `Prints/Home c ad.jpeg`

O ad atual (fundo azul escuro, sem CTA, texto pequeno) se perde no feed. Precisamos de contraste total com os cards brancos da home.

### Especificações visuais
| Elemento | Atual | Proposto |
|---|---|---|
| Fundo | Azul escuro (#1A1E6F aprox.) | Gradiente laranja → amarelo (paleta iFood: #EA1D2C → #FFC244) |
| Headline | "O JOGO RECOMEÇA EM 28/06" | **"Ranking Mata-Mata: 1º lugar ganha R$ 1 MILHÃO"** |
| Sub-copy | "No Ranking Mata-Mata, todo mundo começa do zero. Nova disputa e prêmio de R$ 1 milhão para o 1º colocado Clube iFood!" | "Só para Clube iFood. Ainda dá tempo de entrar." |
| CTA | Nenhum | Botão: **"QUERO SER CLUBE IFOOD →"** (fundo branco, texto laranja iFood, bordas arredondadas) |
| Ícones | Logo CazéTV | Manter logo CazéTV + adicionar ícone troféu 🏆 próximo ao valor R$1M |

### Hierarquia visual
```
[Logo CazéTV]          [Troféu + R$1.000.000]
─────────────────────────────────────────────
RANKING MATA-MATA
1º lugar ganha R$ 1 MILHÃO

Só para Clube iFood. Ainda dá tempo de entrar.

[  QUERO SER CLUBE IFOOD →  ]
```

---

## Tela 2 — Posicionamento do Ad na Home
**Referência:** `Prints/Home.jpeg`

Define onde o ad placeholder acima deve ser inserido na experiência real de scroll.

### Regra
- Inserir o ad **entre o 2º e o 3º card de jogo** de cada dia
- Não exibir antes do jogo 1 (não interrompe a entrada na tela)
- Não exibir após o último jogo do dia

### Mapeamento visual do scroll (dia com 4+ jogos)
```
┌─────────────────┐
│  Card Jogo 1    │  ← entra aqui sem interrupção
├─────────────────┤
│  Card Jogo 2    │
├─────────────────┤
│  AD PLACEHOLDER │  ← posição fixa
│  (tela inteira) │
├─────────────────┤
│  Card Jogo 3    │
├─────────────────┤
│  Card Jogo 4    │
└─────────────────┘
```

---

## Tela 3 — Dia 28/06 (estado vazio + banner Mata-Mata)
**Referência:** `Prints/dia 28.06.jpeg`

O dia 28/06 não terá jogos definidos ainda quando aparecer no carrossel. Em vez de tela vazia, aproveitar o espaço para comunicar a abertura do Mata-Mata.

### Carrossel de datas
- Adicionar **"28 JUNHO"** ao carrossel (mesmo padrão visual dos outros dias)
- Sub-label: **"Mata-Mata"** (substitui "Fase de grupos")

### Banner full-width no lugar dos cards de jogo
Banner único e vertical, maior que o ad padrão — ocupa toda a área de conteúdo da tela.

```
┌─────────────────────────────────┐
│  🏟️  A FASE DECISIVA             │
│      COMEÇA AQUI                │
│                                 │
│  Os confrontos serão definidos  │
│  em breve. Assim que            │
│  confirmados, você já poderá    │
│  dar seus palpites.             │
│                                 │
│  ─────────────────────────────  │
│  Por que virar Clube iFood?     │
│                                 │
│  🏆  Concorra a R$1 milhão      │
│  ⭐  Pontuação exclusiva        │
│      no Mata-Mata               │
│  🛡️  Vantagens iFood            │
│      durante a Copa             │
│                                 │
│  [ VIRAR CLUBE IFOOD ]          │
└─────────────────────────────────┘
```

**Visual:** Fundo azul iFood (consistente com a identidade do bolão), texto branco, ícones coloridos, botão CTA em laranja iFood. Dimensão: ~80% da altura da viewport para impacto.

---

## Tela 4 — Ranking Mata-Mata (empty state com conteúdo)
**Referência:** `Prints/ranking mata mata.jpeg`

Hoje: tela exibe apenas "O ranking ainda está inativo." com área branca vazia abaixo da barra de posição do usuário. Alta oportunidade desperdiçada.

### O que manter
- Cabeçalho "RANKINGS" ← mantém contexto
- Seletor "RANKING DO MATA-MATA" com arrows ← mantém navegação
- Tabs "GERAL / CLUBE IFOOD" ← mantém estrutura
- **Barra verde de posição do usuário** (Sua posição / Seu nome / Seus pontos) ← ancora o usuário na tela

### Bloco a inserir (preenche a área vazia)

**Parte 1 — Como funciona** (acima da mensagem "ranking inativo")
```
COMO FUNCIONA O MATA-MATA

  1  Palpite nos jogos das
     oitavas, quartas e semi

  2  Acumule pontos a
     cada acerto

  3  O 1º colocado Clube iFood
     leva R$ 1 MILHÃO
```
Visual: fundo branco, numeração em azul iFood, texto corrido pequeno.

**Parte 2 — Por que Clube iFood** (destaque visual, fundo verde limão — mesma cor da barra de posição atual para criar coesão visual)
```
┌─────────────────────────────────┐  ← fundo verde limão
│                                 │
│  🏆 Clube iFood concorre ao     │
│     prêmio de R$ 1 MILHÃO       │
│                                 │
│  Usuários Geral participam,     │
│  mas ficam fora da premiação.   │
│                                 │
│  [ ASSINAR CLUBE IFOOD ]        │
└─────────────────────────────────┘
```

**Parte 3 — Mensagem de status** (mantém, mas reposicionada ao final)
> "O ranking será ativado em 28/06, quando começar o Mata-Mata."

_(substitui o atual "O ranking ainda está inativo." por copy com data e contexto)_

---

## Resumo das prioridades

| Prioridade | Tela | Impacto esperado |
|---|---|---|
| Alta | Tela 4 — Ranking Mata-Mata | Usuários que chegam até rankings estão engajados — momento ideal para converter |
| Alta | Tela 3 — Dia 28/06 | Cria urgência de "entre antes que comece" |
| Média | Tela 1 — Ad Placeholder | Aumenta CTR do ad com cores e CTA claros |
| Baixa | Tela 2 — Posicionamento | Garante que o ad apareça no momento certo do scroll |

---

*Brief preparado em 25/06/2026 — Copa do Mundo FIFA 2026*
