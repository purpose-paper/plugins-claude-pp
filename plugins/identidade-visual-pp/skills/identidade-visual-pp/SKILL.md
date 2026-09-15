---
name: "identidade-visual-pp"
description: "Carrega a identidade visual completa da Purpose Paper (paleta do brandbook, tipografia Georgia+Inter, logo, escala de espaçamento/forma, biblioteca de ícones inline e três layouts prontos — dashboard, landing page, página institucional) para aplicar em QUALQUER peça HTML do time. Use sempre que alguém pedir para uma peça \"parecer Purpose\", usar \"as cores da marca\", pedir um dashboard/landing page/layout novo, ou precisar de identidade visual e composição de página fora do contexto de estudo narrativo longform (para isso, use estilo-estudo-narrativo-pp, que herda esta mesma base)."
---

# Identidade Visual · Purpose Paper

Esta skill carrega a **identidade visual oficial da Purpose Paper** (cores do brandbook, tipografia, logo, escala de espaçamento/forma, ícones e componentes de UI prontos) para ser aplicada em **qualquer peça HTML** produzida pelo time — dashboards, landing pages, layouts de página institucionais, relatórios, formulários, protótipos. Ela é a fonte única de verdade sobre "como a Purpose parece", com tudo que uma pessoa precisa para copiar, colar e adaptar: tokens de CSS, biblioteca de ícones e três layouts completos prontos (dashboard, landing page, página institucional).

Diferente da skill `estilo-estudo-narrativo-pp` (que é uma metodologia editorial completa para estudos longform em Atos, com tom de voz "Conselho Estratégico"), esta skill é **identidade visual + composição de layout**: cor, tipografia, logo, espaçamento, ícones, componentes de UI genéricos e exemplos de página inteira. Use-a como base para tudo; use a skill de estudo narrativo em cima dela só quando a peça for especificamente um estudo/ensaio longform.

## Quando usar

Use sempre que alguém do time for criar ou revisar uma peça HTML da Purpose Paper e precisar que ela "pareça Purpose": dashboard interno, landing page de produto, página de vendas, layout de e-mail em HTML, protótipo de app, relatório interativo, página de agradecimento, formulário, ou qualquer outra interface visual. Isso inclui pedidos como "cria um dashboard com a nossa identidade", "faz uma landing page no estilo Purpose", "usa as cores da marca nesse layout", "deixa esse HTML com a nossa cara", "que layout eu uso pra isso".

Não use isoladamente para estudos narrativos completos (Atos numerados, tom Conselho Estratégico, citação de pensadores) — nesse caso, invoque `estilo-estudo-narrativo-pp`, que já herda esta mesma paleta e tipografia mas adiciona a camada narrativa.

## Os pilares da identidade (nunca pule nenhum)

### 1. Paleta — SOMENTE cores do brandbook

| Nome | HEX | Uso típico |
|---|---|---|
| **Marrom Pigmento** | `#4F2C1D` | Cor principal — headers, nav, botões primários, texto de destaque |
| **Branco Pólen** | `#FFFEF3` | Fundo principal (nunca branco puro como fundo default) |
| **Branco Luz** | `#FFFFFF` | Fundo de cards e superfícies elevadas sobre o Pólen |
| **Azul Céu** | `#C0D0E0` | Categoria secundária, KPI/série secundária, badges neutros |
| **Bege Kraft** | `#D3B38D` | Acento quente, séries históricas, hover states suaves |
| **Verde Semente** | `#736635` | Categoria/cenário "ambicioso", sucesso institucional |
| **Laranja Barro** | `#924C2E` | Acento de destaque — eyebrows, itálico de ênfase, CTA secundário |
| **Preto Esferográfico** | `#31261D` | Texto principal |

Cores semáforo — **só** para indicadores +/-, status e alertas, nunca em texto longo ou grandes áreas:

| Nome | HEX | Uso |
|---|---|---|
| Verde Positivo | `#9DA354` | status "ok"/"concluído", Δ positivo |
| Vermelho Vivo | `#C0451D` | status "atenção"/erro, Δ negativo, linha de meta |
| Amarelo Dourado | `#D8A042` | status "em andamento" |

**Proibido:** roxo, ciano, azul-escuro saturado, vermelho puro de sistema, verde de sucesso genérico (tipo `#00C853`), qualquer cor de biblioteca de UI (Tailwind, Material, Bootstrap) que não conste nas tabelas acima.

### 2. Tipografia — duas famílias, papéis fixos

- **Georgia (serif)** — protagonista. Títulos, corpo de texto longo, números grandes/KPIs de destaque, citações, botões primários com peso editorial.
- **Inter (sans-serif)** — suporte. Labels, eyebrows (caixa alta + letter-spacing), navegação, tags, cabeçalhos de tabela, captions, dados pequenos, elementos de interface (filtros, badges, menus).
- **`'Courier New', monospace`** — só para colunas numéricas em tabelas onde o alinhamento de dígito importa (ex: valores financeiros lado a lado).

Regra de bolso: **texto de leitura ou número de destaque → Georgia. Etiqueta, dado pequeno, navegação ou função de interface → Inter.**

Nunca importe Google Fonts adicionais além de Inter. Georgia é system font, não precisa de import.

### 3. Logo

Logo horizontal oficial. Sempre em **Marrom Pigmento `#4F2C1D`** sobre fundos claros (Pólen, Branco), ou em **Branco Pólen `#FFFEF3`** sobre fundos escuros (`.pp-dark`, `.pp-header`). Nunca distorça a proporção, nunca recolora fora dessas duas opções. Para usar sobre fundo escuro, troque `fill="#4f2c1d"` por `fill="#FFFEF3"` no `<g>`.

```svg
<svg viewBox="0 0 5515.98 399.24" xmlns="http://www.w3.org/2000/svg" preserveAspectRatio="xMinYMid meet">
<g fill="#4f2c1d"><path d="M142.22,340.67H0v-25.9l27.78-3.77c15.54-2.83,16.01-6.6,16.01-104.08,0-118.68-1.89-118.21-17.43-120.57L0,83.52v-25.43h151.65c63.1,0,90.9,30.61,90.9,75.35,0,48.04-38.15,96.07-100.79,96.07-19.31,0-39.56-3.76-56.04-9.41,0,86.18,1.89,89.48,15.54,90.9l40.97,3.77v25.9ZM85.71,203.15c18.37,2.36,34.38,3.3,55.57,3.3,34.38,0,54.64-23.55,54.64-60.28,0-40.5-21.67-62.17-66.88-62.17-16.01,0-30.61.94-43.33,2.36v116.8Z"/><path d="M629.16,231.87c0,68.77-28.73,113.98-108.32,113.98s-105.97-37.68-105.97-97.02c0-16.01.94-33.91.94-57.45,0-99.84-.94-104.55-13.66-105.49l-26.84-2.36.47-25.43h127.62v25.43l-31.07,2.83c-13.67,1.89-14.13,7.53-14.13,138.94,0,64.98,22.13,89.48,78.17,89.48,46.63,0,66.88-21.67,66.88-86.67,0-128.57-2.83-139.87-16.01-141.75l-27.78-2.83v-25.43h105.49v25.43l-23.08,2.83c-10.83,2.36-13.66,7.53-13.66,98.43,0,14.6.94,37.21.94,47.1Z"/><path d="M934.33,340.67h-135.64v-25.9l29.2-3.77c14.13-2.36,14.6-6.6,14.6-104.08,0-116.32-1.41-117.74-15.54-120.09l-28.26-3.3v-25.43h161.06c56.51,0,80.54,28.26,80.54,66.87,0,35.8-23.55,68.77-65.47,81.01,35.8,67.34,67.34,102.2,80.54,104.55l20.71,4.24v25.9h-63.11c-17.42-19.31-45.68-64.52-78.17-129.51-17.43,0-35.33-2.83-50.4-7.07,0,103.14.94,104.55,16.01,107.38l33.91,3.3v25.9ZM995.08,134.39c0-34.85-20.26-49.93-66.88-49.93-16.01,0-32.03.47-43.8,1.89v100.78c17.9,2.36,32.97,2.83,51.81,2.83,40.03,0,58.87-18.37,58.87-55.57Z"/><path d="M1335.08,340.67h-142.22v-25.9l27.78-3.77c15.54-2.83,16.01-6.6,16.01-104.08,0-118.68-1.89-118.21-17.43-120.57l-26.37-2.83v-25.43h151.65c63.1,0,90.9,30.61,90.9,75.35,0,48.04-38.15,96.07-100.79,96.07-19.31,0-39.56-3.76-56.04-9.41,0,86.18,1.89,89.48,15.54,90.9l40.97,3.77v25.9ZM1278.57,203.15c18.37,2.36,34.38,3.3,55.57,3.3,34.38,0,54.64-23.55,54.64-60.28,0-40.5-21.67-62.17-66.88-62.17-16.01,0-30.61.94-43.33,2.36v116.8Z"/><path d="M1703.83,345.38c-80.54,0-131.39-60.28-131.39-148.35s56.04-143.65,147.88-143.65c83.83,0,130.92,52.75,130.92,131.39,0,99.38-59.81,160.61-147.41,160.61ZM1722.2,315.71c54.63,0,82.88-33.44,82.88-101.26,0-83.83-40.03-131.87-102.67-131.87-54.16,0-83.35,28.73-83.35,97.49,0,88.07,36.73,135.64,103.14,135.64Z"/><path d="M2177.58,65.63c-1.89,24.03-3.77,48.98-5.18,73.47h-23.54l-1.89-16.48c-3.77-37.67-19.31-45.21-60.75-45.21-36.27,0-57.45,16.01-57.45,41.92,0,23.07,15.54,39.56,72.53,58.4,67.34,22.6,91.37,41.91,91.37,78.65,0,49.91-41.44,89.01-122.92,89.01-37.21,0-68.75-12.24-84.77-22.14,1.41-23.54,2.82-47.1,3.76-70.64h23.55l1.41,16.96c3.3,36.26,28.73,46.15,78.65,46.15,45.21,0,63.1-16.48,63.1-40.51,0-25.43-15.07-40.97-83.83-63.1-58.87-17.9-81.01-40.98-81.01-73.01,0-47.56,41.45-85.24,105.97-85.24,39.1,0,64.52,7.07,81.01,11.77Z"/><path d="M2546.31,239.89l-9.89,48.5c-5.18,24.5-9.43,25.44-126.69,25.44-.19-7.16-.31-39.38-.34-81.9.05-27.57,10.05-37.99,30.32-37.99,23.28,0,42.44,26.43,65.38,26.43l20.7-33.1c-36.16,0-42.86-24.2-73.44-24.2-21,0-34.72,14.06-42.96,27.06.02-48.32.13-98.34.35-105.66,115.38,0,121.51,0,126.22,27.31l7.53,42.86h23.55c-2.83-32.96-4.24-66.87-6.6-96.54h-235.95v25.43l32.96,3.3c10.37.94,10.84,4.71,10.84,113.02s-.94,109.74-8.01,110.68l-34.84,4.24v25.9h237.83c1.89-31.08,4.23-66.41,6.59-100.78h-23.54Z"/><path d="M3221.77,122.82c-13.5-26.09-21.53-41.6-38.72-74.84C3165.85,14.75,3140.63,0,3140.63,0l-161.76,199.62c48.75,0,71.82,23.76,99.26,76.79,13.5,26.09,21.53,41.6,38.72,74.84,17.2,33.24,42.42,47.99,42.42,47.99l161.76-199.62c-48.75,0-71.82-23.76-99.26-76.79Z"/><path d="M3862.63,340.67h-142.3v-25.92l27.8-3.77c15.54-2.83,16.01-6.59,16.01-104.14,0-118.75-1.88-118.28-17.43-120.64l-26.39-2.84v-25.43h151.74c63.14,0,90.95,30.63,90.95,75.39,0,48.07-38.18,96.13-100.85,96.13-19.31,0-39.58-3.77-56.07-9.42,0,86.24,1.88,89.54,15.54,90.95l40.99,3.77v25.92ZM3806.09,203.06c18.37,2.37,34.4,3.31,55.59,3.31,34.41,0,54.67-23.57,54.67-60.32,0-40.54-21.68-62.22-66.91-62.22-16.03,0-30.63.96-43.35,2.37v116.85Z"/><path d="M4161.94,340.67h-106.04v-25.92l11.3-4.24c14.14-6.12,21.21-24.04,122.99-259.19h30.16c12.73,34.41,41.01,96.14,57.49,135.25,45.25,105.55,50.43,120.17,67.87,125.82l8.01,2.36v25.92h-122.99v-25.92l29.69-2.83c11.78-1.41,17.43-3.3,17.43-11.3,0-8.49-10.36-34.4-22.61-63.14-19.33-.94-39.12-.94-60.32-.94-19.8,0-40.54,0-59.85.47-10.85,27.32-17.44,48.06-17.44,57.48s3.77,16.5,14.14,17.44l30.16,2.83v25.92ZM4245.81,216.26c-1.41-2.83-2.36-5.65-3.77-8.48-15.07-33.94-35.81-79.17-48.53-106.04-17.91,40.52-35.83,81.06-49.96,114.51,16.96.47,33.46.47,51.37.47s34.4,0,50.88-.47Z"/><path d="M4607.31,340.67h-142.3v-25.92l27.8-3.77c15.54-2.83,16.01-6.59,16.01-104.14,0-118.75-1.88-118.28-17.43-120.64l-26.39-2.84v-25.43h151.74c63.14,0,90.95,30.63,90.95,75.39,0,48.07-38.18,96.13-100.85,96.13-19.31,0-39.58-3.77-56.07-9.42,0,86.24,1.88,89.54,15.54,90.95l40.99,3.77v25.92ZM4550.77,203.06c18.37,2.37,34.4,3.31,55.59,3.31,34.41,0,54.67-23.57,54.67-60.32,0-40.54-21.68-62.22-66.91-62.22-16.03,0-30.63.96-43.35,2.37v116.85Z"/><path d="M5374.13,340.67h-135.71v-25.92l29.22-3.77c14.13-2.36,14.6-6.59,14.6-104.14,0-116.4-1.41-117.81-15.54-120.17l-28.28-3.31v-25.43h161.16c56.55,0,80.59,28.28,80.59,66.91,0,35.81-23.57,68.8-65.5,81.06,35.81,67.38,67.38,102.25,80.57,104.61l20.74,4.24v25.92h-63.14c-17.44-19.33-45.72-64.56-78.23-129.59-17.43,0-35.34-2.83-50.41-7.08,0,103.21.94,104.62,16.01,107.45l33.93,3.3v25.92ZM5434.92,134.26c0-34.87-20.25-49.94-66.91-49.94-16.03,0-32.04.47-43.82,1.88v100.84c17.9,2.36,32.99,2.83,51.83,2.83,40.06,0,58.91-18.38,58.91-55.61Z"/><path d="M5068.11,239.89l-9.89,48.5c-5.18,24.5-9.43,25.44-126.69,25.44-.19-7.16-.31-39.38-.34-81.9.05-27.57,10.05-37.99,30.32-37.99,23.28,0,42.44,26.43,65.38,26.43l20.7-33.1c-36.16,0-42.86-24.2-73.44-24.2-21,0-34.72,14.06-42.96,27.06.02-48.32.13-98.34.35-105.66,115.38,0,121.51,0,126.22,27.31l7.53,42.86h23.55c-2.83-32.96-4.24-66.87-6.6-96.54h-235.95v25.43l32.96,3.3c10.37.94,10.84,4.71,10.84,113.02s-.94,109.74-8.01,110.68l-34.84,4.24v25.9h237.83c1.89-31.08,4.23-66.41,6.59-100.78h-23.54Z"/></g>
</svg>
```

Altura recomendada: 16–20px em headers/nav, 28–40px em heros. Sempre `preserveAspectRatio="xMinYMid meet"`.

### 4. Espaçamento, forma e profundidade — as decisões de design menos óbvias

Estas são escolhas que não aparecem na paleta mas definem se uma peça "parece Purpose" ou parece genérica. Siga-as sempre, mesmo em componentes novos que não estão no catálogo abaixo.

| Decisão | Valor padrão |
|---|---|
| Espaço entre ícone e texto, dentro de badge | 6–8px |
| Padding interno de card / stat / callout | 20–24px |
| Espaço entre cards de uma mesma grade | 18px |
| Espaço entre seções verticais da página | 64px (96px em heros/landing pages) |
| Largura de leitura confortável (prose, parágrafos) | ~720px |
| Largura de conteúdo de dashboard/app | 1100–1200px |
| Raio pequeno — badge, input, botão | 4px |
| Raio médio — card, tabela, stat | 6px |
| Raio grande — hero card, modal, elemento de destaque | 10px |
| Raio pill — badge de status, tag | 999px |
| Sombra de repouso — cards estáticos, tabelas | `--shadow-soft` |
| Sombra elevada — header sticky, modal, elemento flutuante | `--shadow-med` |
| Ícone inline (ao lado de texto/label) | 16–20px |
| Ícone de navegação/ação | 20–24px |
| Ícone de destaque (feature, empty state) | 40–48px |
| Peso de borda padrão | 1px, cor `--border` |

Regra de composição: **respiro é parte da identidade.** Nunca comprima o padding de cards para caber mais conteúdo — prefira paginar, rolar ou reduzir o número de elementos por tela.

## Bloco de tokens CSS — cole no `<style>` de qualquer HTML

Este é o ponto de partida universal. Funciona igual em dashboard, landing page ou página institucional.

```css
:root {
  /* Tipografia */
  --ff-serif:Georgia,'Times New Roman',serif;
  --ff-sans:'Inter','Helvetica Neue',Arial,sans-serif;
  --ff-mono:'Courier New',monospace;

  /* Paleta oficial do brandbook */
  --pp-marrom:#4F2C1D;
  --pp-polen:#FFFEF3;
  --pp-branco:#FFFFFF;
  --pp-azul:#C0D0E0;
  --pp-bege:#D3B38D;
  --pp-verde:#736635;
  --pp-laranja:#924C2E;
  --pp-preto:#31261D;
  --pp-polen-deep:#F7F0DA;
  --pp-bege-soft:#EADBC2;
  --pp-bege-claro:#B5A98E;

  /* Semáforo (só indicadores/status) */
  --pp-status-ok:#9DA354;
  --pp-status-erro:#C0451D;
  --pp-status-alerta:#D8A042;

  /* Tokens funcionais */
  --text:#3E3025;
  --text-soft:#7A6B5C;
  --border:var(--pp-bege-soft);
  --shadow-soft:0 1px 3px rgba(79,44,29,0.07);
  --shadow-med:0 4px 18px rgba(79,44,29,0.10);

  /* Escala de espaçamento (base 8px) */
  --sp-1:8px; --sp-2:16px; --sp-3:24px; --sp-4:32px; --sp-5:48px; --sp-6:64px; --sp-7:96px;

  /* Escala de forma */
  --radius:6px;
  --radius-sm:4px; --radius-md:6px; --radius-lg:10px; --radius-pill:999px;
}

*{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
body{font-family:var(--ff-serif);background:var(--pp-polen);color:var(--text);line-height:1.6;font-size:16px}
.pp-wrap{max-width:1100px;margin:0 auto;padding:0 28px}

h1,h2,h3,h4{font-family:var(--ff-serif);color:var(--pp-marrom);font-weight:normal}
h1 em, h2 em, h3 em{font-style:italic;color:var(--pp-laranja)}

/* Rótulos, navegação, dados pequenos → Inter */
.pp-eyebrow,.pp-nav,.pp-badge,.pp-label,.pp-caption,.pp-table th,.pp-btn,.pp-input,.pp-select{
  font-family:var(--ff-sans);
}
.pp-eyebrow{font-size:11px;text-transform:uppercase;letter-spacing:4px;color:var(--pp-laranja);font-weight:bold}

/* HEADER / NAV genérico — serve para topbar de dashboard ou nav de landing page */
.pp-header{background:var(--pp-marrom);color:var(--pp-polen);padding:16px 0;box-shadow:var(--shadow-med)}
.pp-header .pp-wrap{display:flex;align-items:center;justify-content:space-between;gap:24px}
.pp-header .pp-logo{height:18px}
.pp-nav{display:flex;gap:4px;font-size:13px;align-items:center}
.pp-nav a{color:#E8DECF;text-decoration:none;padding:8px 12px;border-radius:var(--radius-sm);transition:all .15s}
.pp-nav a:hover,.pp-nav a.active{background:rgba(255,254,243,.12);color:var(--pp-polen)}

/* HERO genérico — landing page ou topo de dashboard/relatório */
.pp-hero{padding:72px 0;border-bottom:1px solid var(--border)}
.pp-hero h1{font-size:52px;line-height:1.1;letter-spacing:-1px;margin-bottom:20px}
.pp-hero .pp-deck{font-size:19px;color:var(--text);font-style:italic;max-width:680px;margin-bottom:32px}

/* SEÇÃO — variantes de fundo (regra de contraste obrigatória) */
.pp-section{padding:64px 0}
.pp-section.pp-alt{background:var(--pp-branco)}
.pp-section.pp-dark{background:var(--pp-marrom);color:var(--pp-polen)}
.pp-section.pp-dark h1,.pp-section.pp-dark h2,.pp-section.pp-dark h3{color:var(--pp-polen)}
.pp-section.pp-dark .pp-eyebrow{color:#E8C9A8}
.pp-section.pp-tint{background:linear-gradient(180deg,var(--pp-polen-deep) 0%,var(--pp-polen) 100%)}

/* BOTÕES */
.pp-btn{display:inline-block;padding:12px 24px;border-radius:var(--radius-sm);font-size:14px;font-weight:600;letter-spacing:.3px;text-decoration:none;cursor:pointer;border:1px solid transparent;transition:all .15s}
.pp-btn-primary{background:var(--pp-marrom);color:var(--pp-polen)}
.pp-btn-primary:hover{background:#3D2117}
.pp-btn-secondary{background:transparent;color:var(--pp-marrom);border-color:var(--pp-marrom)}
.pp-btn-secondary:hover{background:var(--pp-polen-deep)}
.pp-section.pp-dark .pp-btn-secondary{color:var(--pp-polen);border-color:var(--pp-polen)}

/* CARDS */
.pp-card{background:var(--pp-branco);border-radius:var(--radius-md);padding:24px;box-shadow:var(--shadow-soft)}
.pp-card.pp-accent-laranja{border-left:4px solid var(--pp-laranja)}
.pp-card.pp-accent-verde{border-left:4px solid var(--pp-verde)}
.pp-card.pp-accent-azul{border-left:4px solid var(--pp-azul)}
.pp-grid{display:grid;gap:18px}
.pp-grid-2{grid-template-columns:repeat(2,1fr)}
.pp-grid-3{grid-template-columns:repeat(3,1fr)}
.pp-grid-4{grid-template-columns:repeat(4,1fr)}

/* STAT / KPI CARD — base de qualquer dashboard */
.pp-stat{background:var(--pp-branco);border-radius:var(--radius-md);padding:20px 22px;box-shadow:var(--shadow-soft)}
.pp-stat .pp-stat-label{font-family:var(--ff-sans);font-size:11px;text-transform:uppercase;letter-spacing:2px;color:var(--text-soft);font-weight:600;margin-bottom:8px}
.pp-stat .pp-stat-value{font-family:var(--ff-serif);font-size:34px;color:var(--pp-marrom);font-weight:bold;line-height:1}
.pp-stat .pp-stat-delta{font-family:var(--ff-sans);font-size:12.5px;margin-top:6px;font-weight:600}
.pp-stat .pp-stat-delta.up{color:var(--pp-status-ok)}
.pp-stat .pp-stat-delta.down{color:var(--pp-status-erro)}

/* BADGES / STATUS */
.pp-badge{display:inline-flex;align-items:center;gap:6px;font-size:11px;text-transform:uppercase;letter-spacing:1.5px;font-weight:700;padding:4px 10px;border-radius:var(--radius-pill)}
.pp-badge.ok{background:#EDEBD9;color:var(--pp-status-ok)}
.pp-badge.erro{background:#FBE8DE;color:var(--pp-status-erro)}
.pp-badge.alerta{background:#FCF0DC;color:#8A6420}
.pp-badge.neutro{background:var(--pp-bege-soft);color:var(--pp-marrom)}
.pp-dot{width:9px;height:9px;border-radius:50%;display:inline-block}
.pp-dot.ok{background:var(--pp-status-ok)}
.pp-dot.erro{background:var(--pp-status-erro)}
.pp-dot.alerta{background:var(--pp-status-alerta)}

/* CALLOUTS */
.pp-callout{padding:16px 20px;border-radius:var(--radius-sm);font-size:14.5px;line-height:1.6}
.pp-callout.note{background:#FFF8EE;border-left:4px solid var(--pp-bege)}
.pp-callout.alerta{background:#FFF2EA;border-left:4px solid var(--pp-status-alerta)}
.pp-callout.erro{background:#FBEAE5;border-left:4px solid var(--pp-status-erro)}
.pp-callout.ok{background:#EEF4EA;border-left:4px solid var(--pp-status-ok)}

/* TABELAS */
.pp-table{width:100%;border-collapse:collapse;background:var(--pp-branco);border-radius:var(--radius-md);overflow:hidden;box-shadow:var(--shadow-soft)}
.pp-table th{background:var(--pp-marrom);color:var(--pp-polen);padding:12px;text-align:left;font-size:11.5px;text-transform:uppercase;letter-spacing:1px}
.pp-table td{padding:13px 12px;border-bottom:1px solid var(--border);font-size:14px}
.pp-table td.num{font-family:var(--ff-mono);text-align:right}
.pp-table tr:last-child td{border-bottom:none}
.pp-table tr:hover{background:var(--pp-polen-deep)}

/* PROGRESS BAR */
.pp-progress{height:10px;background:var(--pp-bege-soft);border-radius:var(--radius-pill);overflow:hidden}
.pp-progress-fill{height:100%;background:linear-gradient(90deg,var(--pp-laranja),var(--pp-bege))}

/* FORMULÁRIOS / FILTROS — inputs, selects, barra de filtro (dashboards) */
.pp-input,.pp-select{font-size:14px;padding:10px 14px;border:1px solid var(--border);border-radius:var(--radius-sm);background:var(--pp-branco);color:var(--text)}
.pp-input:focus,.pp-select:focus{outline:none;border-color:var(--pp-marrom)}
.pp-input::placeholder{color:var(--text-soft)}
.pp-filter-bar{display:flex;gap:12px;flex-wrap:wrap;margin-bottom:24px;align-items:center}

/* ÍCONES — ver biblioteca de partida na seção "Ícones" */
.pp-icon{width:20px;height:20px;stroke:currentColor;fill:none;stroke-width:1.75;stroke-linecap:round;stroke-linejoin:round;flex-shrink:0}
.pp-icon.sm{width:16px;height:16px}
.pp-icon.lg{width:24px;height:24px}
.pp-icon.feature{width:44px;height:44px;stroke-width:1.5}

/* FOOTER */
.pp-footer{padding:40px 0;text-align:center;font-size:12.5px;color:var(--text-soft);border-top:1px solid var(--border);background:var(--pp-polen-deep)}

@media (max-width:720px){
  .pp-hero h1{font-size:32px}
  .pp-grid-2,.pp-grid-3,.pp-grid-4{grid-template-columns:1fr}
  .pp-header .pp-wrap{flex-direction:column;gap:12px}
}
```

## Regra de ouro de contraste

Toda seção com fundo `.pp-dark` (Marrom) precisa forçar texto claro (`var(--pp-polen)` ou branco) em títulos, prose e labels. Nunca deixe texto `var(--text)` (escuro) sobre fundo marrom — é o erro mais comum ao reaproveitar componentes entre seções claras e escuras. Antes de publicar, percorra cada seção e confirme visualmente a legibilidade.

Fundos aceitos e o texto que combina com cada um:

| Fundo | Classe | Texto |
|---|---|---|
| Pólen `#FFFEF3` | padrão (`body` ou `.pp-section`) | Escuro (`--text`, `--pp-preto`) |
| Branco `#FFFFFF` | `.pp-alt` | Escuro |
| Marrom `#4F2C1D` | `.pp-dark` | Claro (`--pp-polen`, `#F4ECD9`) |
| Gradiente Pólen | `.pp-tint` | Escuro |

## Ícones — estilo e biblioteca de partida

Sempre inline SVG (stroke ajustado à cor do fundo, viewBox 24×24, `stroke-width` 1.5–1.75, cantos arredondados). **Nunca use CDN de bibliotecas de ícones** (Lucide, Font Awesome, Feather etc.) — falham silenciosamente em ambientes sem acesso à internet ou bloqueiam o carregamento da página. Use a classe `.pp-icon` (ver tokens acima) e troque a cor herdando de `color` do elemento pai.

Biblioteca mínima para começar (cole o `<path>`/`<circle>`/`<line>` dentro de um `<svg class="pp-icon" viewBox="0 0 24 24">`):

```html
<!-- check (sucesso, "ok") -->
<circle cx="12" cy="12" r="9"/><path d="M8 12.5l2.5 2.5L16 9"/>

<!-- alerta (triângulo) -->
<path d="M12 3L2 20h20L12 3z"/><line x1="12" y1="9" x2="12" y2="13.5"/><circle cx="12" cy="16.5" r="0.4" fill="currentColor"/>

<!-- tendência de alta -->
<path d="M4 17l5-5 4 4 7-8"/><path d="M15 8h5v5"/>

<!-- tendência de baixa -->
<path d="M4 7l5 5 4-4 7 8"/><path d="M15 16h5v-5"/>

<!-- busca -->
<circle cx="11" cy="11" r="7"/><line x1="21" y1="21" x2="16.65" y2="16.65"/>

<!-- seta para a direita (CTA, "ver mais") -->
<line x1="5" y1="12" x2="19" y2="12"/><path d="M13 6l6 6-6 6"/>

<!-- chevron para baixo (dropdown, accordion) -->
<path d="M6 9l6 6 6-6"/>

<!-- fechar / remover -->
<line x1="6" y1="6" x2="18" y2="18"/><line x1="6" y1="18" x2="18" y2="6"/>
```

Tamanhos: 16–20px em linha com texto/label, 20–24px em navegação/ação, 40–48px em ícones de destaque (feature cards, empty states) usando a classe `.pp-icon.feature`.

## Aplicando por tipo de peça

A base de tokens acima é sempre a mesma. O que muda é como você compõe os blocos — os três layouts prontos abaixo mostram exatamente essa composição.

**Dashboards:** use `.pp-header` como topbar fixa, `.pp-grid-3`/`.pp-grid-4` de `.pp-stat` para KPIs no topo, `.pp-table` para listas de dados, `.pp-badge`/`.pp-dot` para status, `.pp-filter-bar` com `.pp-input`/`.pp-select` para filtros, e Chart.js para gráficos (ver paleta de séries abaixo). Evite `.pp-hero` grande — dashboards priorizam densidade de informação, não impacto editorial.

**Landing pages:** use `.pp-hero` cheio com `h1` grande + `.pp-deck` + `.pp-btn-primary` como CTA principal. Alterne `.pp-section` e `.pp-section.pp-alt` entre blocos de conteúdo para criar ritmo visual. Use `.pp-section.pp-dark` para a seção de CTA final. `.pp-grid-3` com `.pp-card` funciona bem para grades de features/benefícios.

**Layouts de página institucionais (sobre, políticas, páginas internas):** `.pp-header` simples + `.pp-hero` reduzido + `.pp-section` únicos com parágrafos em Georgia, max-width ~720px, para leitura confortável.

**Estudos narrativos longform (Atos, tom Conselho Estratégico):** não recrie aqui — invoque a skill `estilo-estudo-narrativo-pp`, que usa esta mesma paleta e tipografia com uma camada narrativa e de componentes editoriais mais elaborada (pullquotes, matriz SWOT, Stockdale, etc.).

## Layouts prontos — copie e adapte

Estes três esqueletos usam só as classes `.pp-*` do bloco de tokens acima. Cole o HTML dentro do `<body>`, com o CSS de tokens no `<head>`. Onde aparecer `{{LOGO_SVG}}`, cole o SVG do logo (na cor certa para o fundo — pólen dentro do `.pp-header`, marrom fora dele).

### Dashboard

```html
<div class="pp-header">
  <div class="pp-wrap">
    <div class="pp-logo" style="height:18px">{{LOGO_SVG_POLEN}}</div>
    <nav class="pp-nav">
      <a href="#" class="active">Visão Geral</a>
      <a href="#">Vendas</a>
      <a href="#">Produtos</a>
      <a href="#">Configurações</a>
    </nav>
  </div>
</div>

<div class="pp-wrap" style="padding:32px 28px 64px">
  <div style="display:flex;justify-content:space-between;align-items:baseline;margin-bottom:24px">
    <h1 style="font-size:28px">Visão <em>Geral</em></h1>
    <span style="font-family:var(--ff-sans);font-size:12px;color:var(--text-soft)">Atualizado há 4 min</span>
  </div>

  <div class="pp-filter-bar">
    <input class="pp-input" placeholder="Buscar produto...">
    <select class="pp-select"><option>Últimos 30 dias</option><option>Este mês</option></select>
  </div>

  <div class="pp-grid pp-grid-4" style="margin-bottom:32px">
    <div class="pp-stat">
      <div class="pp-stat-label">Receita do mês</div>
      <div class="pp-stat-value">R$ 482k</div>
      <div class="pp-stat-delta up">▲ 12% vs mês anterior</div>
    </div>
    <div class="pp-stat">
      <div class="pp-stat-label">Pedidos</div>
      <div class="pp-stat-value">1.204</div>
      <div class="pp-stat-delta up">▲ 6%</div>
    </div>
    <div class="pp-stat">
      <div class="pp-stat-label">Ticket médio</div>
      <div class="pp-stat-value">R$ 214</div>
      <div class="pp-stat-delta down">▼ 3%</div>
    </div>
    <div class="pp-stat">
      <div class="pp-stat-label">Taxa de reembolso</div>
      <div class="pp-stat-value">1,8%</div>
      <div class="pp-stat-delta up">▲ 0.2pp</div>
    </div>
  </div>

  <div class="pp-card" style="margin-bottom:24px">
    <h3 style="font-size:16px;margin-bottom:16px;color:var(--pp-marrom)">Receita ao longo do tempo</h3>
    <canvas id="chartReceita" height="90"></canvas>
  </div>

  <div class="pp-card">
    <h3 style="font-size:16px;margin-bottom:16px;color:var(--pp-marrom)">Produtos</h3>
    <table class="pp-table">
      <thead><tr><th>Produto</th><th>Status</th><th class="num">Vendas</th></tr></thead>
      <tbody>
        <tr><td>Bíblia de Estudo Purpose</td><td><span class="pp-badge ok"><span class="pp-dot ok"></span>Em dia</span></td><td class="num">1.204</td></tr>
        <tr><td>Devocional 90 Dias</td><td><span class="pp-badge alerta"><span class="pp-dot alerta"></span>Estoque baixo</span></td><td class="num">312</td></tr>
        <tr><td>Kit Presente</td><td><span class="pp-badge erro"><span class="pp-dot erro"></span>Atrasado</span></td><td class="num">87</td></tr>
      </tbody>
    </table>
  </div>
</div>

<div class="pp-footer">Purpose Paper · Dashboard interno</div>
```

### Landing page

```html
<div class="pp-header">
  <div class="pp-wrap">
    <div class="pp-logo" style="height:18px">{{LOGO_SVG_POLEN}}</div>
    <nav class="pp-nav">
      <a href="#produto">Produto</a>
      <a href="#depoimentos">Depoimentos</a>
      <a href="#comprar" class="pp-btn" style="background:var(--pp-polen);color:var(--pp-marrom);padding:8px 18px">Comprar</a>
    </nav>
  </div>
</div>

<section class="pp-hero">
  <div class="pp-wrap">
    <div class="pp-eyebrow">Novo · Coleção 2026</div>
    <h1>Um espaço para <em>permanecer</em><br>em qualquer estação da vida.</h1>
    <p class="pp-deck">O devocional que te ajuda a voltar, todos os dias, ao que sustenta — mesmo quando o esforço não é suficiente.</p>
    <a href="#comprar" class="pp-btn pp-btn-primary">Quero o meu</a>
  </div>
</section>

<section class="pp-section pp-alt" id="produto">
  <div class="pp-wrap">
    <h2 style="text-align:center;margin-bottom:8px">Feito para <em>sua rotina</em> real</h2>
    <p style="text-align:center;color:var(--text-soft);max-width:560px;margin:0 auto 40px">Três motivos pelos quais o time recomenda começar por aqui.</p>
    <div class="pp-grid pp-grid-3">
      <div class="pp-card pp-accent-laranja">
        <h3 style="font-size:19px;margin-bottom:8px">Leitura de 5 minutos</h3>
        <p style="font-size:14.5px;color:var(--text)">Cabe na correria do dia — sem culpa por não ter tempo.</p>
      </div>
      <div class="pp-card pp-accent-verde">
        <h3 style="font-size:19px;margin-bottom:8px">Sem jargão religioso</h3>
        <p style="font-size:14.5px;color:var(--text)">Linguagem direta, sem citação decorativa.</p>
      </div>
      <div class="pp-card pp-accent-azul">
        <h3 style="font-size:19px;margin-bottom:8px">Comunidade</h3>
        <p style="font-size:14.5px;color:var(--text)">Grupo de acompanhamento incluso na compra.</p>
      </div>
    </div>
  </div>
</section>

<section class="pp-section" id="depoimentos">
  <div class="pp-wrap" style="max-width:760px;text-align:center">
    <p style="font-size:22px;font-style:italic;color:var(--pp-marrom);line-height:1.5">"Foi o primeiro devocional que eu de fato terminei."</p>
    <p style="margin-top:16px;font-family:var(--ff-sans);font-size:12px;text-transform:uppercase;letter-spacing:2px;color:var(--text-soft)">— Leitora, turma de 2025</p>
  </div>
</section>

<section class="pp-section pp-dark" id="comprar">
  <div class="pp-wrap" style="text-align:center">
    <h2>Pronta para <em>começar</em>?</h2>
    <p style="margin:16px 0 28px;color:#F0E6D0">Frete grátis para todo o Brasil nesta semana.</p>
    <a href="#" class="pp-btn" style="background:var(--pp-polen);color:var(--pp-marrom)">Comprar agora</a>
  </div>
</section>

<div class="pp-footer">© 2026 Purpose Paper</div>
```

### Página institucional

```html
<div class="pp-header">
  <div class="pp-wrap">
    <div class="pp-logo" style="height:18px">{{LOGO_SVG_POLEN}}</div>
    <nav class="pp-nav">
      <a href="#">Início</a>
      <a href="#">Sobre</a>
      <a href="#">Contato</a>
    </nav>
  </div>
</div>

<section class="pp-hero" style="padding:48px 0">
  <div class="pp-wrap">
    <div class="pp-eyebrow">Sobre a Purpose</div>
    <h1 style="font-size:38px">Nossa <em>história</em></h1>
  </div>
</section>

<section class="pp-section">
  <div class="pp-wrap" style="max-width:720px">
    <p style="margin-bottom:18px">Parágrafo institucional em Georgia, leitura confortável, largura máxima de 720px para não cansar o olho.</p>
    <p>Segundo parágrafo, mesmo padrão — sem grades, sem cards, só texto corrido bem espaçado.</p>
  </div>
</section>

<div class="pp-footer">Purpose Paper · Todos os direitos reservados</div>
```

## Gráficos (Chart.js) — paleta de séries

Ao plotar dados temporais ou comparativos, siga esta atribuição para manter consistência entre peças:

| Série | Cor | Estilo |
|---|---|---|
| Histórico mais antigo | `#B5A98E` | Tracejado fino |
| Histórico recente | `#D3B38D` | Sólido fino |
| Realizado / atual (destaque) | `#4F2C1D` | Sólido grosso, pontos com borda branca |
| Orçamento / projeção | `#7A99B5` | Tracejado curto |
| Meta | `#C0451D` | Tracejado longo |

Para gráficos de barras/categorias sem série temporal, use a sequência: Marrom → Laranja → Verde → Azul → Bege, nessa ordem, e nunca mais de 5 cores num único gráfico.

## Checklist antes de publicar qualquer HTML com esta identidade

1. Todas as cores usadas estão na paleta oficial (sem roxo, ciano, azul-escuro saturado, verde/vermelho de sistema)?
2. Georgia protagoniza texto de leitura e números grandes; Inter cuida de labels/navegação/dados pequenos?
3. Logo presente, na cor certa para o fundo, sem distorção?
4. Todo texto tem contraste legível no fundo em que está (ver tabela de contraste)?
5. Espaçamento segue a escala (padding de card 20–24px, seções 64–96px) — nada espremido?
6. Ícones em inline SVG, no tamanho certo para o contexto (16–20 / 20–24 / 40–48px)?
7. Sem CDN de ícones nem frameworks de UI — tudo autocontido?
8. Sem dependências pesadas além de Chart.js (se houver gráfico)?
9. Responsivo testado em ~1280px (desktop) e ~375px (mobile)?

## Anti-padrões

- Não invente cores fora da paleta, mesmo "parecidas" com o brandbook.
- Não misture nomenclatura desta skill (`.pp-*`) com nomenclatura da skill de estudo narrativo (`.chapter`, `.ato`, `.sintese`) no mesmo documento — são vocabulários de classes distintos para contextos distintos.
- Não use fundo claro com texto claro, ou fundo escuro com texto escuro.
- Não use frameworks de UI (Bootstrap, Tailwind CDN, Material) — eles trazem suas próprias cores e tipografia e conflitam com a identidade.
- Não comprima o espaçamento padrão para "caber mais coisa" — ajuste a hierarquia de conteúdo, não o respiro.
- Não use ícones de CDN externo — sempre inline SVG a partir da biblioteca mínima acima ou equivalente no mesmo estilo.

