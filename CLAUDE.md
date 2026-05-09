# CLAUDE.md

## Projeto

Kogni é uma “company brain” / camada de contexto para empresas.

A missão do produto é capturar contexto de trabalho de fontes como GitHub, Slack, Drive, Jira e outras, e servir esse contexto dentro das ferramentas de IA já usadas pelo usuário, como Claude, ChatGPT, Cursor e futuros copilots.

**Posicionamento central:**

- We don’t compete with them. We feed them.
- Não queremos ser o destino principal como Glean ou Notion AI.
- Queremos ser a camada abaixo das ferramentas já usadas.
- O diferencial é aprender com o trabalho real conforme ele acontece.

## Objetivo atual

Construir a fundação do MVP com foco em:

1. landing page bonita e premium
2. autenticação
3. app shell inicial
4. modelagem de uma funcionalidade simples de contexto
5. base de código limpa e escalável

## MVP

### Escopo incluído agora

- Landing page
- Página de login / sign in / sign up
- Área autenticada inicial com sidebar e topbar
- Estrutura de workspace
- Página inicial do dashboard com estado vazio bem resolvido
- Tela simples de integrações conectáveis
- Primeira feature simples: visão de “context sources” ou “company memory overview”

### Escopo fora do MVP

Não construir ainda:

- chat proprietário completo
- RAG avançado em produção
- sistema multi-org complexo
- permissões granularíssimas
- billing
- sync em tempo real sofisticado
- workflow engine
- automações complexas
- integrações além das prioritárias
- funcionalidades para marketing/sales
- analytics avançado interno

## Público inicial

- Times de engenharia
- Empresas de tecnologia de 20 a 200 pessoas
- Brasil como mercado inicial

## Stack obrigatória

### Frontend
- Next.js (App Router)
- TypeScript
- Tailwind CSS
- shadcn/ui
- Deploy no Vercel

### Backend
- Supabase
- Postgres
- pgvector
- Supabase Auth
- Supabase Storage
- Supabase Edge Functions quando necessário

### IA
- Anthropic API (Sonnet e Haiku)
- OpenAI embeddings

### Integrações iniciais
- GitHub API
- Slack API

### Próximas integrações
- Linear
- Jira
- Notion

## Regras de implementação

### Prioridades

Priorizar nesta ordem:

1. visual premium e consistente
2. clareza de navegação
3. auth funcional
4. app shell sólido
5. estrutura de dados simples e correta
6. feature inicial pequena mas plausível
7. extensibilidade para integrações futuras

### Filosofia de produto

Sempre lembrar:

- Kogni não é um chatbot genérico.
- Kogni não é uma wiki.
- Kogni não é uma ferramenta de docs.
- Kogni é a camada de contexto por trás do trabalho.
- O produto deve parecer infraestrutura inteligente, não ferramenta de produtividade genérica.

### Filosofia de UX/UI

A interface deve ser:

- clean
- moderna
- premium
- confiante
- simples
- útil desde cedo

Evitar:

- visual genérico de dashboard SaaS barato
- excesso de cards sem hierarquia
- excesso de cores
- excesso de texto explicativo
- features falsas ou mockadas demais

### Convenções de código

- usar TypeScript estrito
- preferir server components quando fizer sentido
- usar client components apenas quando necessário
- componentes pequenos e reutilizáveis
- separar UI, domain logic e integration logic
- nomes claros e consistentes
- evitar complexidade prematura
- evitar abstrações cedo demais
- manter comentários ao mínimo

### Estrutura sugerida

- `app/` para rotas
- `components/` para UI e layout
- `lib/` para utilidades, clients e helpers
- `types/` para tipos compartilhados
- `integrations/` para conectores externos
- `supabase/` para schema e helpers

## Direção visual

Referências conceituais:

- Vercel
- Linear
- Stripe (na sensação de polish, não na estética literal)

Características:

- muito espaço em branco
- tipografia forte
- contraste elegante
- poucos acentos de cor
- bordas sutis
- dark mode preparado desde cedo
- motion leve e intencional

## Primeiras telas prioritárias

1. Landing page
2. Login
3. Dashboard shell
4. Integrations
5. Context overview

## Como responder às tasks

Ao receber uma task, seguir este comportamento:

1. Confirmar rapidamente o que será feito
2. Limitar a implementação ao escopo pedido
3. Não expandir para funcionalidades não solicitadas
4. Reutilizar os documentos deste repositório como fonte da verdade
5. Entregar código organizado e pronto para continuar em etapas seguintes

## Estratégia para economizar tokens

- não tentar construir várias áreas ao mesmo tempo
- trabalhar tela por tela
- trabalhar fluxo por fluxo
- manter contexto dos arquivos curto e preciso
- consultar primeiro estes arquivos antes de propor arquitetura nova
- quando houver incerteza, escolher a opção mais simples que preserve evolução futura

## Primeiros pedidos ideais

Boas tasks iniciais:

- criar landing page com hero, manifesto curto, seções de produto e CTA
- criar layout de autenticação com Supabase
- criar app shell com sidebar e header
- criar página de integrações com estados connected / not connected
- criar página de contexto com lista de fontes e cards de activity

## Resultado esperado

Ao fim da primeira fase, o produto deve parecer uma base real de startup early-stage de alto nível, com estética forte, estrutura coerente e MVP claramente focado.