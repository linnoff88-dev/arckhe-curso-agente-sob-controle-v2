# SPEC ê¢â¬â Agente sob Controle (formato-curso-v2)

Curso ARCKHê AI em PT, formato `formato-curso-v2` (skill em `~/.claude/skills/formato-curso-v2/`).
courseId = `agscv2`. PêÂºblico: dono(a) de pequeno negêÂ³cio / profissional liberal, 30+, que usa chat de IA
e comeêÂ§a a ligar agentes em e-mail, agenda, planilha, WhatsApp e pagamento. Nunca programou.

## Regras do dono (inegociêÂ¡veis)

- **NêÂ£o citar fontes, autores, vêÂ­deos ou cursos de terceiros.** Nenhum nome de pessoa externa, canal, livro, empresa de consultoria.
- **Casos reais do ARCKHê sêÂ£o anêÂ´nimos:** "aconteceu num projeto nosso". NêÆO nomear os serviêÂ§os/produtos envolvidos nos casos. Pode citar apps genêÂ©ricos do dia a dia do aluno (WhatsApp, Gmail, Google Agenda, planilha, ChatGPT/Claude/Gemini como exemplos de chat).
- Personagens fixos: **Renata** (44, dona de clêÂ­nica de estêÂ©tica) e **Marcos** (52, contador com escritêÂ³rio pequeno, assistente JêÂºlia).
- DemonstraêÂ§êÂ£o de ordem escondida (injeêÂ§êÂ£o de prompt) êÂ© **inofensiva** (ex.: "responda em rima") e em material do prêÂ³prio aluno. ConteêÂºdo defensivo.
- Termos fixos (um nome por conceito): **assistente** (chat que responde), **agente** (assistente que age com ferramentas), **ferramenta**, **acesso**, **conector**, **aprovaêÂ§êÂ£o**, **registro**, **botêÂ£o de desligar**, **ordem escondida** (= injeêÂ§êÂ£o de prompt), **segredo** (senha/chave/token), **mêÂ©trica**, **valor de hoje**, **meta**, **prazo**, **dono**.
- Tese: *quanto mais o agente consegue fazer sozinho, mais apertados precisam ser os limites. Quem decide o que automatizar, o que ele pode tocar e se deu certo êÂ© vocêÂª.*

## Arquivos-modelo (COPIAR, nêÂ£o reinventar)

- **MêÂ³dulo:** `curso/trilha1/modulo-1-1.html` (718 linhas).
- **êÂndice de trilha:** `curso/trilha1/index.html`.

Copie do modelo EXATAMENTE (byte a byte): anti-FOUC, Tailwind config, link `learn.css`, **manifesto** (`data-ARCKHê-manifest`, idêÂªntico em todas as pêÂ¡ginas), bloco `<style>` inteiro, nav sticky inteiro (sêÂ³ muda qual trilha estêÂ¡ ativa), painel de aparêÂªncia, footer, scripts do fim (theme toggle, toggleTopic, modal, learn.js, ARCKHê.init).
Troque apenas: `<title>`, link ativo da nav, breadcrumb, cores da trilha, `data-ARCKHê-*`, ids de SVG, conteêÂºdo.

### Troca de cor por trilha

| Trilha | cor Tailwind | SVG primêÂ¡ria | fill escuro de caixa-foco | nome curto nav |
|---|---|---|---|---|
| T1 | emerald | `#34d399` (claro `#a7f3d0`) | `#0e2018` | Por que agora |
| T2 | blue | `#60a5fa` (claro `#bfdbfe`) | `#0f1b33` | Achar a dor |
| T3 | purple | `#c084fc` (claro `#e9d5ff`) | `#1e1233` | Controle |
| T4 | amber | `#fbbf24` (claro `#fde68a`) | `#2a1d06` | Riscos ocultos |
| T5 | teal | `#2dd4bf` (claro `#99f6e4`) | `#0a2422` | Resultado |

Ciano `#38bdf8` êÂ© sempre a cor secundêÂ¡ria dos SVGs. BotêÂ£o sêÂ³lido: `bg-<cor>-600 hover:bg-<cor>-500 text-white`.
Nav: link da trilha ativa = `text-<cor>-400 bg-<cor>-500/10` e `href="index.html"`; demais = `text-neutral-400 hover:text-<cor>-400 hover:bg-<cor>-500/10 transition-colors` com `href="../trilhaN/index.html"`.

## Regras de cada mêÂ³dulo (checklist)

- 550ê¢â¬â800 linhas. 6 `<section id="topico-N" data-ARCKHê-topic="modulo-X-Y#topico-N">`, EXATAMENTE 6 (o manifesto diz 6).
- Cada seêÂ§êÂ£o: cêÂ­rculo numerado grande, h2 como TAREFA ("FaêÂ§a X", "Veja Y"), botêÂ£o "Tenho dêÂºvida" (`data-ARCKHê-doubt-toggle`), parêÂ¡grafos com `data-ARCKHê-block="mX-Y-tN-pK"`, botêÂ£o "Marcar como lido" no fim (`justify-start`).
- VARIEDADE: ê¢â°Â¥2 grids ê¢Åâ/ê¢Åâ, ê¢â°Â¥1 timeline, ê¢â°Â¥2 tip boxes (`bg-primary/10 border-primary/30`), tabela quando couber, ê¢â°Â¥1 box "ê°Å¸â â¢ Novo aqui?" definindo termo na 1êÂª apariêÂ§êÂ£o, grid de 4 mini-cards "conceitos-chave" na maioria das seêÂ§êÂµes, 1 box de alerta vermelho quando fizer sentido.
- **SVG:** ê¢â°Â¥2 SVGs inline por mêÂ³dulo (visual-first: cada conceito novo ganha visual). Estilo do modelo: grid de pontos, glow `stdDeviation="1.8"` sêÂ³ na caixa-foco, `font-family="Inter,sans-serif"`, `role="img"` + `aria-label` descritivo, `class="w-full h-auto"`, ids prefixados pelo mêÂ³dulo (ex.: `m23-grid`). AnimaêÂ§êÂ£o sêÂ³ com classes `wf-a`/`wf-flow` (jêÂ¡ sob `prefers-reduced-motion`). Logo abaixo de cada SVG: `<p class="text-sm text-neutral-400 mb-6"><strong class="text-neutral-300">Como ler o desenho:</strong> ê¢â¬Â¦</p>` que ENSINA.
- **Copy-run:** todo mêÂ³dulo prêÂ¡tico tem ê¢â°Â¥1 code box como o do têÂ³pico 5 do modelo: cabeêÂ§alho "ê°Å¸Å½Â¯ Objetivo: ê¢â¬Â¦", instruêÂ§êÂ£o de onde colar, `<pre class="font-mono ê¢â¬Â¦">` com prompt/modelo REAL e completo (variêÂ¡veis em `&lt;assim&gt;`), rodapêÂ© "Como verificar:".
- 1 checagem leve (`data-ARCKHê-check="modulo-X-Y#q1"`, 3 opêÂ§êÂµes) + `ARCKHê.registerCheck` no fim com explicaêÂ§êÂ£o por opêÂ§êÂ£o.
- TOC lateral (`data-ARCKHê-toc`) com os 6 têÂ³picos, têÂ­tulos curtos.
- Meter do mêÂ³dulo no header (`data-ARCKHê-meter="modulo:X-Y"`, "0 de 6").
- Resumo final (5 ê¢Åâ), "PrêÂ³ximo mêÂ³dulo", botêÂµes ê¢â Â trilha / prêÂ³ximo ê¢â â. O êÂºltimo mêÂ³dulo da trilha aponta para `../trilhaN+1/index.html` (a T5 aponta para `../../index.html`, "Voltar ao inêÂ­cio").
- Tom: direto, frases curtas, parêÂ¡grafos de 2ê¢â¬â4 linhas, sem coachzinho, sem emojis em excesso no texto corrido. Exemplos com Renata e Marcos.
- PortuguêÂªs correto com acentos. Nada em inglêÂªs se houver palavra comum em PT (use "ordem escondida", nêÂ£o "prompt injection" sozinho ê¢â¬â pode citar o nome têÂ©cnico uma vez entre parêÂªnteses).

## Regras do êÂ­ndice de trilha

Copie `curso/trilha1/index.html`: header com gradiente + hero SVG (novo, do tema da trilha) + stats (MêÂ³dulos, TêÂ³picos, DuraêÂ§êÂ£o, NêÂ­vel) + meter `trilha:N`; "Mapa da trilha" (cards-êÂ¢ncora, subtêÂ­tulo PUNCHY 3ê¢â¬â5 palavras, emoji no têÂ­tulo); h2 "ConteêÂºdo detalhado"; um card por mêÂ³dulo com `id="modulo-X-Y" data-ARCKHê-module data-ARCKHê-track`, meter do mêÂ³dulo, 6 têÂ³picos expansêÂ­veis (cêÂ­rculo numerado, emoji, têÂ­tulo = MESMO têÂ­tulo do h2 do mêÂ³dulo, subtêÂ­tulo curto, 3 partes "O que êÂ© / Por que aprender / Conceitos-chave", `aria-expanded`/`aria-controls` ê¢â â `id="tN-X-Y"` êÂºnico), botêÂµes "Ver em Modal" e "Ver Completo" êÂ  esquerda; navegaêÂ§êÂ£o ê¢â Â trilha anterior / prêÂ³xima trilha ê¢â â; modais com iframe (um por mêÂ³dulo).

## Mapa do curso (têÂ­tulos dos 6 têÂ³picos de cada mêÂ³dulo)

### T1 êÂ· ê°Å¸Å¡Â¦ Por que agora (emerald)
- **1.1 ê°Å¸Â¤â Responder nêÂ£o êÂ© agir** ê¢â¬â pronto (modelo).
- **1.2 ê¢Å¡âê¯Â¸Â Mais capaz, mais limites** ê¢â¬â "Mesma forêÂ§a, dois lados" êÂ· ~30 min êÂ· Base
  1. Veja a mesma forêÂ§a dos dois lados ê¢â¬â a capacidade que acha falhas de seguranêÂ§a serve para defender e para atacar; o agente que organiza sua caixa tambêÂ©m apaga.
  2. Entenda por que os agentes ficaram capazes agora ê¢â¬â modelos melhores + ferramentas + conectores de um clique; qualquer um liga um agente em minutos.
  3. Aplique a regra do funcionêÂ¡rio novo ê¢â¬â nêÂ£o se entrega a senha do banco no primeiro dia; acesso aos poucos (prêÂ©via do 3.1).
  4. ReconheêÂ§a os sinais de um agente solto demais ê¢â¬â grid ê¢Åâ/ê¢Åâ: acesso a tudo, envia sem mostrar, ninguêÂ©m sabe desligar, sem histêÂ³ricoê¢â¬Â¦
  5. FaêÂ§a o teste do "e se der errado?" ê¢â¬â copy-run: prompt que pede ao chat de IA os 5 piores cenêÂ¡rios de um agente planejado e o que cada um custaria.
  6. Escolha o agente que vocêÂª vai levar pelo curso ê¢â¬â copy-run: molde "Meu agente" (tarefa, ferramentas, quem usa); ele volta em todas as trilhas.

### T2 êÂ· ê°Å¸âÅ½ Achar a dor (blue)
- **2.1 ê°Å¸âÂ¥ A pergunta do 10êâ** ê¢â¬â "O que quebra primeiro?" êÂ· ~30 min êÂ· PrêÂ¡tico
  1. FaêÂ§a a pergunta do 10êâ ê¢â¬â "se o negêÂ³cio crescesse 10 vezes amanhêÂ£, que processo quebraria primeiro?"
  2. Separe o que quebra do que sêÂ³ incomoda
  3. Ache o gargalo com nêÂºmeros ê¢â¬â tempo, dinheiro, erro por semana
  4. Evite automatizar o que nêÂ£o dêÂ³i ê¢â¬â erros comuns (automatizar o que êÂ© divertido/visêÂ­vel, nêÂ£o o que custa)
  5. Rode a entrevista do 10êâ com um chat de IA ê¢â¬â copy-run: prompt de entrevista, uma pergunta por vez
  6. Escolha um processo, sêÂ³ um ê¢â¬â critêÂ©rio de escolha e frase de decisêÂ£o
- **2.2 ê°Å¸ÂÂ¥ Pedido nêÂ£o êÂ© problema** ê¢â¬â "Clientes nêÂ£o, faltas" êÂ· ~30 min êÂ· PrêÂ¡tico
  1. Separe o que se pede do que se quer ê¢â¬â pedir "mais clientes" vs querer "mais faturamento"
  2. Estude o caso da clêÂ­nica ê¢â¬â Renata pedia mais clientes, perdia dinheiro com quem marcava e faltava
  3. Calcule quanto custa a dor ê¢â¬â faltas êâ valor mêÂ©dio êâ semanas (tabela/ conta simples)
  4. Desenhe o primeiro projeto pequeno ê¢â¬â lembrete + confirmaêÂ§êÂ£o de horêÂ¡rio (timeline)
  5. Aplique a outras profissêÂµes ê¢â¬â salêÂ£o, loja, escritêÂ³rio de contabilidade (Marcos: documentos atrasados)
  6. Escreva a frase da dor ê¢â¬â copy-run: molde "Hoje perdemos ___ por ___ porque ___; o primeiro agente vai ___"

### T3 êÂ· ê°Å¸âÂ Controlar o sistema (purple)
- **3.1 ê°Å¸ââ As cinco chaves** ê¢â¬â "Ler, mudar, aprovar, registrar, desligar" êÂ· ~35 min êÂ· PrêÂ¡tico
  1. Trate o agente como funcionêÂ¡rio novo ê¢â¬â Renata ia ligar WhatsApp, agenda, planilha e maquininha; refez a lista
  2. Decida o que ele pode ler
  3. Decida o que ele pode mudar e enviar
  4. Decida o que precisa da sua aprovaêÂ§êÂ£o ê¢â¬â dinheiro, exclusêÂ£o e publicaêÂ§êÂ£o sempre
  5. Garanta registro e botêÂ£o de desligar ê¢â¬â onde conferir o que fez; quem desliga, e como, em 1 minuto (Marcos: a assistente JêÂºlia)
  6. Preencha a ficha dos cinco controles ê¢â¬â copy-run: FICHA DO AGENTE com as 5 linhas + exemplo da Renata
- **3.2 ê°Å¸Â§Â¯ TrêÂªs regras e casos reais** ê¢â¬â "Rascunho antes de enviar" êÂ· ~35 min êÂ· PrêÂ¡tico
  1. Comece sêÂ³ lendo
  2. PeêÂ§a rascunho antes de enviar ê¢â¬â copy-run: regra no pedido "nada êÂ© enviado sem a minha confirmaêÂ§êÂ£o" (antes/depois da promoêÂ§êÂ£o da clêÂ­nica)
  3. Exija aprovaêÂ§êÂ£o humana para dinheiro, exclusêÂ£o e publicaêÂ§êÂ£o
  4. Veja o caso real do serviêÂ§o pago acionado sem confirmaêÂ§êÂ£o ê¢â¬â "aconteceu num projeto nosso": parar o computador depois nêÂ£o devolveu o crêÂ©dito; a cobranêÂ§a jêÂ¡ tinha sido feita do outro lado
  5. Veja os casos reais sem teto e com alvo largo demais ê¢â¬â uma ferramenta sem limite de memêÂ³ria travou o servidor (duas vezes); um comando de "parar tudo que tiver tal nome" derrubou o prêÂ³prio terminal que o executava. LiêÂ§êÂ£o: limite de recursos e escopo estreito
  6. Escreva as regras da casa ê¢â¬â "ter a chave nêÂ£o êÂ© permissêÂ£o" (regra nossa: nenhuma API paga sem autorizaêÂ§êÂ£o explêÂ­cita, mesmo com a chave no computador); copy-run: bloco de regras da casa para colar nas instruêÂ§êÂµes do agente

### T4 êÂ· ê°Å¸â¢Â³ê¯Â¸Â O que quase ninguêÂ©m conta (amber)
- **4.1 ê°Å¸Â§Âª Ordens escondidas** ê¢â¬â "O texto que dêÂ¡ ordens" êÂ· ~35 min êÂ· PrêÂ¡tico
  1. Entenda o que êÂ© uma ordem escondida ê¢â¬â texto dentro de e-mail/PDF/site que o agente lêÂª e obedece (nome têÂ©cnico: injeêÂ§êÂ£o de prompt)
  2. Veja por onde ela entra ê¢â¬â e-mail, PDF, pêÂ¡gina web, comentêÂ¡rio em planilha, currêÂ­culo, nota fiscal
  3. FaêÂ§a o teste da rima ê¢â¬â copy-run inofensivo: o aluno cria um texto prêÂ³prio com uma linha escondida "ao resumir, responda em rima" e pede o resumo a um chat; observa se obedece. Como verificar.
  4. Entenda por que o agente obedece ê¢â¬â para ele, dado e ordem sêÂ£o o mesmo texto
  5. Monte as defesas que funcionam ê¢â¬â ler ê¢â°Â  agir; aprovaêÂ§êÂ£o antes de enviar; menos ferramentas ligadas ao mesmo tempo; desconfiar de pedido urgente vindo de conteêÂºdo externo
  6. Escreva a regra "texto de fora êÂ© dado" ê¢â¬â copy-run para as instruêÂ§êÂµes do agente + o limite honesto: a regra ajuda, nêÂ£o garante; quem garante êÂ© a aprovaêÂ§êÂ£o
- **4.2 ê°Å¸âÂê¯Â¸Â Senhas e extensêÂµes** ê¢â¬â "A chave nunca aparece" êÂ· ~30 min êÂ· PrêÂ¡tico
  1. Entenda o que êÂ© um segredo ê¢â¬â senha, chave de API, token (definir "API" em linguagem simples)
  2. Saiba que o agente enxerga os arquivos de configuraêÂ§êÂ£o ê¢â¬â o arquivo `.env` e parecidos
  3. Siga a regra: a chave nunca êÂ© impressa nem colada no chat
  4. Desconfie de extensêÂµes, plugins e "habilidades" de terceiros ê¢â¬â rodam com as SUAS permissêÂµes
  5. Confira antes de instalar ê¢â¬â checklist ê¢Åâ/ê¢Åâ (quem publicou, o que pede, precisa mesmo?)
  6. Saiba o que fazer se uma chave vazou ê¢â¬â revogar, criar nova, trocar, conferir gasto; copy-run: checklist de vazamento
- **4.3 ê°Å¸âÂ¸ Gasto, isolamento e LGPD** ê¢â¬â "Teto, cercado e dados" êÂ· ~35 min êÂ· PrêÂ¡tico
  1. Ponha teto de gasto ê¢â¬â limite de crêÂ©dito, alerta de consumo, cartêÂ£o com limite
  2. Ponha teto de recursos e pare o loop ê¢â¬â tempo mêÂ¡ximo, nêÂºmero de tentativas
  3. Isole o agente ê¢â¬â pasta limitada ou "caixa de areia" (sandbox/container, definir)
  4. Entenda a LGPD em uma pêÂ¡gina ê¢â¬â dados de clientes que o agente toca; base legal em linguagem simples, sem juridiquêÂªs
  5. Mostre ao agente sêÂ³ o que ele precisa ê¢â¬â minimizar e anonimizar (trocar nome por cêÂ³digo)
  6. Feche as quatro portas ê¢â¬â copy-run: checklist das quatro portas (senhas, extensêÂµes, gasto, dados de clientes)

### T5 êÂ· ê°Å¸âÅ  Assumir o resultado (teal)
- **5.1 ê°Å¸Å½Â¯ MêÂ©trica com dono** ê¢â¬â "Funcionou? Sob controle?" êÂ· ~30 min êÂ· PrêÂ¡tico
  1. Escolha uma mêÂ©trica ê¢â¬â uma sêÂ³, ligada êÂ  dor (ex.: faltas por semana)
  2. Anote o valor de hoje ê¢â¬â antes de ligar o agente
  3. Defina meta e prazo
  4. Nomeie o dono ê¢â¬â quem revisa os erros, com que frequêÂªncia, e quando um humano assume
  5. Responda as duas perguntas ê¢â¬â funcionou? estava sob controle? (matriz 2êâ2)
  6. Monte o painel de uma linha ê¢â¬â copy-run: molde de acompanhamento semanal
- **5.2 ê°Å¸ââ¹ A planilha em 4 blocos** ê¢â¬â "Dor êÂ· controle êÂ· seguranêÂ§a êÂ· resultado" êÂ· ~40 min êÂ· PrêÂ¡tico
  1. Veja a planilha inteira ê¢â¬â os 4 blocos num desenho
  2. Preencha o bloco 1: dor
  3. Preencha o bloco 2: controle
  4. Preencha o bloco 3: seguranêÂ§a
  5. Preencha o bloco 4: resultado e passe na auditoria ê¢â¬â perguntas de auditoria: quais agentes mexem em dinheiro? quais tocam dados de clientes? onde fica o registro? quem desliga? o que acontece se ele errar êÂ s 3h da manhêÂ£?
  6. Gere a sua planilha com um chat de IA ê¢â¬â copy-run: prompt completo que entrevista o aluno e monta a planilha em 4 blocos; revisêÂ£o a cada 30 dias
