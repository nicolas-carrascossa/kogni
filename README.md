# Kogni

Kogni é uma camada de contexto para empresas. Em vez de tentar substituir as ferramentas de IA que as pessoas já usam, o produto injeta o contexto certo dentro de ferramentas como ChatGPT, Claude, Cursor e outras.

**Frase de posicionamento:** “We don’t compete with them. We feed them.”

## Tese

Hoje, times repetem o mesmo contexto várias vezes em diferentes ferramentas: PRDs em Notion, discussões no Slack, código no GitHub, tarefas no Jira, arquivos no Drive e prompts manuais em copilots. Isso gera perda de tempo, respostas inconsistentes e baixa memória organizacional.

A proposta da Kogni é:

- Ingerir contexto de ferramentas de trabalho uma vez.
- Estruturar esse contexto em uma camada própria.
- Entregar o contexto certo no momento certo, dentro da interface de IA que o usuário já prefere.
- Aprender continuamente com o trabalho real conforme PRs, issues, campanhas e decisões acontecem.

## Usuário inicial

Segmento inicial:

- Times de engenharia
- Empresas de tecnologia com 20 a 200 pessoas
- Foco geográfico inicial: Brasil

Expansão futura:

- Marketing
- Vendas
- Outras funções cross-functional

## Estágio atual

- Startup em fase muito inicial
- Ideia começou há cerca de 1 semana
- Ainda sem MVP
- Ainda sem usuários
- Conversas iniciais com devs e pequenas empresas já aconteceram

## Objetivo imediato

Montar uma base clara para começar a usar Claude Code de forma eficiente, com contexto bem estruturado e baixo desperdício de tokens.

Escopo da primeira fase:

1. Landing page / homepage
2. Login / autenticação
3. Shell inicial da aplicação web
4. Primeira modelagem de funcionalidade simples
5. Base visual premium e consistente

## Stack planejada

### Frontend
- Next.js
- Tailwind CSS
- shadcn/ui
- Vercel
- TypeScript

### Backend / Infra
- Supabase
- Postgres
- pgvector
- Auth
- Storage
- Edge Functions

### IA
- Anthropic API (Sonnet + Haiku)
- OpenAI embeddings

### Integrações iniciais
- GitHub API
- Slack API

### Próximas integrações
- Linear
- Jira
- Notion

### Ferramentas de desenvolvimento
- Claude Code
- Cursor
- GitHub

### Analytics
- PostHog free

## Estrutura sugerida do repositório

```text
.
├── README.md
├── CLAUDE.md
├── .env.example
├── product/
│   ├── brief.md
│   └── user-flows.md
├── design/
│   └── ui-standards.md
├── docs/
│   ├── architecture.md
│   └── data-model.md
└── supabase/
    └── schema.sql
```

## Como usar este pacote com Claude Code

Ordem recomendada:

1. Ler `README.md`
2. Ler `CLAUDE.md`
3. Ler `product/brief.md`
4. Ler `design/ui-standards.md`
5. Ler `product/user-flows.md`
6. Ler `docs/architecture.md`
7. Ler `docs/data-model.md`
8. Ler `supabase/schema.sql`

Depois disso, pedir implementações em etapas pequenas.

## Estratégia de prompting

Evitar prompts como:

- “construa o produto inteiro”
- “faça toda a plataforma”
- “implemente tudo do MVP”

Preferir pedidos pequenos e sequenciais:

1. Criar landing page com hero, prova social e CTA
2. Implementar autenticação com Supabase
3. Criar app shell autenticado
4. Criar página de conexões/integrations
5. Criar primeira visão de contexto por repositório ou workspace

## O que não construir ainda

- Agente autônomo complexo
- Memory engine completo multi-tenant com feedback loop sofisticado
- Permissões empresariais avançadas
- Billing
- Admin complexo
- Busca universal perfeita
- Integrações demais ao mesmo tempo
- Sistema completo para marketing e vendas

## Princípio de produto

A Kogni não quer ser mais uma interface de destino. Ela quer ser a infraestrutura de contexto que torna outras interfaces mais inteligentes.