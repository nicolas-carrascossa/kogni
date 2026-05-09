# Data Model

## Objetivo

Ter um schema inicial pequeno, mas que represente bem a estrutura base do produto.

## Entidades principais

### users
Gerenciados prioritariamente por Supabase Auth.

### workspaces
Representam a empresa ou time.

Campos sugeridos:

- id
- name
- slug
- created_at

### memberships
Ligam usuários a workspaces.

Campos sugeridos:

- id
- workspace_id
- user_id
- role
- created_at

### integrations
Representam conexões com provedores externos.

Campos sugeridos:

- id
- workspace_id
- provider
- status
- connected_by
- connected_at
- last_synced_at
- metadata jsonb
- created_at

### sources
Representam unidades principais de contexto vindas de integrações.

Exemplos:

- repositório GitHub
- canal Slack
- projeto no Jira
- documento no Notion

Campos sugeridos:

- id
- workspace_id
- integration_id
- source_type
- external_id
- name
- status
- metadata jsonb
- last_ingested_at
- created_at

### activity_items
Representam eventos ou mudanças recentes.

Exemplos:

- PR merged
- issue criada
- canal atualizado
- documento modificado

Campos sugeridos:

- id
- workspace_id
- source_id
- actor_name
- event_type
- title
- summary
- happened_at
- metadata jsonb
- created_at

### entities
Representam objetos canônicos importantes para o brain.

Exemplos:

- repository
- project
- person
- document

Campos sugeridos:

- id
- workspace_id
- entity_type
- name
- external_ref
- metadata jsonb
- created_at
- updated_at

### document_chunks (futuro próximo)
Base para embeddings e retrieval.

Campos sugeridos:

- id
- workspace_id
- entity_id
- content
- embedding vector
- metadata jsonb
- created_at

## Relações importantes

- um workspace tem muitos memberships
- um workspace tem muitas integrations
- uma integration tem muitas sources
- uma source tem muitos activity_items
- um workspace tem muitas entities

## Princípios de modelagem

- usar `workspace_id` em tudo que for multi-tenant
- preferir `jsonb` para metadados variáveis de providers
- manter tipos explícitos como `provider`, `source_type` e `event_type`
- não tentar normalizar demais cedo
- preservar flexibilidade para conectores futuros