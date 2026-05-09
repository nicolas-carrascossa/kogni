# Architecture

## Objetivo

Definir uma arquitetura inicial simples, pragmática e compatível com um MVP rápido.

## Princípios

- começar simples
- separar claramente frontend, backend e integrações
- evitar overengineering
- preparar base para múltiplas integrações futuras
- manter o domínio de “context layer” explícito

## Stack

### Frontend
- Next.js App Router
- TypeScript
- Tailwind CSS
- shadcn/ui
- hospedagem no Vercel

### Backend / Data
- Supabase Postgres
- Supabase Auth
- Supabase Storage
- pgvector
- Edge Functions quando necessário

### IA
- Anthropic para geração
- OpenAI para embeddings

## Módulos sugeridos

### 1. Web app
Responsável por landing, auth, dashboard e páginas do produto.

### 2. Auth + workspace layer
Responsável por usuários, workspaces, memberships e controle inicial de acesso.

### 3. Integrations layer
Responsável por conectar fontes externas como GitHub e Slack.

### 4. Ingestion layer
Responsável por receber, normalizar e persistir eventos/documentos/sinais.

### 5. Context layer
Responsável por representar entidades, activity, links e memória operacional.

### 6. Retrieval/application layer
Responsável por expor esse contexto para experiências futuras dentro e fora do app.

## Arquitetura lógica inicial

```text
Next.js app
   |
   |-- Supabase Auth
   |-- Supabase DB
   |-- Supabase Storage
   |
   |-- integrations/
   |     |-- github
   |     |-- slack
   |
   |-- lib/context
   |-- lib/workspaces
   |-- lib/activity
```

## Decisões iniciais

### Multi-tenant desde o início, mas simples

Todas as entidades principais devem carregar `workspace_id`.

### Integrações modeladas como conectores

Cada integração deve ter:

- provider
- status
- credentials ou reference segura
- metadados de sync

### Ingestão orientada a eventos e artefatos

No começo, não precisa existir pipeline complexo. Basta suportar a ideia de:

- fonte conectada
- item ingerido
- activity gerada
- entidade atualizada

### Contexto como camada própria

Não tratar tudo como apenas documentos soltos. A arquitetura deve preparar espaço para:

- repositories
- channels
- projects
- documents
- people
- activity items

## Primeira entrega técnica recomendada

### Fase 1
- base Next.js
- auth Supabase
- UI shell
- tabela de workspaces
- tabela de memberships
- tabela de integrations

### Fase 2
- página de integrations
- registrar conexões mockadas ou simples
- tabela de sources
- tabela de activity_items

### Fase 3
- primeira tela de overview
- leitura de dados reais do banco
- estados vazios e loading

## O que evitar agora

- event bus complexo
- microservices
- filas sofisticadas demais
- ACL avançado
- pipelines de embeddings em tempo real muito cedo
- abstração exagerada de providers