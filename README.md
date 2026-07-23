# AI KNOWLEDGE ASSISTANT
## CHALLENGE ALURA AGENTE

Agente Inteligente,  que transforma documentos técnicos em conhecimento estruturado por meio de classificação temática, extração de palavras-chave e técnicas de Inteligência Artificial.

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Google Gemini](https://img.shields.io/badge/Google%20Gemini-1.0%20Pro-orange.svg)
![Colab](https://img.shields.io/badge/Google%20Colab-Suportado-yellow.svg)
![Status](https://img.shields.io/badge/Status-Funcionando-brightgreen.svg)

---

## 🏆 Desafio
Este projeto foi desenvolvido como desafio do **ONE AI TECH BUILDER** e envolve :
1. Criar um agente de IA
2. Processar documentos (PDF/CSV)
3. Fazer deploy na Oracle Cloud (OCI)
. 

## 📌 Sobre o Projeto

Um **Agente Inteligente** capaz de analisar documentos PDF e responder perguntas utilizando :

- 🧠 **Google Gemini 1.0 Pro** para processamento de linguagem natural
- 📄 **PyPDF2** para extração de texto de documentos
- ☁️ **Google Colab** como ambiente de desenvolvimento
- 🚀 **OCI** para deploy na nuvem


## 🎯 Objetivo
Facilitar a consulta e análise de documentos complexos, permitindo que colaboradores obtenham respostas rápidas e precisas em linguagem natural.


## 💡 Solução Proposta

A solução recebe documentos técnicos em PDF (como relatórios de riscos a direitos humanos) e utiliza **técnicas avançadas de Inteligência Artificial** (Google Gemini) para analisar o conteúdo e retornar **informações estruturadas e respostas em linguagem natural**.


## ✨ Funcionalidades e Descrições Técnicas

✅ 📄 **Classificação Automática de Conteúdos** : Identifica automaticamente seções específicas sobre o tema consultado

✅ 🔑 **Extração de Palavras-Chave** : Extrai termos-chave como "Due Diligence", "Cadeia de Suprimentos" 

✅ 🔗 **Identificação de Conteúdos Relacionados** : Conecta diferentes partes do documento que tratam do mesmo tópico

✅ 🧠 **Organização Inteligente da Base de Conhecimento** : Estrutura as informações para respostas rápidas e precisas


## ❗ Diferencial
Diferente de buscadores tradicionais, o agente **compreende o contexto** e responde em **linguagem natural**, sem que o usuário precise ler documentos extensos.

## 🏗️ Arquitetura da Solução

```
graph LR
    A[Usuário] --> B[Interface no Colab]
    B --> C[PDF Upload]
    C --> D[Extração de Texto]
    D --> E[Google Gemini API]
    E --> F[Análise de Riscos]
    F --> G[Resposta]
````

## ⚙️ Funcionalidades Técnicas

### 📥 Processamento de Documentos
- **Upload de PDFs** via Google Colab
- **Extração automática** de texto com PyPDF2
- **Limpeza e preparação** do texto para análise

### 🧠 Inteligência Artificial
- **Modelo:** Google Gemini 1.0 Pro (via API)
- **Técnica:** RAG (Retrieval-Augmented Generation)
- **Contexto:** Os documentos são usados como base de conhecimento
- **Personalização:** O agente responde APENAS com base no documento fornecido

## 💬 Exemplo de Interação

### 📄 Documento Fornecido
*Análise de Dados da Teoia a Prática*

### ❓ Pergunta do Usuário
*Quais são os principais tipos de análise de dados mencionados e o que é dito sobre recomendações de governança de IA?*

### 🧠 Processamento
1. O agente extrai o texto do documento
2. Busca trechos relevantes sobre riscos trabalhistas
3. Gera uma resposta estruturada

### ✅ Resposta do Agente
*Com base nos documentos fornecidos, apresento as respostas para as duas partes da sua pergunta ....*

## 📁 Estrutura de Pastas

```
agente-riscos/
├── agente.ipynb          # Notebook com todas as células
├── requirements.txt      # Opcional (para instalação)
└── README.md             # Idêntico ao do VS Code
```
