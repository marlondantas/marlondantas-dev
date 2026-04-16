# marlondantas.dev

Landing page pessoal e portfólio de Marlon Dantas, acessível em [marlondantas.dev](https://marlondantas.dev).

## Stack

- [Astro](https://astro.build) — geração estática
- CSS puro — sem frameworks de estilo
- GitHub Pages — hospedagem
- Cloudflare — DNS

## Desenvolvimento

```bash
npm install
npm run dev
```

## Deploy

Push na branch `master` dispara o workflow do GitHub Actions que faz o build e publica automaticamente no GitHub Pages.

```
push → GitHub Actions → dist/ → GitHub Pages → marlondantas.dev
```

Detalhes de DNS e configuração em [`docs/deploy.md`](docs/deploy.md).
