# buyer-personas-pp

Plugin Cowork com o conhecimento de Buyer Personas da Purpose Paper, para uso pelo time interno (marketing, conteúdo, CRM, produto).

## O que este plugin contém

Duas skills:

1. **`buyer-personas-pp`** — a referência vigente. Metodologia de Jobs-to-be-Done (Christensen) + Customer Profile (Osterwalder) + 5 Rings of Buying Insight (Revella), aplicada às três hipóteses finais de persona da Purpose Paper: **A Iniciante**, **A Praticante** (bifurcada em Fé Fria / Fé Quente) e **A Mãe em Jornada**. Construída no Passo 06 da Fundação Growth Hacking (julho/2026).

2. **`analise-dados-personas-pp`** — a base empírica histórica (abril/2026) que deu origem às hipóteses acima: o cruzamento de Shopify, Meta Ads e Google Search Console por produto de primeira compra, organizado em quatro agrupamentos de dados (Discípula, Praticante, Mãe, Organizadora) e no mapa completo de retenção por produto de entrada. Serve como rastro de evidência — não como as personas vigentes.

## Como usar

Instale o plugin e as duas skills carregam automaticamente quando relevante: perguntas sobre "quem é a cliente", decisões de produto/campanha/conteúdo que dependam de entender motivação de compra, ou pedidos pelos números de origem de uma hipótese de persona.

Para decisões do dia a dia (produto, campanha, conteúdo, CRM), a Claude vai puxar `buyer-personas-pp`. Para rastrear de onde veio um número específico ou entender a evolução da análise, ela vai puxar `analise-dados-personas-pp`.

## Como manter

Quando as hipóteses [H] forem validadas ou refutadas em campo (roadmap Q3/Q4 2026, descrito na skill `buyer-personas-pp`), atualize o `SKILL.md` da skill `buyer-personas-pp` com os achados. Se surgir uma nova rodada de análise quantitativa, adicione-a a `analise-dados-personas-pp` — nunca misture as duas: uma é hipótese vigente, a outra é histórico.
