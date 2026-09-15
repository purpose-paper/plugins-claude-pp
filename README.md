# purpose-paper-plugins

Marketplace interno de plugins Claude/Cowork da Purpose Paper. Cada pessoa do time conecta este repositório uma vez no próprio Claude e passa a instalar (e receber atualizações de) qualquer plugin listado aqui, sem precisar receber arquivo `.plugin` por Slack/e-mail a cada versão nova.

## Como o time instala (uma vez)

No Cowork (desktop):

1. Abrir **Customize** → aba **Plugins** → seção **Personal plugins** → botão **"+"** → **Add marketplace**.
2. Escolher **"Add from a repository"** e colar a URL deste repositório no GitHub.
3. Depois de sincronizar, instalar o plugin **`metodo-estudo-performance-produto-pp`** a partir da lista.

No Claude Code (CLI), o equivalente é:

```
/plugin marketplace add <url-deste-repositório>
/plugin install metodo-estudo-performance-produto-pp@purpose-paper-plugins
```

## Como adicionar um novo plugin depois

1. Criar a pasta `plugins/<nome-do-plugin>/` com `.claude-plugin/plugin.json`, `skills/*/SKILL.md` etc. (mesma estrutura de `plugins/metodo-estudo-performance-produto-pp/`).
2. Adicionar uma entrada em `.claude-plugin/marketplace.json`, dentro do array `plugins`, apontando `source` para `./plugins/<nome-do-plugin>`.
3. Commitar e dar push. Quem já conectou o marketplace recebe a atualização (ou roda `/plugin marketplace update` no CLI).

## Como atualizar um plugin existente

Editar os arquivos dentro de `plugins/<nome-do-plugin>/`, subir a versão em `plugin.json` e em `.claude-plugin/marketplace.json`, e dar push. Não precisa recriar o marketplace nem reenviar arquivo pra ninguém.

## Plugins neste marketplace

| Plugin | O que faz |
|---|---|
| `metodo-estudo-performance-produto-pp` | Cria o estudo completo de um produto (dashboard de dados + estudo narrativo em Atos do Conselho) num único HTML, no padrão do Baby Journal 5 Anos. Inclui a skill de identidade visual da marca como dependência. |
