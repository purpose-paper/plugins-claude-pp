---
name: analise-dados-personas-pp
description: >
  Análise quantitativa histórica (abril/2026) que cruzou Shopify, Meta Ads e
  Google Search Console por produto de primeira compra da Purpose Paper — os
  achados empíricos que originaram as hipóteses de persona atuais. Cobre os
  quatro agrupamentos de dados por produto de entrada (Discípula/Bíblia,
  Praticante/Journal devocional, Mãe/Baby Journal, Organizadora/Planner), o
  ecossistema Fernanda Witwytzky e o mapa de retenção por produto de entrada
  (86.769 compradores). Use esta skill quando precisar rastrear a origem
  empírica de uma hipótese de persona, citar números específicos de LTV/
  recorrência/ROAS por produto de entrada, ou entender por que a Purpose
  Paper chegou às três hipóteses finais. NÃO use esta skill para nomear ou
  apresentar as personas vigentes da PP — para isso use a skill
  `buyer-personas-pp`, que é a referência atual.
---

# Análise de Dados de Personas — Purpose Paper (base histórica, abril/2026)

## O que esta skill é — e o que ela NÃO é

Esta skill guarda a **análise quantitativa bruta** que a Purpose Paper fez em abril de 2026, cruzando dados de Shopify, Meta Ads e Google Search Console por produto de primeira compra. Ela agrupou os clientes em quatro rótulos de trabalho — **A Discípula, A Praticante, A Mãe, A Organizadora** — nomeados pelo produto de entrada (Bíblia, Journal devocional, Baby Journal, Planner).

**Esses quatro rótulos NÃO são as personas vigentes da Purpose Paper.** Em julho de 2026, esse material foi reinterpretado pela lente de Jobs-to-be-Done e consolidado em três hipóteses finais de persona — A Iniciante, A Praticante (bifurcada) e A Mãe em Jornada — descritas na skill `buyer-personas-pp`. Aquela skill é a referência ativa para decisões de produto, campanha, conteúdo e CRM.

Use esta skill apenas como **rastro de evidência**: de onde vieram os números, o que foi observado, e como a leitura evoluiu. Se alguém perguntar "quem é a cliente da PP", responda com `buyer-personas-pp`, não com os quatro rótulos daqui. Se quiser mapear os dois: Discípula ≈ base que deu origem à Iniciante + parte da Praticante (contexto Bible Studies); Organizadora ≈ dados que hoje compõem o contexto "Fé Quente" da Praticante (Planner/Journals) — mas trate esse mapeamento como aproximado, não oficial.

---

## Metodologia da análise original

- **Shopify:** CSVs de primeiras compras, pedidos completos, base de clientes (26.673 registros no recorte de personas; 150.824 registros na base completa de abril/2026)
- **Meta Ads:** CSV com nome de campanha + nome de anúncio, abril/2025–abril/2026
- **Google Search Console:** 1.000 queries + páginas, últimos 12 meses
- **Shopify Analytics:** receita por produto filtrada por UTM source = facebook

---

## Os quatro agrupamentos por produto de entrada

### A Discípula (entrada: Bíblia)
**Base:** 26.977 primeiros compradores | **LTV médio:** R$217 | **Recorrência:** 14%
- Email consent 22,8% — o mais baixo de todos os agrupamentos, apesar de 16.740 novos clientes em 2025
- 2ª compra: 43,5% compra outra Bíblia (padrão de presente/edição); 27,4% migra para journals/devocionais
- Meta Ads: ROAS 9,7×. Perfil etário 18-24 (26,5%), 25-34 (50,3%), 35-44 (17,6%). 12,9% masculino — o mais alto de todos
- GSC: domina "biblia purpose" (pos. 1,1), "como estudar a bíblia" (1.275 cliques), "bible journaling" (327 cliques) — busca comportamental de quem quer *aprender* a usar a Bíblia, não só comprá-la
- Shopify Facebook: Bíblia TPB = R$252k, produto #1 em receita Facebook
- Geográfico: mais distribuída (SP 30,9%), mais masculina (14,2%)

### A Praticante (entrada: Journal devocional)
**Base:** 6.790 primeiros compradores | **LTV:** R$354 (maior de todos) | **Recorrência:** 43%
- Email consent 59% — o mais alto de todos
- Entrada: Betel (1.796), Betânia (1.680), Diário de Culto (1.609)
- Meta Ads: ROAS 8,6× mas só 5% do budget — zero campanha dedicada para journals devocionais
- GSC: "o que é devocional" (62.936 impressões, CTR 0,4%) — maior oportunidade de SEO da empresa, busca informacional
- Canal: Instagram orgânico + Google, não paid dedicado
- Bimodal: Núcleo (5,8% da base, >R$700, 6,5 pedidos) vs. Experimentadora (52,4%, <R$200, 1 compra)

### A Mãe (entrada: Baby Journal + Devocionais Fernanda)
**Base (CSV analisado):** 7.432 clientes únicos (nota: discrepância com os 16.023 da análise por tags — subconjunto não totalmente explicado, usar com cautela) | **LTV:** R$336 | **Recorrência:** 21,3%
- Cross real para Bíblia: 4,1% (número anterior de 78,1% via tags é suspeito e não confirmado)
- Gifting loop: 47,3% dos clientes recorrentes compram um 2º BBJ no segundo pedido — funciona como produto de presente, não de autoconsumo
- Ecossistema BBJ: 29,4% compram ao menos 1 acessório
- Cross-sell Para Mães: 8,6%
- Canal: Instagram (30,2%), Google (20,8%), Fernanda (7,6%) — recorrência mais alta via Fernanda (28,6% vs. 20,7% geral)
- Meta Ads: ROAS 7,5×. 25-34 anos (58%), 35-44 (22,2%), 96,1% feminino
- Shopify Facebook: BBJ = R$329k combinado, #2 produto em receita absoluta

### A Organizadora (entrada: Planner)
**Base:** 9.796 primeiros compradores | **LTV:** R$315 | **Recorrência:** 33%
- Compra anual confirmada: 77 clientes compraram planner 4 anos seguidos; ~20% retorna ano a ano
- Meta Ads: ROAS 7,5× (menor ROAS imediato, mas o modelo de atribuição não captura a recompra anual). 18-24 (20,8%), 25-34 (56%), 35-44 (19,1%). 97,3% feminino
- GSC: domina nicho cristão — "planner cristão 2026" (pos. 1,07), "planner evangélico 2026" (pos. 1,07); busca pela metodologia ("planner não datado", "planner de leitura", "disciplinas espirituais")
- Conexão com Regra de Vida: cluster semântico inexplorado ("Praticando o Caminho" + "Uma Regra Comum" + "disciplinas espirituais")
- Gap crítico: /collections/planners na posição 2 com CTR 0,21% — maior desperdício orgânico identificado
- 37% nunca comprou Bíblia — o agrupamento mais independente do core Bíblia

---

## Análise de entrada por produto — abril/2026 (mapa completo)

Base: 150.824 clientes (Shopify, exportação completa até abril/2026). Compradores reais (≥1 pedido): 86.769.

### Tabela de retenção por produto de primeira compra

| Produto | n | Só 1x | Voltou 2+ | Fiel 3+ | Gasto médio | Cross Bíblia | Cross Planner |
|---|---|---|---|---|---|---|---|
| Journals PP-nativos (MPN + Prat.Palavra) | 2.639 | 70,7% | 29,3% | 16,1% | R$373 | 39,8% | 14,2% |
| NJ (Nosso Journal — Fernanda) | 2.787 | 69,8% | 30,2% | 12,3% | R$404 | 81,4% | 3,1% |
| Box Vanessa Belmonte | 796 | 71,5% | 28,5% | 11,2% | R$318 | 33,9% | 6,2% |
| BBJ (Baby Journal — Fernanda) | 16.023 | 73,9% | 26,1% | 9,8% | R$343 | 78,1% | 1,7% |
| Bible Study Ana Rute Cavaco | 413 | 78,5% | 21,5% | 8,2% | R$317 | 22,8% | 8,2% |
| Uma Regra Comum (foreign) | 355 | 78,9% | 21,1% | 9,0% | R$259 | 18,9% | 4,2% |
| Diário Minhas Estações (Fernanda) | 3.438 | 76,8% | 23,2% | 7,9% | R$229 | 54,1% | 2,9% |
| **Base Geral PP** | **86.769** | **78,9%** | **21,1%** | **8,1%** | **R$244** | **69,2%** | **12,4%** |
| Bible Study Efésios (Bazzo) | 487 | 86,9% | 13,1% | 2,9% | R$273 | 28,1% | 5,3% |
| Journal de Receitas (PP-nativo, não devocional) | 495 | 87,9% | 12,1% | 3,8% | R$214 | 13,9% | 6,7% |
| Praticando o Caminho (J.M. Comer) | 1.118 | 87,5% | 12,5% | 3,7% | R$206 | 11,1% | 2,4% |
| Sagrado Agora (Roberta Vicente) | 1.521 | 87,8% | 12,2% | 3,2% | R$149 | 12,0% | 12,8% |
| Para Mães (Fernanda) | 6.584 | 84,2% | 15,8% | 3,8% | R$169 | 8,2% | 1,2% |
| Wedding Planner (evento único) | 237 | 91,1% | 8,9%* | 1,7%* | R$247 | 4,6% | 4,2% |

*Recorrência baixa é esperada — produto de evento único.

### Categorias de entrada
1. **Construtoras de Base** (acima da média em tudo): Journals PP-nativos devocionais, Nosso Journal, Box Vanessa Belmonte
2. **Neutras / Médias**: Bible Study Ana Rute Cavaco, Uma Regra Comum, Diário Minhas Estações
3. **Tráfego sem Lealdade** (bem abaixo da média): Bible Study Efésios, Journal de Receitas, Praticando o Caminho, Sagrado Agora, Para Mães, Wedding Planner

### Insight central da análise
A variável discriminante entre alta e baixa retenção **não é** "produto próprio vs. autor externo" — **é a fé como motivação central do produto.** Journal de Receitas (PP-nativo, não-devocional) tem a mesma retenção que livros de autores passageiros; Box Vanessa Belmonte (externo, nicho devocional profundo) quase iguala os produtos PP-nativos. Produtos que resolvem "aprofundar minha vida espiritual com método" constroem base; produtos que resolvem outros jobs (organizar casamento, registrar receitas) geram tráfego pontual.

### Ecossistema Fernanda Witwytzky
28.086 clientes únicos = 32% da base compradora PP (risco de concentração). Sobreposição máxima entre quaisquer dois produtos: 7,8%.

| Produto | n | Natureza | Comportamento |
|---|---|---|---|
| Nosso Journal (NJ) | 2.787 | Álbum de casal, R$419,90 | Melhor externo da base |
| Baby Journal (BBJ) | 16.023 | Diário do bebê | Excelente, maior volume |
| Diário Minhas Estações | 3.438 | Diário sazonal | Médio-bom |
| Para Mães | 6.584 | Devocional maternidade | Fraco, audiência não-alinhada |

---

## Achados transversais

- "Praticando o Caminho" (parceria Thomas Nelson encerrada): 4.600 cliques/ano em páginas sem produto — "Uma Regra Comum" + Planner são o substituto natural
- Canibalização de Bíblia: 4 URLs competindo pelas mesmas buscas
- Nomenclatura genérica de anúncios (AD01, AD02): 30% do budget Meta opaco para análise
- Universo Fernanda em declínio: Nosso Journal quase morto (6-26 pedidos/mês) desde que ela parou de falar de casamento

## Sub-segmentos em construção (nomenclatura de transição, não oficial)
Estes rótulos foram propostos durante a análise mas não substituem as três hipóteses de `buyer-personas-pp`: Praticante Real (journals PP-nativos devocionais), Discípula Real (sub-segmento Bíblia com sinal de estudo sistemático), A Criativa (Bíblia + acessórios de bible journaling), Maioria Silenciosa (85,1% dos compradores de Bíblia sem sinal de prática), Leitora de Autora (Alinhada Profunda / Bíblia-Bound / Passageira, conforme a autora de entrada), A Noiva / Marco de Vida (via Nosso Journal ou Wedding Planner).

## Dashboards que visualizam estes dados
- `dashboard_buyer_personas.html` — dashboard com 8 abas e 7 gráficos (Chart.js) construído sobre estes quatro agrupamentos
- `GSC_Dashboard_Purpose_Paper.html`, `MetaAds_Dashboard_Purpose_Paper.html` — dashboards de canal com o detalhamento por agrupamento
