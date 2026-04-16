# marlondantas-dev — Agent Behavior

> Define como o agente de IA deve se comportar ao trabalhar neste projeto.

## Contexto do Projeto

- **Domínio**: marlondantas.dev
- **Tipo**: Landing page pessoal e portfólio estático
- **Stack**: Astro, HTML, CSS puro
- **Deploy**: GitHub Pages + Cloudflare DNS
- **Estágio atual**: Fase 1 — placeholder enquanto o portfólio completo não está pronto

## Documentação Obrigatória

Antes de qualquer raciocínio de domínio, o agente deve ler:

| Fonte | Caminho | Quando |
|---|---|---|
| Índice do projeto | `docs/index.md` | Sempre primeiro |
| Processo de deploy | `docs/deploy.md` | Antes de alterar deploy ou DNS |
| Produto (negócio) | `ALuaAzul-meta-docs/01-business/products/marlondantas-dev.md` | Quando precisar de contexto de produto |
| Regras de AI | `ALuaAzul-meta-docs/06-ai/marlondantas-dev/rules.md` | Antes de decisões de comportamento |

## Princípios de Trabalho

### Simplicidade acima de tudo
- Este é um projeto pessoal em **Fase 1**. Não sugerir infraestrutura complexa.
- Preferir soluções diretas: arquivo único, CSS inline, zero dependências desnecessárias.
- Não adicionar abstrações, componentes reutilizáveis ou sistemas que não serão usados agora.

### Sem especulação
- Nunca derivar regras de negócio a partir do código.
- Se a documentação estiver ausente ou incompleta, notificar o usuário antes de continuar.
- Não assumir comportamentos não documentados.

### Escopo restrito
- O único consumidor é o próprio dono — não otimizar para escala ou múltiplos usuários.
- Mudanças de deploy e DNS devem seguir `docs/deploy.md` à risca.

## Restrições Técnicas

- **Não usar SSR** — o projeto é 100% estático, gerado via `astro build`.
- **Não adicionar frameworks de UI** (React, Vue, etc.) sem solicitação explícita.
- **Não modificar `astro.config.mjs`** sem verificar impacto no deploy do GitHub Pages.
- **Não alterar o CNAME** em `public/CNAME` — ele aponta para `marlondantas.dev` via Cloudflare.

## Fluxo de Deploy

```
git push → GitHub Actions → astro build → GitHub Pages → Cloudflare DNS → marlondantas.dev
```

Qualquer alteração que afete esse fluxo deve ser revisada em `docs/deploy.md` primeiro.

## O que NÃO fazer

- Não criar arquivos de documentação extras além dos listados em `docs/index.md` sem atualizar o índice.
- Não instalar dependências sem justificativa clara.
- Não sugerir migração de stack (ex.: Next.js, Vite) — Astro é a escolha definitiva para este projeto.
- Não criar backends, APIs ou banco de dados — o projeto é e deve permanecer estático.
