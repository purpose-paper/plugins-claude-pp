# metodo-estudo-performance-produto-pp

Plugin interno da Purpose Paper com a metodologia usada para criar o estudo **Baby Journal 5 Anos**, para o time replicar em outros produtos.

## O que vem dentro

- **`estudo-produto-pp`** — a skill principal. Cria o estudo completo de um produto (dashboard de dados + estudo narrativo em Atos do Conselho) num único arquivo HTML, no padrão do Baby Journal 5 Anos. Cobre as 4 fontes de dado (Shopify, PNP, DRE, Judge.me), a disciplina FATO vs. HIPÓTESE, a estrutura de Atos e Decisão do Conselho, os padrões técnicos de abas, e — importante — um **gate automático de contraste** (script Python/Playwright pronto para rodar) que bloqueia a entrega até garantir que os bugs de contraste que já apareceram no Baby Journal (texto cinza em fundo marrom, texto off-white em fundo branco) não se repitam.
- **`identidade-visual-pp`** — a skill de identidade visual da marca (paleta do brandbook, tipografia Georgia + Inter, logo, escala de espaçamento/forma, ícones, componentes de UI prontos). A `estudo-produto-pp` depende dela — por isso as duas vêm juntas neste plugin.

## Quando usar

Peça um "estudo de produto", "dashboard + estudo", "análise completa de [produto]", ou cite o Baby Journal como modelo a replicar. A skill vai te fazer algumas perguntas antes de começar (produto/período, quais fontes de dado existem, audiência, hipótese motivadora, se é um estudo novo ou atualização).

## Instalação

No Claude Code ou Cowork, instale o arquivo `.plugin` recebido. As duas skills (`estudo-produto-pp` e `identidade-visual-pp`) ficam disponíveis automaticamente depois disso.

## Origem

Construído a partir do estudo Baby Journal 5 Anos e do processo de correção de bugs de contraste identificado nele — a skill principal já nasce com a lição desses bugs incorporada como regra técnica (CSS pronto + script de validação), não apenas como instrução em texto.
