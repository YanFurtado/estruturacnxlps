# Conexão — Landing Pages de Estruturação

Sites estáticos (HTML único por página, imagens embutidas) servidos por Nginx.

| Rota | Página |
|---|---|
| `/branding/` | CNX Branding 2 — Estruturação de Branding |
| `/conversao/` | CNX Con 3 — Estruturação de Conversão |
| `/comercial/` | CNX Comercial 3 — Estruturação Comercial |
| `/` | Índice com links para as 3 |
| `/health` | Healthcheck (retorna `ok`) |

## Rodar local

```bash
docker build -t cnx-lps .
docker run -d -p 8080:80 --name cnx-lps cnx-lps
# abrir http://localhost:8080/branding/
```

## Subir no Git

```bash
git init
git add .
git commit -m "LPs de estruturação Conexão"
git branch -M main
git remote add origin <URL-do-repositorio>
git push -u origin main
```

## Deploy

Qualquer plataforma que construa a partir do `Dockerfile` (Coolify, Easypanel, Render, Railway, Fly.io, VPS com Docker). Porta exposta: **80**.

## Editar

Cada página é um único `index.html` em `site/<rota>/`. Fontes do Google Fonts e scripts de CDN carregam pela internet; o resto está embutido no próprio arquivo.
