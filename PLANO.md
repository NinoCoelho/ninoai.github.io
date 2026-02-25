# 📋 Plano de Postagens - Nexus AI

## Workflow de Status
- **[D]** Draft - Rascunho inicial
- **[A]** Aprovado - Pronto para publicar
- **[R]** Revisar - Precisa ajustes
- **[P]** Publicado - No ar

---

## Mês 1: Fundamentos de AI

### Semana 1: IA vs ML vs LLM ✅ CONCLUÍDO

- [x] Post Draft criado: "IA vs ML vs LLM - Guia Completo"
- [x] Imagens geradas (3): hierarchy, cloud-vs-local, demo
- [x] Tweets criados (3): IA, IA vs ML, O que é LLM
- [x] Template.md criado com regras de estilo
- [ ] **Aprovação do Nino** - Post revisado e tweets aprovados?
- [ ] Mover para [P] publicado após aprovação
- [ ] Postar tweets via xurl

**Tema Focado:** Terminologia e hierarquia (superficial mas necessário)

---

### Semana 1b: Cloud vs Local AI (Novo Post Separado)

- [ ] Post: "Cloud vs Local AI: Trade-Offs Completos e Quando Usar Cada Um"
- [ ] Imagens: comparação arquitetura, custo, privacidade
- [ ] Tweets (3): Arquitetura, trade-offs, quando usar
- [ ] **Tema Profundo:** Análise comparativa de custos/risco

**Conteúdo detalhado:**
- Arquitetura técnica: onde dados são armazenados
- Custo realista: hardware vs API (TCO 3 anos)
- Segurança: ataque vetorial, modelo poisoning
- Compliance: GDPR, LGPD, HIPAA (quando usar cada)
- Performance: latência, throughput, context window
- Híbrido: cloud para treinamento, local para inferência
- Casos de uso: empresarial, pessoal, sensível
- Tabela decisão: quando usar cloud vs local
- Exemplo real: migrar startup de GPT-4 para Llama 3.1

---

### Semana 1c: Code Assist Local com Histórico (Ferramentas CLI e IDEs)

- [ ] Post: "Code Assist Local com Histórico: Continue, Aider, Cursor vs Claude Code"
- [ ] Imagens: screenshots IDEs, fluxo de trabalho, comparação features
- [ ] Tweets (3): O que é code assist, ferramentas, destaque Claude Code
- [ ] **Tema Profundo:** Ferramentas CLI/IDEs com histórico e contexto

**Conteúdo detalhado:**
- O que é code assist (diferença vs copilot)
- **Ferramentas CLI:** Continue, Aider (CLI-first)
- **Ferramentas IDE:** Cursor, Cline, VS Code plugins
- Claude Code (Anthropic): líder em qualidade, context window massivo
- Setup local: instalação, configuração, modelos suportados (Ollama, OpenAI)
- Integração com histórico: chats anteriores, projeto completo, arquivos recentes
- Comparação de features: context window, suporte a multi-file, diff quality
- Casos de uso: refatoração, debugging, geração de código
- Benchmarks de qualidade: HumanEval, MBPP, code quality
- Custo: grátis local vs Claude Code pago
- Quando usar cada ferramenta: por projeto, por tipo de código, por team size

---

### Semana 2: Markdown > DOCX

- [ ] Post: "Markdown > DOCX: Por que MD é o Futuro da AI"
- [ ] Imagens: fluxo de trabalho MD, comparação visual, exemplos
- [ ] Tweets (3): Por que MD > DOCX, Git versionamento, renderização
- [ ] **Tema Profundo:** Como MD habilita AI-first workflows

**Conteúdo detalhado:**
- Por que MD superior para AI prompts
- Git versionamento de prompts vs arquivos binários
- Ferramentas: Obsidian, Typora, VS Code plugins
- Renderização instantânea: Hugo, Jekyll, Astro
- Exemplos práticos de code blocks formatados
- Integração com LLMs (prompt = MD file)
- Comparação: DOCX (binário, lento) vs MD (texto, rápido)
- Workflow real: editar MD → preview instantâneo → commit

---

### Semana 3: Backups de Chats

- [ ] Post: "Backup seus Chats: Nunca Perca Conhecimento em 3 Passos"
- [ ] Imagens: Screenshots de processo, fluxo RAG, scripts
- [ ] Tweets (3): Exportar ChatGPT, Backup Claude, Evite perda de knowledge
- [ ] **Tema Profundo:** Soberania de dados e RAG

**Conteúdo detalhado:**
- Exportação ChatGPT (Account Settings → Data export)
- Workaround para Claude (screen scrape, browser extensions)
- Parse JSON/HTML para formato estruturado
- Indexar com RAG (Ollama + embeddings)
- Ferramentas: Memory Forge, ChatGPT Exporter
- Scripts Python para merge múltiplos exports
- Armazenamento: local vs cloud criptografado
- Caso real: migrar anos de conversas para RAG local
- Benefícios: busca semântica em toda sua história

---

### Semana 4: Mitos Desmascarados

- [ ] Post: "20 Mitos sobre IA Local: Verdades e Mentiras"
- [ ] Imagens: Checklist visual, comparações factuais, gráficos
- [ ] Tweets (3): "AI é perigosa?", "AI rouba empregos?", "IA local é lenta?"
- [ ] **Tema Profundo:** Desmistificação de medos e preocupações

**Conteúdo detalhado:**
- Mito 1: "AI é perigosa e incontrolável" → Verdade: Controle é maior em local
- Mito 2: "AI vai roubar empregos" → Verdade: AI como ferramenta, não substituto
- Mito 3: "AI local é lenta e fraca" → Verdade: Llama 3.2 compete com GPT-4
- Mito 4: "Precisa de supercomputador" → Verdade: MacBook Pro 2020 roda Llama 3.2
- Mito 5: "Modelos open-source são inferiores" → Verdade: Mistral, Gemma superam GPT-3.5
- Dados científicos e benchmarks
- Cenários reais de uso empresarial
- Riscos reais vs medos imaginados
- Guia para conversar com céticos

---

## Mês 2: Ferramentas Locais Básicas

### Semana 5: Ollama + Ferramentas Locais Completo

- [ ] Post: "Ollama + Ecosistema: Chat Local, RAG e Code Assist"
- [ ] Imagens: diagrama ecosistema, setup interfaces, fluxo RAG
- [ ] Tweets (3): Ollama install, ferramentas de chat, setup completo
- [ ] **Tema Profundo:** Ecosistema completo de AI local

**Conteúdo detalhado:**
- Instalação Mac/Linux/Windows (curl, brew, winget)
- Arquitetura Ollama: quantização, GGUF, CPU vs GPU vs MPS
- **Ferramentas de Chat Locais:**
  - Open WebUI: interface tipo ChatGPT, suporte a múltiplos modelos
  - text-generation-webui: opções avançadas, extensões
  - Ollama Python/Go API: integração com seus scripts
- **RAG Local:**
  - Vector databases: ChromaDB (simples), Qdrant (escalável), Weaviate (feature-rich)
  - Chunking strategies: fixed-size, semantic, recursive splitting
  - Código Python para setup RAG básico com LangChain
  - Hybrid search: vector + keyword (BM25)
- **Modelos e Performance:**
  - Llama 3.1, 3.2, Mixtral, Qwen, Gemma
  - Tamanhos: 1B, 3B, 7B, 8B, 70B
  - Quantização: Q4, Q5, Q8 trade-offs (memória vs precisão)
  - Context window: 4k, 8k, 32k, 128k (quando usar)
- **Comandos avançados:** `ollama show`, `ollama run --num-gpu`, `--temperature`
- **Casos de uso real:** coding, chat, análise de documentos
- **Troubleshooting comum:** OOM, slow inference, temperatura alta

---

### Semana 6: Open WebUI

- [ ] Post: "Open WebUI: Interface ChatGPT Local com RAG e Plugins"
- [ ] Imagens: screenshots, UI features, RAG workflow
- [ ] Tweets (3): Setup, upload documentos, plugins
- [ ] **Tema Profundo:** RAG local e personalização

**Conteúdo detalhado:**
- Docker setup one-liner
- Configuração de modelos (Hugging Face, GGUF local)
- RAG integration: upload documentos, chunking strategies
- Plugins: web search, image generation, code interpreter
- Customização: temas, prompts do sistema, modos de chat
- Multi-user support: RBAC, histórico separado
- Performance: GPU acceleration, quantization, caching
- Casos de uso: equipe, pessoal, servidor
- Comparação vs ChatGPT UI

---

### Semana 7: MacWhisper

- [ ] Post: "MacWhisper: Transcrição de Áudio Local com Precisão Humana"
- [ ] Imagens: interface, benchmark, workflow completo
- [ ] Tweets (3): Setup, precisão, automação
- [ ] **Tema Profundo:** Integrações e automação

**Conteúdo detalhado:**
- Instalação: App Store vs command line
- Modelos: tiny, base, small, medium, large (trade-offs)
- Benchmark: WER (Word Error Rate) vs OpenAI Whisper
- Batch processing: múltiplos arquivos automaticamente
- Formatos: MP3, WAV, M4A, MKV
- Integração DaVinci Resolve (subtítulos automáticos)
- Timestamps e segmentação
- Idiomas suportados e multilíngue
- Scripts Python para automação de pipeline
- Casos reais: podcasts, reuniões, vídeos

---

### Semana 8: Soberania de Dados Básica

- [ ] Post: "Soberania de Dados: Conceitos Básicos e Checklist Prático"
- [ ] Imagens: diagrama soberania, checklist, fluxo de controle
- [ ] Tweets (3): O que é soberania, data portability, encryption
- [ ] **Tema Profundo:** Teoria de soberania digital

**Conteúdo detalhado:**
- Definição: o que é data sovereignty
- Vetores de soberania: infraestrutura, dados, identidade
- Framework legal: GDPR, LGPD, CCPA
- Criptografia: GPG, VeraCrypt, LUKS
- Self-hosting: Nextcloud, Syncthing
- Backup 3-2-1: 3 cópias, 2 mídias, 1 offsite
- Portability: formatos abertos (MD, JSON, CSV)
- Identidade digital: passkeys, 2FA, hardware keys
- Auditoria: como verificar que seus dados não saíram

---

## Mês 3: Avançado - RAG e Automação

### Semana 9: RAG Completo

- [ ] Post: "RAG Completo: AI Respondendo com SEUS Dados (Código Incluído)"
- [ ] Imagens: arquitetura RAG, fluxo pipeline, resultados
- [ ] Tweets (3): O que é RAG, chunking strategies, embeddings
- [ ] **Tema Profundo:** Implementação técnica avançada

**Conteúdo detalhado:**
- Arquitetura: Retrieval + Augmentation + Generation
- Embeddings: Ollama embeddings, Hugging Face sentence-transformers
- Chunking: fixed-size, semantic, recursive splitting
- Vector databases: ChromaDB, Qdrant, Weaviate
- Reranking: cohere, colbert, cross-encoder
- Código Python completo com LangChain/LlamaIndex
- Hybrid search: vector + keyword (BM25)
- Context window management: limitar e recuperar relevante
- RAG evaluation: RAGAS, faithfulness metrics
- Casos reais: documentos técnicos, chat history, código

---

### Semana 10: Automação Diária

- [ ] Post: "Automação Diária: Whisper + Ollama → Resumos Automáticos"
- [ ] Imagens: pipeline visual, workflow completo, exemplos de output
- [ ] Tweets (3): Setup, casos de uso, otimização
- [ ] **Tema Profundo:** Orquestração e escalabilidade

**Conteúdo detalhado:**
- Pipeline: gravação automática → transcrição → RAG → resumo
- Ferramentas: ffmpeg, whisper-standalone, Ollama API
- Scripts shell/Python completos
- Cron jobs: Linux/macOS launchd/Windows Task Scheduler
- Alertas: email, Telegram, Slack (OpenClaw)
- Storage: organizar por data, tags, search
- Versionamento: Git LFS para áudios, DVC para modelos
- Casos reais: reuniões, podcasts, voz mental
- Troubleshooting: silêncio, qualidade baixa, timestamps

---

## Mês 4+: OpenClaw e Multi-Agentes

### Semana 11: OpenClaw Setup VPS

- [ ] Post: "OpenClaw Setup VPS: Seu Agente 24/7 (Tutorial Completo)"
- [ ] Imagens: setup passo a passo, arquitetura, dashboard
- [ ] Tweets (3): VPS benefits, skills, uptime
- [ ] **Tema Profundo:** DevOps e operacionalização

**Conteúdo detalhado:**
- Escolha de VPS: AWS EC2, DigitalOcean, Hetzner
- OS: Ubuntu 22.04 LTS vs Debian 12
- Docker vs bare metal: trade-offs
- OpenClaw install: git clone, config, auth
- Skills disponíveis: gog (Google), weather, gh-issues
- Telegram/WhatsApp integration: setup e segurança
- HTTPS com certbot/letsencrypt
- Monitoring: Uptime Robot, custom health checks
- Backup do VPS: snapshots, rsync, restic
- Escalabilidade: múltiplos agentes, load balancing
- Casos reais: alertas automáticos, automações de negócio
- Custo: orçamento mensal realista

---

### Semana 12: Multi-Agentes

- [ ] Post: "Multi-Agentes: O Futuro da IA Local (Arquitetura e Casos)"
- [ ] Imagens: arquitetura multi-agent, orquestração, workflow
- [ ] Tweets (3): O que são multi-agentes, casos, ferramentas
- [ ] **Tema Profundo:** Teoria de agência multi-modal

**Conteúdo detalhado:**
- Arquitetura: central dispatcher, agentes especializados, orquestrador
- Comunicação: message bus (RabbitMQ, Redis streams), gRPC
- Agentes: coder, researcher, planner, executor
- Frameworks: AutoGen, LangGraph, CrewAI
- State management: shared state vs distributed
- Memória compartilhada: vector DB, Redis, PostgreSQL
- Scheduling: task queue, priority, deadlines
- Exemplo completo: agente de pesquisa (coder + scraper + analyzer)
- Human-in-the-loop: aprovação, correção, override
- Casos reais: pesquisa de mercado, análise financeira, código complexo

---

## Status Global

**Mês Atual**: 1
**Semana Atual**: 1
**Progresso**: 1/12 semanas (8%)

**Próxima Data-Alvo**: Semana 1b post (Cloud vs Local)

---

## Métricas de Sucesso

### Por Post
- [ ] Foco em UM tema (não misturar)
- [ ] Detalhamento técnico aprofundado
- [ ] Exemplos práticos funcionais
- [ ] Código testado e replicável
- [ ] Emojis moderados (max ~10)
- [ ] Imagens relevantes e não redundantes
- [ ] CTA específico (próximo artigo definido)

### Por Mês
- [ ] 4 posts publicados (1/semana)
- [ ] 12 tweets gerados (3/post)
- [ ] 4-8 imagens criadas
- [ ] Feedback recebido do público
- [ ] Métricas: engajamento, cliques, tempo de leitura

---

## Estrutura de Pastas

```
content/stages/
├── draft/       # [D] Rascunhos iniciais
├── aprovar/     # [A] Aprovado por Nino
├── revisar/     # [R] Precisa de ajustes
└── publicado/   # [P] No ar

static/images/
└── /nome-do-post/
    ├── img1.png
    ├── img2.png
    └── img3.png

tweets/
└── nome-do-post.md
```

---

## Última Atualização

**Data**: 2026-01-06
**Alterações**:
- Revisão completa do PLANO com temas profundos por semana
- Adicionadas Semanas 1b, 1c (Cloud vs Local, Code Assist)
- Cada semana agora tem "Tema Profundo" específico
- Detalhamento do conteúdo técnico em cada post
- Métricas de sucesso definidas
- Estrutura de pastas documentada
- TEMPLATE.md criado com regras de estilo

---

## Notas Importantes

### Foco Didático
- Ensinar, não vender
- Exemplos antes da teoria
- Transições naturais entre seções
- Um tema por post (não misturar conceitos)

### Profundidade Técnica
- Cada post tem "Tema Profundo" específico
- Conteúdo detalhado: arquiteturas, implementações, benchmarks
- Casos reais de uso
- Código funcional e testado
- Troubleshooting comum

### Qualidade Visual
- Imagens geradas com Nano Banana Pro
- Diagramas técnicos (hierarquia, arquitetura, fluxo)
- Screenshots reais quando aplicável
- Legenda explicativa (não redundante com texto)
