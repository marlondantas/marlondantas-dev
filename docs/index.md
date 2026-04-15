# marlondantas-dev — Docs Index

> Landing page pessoal e portfólio para o domínio marlondantas.dev

## Sobre o Projeto

Landing page estática construída com Astro, publicada no GitHub Pages com domínio personalizado `marlondantas.dev` via Cloudflare.

## Arquivos de Documentação

| Arquivo | Descrição | Quando ler |
|---|---|---|
| `docs/index.md` | Este arquivo — mapa de navegação | Sempre primeiro |
| `docs/deploy.md` | Processo de deploy, GitHub Pages e Cloudflare DNS | Antes de qualquer alteração de deploy |

## Estrutura do Projeto

```
marlondantas-dev/
├── src/
│   └── pages/
│       └── index.astro     # Página principal
├── public/                  # Assets estáticos
├── astro.config.mjs         # Configuração do Astro
├── package.json
└── docs/
    └── index.md             # Este arquivo
```

## Stack

- **Framework**: Astro (geração estática)
- **Estilos**: CSS puro
- **Deploy**: GitHub Pages
- **DNS**: Cloudflare → marlondantas.dev

## Estágio Atual

**Fase 1 — Em Construção**: Página placeholder para validar DNS e domínio antes de desenvolver o portfólio completo.
