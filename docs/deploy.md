# Deploy — marlondantas.dev

> Documentação do processo de deploy: GitHub Pages + Cloudflare DNS + HTTPS.

## Stack de Deploy

- **Hospedagem**: GitHub Pages
- **Build**: Astro (output estático em `dist/`)
- **CI/CD**: GitHub Actions (`.github/workflows/deploy.yml`)
- **DNS**: Cloudflare
- **Domínio**: `marlondantas.dev`

---

## GitHub Actions

O workflow em `.github/workflows/deploy.yml` roda automaticamente a cada push na branch `main`:

1. Faz checkout do código
2. Instala dependências com `npm ci`
3. Roda `npm run build` (gera `dist/`)
4. Publica o `dist/` no GitHub Pages

**Configuração necessária no repositório:**
- Settings → Pages → Source: **GitHub Actions**

---

## Cloudflare DNS

Registros configurados no painel do Cloudflare:

| Type | Name | Content | Proxy |
|------|------|---------|-------|
| A | `marlondantas.dev` | `185.199.108.153` | DNS only |
| A | `marlondantas.dev` | `185.199.109.153` | DNS only |
| A | `marlondantas.dev` | `185.199.110.153` | DNS only |
| A | `marlondantas.dev` | `185.199.111.153` | DNS only |
| CNAME | `www` | `marlondantas.github.io` | DNS only |

> Os registros A devem ficar como **DNS only** (nuvem cinza). O proxy ativo (nuvem laranja) impede a verificação do certificado pelo GitHub.

---

## Domínio Customizado no GitHub

- Settings → Pages → Custom domain → `marlondantas.dev` → Save
- O GitHub verifica o DNS e emite o certificado automaticamente
- Após verificação, ativar **Enforce HTTPS**

O arquivo `public/CNAME` com o conteúdo `marlondantas.dev` garante que o domínio não seja removido a cada novo deploy.

---

## HTTPS

O certificado é emitido pelo GitHub via Let's Encrypt e cobre `marlondantas.dev`.

**Atenção:** acessar via `www.marlondantas.dev` resulta em erro de certificado (`ERR_CERT_COMMON_NAME_INVALID`) pois o certificado cobre apenas o apex. O domínio correto é sempre `https://marlondantas.dev`.

---

## Resumo do Fluxo

```
push na main
  → GitHub Actions build
    → dist/ publicado no GitHub Pages
      → acessível em https://marlondantas.dev
```
