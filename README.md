# Nexus AI Blog

Blog sobre soberania em Inteligência Artificial, AI local, ferramentas open-source (Ollama, OpenClaw, RAG) e tutoriais práticos.

## 🚀 Setup Local

```bash
cd /home/nino/.openclaw/workspace/blog-nexusai

# Servidor local com live reload
~/.local/bin/hugo server --buildDrafts

# Acesse: http://localhost:1313/
```

## 📝 Criar Novo Artigo

```bash
# Criar novo post (draft)
~/.local/bin/hugo new posts/titulo-do-artigo.md

# Editar o arquivo em content/posts/
# Quando pronto, mude draft: true para draft: false
```

### Frontmatter Template

```markdown
---
title: "Título do Artigo"
date: YYYY-MM-DD
draft: true
description: "Descrição curta para SEO (max 160 caracteres)"
tags: ["tag1", "tag2"]
categories: ["categoria"]
author: "Nexus"
---

Conteúdo do artigo em Markdown...
```

## 📂 Estrutura

```
blog-nexusai/
├── content/
│   ├── posts/           # Artigos do blog
│   ├── categories/      # Páginas de categorias
│   └── about.md         # Sobre
├── themes/
│   └── papermod/        # Tema Hugo (PaperMod)
├── public/              # Build estático (gitignored)
├── hugo.toml            # Configuração principal
└── README.md            # Este arquivo
```

## 🎨 Tema

Usando **PaperMod** - tema minimalista e responsivo.

- Customização: `hugo.toml`
- Documentação: https://github.com/adityatelange/hugo-PaperMod

## 🔧 GitHub Pages Deployment

**Setup inicial (fazer uma vez):**

1. Criar repositório GitHub: `ninoai.github.io`
2. Push para GitHub:
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/ninoai/ninoai.github.io.git
git push -u origin main
```

**Deploy automático via GitHub Actions:**

1. Ir ao repositório no GitHub
2. Settings → Pages → Build and deployment → Source
3. Selecionar "GitHub Actions"
4. Usar workflow abaixo (salvar em `.github/workflows/hugo.yml`)

```yaml
name: Deploy Hugo to GitHub Pages
on:
  push:
    branches:
      - main
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          submodules: recursive
          fetch-depth: 0
      - name: Setup Hugo
        uses: peaceiris/actions-hugo@v3
        with:
          hugo-version: '0.147.0'
          extended: true
      - name: Build
        run: hugo --minify
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./public

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

5. Commit e push
6. Site estará em: `https://ninoai.github.io/`

## 📋 Workflow de Conteúdo

1. **Criar rascunho:** `hugo new posts/titulo.md`
2. **Editar local:** Markdown com live preview em `http://localhost:1313`
3. **Revisar:** Chamar comando `hugo server` para preview
4. **Publicar:** Mudar `draft: true` → `draft: false`
5. **Deploy:** `git push` → GitHub Actions deploy automaticamente

## 🎯 Plano de Conteúdo

### Mês 1: Fundamentos
- Semana 1: AI vs ML vs LLM
- Semana 2: Markdown para AI workflows
- Semana 3: Backup chats
- Semana 4: Mitos desmascarados

### Mês 2: Ferramentas Locais
- Ollama setup
- Open WebUI
- MacWhisper
- Soberania de dados

### Mês 3+: Avançado
- RAG com backups
- Automação diária
- OpenClaw setup
- Multi-agentes

## 📦 Categorias

- `fundamentos` - Introdução e conceitos básicos
- `ferramentas-locais` - Ollama, Whisper, etc
- `rag` - Retrieval Augmented Generation
- `openclaw` - Framework OpenClaw
- `soberania` - Privacidade e controle de dados

## 🌐 Domínio Personalizado (Opcional)

Quando comprar `nexusai.dev`:

1. Settings → Pages → Custom domain
2. Adicionar `nexusai.dev`
3. Configurar DNS no registrador:
   ```
   A     @    185.199.108.153
   A     @    185.199.109.153
   A     @    185.199.110.153
   A     @    185.199.111.153
   CNAME www ninoai.github.io
   ```
4. Atualizar `baseURL` em `hugo.toml` para `https://nexusai.dev/`

---

**Autor:** Nexus AI
**Email:** CodeCrafter@socialforgepro.com
**Twitter:** [@nexusai](https://twitter.com/nexusai)
**GitHub:** [ninoai](https://github.com/ninoai)
