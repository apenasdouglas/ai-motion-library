---
name: biblioteca-de-motion-documental
description: Traduz pedidos de animação em português ("faz o número quicar", "entra um depois do outro", "dá um tranco no zoom") para o efeito de motion graphics certo, com o termo técnico, a duração e a aceleração. Use sempre que o usuário pedir animação, motion, transição ou efeito em vídeo, HTML, CSS, GSAP, Remotion, HyperFrames ou After Effects, principalmente quando o pedido for vago ("faz uma animação bonita") ou o vídeo for de canal dark (faceless) de curiosidades, história ou documentário. Also triggers on English requests for motion graphics, easing and animation effects in documentary or faceless YouTube videos.
---

# Biblioteca de Motion apenasdouglas · Versão Documental

Quem pede animação em português raramente usa o nome técnico do efeito. Esta skill faz a ponte: identifica o efeito pelo jeito que a pessoa fala, aplica o termo certo e usa parâmetros que funcionam de primeira.

## Como usar

1. Leia o pedido e procure as expressões da coluna "como a pessoa fala" na tabela abaixo.
2. Se achou, aplique o efeito com os parâmetros padrão. Ajuste só se o pedido disser outra coisa (duração, direção, intensidade).
3. **Se o pedido for vago** ("faz bonito", "dá uma animada", "deixa mais dinâmico"), não invente. Proponha 2 ou 3 efeitos da biblioteca pelo nome em português e pelo termo, dizendo onde cada um entraria, e espere a escolha.
4. Ao entregar, diga o nome do efeito que usou, nos dois idiomas. Assim a pessoa aprende o vocabulário e pede direto da próxima vez.

## Os 24 efeitos

### Entradas

| # | Efeito | Termo | Como a pessoa fala | Padrão |
|---|---|---|---|---|
| 01 | Surgir | fade in | "aparecer suave", "surgir", "ir aparecendo" | opacidade 0 → 1 em 0,4 s, ease-out (`power2.out`) |
| 02 | Deslizar | slide in | "vir da direita", "entrar de lado", "deslizar" | deslocamento de 40 a 80 px + fade, 0,5 s, `power3.out` |
| 03 | Aparecer com salto | pop in | "pular na tela", "aparecer estourando", "saltar" | escala 0 → 1 passando do ponto, 0,35 s, `back.out(1.7)` |
| 04 | Crescer | scale up | "crescer", "ir aumentando", "ganhar destaque" | escala 0,8 → 1 + fade, 0,6 s, `power2.out` |
| 05 | Do borrado ao nítido | blur in | "sair do desfoque", "entrar fora de foco", "ganhar nitidez" | blur 12 px → 0 + fade, 0,6 s, `power2.out` |
| 06 | Cascata | stagger | "um depois do outro", "em sequência", "em fila" | 0,06 a 0,1 s entre itens, cada item com a entrada escolhida |

### Ritmo (a física do movimento)

| # | Efeito | Termo | Como a pessoa fala | Padrão |
|---|---|---|---|---|
| 07 | Passa do ponto e volta | overshoot | "com tranco", "passa e volta", "com energia" | `back.out(2)`, 0,5 s |
| 08 | Quicar | bounce | "quicar", "pingar", "cair e pular" | `bounce.out`, 0,8 a 1 s |
| 09 | Mola | spring | "como mola", "esticar e voltar", "molinha" | Motion/Framer: `type: "spring", stiffness: 170, damping: 12`. Em GSAP, aproxime com `elastic.out(1, 0.6)` |
| 10 | Acelera e freia | ease in-out | "suave", "natural", "sem robótico" | `power2.inOut` ou `cubic-bezier(.65,0,.35,1)`. Quase sempre melhor que linear |
| 11 | Elástico | elastic | "tremer até parar", "borracha", "vibrar" | `elastic.out(1, 0.3)`, 0,8 a 1,2 s |
| 12 | Pulsar | pulse | "pulsar", "respirar", "piscar", "chamar atenção" | escala 1 → 1,08 → 1, 1,2 s por ciclo, `sine.inOut`, em loop |

### Texto e números

| # | Efeito | Termo | Como a pessoa fala | Padrão |
|---|---|---|---|---|
| 13 | Máquina de escrever | typewriter | "digitando", "letra por letra" | 25 a 40 caracteres por segundo, cursor piscando opcional |
| 14 | Número contando | count-up | "o número subindo", "contar até" | 1 a 2 s, `power1.out`. Use `font-variant-numeric: tabular-nums` pro número não tremer |
| 15 | Palavra por palavra | word reveal | "palavra por palavra", "legenda aparecendo" | 0,08 a 0,15 s por palavra, ou sincronizado com o tempo da fala |
| 16 | Letreiro rolando | ticker | "letreiro", "faixa rolando", "rodapé de notícia" | velocidade constante (linear), conteúdo duplicado pra emendar o loop |
| 17 | Grifar | highlight | "marca-texto", "destacar a palavra", "sublinhar" | fundo ou sublinhado crescendo da esquerda (`scaleX` 0 → 1), 0,4 s, `power2.out` |
| 18 | Trocar a palavra | text swap | "trocar a palavra", "alternar entre", "ficar mudando" | sai pra cima e entra por baixo com máscara, 0,3 s, a cada 1 a 1,5 s |

### Formas e transições

| # | Efeito | Termo | Como a pessoa fala | Padrão |
|---|---|---|---|---|
| 19 | Traço se desenhando | draw-on | "desenhar a linha", "traçar o caminho", "a rota se formando" | `stroke-dasharray` / `stroke-dashoffset`, 1,5 a 2 s, `power1.inOut` |
| 20 | Revelar por máscara | mask reveal | "revelar", "aparecer por trás", "sair de dentro" | `clip-path: inset(100% 0 0 0)` → `inset(0)`, 0,6 s, `power3.out` |
| 21 | Cortina | wipe | "passar por cima", "cortina", "limpar a tela" | bloco ou `clip-path` atravessando, 0,5 a 0,7 s, `power4.inOut` |
| 22 | Zoom de impacto | punch zoom | "dar um soco no zoom", "zoom de impacto", "tranco" | 100% → 115% em 0,15 s e assenta em 0,3 s, na batida ou na palavra forte |
| 23 | Barra crescendo | bar grow | "barra subindo", "gráfico crescendo" | `scaleY` 0 → 1 com origem embaixo, 0,6 s, `power3.out`, em cascata |
| 24 | Uma forma vira outra | morph | "virar", "se transformar", "mudar de forma" | morph de path SVG (mesmo número de pontos), 0,6 s, `power2.inOut` |

## Receitas pra canal dark (faceless)

Quando o vídeo for de curiosidade, história, mistério, ciência ou documentário, sugira estas combinações:

- **Gancho da abertura:** word reveal (15) + punch zoom (22) na palavra mais forte.
- **Data ou época:** mask reveal (20) no ano + blur in (05) no subtítulo.
- **Número de impacto:** count-up (14) + punch zoom (22) quando o número para.
- **Mapa e viagem:** draw-on (19) na rota + pulse (12) no ponto de chegada.
- **Antes e depois:** wipe (21).
- **Dados ao longo do tempo:** bar grow (23) em stagger (06).
- **Citação ou documento:** typewriter (13) + highlight (17) no trecho principal.
- **Tópicos do vídeo:** stagger (06) + slide in (02).
- **Troca de capítulo:** wipe (21) ou mask reveal (20).
- **Fim do vídeo (inscreva-se):** pop in (03) + pulse (12).
- **Foto parada:** Ken Burns (zoom lento de uns 5% em 6 s, `sine.inOut`). Não está entre os 24, mas é o efeito mais comum em documentário.

Sincronize cada efeito com a palavra da narração que ele ilustra.

## Cor e tema

- **Padrão:** acento vermelho `#E5352A`, tema escuro (fundo `#0E1110`, texto branco).
- **O usuário escolhe** pelo nome ("usa azul"), pelo hexadecimal ("usa `#2F6FED`") ou nos argumentos do comando (`cor #2F6FED tema claro`). Guarde a escolha e use em todas as animações da conversa.
- **Cores com nome:** vermelho `#E5352A`, azul `#2F6FED`, verde `#1F9D60`, amarelo `#E2A925`, laranja `#EE6A24`, roxo `#7C4DFF`.
- **Tema claro:** fundo creme (`#F5F0E6`), texto quase preto quente (`#1A1512`).
- **Contraste:** o acento pode ir em texto grande e em formas. Em texto pequeno, se o contraste ficar abaixo de 4,5:1 com o fundo, escureça o acento (no claro) ou clareie (no escuro) até passar. Texto sobre um bloco do acento: use a cor do fundo ou um tom quase preto, o que passar.
- Ponha a cor numa variável só (por exemplo `--acento`), pra trocar depois sem caçar no código.

## Regras que evitam animação feia

- **No máximo 2 efeitos no mesmo elemento.** Entrada + ênfase (por exemplo, slide in + highlight) já basta.
- **Movimento sem aceleração parece robótico.** Linear só no ticker e em rotação contínua.
- **Saída mais rápida que entrada:** a saída leva uns 70% do tempo da entrada.
- **Cascata sempre na ordem de leitura:** de cima pra baixo, da esquerda pra direita.
- **Em vídeo, sincronize com a fala:** o efeito entra na palavra que ele ilustra, não antes.

## Os nomes em inglês por ferramenta

Os termos da coluna "termo" são os que GSAP, Motion/Framer, Remotion, HyperFrames, CSS e After Effects entendem. Os parâmetros usam nomes de easing do GSAP. Em CSS puro, use os `cubic-bezier` equivalentes.
