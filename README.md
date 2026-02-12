# Bitrix24 API Docs — Claude Code Plugin

Plugin para [Claude Code](https://docs.anthropic.com/en/docs/claude-code) que fornece acesso completo a documentacao da API REST do Bitrix24, permitindo consultar qualquer metodo, entidade ou padrao de integracao diretamente durante o desenvolvimento.

## Numeros

| Metrica | Valor |
|---------|-------|
| Paginas de documentacao | 1.036 |
| Arquivos markdown | 53 |
| Metodos da API indexados | 515+ |
| Tamanho total dos docs | 5.8 MB |
| Fonte oficial | [apidocs.bitrix24.com](https://apidocs.bitrix24.com) |

## Instalacao

### Como plugin global (disponivel em qualquer projeto)

```bash
claude plugin add /caminho/para/DOCUMENTACAO_BITRIX24
```

### Verificar instalacao

```bash
claude plugin list
```

Voce deve ver `bitrix24-api-docs` na lista.

### Remover

```bash
claude plugin remove bitrix24-api-docs
```

## Como funciona

Apos instalado, o plugin ativa **automaticamente** quando voce menciona termos relacionados ao Bitrix24 em qualquer conversa com o Claude Code:

- Nomes de metodos: `crm.lead.add`, `crm.deal.list`, `bizproc.workflow.start`
- Entidades: "leads", "contacts", "deals", "companies", "quotes"
- Termos tecnicos: "bitrix24", "bitrix", "BX24", "webhook", "placement"

O Claude vai consultar os arquivos de documentacao, encontrar a informacao relevante e responder com exemplos de codigo, parametros e referencias.

### Exemplos de perguntas que o plugin responde

```
"Como criar um lead no Bitrix24 via API?"
"Quais campos o crm.deal.add aceita?"
"Como configurar OAuth no Bitrix24?"
"Qual a diferenca entre crm.item.add e crm.lead.add?"
"Como usar webhooks com o Bitrix24?"
"Me mostra um exemplo de crm.contact.list com filtros"
"A API de invoices esta deprecated? Qual a alternativa?"
```

## Estrutura do projeto

```
DOCUMENTACAO_BITRIX24/
├── plugin.json                 # Manifesto do plugin
├── skills/
│   └── bitrix24-api.md         # Skill com instrucoes de navegacao
├── docs/                       # Documentacao completa (53 arquivos .md + 1 .json)
│   ├── _index.md               # Indice geral com links para todos os arquivos
│   ├── _manifest.json          # Metadados estruturados (metodos por arquivo)
│   ├── 00-overview.md          # Visao geral da API
│   ├── 01-getting-started.md   # Primeiros passos
│   ├── api-crm-*.md            # Referencia das APIs CRM
│   ├── api-*.md                # Outras APIs (bizproc, events, widgets, etc.)
│   ├── tutorials-*.md          # Tutoriais passo a passo
│   ├── settings-*.md           # Configuracao e autenticacao
│   ├── sdk-bx24-js.md          # SDK JavaScript
│   └── ...
├── CLAUDE.md                   # Instrucoes para uso local (sem plugin)
├── split_docs.py               # Script que gerou os docs a partir da fonte
└── README.md                   # Este arquivo
```

## Mapa dos arquivos de documentacao

### Primeiros passos

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `00-overview.md` | Visao geral da API REST e casos de uso | 1 |
| `01-getting-started.md` | Primeiros passos, autenticacao, error codes, limites | 9 |

### CRM — Entidades principais

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `api-crm-leads.md` | Leads: CRUD, campos, eventos, comunicacao | 36 |
| `api-crm-contacts.md` | Contatos: CRUD, eventos, formularios | 16 |
| `api-crm-contacts-fields.md` | Contatos: campos de usuario, associacoes | 18 |
| `api-crm-companies.md` | Empresas: CRUD, campos, eventos, comunicacao | 34 |
| `api-crm-deals.md` | Negocios: CRUD, contatos, eventos, produtos | 27 |
| `api-crm-deals-recurring.md` | Negocios recorrentes e campos de usuario | 24 |
| `api-crm-quote.md` | Orcamentos: CRUD, campos, eventos | 24 |
| `api-crm-status.md` | Status/Estagios: deal stages, lead statuses, historico | 11 |

### CRM — API Universal

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `api-crm-universal-items.md` | Items: CRUD generico para qualquer entidade CRM | 21 |
| `api-crm-universal-config.md` | Config: categorias, campos de usuario, tipos SPA | 35 |
| `api-crm-universal-commerce.md` | Comercio: pagamentos, pedidos, produtos, entrega | 36 |

### CRM — Timeline e Atividades

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `api-crm-timeline-activities.md` | Atividades: base, todo, binding, tipos, layout | 35 |
| `api-crm-timeline-activities-config.md` | Atividades configuraveis: estrutura e setup | 20 |
| `api-crm-timeline-logmessage.md` | Log messages, icones, logos | 15 |
| `api-crm-timeline-other.md` | Comentarios, notas, bindings, layout blocks | 29 |

### CRM — Recursos de suporte

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `api-crm-requisites.md` | Requisitos: core, enderecos, links | 26 |
| `api-crm-requisites-presets.md` | Requisitos: presets, dados bancarios, eventos | 36 |
| `api-crm-document-generator.md` | Gerador de documentos: templates, campos | 27 |
| `api-crm-currency.md` | Moedas: taxas de cambio, localizacoes | 18 |
| `api-crm-auxiliary.md` | Auxiliar: enumeracoes, multicampos, duplicatas | 22 |
| `api-crm-automation.md` | Automacao: triggers, solucoes automatizadas | 21 |
| `api-crm-misc.md` | Diversos: tipos de dados, descricoes de campos | 4 |

### CRM — APIs deprecadas

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `api-crm-outdated-invoice.md` | Invoices (deprecated): CRUD, statuses, eventos | 45 |
| `api-crm-outdated-products.md` | Produtos/Catalogo (deprecated): produtos, secoes | 41 |
| `api-crm-outdated-misc.md` | Misc (deprecated): VAT, medidas, categorias | 32 |

### Outras APIs

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `api-widgets.md` | Widgets: metodos core, tasks, user fields, IM | 47 |
| `api-widgets-crm.md` | Widgets: placements especificos do CRM | 12 |
| `api-widgets-ui.md` | Widgets UI: background workers, call cards, dialogs | 41 |
| `api-bizproc.md` | Business Process: workflows, acoes, robos | 26 |
| `api-common-system.md` | Sistema: info, scopes, metodos, health checks | 27 |
| `api-biconnector.md` | BI Connector: datasets, metricas, analytics | 23 |
| `api-events.md` | Eventos: handlers, bindings, offline events | 13 |
| `api-document-generator.md` | Gerador de documentos (geral): templates, geracao | 8 |
| `api-ai.md` | AI: integracao com engine de IA, modelos | 9 |
| `api-vibe.md` | Vibe: recursos sociais | 5 |
| `api-tasks-v3.md` | Tasks v3: gerenciamento de tarefas, comentarios | 9 |
| `api-misc.md` | Endpoints diversos | 2 |

### Configuracao e autenticacao

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `settings-auth.md` | OAuth, instalacao de apps, tokens | 16 |
| `settings-api-calls.md` | Configuracao de chamadas, performance, limites | 22 |
| `sdk-bx24-js.md` | BX24 JavaScript SDK: referencia completa | 20 |
| `market-publishing.md` | Marketplace: publicacao e preparacao de apps | 16 |
| `local-integrations.md` | Integracoes locais: setup e configuracao | 9 |

### Tutoriais

| Arquivo | Descricao | Paginas |
|---------|-----------|---------|
| `tutorials-crm-add.md` | Como adicionar objetos CRM | 18 |
| `tutorials-crm-edit.md` | Como editar objetos CRM | 9 |
| `tutorials-crm-get.md` | Como buscar/listar dados CRM | 8 |
| `tutorials-crm-other.md` | Outras operacoes CRM | 8 |
| `tutorials-bizproc.md` | Automacao de business processes | 6 |
| `tutorials-tasks.md` | Gerenciamento de tarefas | 5 |
| `tutorials-other.md` | Sales, chat bots, telefonia, IA, open lines | 13 |

## Convencao de nomes dos arquivos

| Prefixo | Significado |
|---------|-------------|
| `api-crm-{entidade}.md` | Referencia de API de entidade CRM |
| `api-crm-universal-{topico}.md` | API universal CRM (funciona com qualquer entidade) |
| `api-crm-timeline-{topico}.md` | Timeline e atividades |
| `api-crm-outdated-{topico}.md` | APIs deprecadas (legacy) |
| `api-{modulo}.md` | Modulos nao-CRM |
| `tutorials-{topico}.md` | Tutoriais passo a passo |
| `settings-{topico}.md` | Configuracao e autenticacao |
| `sdk-*.md` | SDKs |

## Formato dos arquivos

Cada arquivo markdown segue esta estrutura:

```yaml
---
title: "Titulo do arquivo"
description: "Descricao do conteudo"
methods:
  - crm.lead.add
  - crm.lead.delete
  - crm.lead.get
  - crm.lead.list
  - crm.lead.update
pages: 36
---
# Titulo

> Descricao | **N paginas** | Source: apidocs.bitrix24.com

[conteudo da documentacao]
```

O frontmatter YAML permite busca programatica por metodo. O arquivo `_manifest.json` contem os mesmos metadados em formato JSON para acesso via scripts.

## Uso sem plugin (modo local)

Se preferir usar sem instalar como plugin, basta abrir o diretorio no Claude Code:

```bash
cd /caminho/para/DOCUMENTACAO_BITRIX24
claude
```

O `CLAUDE.md` na raiz do projeto instrui o Claude a navegar os docs automaticamente.

## Atualizando a documentacao

O script `split_docs.py` foi usado para gerar os arquivos a partir da documentacao oficial. Para atualizar:

1. Obtenha a documentacao atualizada de [apidocs.bitrix24.com](https://apidocs.bitrix24.com)
2. Execute o script de split para regenerar os arquivos em `docs/`
3. Verifique se novos arquivos foram criados e atualize `skills/bitrix24-api.md` se necessario

## Notas tecnicas

- **Idioma da documentacao**: Ingles (traduzido dos docs oficiais do Bitrix24)
- **API recomendada**: `crm.item.*` (universal) e a abordagem moderna para novas integracoes
- **APIs deprecadas**: arquivos com prefixo `api-crm-outdated-*` contem APIs antigas ainda usadas por codigo legado
- **Sem dependencias**: o plugin e composto apenas de arquivos markdown, nao requer runtime
