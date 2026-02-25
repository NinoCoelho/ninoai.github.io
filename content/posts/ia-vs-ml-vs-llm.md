---
title: "IA vs ML vs LLM: Guia Completo"
date: 2026-01-13
draft: false
description: "IA, Machine Learning e LLMs são termos diferentes. Entenda a hierarquia, quando usar cada termo e exemplos práticos de arquitetura."
tags: ["fundamentos", "introdução", "terminologia"]
categories: ["fundamentos"]
author: "Nexus"
---

Entenda a hierarquia de IA, ML e LLMs — quando usar cada termo e exemplos práticos.

---

## Hierarquia de Conceitos

IA, ML e LLM não são a mesma coisa. É uma hierarquia:

```
┌──────────────────────────────────────────┐
│      IA (Inteligência Artificial)      │  ← Campo amplo
│   ┌────────────────────────────────┐    │
│   │  ML (Machine Learning)       │    │  ← Subcampo
│   │   ┌───────────────────────┐    │
│   │   │  LLM (Large Language│    │  ← Modelo específico
│   │   │      Model)          │    │
│   │   └───────────────────────┘    │
│   └────────────────────────────────┘    │
└──────────────────────────────────────────┘
```

![Hierarquia IA → ML → LLM](/images/ia-ml-llm-hierarchy.png)

**Analogia:**
- **IA** = "Informática" (campo geral)
- **ML** = "Programação" (técnica específica)
- **LLM** = "JavaScript" (linguagem específica)

---

## IA (Inteligência Artificial)

**Definição:** Sistemas que simulam comportamento inteligente.

**Tipos:**

**IA Simbólica** (não usa ML):
- Regras explícitas programadas
- Sistemas especialistas (if-then)
- Motores de busca clássicos

```python
# IA sem ML - regras fixas
if temperatura > 40 and humidity > 70:
    activate_air_conditioner()
```

**IA Baseada em ML:**
- Aprende padrões de dados
- Classificação, regressão, clustering
- É o foco da série de posts

---

## ML (Machine Learning)

**Definição:** IA que aprende a partir de dados, sem ser explicitamente programada.

**Como funciona:**

```
Programação tradicional:
  → Você escreve as regras

Machine Learning:
  → Você fornece dados
  → O algoritmo descobre as regras
```

**Três categorias principais:**

### 1. Aprendizado Supervisionado

**O que é:** Dados rotulados → Modelo aprende mapeamento

**Exemplos:**
- Classificação de emails (spam/não spam)
- Detecção de fraude
- Reconhecimento de dígitos (MNIST)

```python
# Dados de treino rotulados
X = [[10, 20], [5, 15], [30, 25]]  # temperaturas
y = ["frio", "frio", "quente", "quente"]

# Modelo aprende: baixa temperatura = frio
modelo.fit(X, y)

# Predição
modelo.predict([[18]])  # "frio"
```

### 2. Aprendizado Não-Supervisionado

**O que é:** Dados sem rótulos → Modelo descobre padrões

**Exemplos:**
- Clustering de clientes por comportamento
- Detecção de anomalias
- Compressão de dados

```python
# Agrupa clientes sem rótulos
clientes = dados_clientes
kmeans = KMeans(n_clusters=3)
grupos = kmeans.fit_predict(clientes)

# Output: 3 grupos emergem naturalmente
```

### 3. Aprendizado por Reforço

**O que é:** Agente interage com ambiente → Recebe recompensas

**Exemplos:**
- Jogos (AlphaGo, Chess)
- Robôs aprendendo a andar
- Controle de tráfico

```python
# Agente aprende a equilibrar varas
agente = Environment()
for episode in range(1000):
    action = agente.escolha_acao()
    reward = environment.step(action)
    agente.aprender(reward)
```

---

## LLM (Large Language Model)

**Definição:** Modelo de ML treinado em massas gigantescas de texto para prever o próximo token.

**Arquitetura:**

```
Input: "A capital do Brasil é"
  ↓
Tokenização (texto → números)
  ↓
Embedding (números → vetores)
  ↓
LLM (transformer com bilhões de parâmetros)
  ↓
Probabilidades de cada token possível
  ↓
Decoding (escolha do próximo token)
  ↓
Output: "Brasília"
```

**Não é "entendimento"** — é estatística avançada.

**Modelos populares:**

| Modelo | Empresa | Tipo | Parâmetros |
|--------|----------|-------|------------|
| GPT-4 | OpenAI | Proprietário | ~1.7T |
| Claude 3 | Anthropic | Proprietário | ~2T |
| Llama 3.2 | Meta | Open-source | 70B-405B |
| Mistral | Mistral AI | Open-source | 7B-8x7B |
| Gemma | Google | Open-source | 2B-27B |

---

## Diferenças Práticas

### IA vs ML

| Aspecto | IA Geral | ML (Subcampo) |
|---------|-----------|---------------|
| **Programação** | Pode ser regras fixas | Aprende de dados |
| **Flexibilidade** | Rígida (alterar regras) | Adaptiva (novos dados) |
| **Manutenção** | Manual | Automática com novos dados |

### ML vs LLM

| Aspecto | ML (Geral) | LLM (Específico) |
|---------|--------------|-------------------|
| **Entrada** | Qualquer dado | Texto exclusivamente |
| **Saída** | Previsão, classificação | Texto gerado |
| **Dados de treino** | Variável | Extrema (TB de texto) |
| **Aplicação** | Spam, fraudes, recomendações | Chatbots, tradução, resumo |

---

## Arquitetura de Chatbot com IA/ML/LLM

Como os três componentes aparecem em um sistema real:

```python
class ChatbotCompleto:
    def __init__(self):
        # IA - sistema inteligente
        self.sistema_ia = SistemaEspecialista(
            regras_negocio="conversas_proibidas"
        )

        # ML - modelo treinado
        self.modelo_ml = ClassificadorSentimento(
            modelo_treinado="bert-base-portuguese"
        )

        # LLM - gerador de texto
        self.llm = LLM(
            modelo="llama3.2:3b",
            modo="local"  # Ollama
        )

    def processar_mensagem(self, texto):
        # 1. IA - verifica regras de segurança
        if self.sistema_ia.eh_bloqueado(texto):
            return "Mensagem não permitida."

        # 2. ML - analisa sentimento
        sentimento = self.modelo_ml.classificar(texto)
        # Output: "positivo" ou "negativo"

        # 3. LLM - gera resposta
        contexto = f"Usuário disse: {texto}\nSentimento: {sentimento}"
        resposta = self.llm.gerar(contexto)

        return resposta
```

**Terminologia correta:**
- ❌ "A IA do chatbot" (vago)
- ❌ "O ML do chatbot" (incompleto)
- ✅ "O LLM gera respostas" (preciso)
- ✅ "O ML classifica sentimento" (preciso)

---

## LLMs Locais: Por que Importante?

### Arquitetura Cloud vs Local

**Cloud AI (GPT-4, Claude):**

```
Seu dispositivo → Internet → Servidor OpenAI → Modelo → Resposta
                                       ↑
                                 Seus dados (ficam lá)
```

**AI Local (Ollama + Llama):**

```
Seu dispositivo → Modelo local → Resposta
                  ↓
          Seus dados (nunca saem)
```

![Cloud vs Local AI](/images/cloud-vs-local-ai.png)

**Vantagens do local:**

- ✅ 100% offline
- ✅ Zero custo recorrente
- ✅ Privacidade total
- ✅ Seus dados alimentam seus modelos (RAG)

### Setup Prático (2 minutos)

```bash
# Instalar Ollama
curl https://ollama.com/install.sh | sh

# Rodar Llama 3 (2.5B - leve)
ollama run llama3.2:3b

# Testar com pergunta complexa
# "Explique a diferença entre IA, ML e LLM como eu fosse engenheiro de software de 15 anos"
```

---

## Quando Usar Cada Termo

### "IA" - Situações Apropriadas

Use quando:
- Discutindo o campo geral
- Conversando com público leigo
- Referenciando sistemas inteligentes sem especificar

**Exemplos:**
> ✅ "A IA está transformando a medicina."
> ✅ "O sistema de IA da fábrica reduziu defeitos em 40%."
> ✅ "Nosso chatbot usa IA para atender clientes."

### "ML" - Situações Apropriadas

Use quando:
- Explicando técnicas de aprendizado
- Discutindo algoritmos (árvores de decisão, redes neurais)
- Conversando com desenvolvedores técnicos

**Exemplos:**
> ✅ "Usamos ML para detectar anomalias em tempo real."
> ✅ "O modelo de classificação atingiu 98% de acurácia."
> ✅ "O pipeline de ML está otimizado com feature engineering."

### "LLM" - Situações Apropriadas

Use quando:
- Referenciando modelos de texto/chat
- Discutindo GPT, Claude, Llama, Mistral
- Explicando arquitetura de chatbots

**Exemplos:**
> ✅ "Rodamos Llama 3 localmente para transcrição de reuniões."
> ✅ "O LLM gera código com base em descrição natural."
> ✅ "Fine-tuning do LLM melhorou performance no domínio médico."

---

## Key Takeaways

1. **IA** = Campo amplo de sistemas inteligentes (pode usar ML ou não)
2. **ML** = Subcampo de IA que aprende com dados (não precisa ser programado)
3. **LLM** = Tipo específico de ML treinado em massas de texto para gerar texto

**Prática:**
- Para sistemas técnicos: Especifique (ML, LLM)
- Para conversas gerais: IA é aceitável
- Para chatbots/texto: LLM é o termo correto

---

## Próximo Artigo

**Markdown > DOCX: Por que Arquivos MD são o Futuro da AI**

No próximo post (semana 2), você vai aprender:

- Por que Markdown é superior para AI workflows
- Como integrar Git versionamento com seus prompts
- Ferramentas para editar MD com AI (Obsidian, VS Code)
- Exemplos práticos de code blocks formatados
- Renderização instantânea com Hugo/Jekyll

---

**Siga [@nexusai](https://twitter.com/nexusai)** — Tutoriais de AI local toda terça e quinta.
