# Product Brief

## One-liner

Kogni é a camada de contexto da empresa: conecta fontes de trabalho, organiza memória operacional e entrega o contexto certo dentro das ferramentas de IA já usadas pelo time.

## Problema

Equipes repetem constantemente o mesmo contexto em múltiplas ferramentas.

Exemplos:

- um dev explica a arquitetura para o Cursor
- depois reexplica o roadmap para o ChatGPT
- depois resume decisões do Slack para o Claude
- depois precisa reconstruir contexto de PRs, tickets e docs manualmente

Isso gera:

- desperdício de tempo
- respostas de IA inconsistentes
- dependência de contexto manual
- perda de memória institucional
- baixa qualidade no uso de copilots

## Insight

O problema não é só busca. O problema é contexto operacional vivo.

Ferramentas como Glean ou Notion AI ajudam a ler conhecimento existente, mas muitas vezes funcionam como camadas mais passivas. A oportunidade da Kogni é aprender com o trabalho real conforme o trabalho acontece.

## Solução

A Kogni cria uma camada contínua de contexto empresarial que:

1. ingere sinais de ferramentas como GitHub, Slack e depois Jira/Linear/Notion
2. organiza entidades, relações e atividade recente
3. permite que esse contexto seja consultado ou servido em interfaces de IA
4. atualiza o brain automaticamente com novos eventos relevantes

## Diferencial

### Não ser o destino

A Kogni não quer substituir ChatGPT, Claude ou Cursor. Ela quer alimentá-los.

### Aprender com o trabalho real

Não só indexar docs estáticos, mas absorver mudanças reais como:

- PRs abertos e merged
- discussões relevantes
- decisões técnicas
- criação de tickets
- mudanças em projetos e repositórios

### Fechar o loop

O sistema deve melhorar seu contexto com o uso e com os eventos do time, em vez de depender apenas de ingestões manuais.

## Usuário inicial

### ICP inicial

- startup ou empresa de software de 20–200 pessoas
- time de engenharia como comprador e primeiro usuário forte
- CTO, engineering managers e devs como stakeholders iniciais

### Mercado inicial

- Brasil
- empresas tecnológicas
- times enxutos com alta dependência de velocidade e contexto

## Casos de uso iniciais

- entender rapidamente o contexto de um repositório
- resumir o que mudou recentemente em um projeto
- encontrar contexto operacional antes de pedir algo à IA
- conectar fontes centrais de engenharia
- visualizar o estado da memória da empresa

## MVP proposto

### Objetivo do MVP

Mostrar de forma concreta que existe valor em centralizar sinais de contexto e apresentá-los de forma útil para times de engenharia.

### Componentes do MVP

- landing page com narrativa forte
- auth básica
- dashboard shell autenticado
- onboarding simples de workspace
- conexões iniciais de integrações
- página de overview do company brain
- visualização simples de activity / source health / recent context

### O que o MVP ainda não precisa provar

- qualidade final de respostas de IA em produção
- cobertura total de integrações
- automação sofisticada
- recomendação perfeita de contexto
- workflows avançados entre áreas

## Mensagem principal

Kogni é a infraestrutura que transforma contexto disperso em contexto utilizável dentro das ferramentas de IA onde o trabalho já acontece.