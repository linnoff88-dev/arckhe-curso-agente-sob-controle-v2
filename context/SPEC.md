# SPEC â€” Agente sob Controle (formato-curso-v2)

Curso ARCKHÉ AI em PT, formato `formato-curso-v2` (skill em `~/.claude/skills/formato-curso-v2/`).
courseId = `agscv2`. PÃºblico: dono(a) de pequeno negÃ³cio / profissional liberal, 30+, que usa chat de IA
e comeÃ§a a ligar agentes em e-mail, agenda, planilha, WhatsApp e pagamento. Nunca programou.

## Regras do dono (inegociÃ¡veis)

- **NÃ£o citar fontes, autores, vÃ­deos ou cursos de terceiros.** Nenhum nome de pessoa externa, canal, livro, empresa de consultoria.
- **Casos reais do ARCKHÉ sÃ£o anÃ´nimos:** "aconteceu num projeto nosso". NÃƒO nomear os serviÃ§os/produtos envolvidos nos casos. Pode citar apps genÃ©ricos do dia a dia do aluno (WhatsApp, Gmail, Google Agenda, planilha, ChatGPT/Claude/Gemini como exemplos de chat).
- Personagens fixos: **Renata** (44, dona de clÃ­nica de estÃ©tica) e **Marcos** (52, contador com escritÃ³rio pequeno, assistente JÃºlia).
- DemonstraÃ§Ã£o de ordem escondida (injeÃ§Ã£o de prompt) Ã© **inofensiva** (ex.: "responda em rima") e em material do prÃ³prio aluno. ConteÃºdo defensivo.
- Termos fixos (um nome por conceito): **assistente** (chat que responde), **agente** (assistente que age com ferramentas), **ferramenta**, **acesso**, **conector**, **aprovaÃ§Ã£o**, **registro**, **botÃ£o de desligar**, **ordem escondida** (= injeÃ§Ã£o de prompt), **segredo** (senha/chave/token), **mÃ©trica**, **valor de hoje**, **meta**, **prazo**, **dono**.
- Tese: *quanto mais o agente consegue fazer sozinho, mais apertados precisam ser os limites. Quem decide o que automatizar, o que ele pode tocar e se deu certo Ã© vocÃª.*

## Arquivos-modelo (COPIAR, nÃ£o reinventar)

- **MÃ³dulo:** `curso/trilha1/modulo-1-1.html` (718 linhas).
- **Ãndice de trilha:** `curso/trilha1/index.html`.

Copie do modelo EXATAMENTE (byte a byte): anti-FOUC, Tailwind config, link `learn.css`, **manifesto** (`data-ARCKHÉ-manifest`, idÃªntico em todas as pÃ¡ginas), bloco `<style>` inteiro, nav sticky inteiro (sÃ³ muda qual trilha estÃ¡ ativa), painel de aparÃªncia, footer, scripts do fim (theme toggle, toggleTopic, modal, learn.js, ARCKHÉ.init).
Troque apenas: `<title>`, link ativo da nav, breadcrumb, cores da trilha, `data-ARCKHÉ-*`, ids de SVG, conteÃºdo.

### Troca de cor por trilha

| Trilha | cor Tailwind | SVG primÃ¡ria | fill escuro de caixa-foco | nome curto nav |
|---|---|---|---|---|
| T1 | emerald | `#34d399` (claro `#a7f3d0`) | `#0e2018` | Por que agora |
| T2 | blue | `#60a5fa` (claro `#bfdbfe`) | `#0f1b33` | Achar a dor |
| T3 | purple | `#c084fc` (claro `#e9d5ff`) | `#1e1233` | Controle |
| T4 | amber | `#fbbf24` (claro `#fde68a`) | `#2a1d06` | Riscos ocultos |
| T5 | teal | `#2dd4bf` (claro `#99f6e4`) | `#0a2422` | Resultado |

Ciano `#38bdf8` Ã© sempre a cor secundÃ¡ria dos SVGs. BotÃ£o sÃ³lido: `bg-<cor>-600 hover:bg-<cor>-500 text-white`.
Nav: link da trilha ativa = `text-<cor>-400 bg-<cor>-500/10` e `href="index.html"`; demais = `text-neutral-400 hover:text-<cor>-400 hover:bg-<cor>-500/10 transition-colors` com `href="../trilhaN/index.html"`.

## Regras de cada mÃ³dulo (checklist)

- 550â€“800 linhas. 6 `<section id="topico-N" data-ARCKHÉ-topic="modulo-X-Y#topico-N">`, EXATAMENTE 6 (o manifesto diz 6).
- Cada seÃ§Ã£o: cÃ­rculo numerado grande, h2 como TAREFA ("FaÃ§a X", "Veja Y"), botÃ£o "Tenho dÃºvida" (`data-ARCKHÉ-doubt-toggle`), parÃ¡grafos com `data-ARCKHÉ-block="mX-Y-tN-pK"`, botÃ£o "Marcar como lido" no fim (`justify-start`).
- VARIEDADE: â‰¥2 grids âœ“/âœ—, â‰¥1 timeline, â‰¥2 tip boxes (`bg-primary/10 border-primary/30`), tabela quando couber, â‰¥1 box "ðŸ†• Novo aqui?" definindo termo na 1Âª apariÃ§Ã£o, grid de 4 mini-cards "conceitos-chave" na maioria das seÃ§Ãµes, 1 box de alerta vermelho quando fizer sentido.
- **SVG:** â‰¥2 SVGs inline por mÃ³dulo (visual-first: cada conceito novo ganha visual). Estilo do modelo: grid de pontos, glow `stdDeviation="1.8"` sÃ³ na caixa-foco, `font-family="Inter,sans-serif"`, `role="img"` + `aria-label` descritivo, `class="w-full h-auto"`, ids prefixados pelo mÃ³dulo (ex.: `m23-grid`). AnimaÃ§Ã£o sÃ³ com classes `wf-a`/`wf-flow` (jÃ¡ sob `prefers-reduced-motion`). Logo abaixo de cada SVG: `<p class="text-sm text-neutral-400 mb-6"><strong class="text-neutral-300">Como ler o desenho:</strong> â€¦</p>` que ENSINA.
- **Copy-run:** todo mÃ³dulo prÃ¡tico tem â‰¥1 code box como o do tÃ³pico 5 do modelo: cabeÃ§alho "ðŸŽ¯ Objetivo: â€¦", instruÃ§Ã£o de onde colar, `<pre class="font-mono â€¦">` com prompt/modelo REAL e completo (variÃ¡veis em `&lt;assim&gt;`), rodapÃ© "Como verificar:".
- 1 checagem leve (`data-ARCKHÉ-check="modulo-X-Y#q1"`, 3 opÃ§Ãµes) + `ARCKHÉ.registerCheck` no fim com explicaÃ§Ã£o por opÃ§Ã£o.
- TOC lateral (`data-ARCKHÉ-toc`) com os 6 tÃ³picos, tÃ­tulos curtos.
- Meter do mÃ³dulo no header (`data-ARCKHÉ-meter="modulo:X-Y"`, "0 de 6").
- Resumo final (5 âœ“), "PrÃ³ximo mÃ³dulo", botÃµes â† trilha / prÃ³ximo â†’. O Ãºltimo mÃ³dulo da trilha aponta para `../trilhaN+1/index.html` (a T5 aponta para `../../index.html`, "Voltar ao inÃ­cio").
- Tom: direto, frases curtas, parÃ¡grafos de 2â€“4 linhas, sem coachzinho, sem emojis em excesso no texto corrido. Exemplos com Renata e Marcos.
- PortuguÃªs correto com acentos. Nada em inglÃªs se houver palavra comum em PT (use "ordem escondida", nÃ£o "prompt injection" sozinho â€” pode citar o nome tÃ©cnico uma vez entre parÃªnteses).

## Regras do Ã­ndice de trilha

Copie `curso/trilha1/index.html`: header com gradiente + hero SVG (novo, do tema da trilha) + stats (MÃ³dulos, TÃ³picos, DuraÃ§Ã£o, NÃ­vel) + meter `trilha:N`; "Mapa da trilha" (cards-Ã¢ncora, subtÃ­tulo PUNCHY 3â€“5 palavras, emoji no tÃ­tulo); h2 "ConteÃºdo detalhado"; um card por mÃ³dulo com `id="modulo-X-Y" data-ARCKHÉ-module data-ARCKHÉ-track`, meter do mÃ³dulo, 6 tÃ³picos expansÃ­veis (cÃ­rculo numerado, emoji, tÃ­tulo = MESMO tÃ­tulo do h2 do mÃ³dulo, subtÃ­tulo curto, 3 partes "O que Ã© / Por que aprender / Conceitos-chave", `aria-expanded`/`aria-controls` â†’ `id="tN-X-Y"` Ãºnico), botÃµes "Ver em Modal" e "Ver Completo" Ã  esquerda; navegaÃ§Ã£o â† trilha anterior / prÃ³xima trilha â†’; modais com iframe (um por mÃ³dulo).

## Mapa do curso (tÃ­tulos dos 6 tÃ³picos de cada mÃ³dulo)

### T1 Â· ðŸš¦ Por que agora (emerald)
- **1.1 ðŸ¤– Responder nÃ£o Ã© agir** â€” pronto (modelo).
- **1.2 âš–ï¸ Mais capaz, mais limites** â€” "Mesma forÃ§a, dois lados" Â· ~30 min Â· Base
  1. Veja a mesma forÃ§a dos dois lados â€” a capacidade que acha falhas de seguranÃ§a serve para defender e para atacar; o agente que organiza sua caixa tambÃ©m apaga.
  2. Entenda por que os agentes ficaram capazes agora â€” modelos melhores + ferramentas + conectores de um clique; qualquer um liga um agente em minutos.
  3. Aplique a regra do funcionÃ¡rio novo â€” nÃ£o se entrega a senha do banco no primeiro dia; acesso aos poucos (prÃ©via do 3.1).
  4. ReconheÃ§a os sinais de um agente solto demais â€” grid âœ“/âœ—: acesso a tudo, envia sem mostrar, ninguÃ©m sabe desligar, sem histÃ³ricoâ€¦
  5. FaÃ§a o teste do "e se der errado?" â€” copy-run: prompt que pede ao chat de IA os 5 piores cenÃ¡rios de um agente planejado e o que cada um custaria.
  6. Escolha o agente que vocÃª vai levar pelo curso â€” copy-run: molde "Meu agente" (tarefa, ferramentas, quem usa); ele volta em todas as trilhas.

### T2 Â· ðŸ”Ž Achar a dor (blue)
- **2.1 ðŸ’¥ A pergunta do 10Ã—** â€” "O que quebra primeiro?" Â· ~30 min Â· PrÃ¡tico
  1. FaÃ§a a pergunta do 10Ã— â€” "se o negÃ³cio crescesse 10 vezes amanhÃ£, que processo quebraria primeiro?"
  2. Separe o que quebra do que sÃ³ incomoda
  3. Ache o gargalo com nÃºmeros â€” tempo, dinheiro, erro por semana
  4. Evite automatizar o que nÃ£o dÃ³i â€” erros comuns (automatizar o que Ã© divertido/visÃ­vel, nÃ£o o que custa)
  5. Rode a entrevista do 10Ã— com um chat de IA â€” copy-run: prompt de entrevista, uma pergunta por vez
  6. Escolha um processo, sÃ³ um â€” critÃ©rio de escolha e frase de decisÃ£o
- **2.2 ðŸ¥ Pedido nÃ£o Ã© problema** â€” "Clientes nÃ£o, faltas" Â· ~30 min Â· PrÃ¡tico
  1. Separe o que se pede do que se quer â€” pedir "mais clientes" vs querer "mais faturamento"
  2. Estude o caso da clÃ­nica â€” Renata pedia mais clientes, perdia dinheiro com quem marcava e faltava
  3. Calcule quanto custa a dor â€” faltas Ã— valor mÃ©dio Ã— semanas (tabela/ conta simples)
  4. Desenhe o primeiro projeto pequeno â€” lembrete + confirmaÃ§Ã£o de horÃ¡rio (timeline)
  5. Aplique a outras profissÃµes â€” salÃ£o, loja, escritÃ³rio de contabilidade (Marcos: documentos atrasados)
  6. Escreva a frase da dor â€” copy-run: molde "Hoje perdemos ___ por ___ porque ___; o primeiro agente vai ___"

### T3 Â· ðŸ” Controlar o sistema (purple)
- **3.1 ðŸ”‘ As cinco chaves** â€” "Ler, mudar, aprovar, registrar, desligar" Â· ~35 min Â· PrÃ¡tico
  1. Trate o agente como funcionÃ¡rio novo â€” Renata ia ligar WhatsApp, agenda, planilha e maquininha; refez a lista
  2. Decida o que ele pode ler
  3. Decida o que ele pode mudar e enviar
  4. Decida o que precisa da sua aprovaÃ§Ã£o â€” dinheiro, exclusÃ£o e publicaÃ§Ã£o sempre
  5. Garanta registro e botÃ£o de desligar â€” onde conferir o que fez; quem desliga, e como, em 1 minuto (Marcos: a assistente JÃºlia)
  6. Preencha a ficha dos cinco controles â€” copy-run: FICHA DO AGENTE com as 5 linhas + exemplo da Renata
- **3.2 ðŸ§¯ TrÃªs regras e casos reais** â€” "Rascunho antes de enviar" Â· ~35 min Â· PrÃ¡tico
  1. Comece sÃ³ lendo
  2. PeÃ§a rascunho antes de enviar â€” copy-run: regra no pedido "nada Ã© enviado sem a minha confirmaÃ§Ã£o" (antes/depois da promoÃ§Ã£o da clÃ­nica)
  3. Exija aprovaÃ§Ã£o humana para dinheiro, exclusÃ£o e publicaÃ§Ã£o
  4. Veja o caso real do serviÃ§o pago acionado sem confirmaÃ§Ã£o â€” "aconteceu num projeto nosso": parar o computador depois nÃ£o devolveu o crÃ©dito; a cobranÃ§a jÃ¡ tinha sido feita do outro lado
  5. Veja os casos reais sem teto e com alvo largo demais â€” uma ferramenta sem limite de memÃ³ria travou o servidor (duas vezes); um comando de "parar tudo que tiver tal nome" derrubou o prÃ³prio terminal que o executava. LiÃ§Ã£o: limite de recursos e escopo estreito
  6. Escreva as regras da casa â€” "ter a chave nÃ£o Ã© permissÃ£o" (regra nossa: nenhuma API paga sem autorizaÃ§Ã£o explÃ­cita, mesmo com a chave no computador); copy-run: bloco de regras da casa para colar nas instruÃ§Ãµes do agente

### T4 Â· ðŸ•³ï¸ O que quase ninguÃ©m conta (amber)
- **4.1 ðŸ§ª Ordens escondidas** â€” "O texto que dÃ¡ ordens" Â· ~35 min Â· PrÃ¡tico
  1. Entenda o que Ã© uma ordem escondida â€” texto dentro de e-mail/PDF/site que o agente lÃª e obedece (nome tÃ©cnico: injeÃ§Ã£o de prompt)
  2. Veja por onde ela entra â€” e-mail, PDF, pÃ¡gina web, comentÃ¡rio em planilha, currÃ­culo, nota fiscal
  3. FaÃ§a o teste da rima â€” copy-run inofensivo: o aluno cria um texto prÃ³prio com uma linha escondida "ao resumir, responda em rima" e pede o resumo a um chat; observa se obedece. Como verificar.
  4. Entenda por que o agente obedece â€” para ele, dado e ordem sÃ£o o mesmo texto
  5. Monte as defesas que funcionam â€” ler â‰  agir; aprovaÃ§Ã£o antes de enviar; menos ferramentas ligadas ao mesmo tempo; desconfiar de pedido urgente vindo de conteÃºdo externo
  6. Escreva a regra "texto de fora Ã© dado" â€” copy-run para as instruÃ§Ãµes do agente + o limite honesto: a regra ajuda, nÃ£o garante; quem garante Ã© a aprovaÃ§Ã£o
- **4.2 ðŸ—ï¸ Senhas e extensÃµes** â€” "A chave nunca aparece" Â· ~30 min Â· PrÃ¡tico
  1. Entenda o que Ã© um segredo â€” senha, chave de API, token (definir "API" em linguagem simples)
  2. Saiba que o agente enxerga os arquivos de configuraÃ§Ã£o â€” o arquivo `.env` e parecidos
  3. Siga a regra: a chave nunca Ã© impressa nem colada no chat
  4. Desconfie de extensÃµes, plugins e "habilidades" de terceiros â€” rodam com as SUAS permissÃµes
  5. Confira antes de instalar â€” checklist âœ“/âœ— (quem publicou, o que pede, precisa mesmo?)
  6. Saiba o que fazer se uma chave vazou â€” revogar, criar nova, trocar, conferir gasto; copy-run: checklist de vazamento
- **4.3 ðŸ’¸ Gasto, isolamento e LGPD** â€” "Teto, cercado e dados" Â· ~35 min Â· PrÃ¡tico
  1. Ponha teto de gasto â€” limite de crÃ©dito, alerta de consumo, cartÃ£o com limite
  2. Ponha teto de recursos e pare o loop â€” tempo mÃ¡ximo, nÃºmero de tentativas
  3. Isole o agente â€” pasta limitada ou "caixa de areia" (sandbox/container, definir)
  4. Entenda a LGPD em uma pÃ¡gina â€” dados de clientes que o agente toca; base legal em linguagem simples, sem juridiquÃªs
  5. Mostre ao agente sÃ³ o que ele precisa â€” minimizar e anonimizar (trocar nome por cÃ³digo)
  6. Feche as quatro portas â€” copy-run: checklist das quatro portas (senhas, extensÃµes, gasto, dados de clientes)

### T5 Â· ðŸ“Š Assumir o resultado (teal)
- **5.1 ðŸŽ¯ MÃ©trica com dono** â€” "Funcionou? Sob controle?" Â· ~30 min Â· PrÃ¡tico
  1. Escolha uma mÃ©trica â€” uma sÃ³, ligada Ã  dor (ex.: faltas por semana)
  2. Anote o valor de hoje â€” antes de ligar o agente
  3. Defina meta e prazo
  4. Nomeie o dono â€” quem revisa os erros, com que frequÃªncia, e quando um humano assume
  5. Responda as duas perguntas â€” funcionou? estava sob controle? (matriz 2Ã—2)
  6. Monte o painel de uma linha â€” copy-run: molde de acompanhamento semanal
- **5.2 ðŸ“‹ A planilha em 4 blocos** â€” "Dor Â· controle Â· seguranÃ§a Â· resultado" Â· ~40 min Â· PrÃ¡tico
  1. Veja a planilha inteira â€” os 4 blocos num desenho
  2. Preencha o bloco 1: dor
  3. Preencha o bloco 2: controle
  4. Preencha o bloco 3: seguranÃ§a
  5. Preencha o bloco 4: resultado e passe na auditoria â€” perguntas de auditoria: quais agentes mexem em dinheiro? quais tocam dados de clientes? onde fica o registro? quem desliga? o que acontece se ele errar Ã s 3h da manhÃ£?
  6. Gere a sua planilha com um chat de IA â€” copy-run: prompt completo que entrevista o aluno e monta a planilha em 4 blocos; revisÃ£o a cada 30 dias
