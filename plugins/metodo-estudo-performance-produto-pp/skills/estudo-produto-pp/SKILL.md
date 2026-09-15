---
name: estudo-produto-pp
description: "Cria o estudo completo de um produto Purpose Paper (dashboard de dados + estudo narrativo em Atos do Conselho) num único HTML, no padrão usado no Baby Journal 5 Anos. Use para um \"estudo de produto\", \"dashboard + estudo\", ou quando citarem o Baby Journal como modelo."
---

# Estudo de Produto — Purpose Paper

Esta skill replica, para qualquer produto da Purpose Paper, o formato criado originalmente para o **Baby Journal 5 Anos**: um único arquivo HTML com duas camadas — um **dashboard de dados** (o que aconteceu, com número) e um **estudo narrativo em Atos** (por que aconteceu e o que fazer, com metodologia). As duas camadas vivem juntas, navegáveis por abas, e se citam uma à outra.

Não é uma skill de identidade visual (para isso já existe `identidade-visual-pp`) nem de estudo narrativo genérico (para isso já existe `estilo-estudo-narrativo-pp`, pensada para ensaios tipo "Crescimento Purpose 2026"). Esta é específica do formato **produto + 5 (ou N) anos + dashboard + Atos + Perspectivas**, com os padrões técnicos e as fontes de dado que esse formato historicamente usa na Purpose.

## Quando usar

Use sempre que alguém pedir um estudo completo de um produto ou linha de produto — "faz um estudo do [produto] igual ao do Baby Journal", "quero um dashboard e um estudo desse produto", "vamos analisar 1 ano/2 anos/5 anos de [produto]". Também quando o pedido vier em partes ao longo de várias conversas (primeiro o dashboard, depois o estudo, depois ajustes) — mesmo assim, o destino final é sempre um único HTML.

Não use para um estudo puramente narrativo sem dado quantitativo por trás (aí é `estilo-estudo-narrativo-pp`), nem para um dashboard solto sem a camada de metodologia/Atos (aí é só aplicar `identidade-visual-pp` direto).

## Antes de começar: sempre pergunte

Esta skill é usada por pessoas do time de criação/growth que nem sempre vão saber o que informar de cara. Antes de escrever qualquer HTML, faça estas perguntas (pode ser em uma leva só, com `AskUserQuestion` se a interface tiver, ou em texto):

1. **Qual produto e qual período?** (nome exato do produto/linha, data de lançamento, até quando vai a análise — isso define o "N anos" do estudo.)
2. **Quais fontes de dado existem para este produto?** Pergunte especificamente por cada uma das quatro fontes que o Baby Journal usou (ver seção "Camada 1" abaixo) — não assuma que todas existem. Se uma fonte não existir (ex: produto novo sem reviews ainda, ou sem PNP próprio porque ainda não tem SKU individualizado), **a seção correspondente é adaptada ou omitida**, nunca preenchida com dado inventado.
3. **Quem é a audiência final?** Time interno, board, ou vai virar apresentação para outra área? Isso muda o quanto simplificar a linguagem técnica.
4. **Já existe alguma hipótese ou dúvida específica que motivou o pedido?** (Igual ao Baby Journal, que nasceu de perguntas específicas da Maeli sobre carrinho, reviews e Obviously Awesome.) Se existir, o estudo deve responder essas perguntas explicitamente antes de expandir para o resto.
5. **Existe um estudo anterior deste produto para atualizar, ou é do zero?** Se for atualização, leia o arquivo anterior inteiro antes de editar — nunca reescreva às cegas.

Não trave o trabalho por muito tempo nessas perguntas — se a pessoa não souber responder uma, prossiga com a melhor suposição, deixe a suposição explícita no próprio arquivo (numa nota `FATO/HIPÓTESE`) e siga.

## Visão geral do formato

Um único arquivo `.html`, autocontido (CSS e JS inline, sem dependências externas além de Chart.js via CDN), estruturado em **três macro-páginas** navegadas por abas no topo (padrão `.macro-page` / `.macro-page.is-active`, JS troca a classe, não recarrega a página):

- **I · Dados** — o dashboard. Seções numeradas, cada uma fechando com uma conclusão.
- **II · Estudos** — o estudo narrativo, dividido em **Atos** numerados (mesma lógica de abas, `.estudos-tab` / `.estudos-tab.is-active`), mais um "Quadro Geral" de abertura.
- **III · Perspectivas** — a síntese: ciclo de vida, decisões de investimento, e a "Decisão do Conselho" final.

Cada macro-página tem seu próprio subnav (lista de âncoras/abas logo abaixo do header). O header principal (marrom, fixo) tem só os três links macro: DADOS / ESTUDOS / PERSPECTIVAS.

Sempre chame a skill `identidade-visual-pp` primeiro para carregar os tokens de cor, tipografia e o bloco de CSS base — esta skill assume esses tokens (`--pp-marrom`, `--pp-polen`, `--pp-bege`, `--pp-laranja`, `--pp-azul`, `--pp-verde`, cores de status) já carregados e constrói em cima deles.

## Camada 1 — Dados (o dashboard)

### As quatro fontes de dado

O Baby Journal usou estas quatro fontes; confirme com quem pediu quais existem para o produto atual antes de assumir:

1. **Shopify (pedidos/clientes)** — export de pedidos completos. Dá volume, AOV, cross-sell real (o que foi comprado junto, calculado pedido a pedido, nunca estimado), segmentação por canal/estado/cliente novo vs recorrente.
2. **PNP — Plano de Negócio por Produto** — CSV mensal por produto/SKU, cobrindo todo o catálogo Purpose (não só o produto em análise — filtre pelo produto certo). Colunas: Faturamento Bruto/Líquido, Quantidade Vendida, Descontos (R$/%), Devoluções, Preço Líquido Médio, CMV, Custo unitário, Licenças, Royalties, Taxas Financeiras, Lucro Bruto, Margem Bruta%. É a fonte mais granular de custo/lucro por SKU — use sempre que a pergunta for sobre economia de um item específico (não só do produto principal, mas de acessórios/refis da mesma família).
   **Cuidado ao processar**: os números vêm com vírgula como separador de milhar (ex. `"56,918.74"`). Um parser ingênuo de `float()` sem remover a vírgula primeiro lê como erro/zero silenciosamente — sempre `.replace(',', '')` antes de converter, e sempre valide o total agregado contra pelo menos uma linha mensal individual (se um mês sozinho for maior que o "total anual" calculado, o parser está quebrado). O arquivo costuma vir em encoding `latin-1`, não UTF-8.
   **Para investigar causa de lucro/margem estranha**: cruze `Descontos (%)`, `Preço Líquido Médio` e `Custo unitário` lado a lado. Custo unitário estável + desconto disparando = problema de desconto/brinde, não de produção. Custo unitário subindo = problema de produção/CMV de verdade. Não escreva a causa como fato até confirmar qual dos dois padrões aparece nos números — e prefira sempre confirmar com quem pediu antes de publicar uma hipótese causal (ver seção "Disciplina FATO vs HIPÓTESE" abaixo).
3. **DRE financeiro interno** — visão contábil do produto principal (normalmente só do item "âncora" da família, não dos acessórios). Pode divergir ligeiramente da PNP (~1-2%) por diferença de rateio de custo entre as duas fontes — isso é esperado, não é erro; não tente reconciliar na força, só documente a diferença numa nota `<details>` colapsada.
4. **Judge.me (reviews)** — CSV de avaliações publicadas. Leia as reviews na íntegra, não só a média/nota — extraia padrões reais (por que presenteiam, o que gera atrito, o que gera antecipação antes do 1º uso, sinais de recompra) e cite trechos reais de cliente, não paráfrases genéricas. Confirme sempre a contagem real de reviews com quem pediu antes de publicar um número — bancos de review costumam ter exports "not-published" e "all-published" que dão contagens diferentes; pergunte qual é a fonte de verdade.

Se alguma fonte não existir para o produto em questão, **não invente o gráfico correspondente** — omita a seção ou substitua por uma nota curta explicando a ausência (ex: "produto lançado há N meses, ainda sem reviews publicadas suficientes para análise de padrão").

### Estrutura das seções de Dados

- Seções numeradas (01, 02, 03...) tanto no eyebrow de cada seção quanto no subnav — a ordem deve seguir uma progressão lógica (normalmente: ciclo de vida/economia geral → produtos/SKUs → produção/operação → clientes → cross-sell/carrinho → canais/tráfego → reviews, adaptando conforme o que fizer sentido pro produto).
- **Toda seção termina com uma conclusão visível** (`.conclusao-secao`, fundo marrom) — nunca deixe uma seção "solta" sem síntese, nem enterre a conclusão no meio do texto.
- **Boxes de curiosidade** (explicam uma discrepância de dado que não é o achado principal — ex: "por que dois números diferentes de pedidos aparecem aqui") viram `<details class="pp-collapse-note">` fechados por padrão, mostrando só a pergunta. **Achados de negócio de verdade ficam sempre visíveis**, nunca escondidos atrás de um clique.
- Gráficos seguem a skill `dataviz` (carregue-a antes de montar qualquer gráfico): Chart.js, sem eixo duplo, cores por família (categórica em ordem fixa, sequencial para magnitude, status reservado para bom/alerta/crítico), sempre com hover. Barras empilhadas para composição (ex: produto principal x acessórios), nunca pizza para mais de poucas categorias.
- KPIs em cards com hover revelando o texto completo do delta (não force tudo num número só sem contexto).

### Disciplina FATO vs HIPÓTESE

Nunca escreva uma explicação causal ("isso caiu porque X") como se fosse fato até checar os números que sustentam especificamente aquela causa. Quando a causa não estiver 100% clara pelos dados disponíveis, marque explicitamente como hipótese de trabalho e diga o que confirmaria ou refutaria. Se quem pediu o estudo corrigir uma hipótese sua com base em dado que você não tinha visto, **verifique a correção contra os números antes de aceitar** — não troque uma hipótese por outra sem conferir, mesmo vindo de quem pediu.

## Camada 2 — Estudo (a narrativa em Atos)

### Estrutura

- Um **Quadro Geral** de abertura, sintetizando as 6-8 lentes de análise mais relevantes para este produto (nem todo produto precisa das 8 lentes do Conselho — use as que realmente importam para as perguntas que motivaram o estudo).
- **Atos numerados** (tipicamente 5 a 8, um por framework/pergunta central), cada um em sua própria aba (`.estudos-tab`). Título de cada Ato: "Ato 0N · [uma frase que resume a tese do Ato]", seguido de um subtítulo que já entrega a conclusão do Ato (não guarde a conclusão pro final do Ato — anuncie logo no título/deck).
- Um Ato de **Diagnóstico consolidado** perto do fim (estilo "fatos brutais a confrontar", inspirado no Paradoxo de Stockdale) — o que está funcionando de verdade vs. o que precisa de decisão.
- A macro-página **Perspectivas** fecha com Ciclo de Vida, 2-3 "Perspectivas" de decisão de investimento (cada uma aplicando um framework, ex: Drucker/abandono planejado, Biddle/DHM revisitado, Roger Martin/Playing to Win com os decision-cards i./ii./iii./iv.), e termina em uma seção "Decisão do Conselho" no formato da seção 39 das instruções do projeto: 🎯 Decisão Recomendada, 📊 O que sustenta, 💰 Implicação econômica, ⚠️ Principal risco, 🔎 O que aumentaria a confiança, ✅ Próximas 3 ações, 💡 Pergunta de conselho.

### Frameworks — use os que servem, não todos por obrigação

As instruções do projeto já trazem o painel completo de pensadores/frameworks (JTBD de Christensen, Outcome-Driven Innovation de Ulwick, Obviously Awesome de Dunford, DHM de Biddle, Playing to Win de Roger Martin, Abandono Planejado de Drucker, Purple Cow de Godin, etc). Escolha os frameworks que respondem às perguntas reais que motivaram o estudo — não force um Ato por framework só para preencher 8 Atos. Um estudo de produto novo (sem histórico) pode ter só 4-5 Atos; um produto de linha madura com muita extensão pode justificar mais.

Quando citar um framework, aplique de verdade (responda as perguntas específicas dele com dado real do produto) — nunca cite o nome do pensador como decoração sem aplicar o método.

### Voz e evidência

Tom "Conselho Estratégico": analítico, direto, comercial, sem elogiar ideia antes de examinar. Toda leitura qualitativa (JTBD, positioning, etc.) deve ser sustentada com evidência real sempre que existir — trechos reais de review, números reais de conversão/cross-sell, não hipótese pura. Quando a leitura for só hipótese do Conselho (sem evidência de cliente ainda), diga isso explicitamente.

## Padrões técnicos (aprendidos com o Baby Journal — aplique desde o início, evita retrabalho)

### Arquitetura de abas — dois níveis independentes

Existem dois sistemas de aba independentes no mesmo arquivo, não confunda um com o outro:

1. **Macro-páginas** (`Dados` / `Estudos` / `Perspectivas`): `.macro-page{display:none} .macro-page.is-active{display:block}`, trocado por clique nos 3 links do header.
2. **Atos dentro de Estudos**: `.estudos-tab{display:none} .estudos-tab.is-active{display:block}`, trocado por clique nos links do subnav de Estudos (`.estudos-tab-link`).

**A aba ativa de qualquer subnav claro (fundo `--pp-polen-deep`) usa este CSS, literalmente, sem adaptar a cor de texto/fundo por conta própria:**

```css
.subnav a.is-active{
  background:var(--pp-marrom);
  color:var(--pp-polen);
  font-weight:bold;
}
.subnav a.is-active .num{
  color:#E8C9A8; /* NUNCA var(--pp-laranja) aqui — é a cor do numeral inativo, some em cima do marrom */
}
.subnav a.is-active:hover{
  background:var(--pp-marrom); /* trava: sem isso, o :hover do subnav (fundo bege claro) reaparece por cima do estado ativo quando o mouse pousa nele, e o texto claro vira ilegível de novo */
}
```

Regra de ouro, para qualquer estado `.is-active`/`.selected`/`.current` que você vier a criar: **defina `background` E `color` juntos, na mesma regra, sempre** — nunca herde uma cor de texto pensada para outro fundo (é assim que o texto “branco sobre branco” acontece: alguém copia só a cor de texto de um componente de fundo escuro pra um elemento de fundo claro, e esquece de trocar o fundo junto).

### Regra de contraste em seções de fundo escuro (`.chapter-dark`)

Qualquer componente reaproveitável (decision-card, callout, etc.) que possa aparecer tanto numa seção clara quanto dentro de uma `.chapter-dark` **precisa ter as duas versões escritas juntas, no mesmo momento em que você cria o componente** — nunca só a versão clara "por enquanto". Copie e adapte este par (light + dark) sempre que estilizar um componente novo desse tipo:

```css
/* versão padrão (seção clara) */
.decision-card .roman{color:var(--pp-marrom)}
.decision-card .body h4{color:var(--deep)}
.decision-card .body p{color:var(--text)}
.decision-card .body p strong{color:var(--deep)}

/* par obrigatório — mesma hora, não "depois": versão para dentro de .chapter-dark */
.chapter-dark .decision-card .roman{color:var(--pp-bege)}
.chapter-dark .decision-card .body h4{color:#FFFEF3}
.chapter-dark .decision-card .body p{color:#F4ECD9}
.chapter-dark .decision-card .body p strong{color:#FFFEF3}

/* mesma lógica pros callouts que têm variante de cor (.note/.success/.alert):
   a variante já define um fundo claro fixo (ex: #FFF8EE) que, dentro de uma
   .chapter-dark, empata em especificidade CSS com a regra escura genérica e
   pode vencer por estar depois no arquivo — força a versão escura aqui: */
.chapter-dark .callout.note,
.chapter-dark .callout.success,
.chapter-dark .callout.alert{
  background:rgba(255,254,243,0.08);
  border-left-color:#E8C9A8;
}
```

Nunca deixe uma cor de texto herdar de `var(--deep)`, `var(--text)`, ou qualquer variável clara-sobre-branco dentro de um elemento que more (ainda que só às vezes) dentro de `.chapter-dark` — mesmo que hoje o componente só apareça em fundo claro. É exatamente esse hiato ("hoje só existe na versão clara, escrevo a escura quando precisar") que gerou os dois bugs de contraste no Baby Journal.

### Gate automático de contraste — obrigatório antes de entregar

Não confie só em revisão visual. Depois de montar o arquivo (e de novo depois de qualquer edição de CSS/cor), rode este script via Playwright contra o HTML final, clicando em cada macro-página e cada Ato antes de cada leitura (ele só enxerga o que está `display:block` no momento). Trate qualquer resultado não-vazio como bloqueador — não entregue até a lista vir vazia:

```python
# contrast_check.py — cole, rode com `python3 contrast_check.py`
from playwright.sync_api import sync_playwright
import json, time

JS = r"""
() => {
  function parseColor(str){ const m=str.match(/rgba?\(([^)]+)\)/); if(!m) return null;
    const p=m[1].split(',').map(s=>parseFloat(s.trim()));
    return {r:p[0],g:p[1],b:p[2],a:p.length>3?p[3]:1}; }
  function relLum(c){ function lin(v){v/=255; return v<=0.03928? v/12.92 : Math.pow((v+0.055)/1.055,2.4);}
    return 0.2126*lin(c.r)+0.7152*lin(c.g)+0.0722*lin(c.b); }
  function blend(top,bottom){ const a=top.a; return {r:top.r*a+bottom.r*(1-a), g:top.g*a+bottom.g*(1-a), b:top.b*a+bottom.b*(1-a), a:1}; }
  function effectiveBg(el){ let node=el; const layers=[];
    while(node){ const cs=getComputedStyle(node); const bg=parseColor(cs.backgroundColor);
      if(bg && bg.a>0.001){ layers.push(bg); if(bg.a>=0.999) break; } node=node.parentElement; }
    if(layers.length===0) return {r:255,g:255,b:255,a:1};
    let result=layers[layers.length-1]; if(result.a<0.999) result=blend(result,{r:255,g:255,b:255,a:1});
    for(let i=layers.length-2;i>=0;i--){ result=blend(layers[i],result); } return result; }
  function contrast(c1,c2){ const l1=relLum(c1), l2=relLum(c2);
    return (Math.max(l1,l2)+0.05)/(Math.min(l1,l2)+0.05); }
  const results=[];
  for(const el of document.querySelectorAll('body *')){
    let hasText=false;
    for(const c of el.childNodes){ if(c.nodeType===3 && c.textContent.trim()) { hasText=true; break; } }
    if(!hasText) continue;
    const rect=el.getBoundingClientRect(); if(rect.width===0||rect.height===0) continue;
    const cs=getComputedStyle(el);
    if(cs.visibility==='hidden'||cs.display==='none'||parseFloat(cs.opacity)<0.05) continue;
    const fg=parseColor(cs.color); if(!fg) continue;
    const effBg=effectiveBg(el);
    const ratio=contrast(fg,effBg);
    const fs=parseFloat(cs.fontSize), bold=parseInt(cs.fontWeight)>=700;
    const threshold=(fs>=24||(fs>=18.66&&bold))?3.0:4.5;
    if(ratio<threshold){
      let text=''; for(const c of el.childNodes){ if(c.nodeType===3) text+=c.textContent; }
      results.push({text:text.trim().slice(0,60), ratio:ratio.toFixed(2),
        fg:cs.color, effBg:`rgb(${Math.round(effBg.r)},${Math.round(effBg.g)},${Math.round(effBg.b)})`});
    }
  }
  return results;
}
"""

with sync_playwright() as p:
    browser = p.chromium.launch(executable_path='/opt/pw-browsers/chromium')
    page = browser.new_page(viewport={'width':1400,'height':1000})
    page.goto('file:///CAMINHO/PARA/O/ARQUIVO.html')  # ajuste o caminho
    all_issues = {}
    # troque estes seletores pelos das abas reais do arquivo em questão
    page.click('a[href="#dados"]'); time.sleep(0.1)
    for r in page.evaluate(JS): all_issues[(r['text'], r['ratio'])] = r
    page.click('a[href="#estudos"]'); time.sleep(0.1)
    for tab in ['ato1','quadro-geral','ato2','ato3','ato4','ato5','ato6','ato7','ato8']:
        try:
            page.click(f'a.estudos-tab-link[data-target="{tab}"]')
            page.mouse.move(700, 5)  # tira o cursor de cima do link clicado, senão :hover contamina a leitura
            time.sleep(0.1)
        except Exception:
            continue
        for r in page.evaluate(JS): all_issues[(r['text'], r['ratio'])] = r
    page.click('a[href="#perspectivas"]'); time.sleep(0.1)
    for r in page.evaluate(JS): all_issues[(r['text'], r['ratio'])] = r
    browser.close()
    print(f"{len(all_issues)} problema(s) de contraste:")
    for v in all_issues.values(): print(json.dumps(v, ensure_ascii=False))
```

Se a lista vier vazia, siga. Se vier algo, corrija o CSS (usando o par light/dark acima como modelo) e rode de novo — não entregue com a lista não-vazia, mesmo que pareça "pequeno" ou "só um texto".

### Padrão de callout duplo

O arquivo usa dois sistemas de callout diferentes por página — não misture:
- `.pp-callout.{note|ok|alerta|erro}` — usado na macro-página Dados.
- `.callout.{note|success|alert}` — usado nas macro-páginas Estudos/Perspectivas.

## Checklist de validação antes de entregar

1. Rode o arquivo num browser headless (Playwright) clicando por **todas** as macro-páginas e **todos** os Atos — confira zero erros de console/JS em cada clique, não só no carregamento inicial.
2. **Rode o script de gate de contraste** (seção "Gate automático de contraste" acima) e confirme que a lista sai vazia. Isso não é opcional nem substituível por "olhar com atenção" — os dois bugs de contraste do Baby Journal passaram por revisão visual antes de serem pegos pelo script. Se der problema, corrija com o par light/dark e rode de novo até vir vazio.
3. Tire screenshot de cada macro-página e de pelo menos um Ato de fundo escuro, como conferência visual complementar ao script (não no lugar dele).
4. Confira que todo número citado no texto bate com o número correspondente no gráfico/tabela da mesma seção (Chart.js runtime pode ser lido via `Chart.getChart(id)` para conferir os dados carregados).
5. Confira que nenhuma seção ficou sem conclusão, e que nenhum achado de negócio real ficou escondido dentro de um `<details>`.
6. Releia a lista de FATO vs HIPÓTESE — nenhuma hipótese deve estar escrita como fato.

## Entrega

Entregue o arquivo `.html` via SendUserFile, e se houver computador vinculado com uma pasta de saída conhecida do projeto, salve lá também. Ao final de uma rodada de mudanças relevantes, registre um resumo no doc de status do projeto (se existir um doc de acompanhamento do produto em questão) — o que foi pedido, o que foi decidido, o que ficou pendente — para que uma sessão futura consiga continuar sem reconstruir o contexto do zero.