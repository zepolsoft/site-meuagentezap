# site-meuagentezap

Página de vendas do **Kit Meu Agente Zap** (meuagentezap.com).
Site estático (HTML puro) servido por Nginx em Docker, publicado na VPS da Hostinger via EasyPanel.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | Página de vendas (venda direta pela Hotmart) |
| `termos.html` | Termos de uso |
| `privacidade.html` | Política de privacidade (LGPD) |
| `capa.jpg` | Imagem de prévia ao compartilhar o link (1200×630) |
| `favicon.png` | Ícone da aba do navegador |
| `Dockerfile` | Nginx servindo os arquivos |

## Pendências antes de anunciar

- [ ] Trocar `[SEU CNPJ]` em `index.html`, `termos.html` e `privacidade.html`
- [ ] Criar o pixel da Meta, trocar `SEU_PIXEL_ID` e descomentar o bloco no `<head>` do `index.html`

## Deploy (EasyPanel)

1. EasyPanel → Projeto → **+ Service → App** → nome `meuagentezap`
2. Source: **GitHub** → `zepolsoft/site-meuagentezap`, branch `main`
3. Build: **Dockerfile**
4. Domains: adicionar `meuagentezap.com` e `www.meuagentezap.com`, porta **80**, HTTPS ligado
5. Deploy

## DNS (Hostinger → Domínios → meuagentezap.com → DNS)

| Tipo | Nome | Valor |
|---|---|---|
| A | `@` | IP da VPS |
| CNAME | `www` | `meuagentezap.com` |

Remova registros A/CNAME antigos de `@` e `www` que apontem para a hospedagem padrão da Hostinger.
A propagação costuma levar de alguns minutos a algumas horas.
