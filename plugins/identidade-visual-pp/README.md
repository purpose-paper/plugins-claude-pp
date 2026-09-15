# identidade-visual-pp

Plugin interno da Purpose Paper com a identidade visual oficial da marca, pronta para aplicar em qualquer peça HTML do time.

## O que vem dentro

- **`identidade-visual-pp`** — carrega a paleta do brandbook, tipografia (Georgia + Inter), logo, escala de espaçamento/forma, biblioteca de ícones inline e três layouts prontos (dashboard, landing page, página institucional). É a fonte única de verdade sobre "como a Purpose parece".

## Quando usar

Peça para uma peça "parecer Purpose", usar "as cores da marca", ou peça um dashboard, landing page, layout de e-mail, protótipo ou relatório novo. Não é necessária para estudos narrativos longform (Atos do Conselho) — para isso use a skill `estilo-estudo-narrativo-pp`, que já herda esta mesma base.

## Relação com outros plugins internos

Esta skill também vem embutida dentro do plugin `metodo-estudo-performance-produto-pp` (porque `estudo-produto-pp` depende dela). As duas cópias são intencionais: cada plugin instala de forma independente e autocontida, sem depender de outro plugin já estar instalado. Se o conteúdo da identidade visual mudar, atualize as duas cópias.

## Instalação

Via marketplace `purpose-paper-plugins` (ver `plugins-internos-pp.md` no projeto de estratégia de produto) — recomendado, porque atualizações futuras chegam sem reenvio manual. Alternativa pontual: instalar direto o arquivo `.plugin` anexado numa conversa do Cowork.

## Histórico de versões

- **0.1.0** (15/09/2026) — primeira versão, extraída do plugin `metodo-estudo-performance-produto-pp` para permitir instalação isolada por quem só precisa de identidade visual, sem a metodologia completa de estudo de produto.
