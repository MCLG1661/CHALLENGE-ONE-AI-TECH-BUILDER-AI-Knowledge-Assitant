# AI KNOWLEDGE ASSISTANT

**AGENTE INTELIGENTE CO RAG PARA CONSULTA E GESTÂO DE CONHECIMENTO DOCCUENTAL**

![Python](https://img.shields.io/badge/Python-3.9+-blue?style=for-the-badge&logo=python&logoColor=white)
![Google Gemini](https://img.shields.io/badge/Gemini-1.5%20Flash-8E75B2?style=for-the-badge&logo=google&logoColor=white)
![Gradio](https://img.shields.io/badge/Gradio-UI-ff69b4?style=for-the-badge&logo=gradio&logoColor=white)
![FAISS](https://img.shields.io/badge/FAISS-Vector%20Search-0052CC?style=for-the-badge)
![Colab](https://img.shields.io/badge/Google%20Colab-Suportado-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)
![Drive](https://img.shields.io/badge/Google%20Drive-Persistência-4285F4?style=for-the-badge&logo=googledrive&logoColor=white)
![Status](https://img.shields.io/badge/Status-Funcionando-brightgreen?style=for-the-badge)

---

### 🏆 Desafio

1. Criar um agente de IA
2. Processar documentos (PDF/CSV)
3. Fazer deploy na Oracle Cloud (OCI)

---

### 📌 Sobre o Projeto

Uma solução de Inteligência Artificial Generativa desenvolvida para transformar documentos técnicos em uma ***base de conhecimento pesquisável e persistente***.
A aplicação utiliza uma arquitetura baseada em ***Retrieval-Augmented Generation (RAG)***, combinando processamento de documentos, embeddings semânticos, busca vetorial com FAISS e Google Gemini para responder perguntas em linguagem natural utilizando o conteúdo recuperado da base documental.

O projeto foi desenvolvido no ***Challenge ONE AI Tech Builder — Oracle Next Education (ONE) / Alura***, explorando conceitos de IA Generativa, processamento de documentos, busca semântica e gestão de conhecimento.
Permitindo que você mantenha os documentos e o índice FAISS entre diferentes sessões no Google Colab e a outra, a possibilidade de se carregar novos arquivos, criando assim novas bases de dados. A base de dados atual, capacita o agente para analisar documentos PDF e responder perguntas sobre:

- 📄 **Governança de IA no Setor Público** - Recomendações da Transparência Brasil
- 📘 **Manual de Inteligência Artificial** - Conceitos, ferramentas (Dify, DISC) e modelos de negócio
- 📚 **Inteligência Artificial: Avanços e Tendências** - Publicação da USP sobre IA
- 📊 **Análise de Dados: Da Teoria à Prática** - Conceitos fundamentais de análise de dados

---

### 🎯 Objetivo

Desenvolver um assistente inteligente capaz de transformar documentos pessoais ou corporativos em uma base de conhecimento consultável por meio de linguagem natural.
A solução busca reduzir o esforço necessário para localizar e interpretar informações distribuídas em documentos extensos, permitindo que o usuário realize perguntas e receba respostas contextualizadas a partir do conteúdo disponível na base.

---

### 💡 Solução Proposta

O AI Knowledge Assistant processa os documentos adicionados à base, divide o conteúdo em trechos menores (chunks), gera representações vetoriais (embeddings) e cria um índice utilizando FAISS.
Quando uma pergunta é realizada, o sistema utiliza busca por similaridade para localizar os trechos semanticamente mais relevantes e fornece esse contexto ao modelo de linguagem para geração da resposta.

```text

Documentos
PDF | DOCX | TXT | MD
        ↓
Extração de Texto
        ↓
Divisão em Chunks
        ↓
Sentence Transformers
        ↓
Embeddings
        ↓
FAISS
Indexação Vetorial
        ↓
Busca por Similaridade
        ↓
Contexto Recuperado
        ↓
Google Gemini
        ↓
Resposta em Linguagem Natural

```
---

## ✨ Principais Funcionalidades

📂 Gestão da Base Documental
- Importação automática de documentos armazenados no Google Drive
- Upload manual de novos documentos
- Suporte a PDF, DOCX, TXT e Markdown
- Possibilidade de criação e atualização de diferentes bases documentais

🧠 Busca Semântica
- Divisão automática dos documentos em chunks
- Geração de embeddings semânticos
- Indexação vetorial com FAISS
- Recuperação dos trechos mais relevantes para cada consulta

💬 Consulta em Linguagem Natural

- O usuário pode realizar perguntas diretamente sobre os documentos armazenados na base.
- O sistema recupera o contexto relevante e utiliza o Google Gemini para produzir respostas contextualizadas.

💾 Persistência da Base de Conhecimento

A base é armazenada no Google Drive, permitindo preservar:

- Documentos processados
- Chunks de texto
- Metadados
- Índice vetorial FAISS

Dessa forma, o índice pode ser reutilizado entre diferentes sessões do Google Colab sem necessidade de reconstrução completa da base.

📤 Recursos adicionais
- Exportação da conversa em arquivo .txt
- Limpeza do histórico da conversa
- Exemplos de perguntas
- Interface interativa desenvolvida com Gradio

## ❗ Diferencial
Diferente de buscadores tradicionais, o agente **compreende o contexto** e responde em **linguagem natural**, sem que o usuário precise ler documentos extensos.

## 🏗️ Arquitetura da Solução

```
flowchart TD
    A[Documentos PDF, DOCX, TXT, MD] --> B[Extração de Texto]
    B --> C[Divisão em Chunks]
    C --> D[Embeddings com Sentence Transformers]
    D --> E[(FAISS - Indexação Vetorial)]
    F[Pergunta do Usuário] --> G[Embedding da Pergunta]
    G --> E
    E --> H[Busca por Similaridade]
    H --> I[Contexto Recuperado]
    I --> J[Gemini 1.5 Flash]
    J --> K[Resposta com Citação das Fontes]

```

## 🎨 Interface Personalizada
Este agente possui uma interface moderna com : 

- Temas personalizáveis (azul, roxo, verde, laranja, escuro)
- Upload de documentos via interface
- Exemplos de perguntas prontas para uso
- Respostas em linguagem natural baseadas nos documentos

## 🛠️ Tecnologias

- **Google Colab**: Ambiente de desenvolvimento e execução.
- **Google Gemini 1.5 Flash (via `google-genai`)**: Modelo de linguagem para geração de respostas.
- **Gradio 4.0+**: Criação da interface web interativa.
- **Sentence Transformers**: Geração de embeddings para busca semântica.
- **FAISS**: Indexação e busca vetorial de alta performance.
- **PyPDF, python-docx**: Leitura de arquivos PDF, DOCX, TXT e MD.
- **Google Drive**: Armazenamento persistente dos documentos e da base de dados (chunks, metadados e índice).

### ☁️ Infraestrutura e Deploy

**Google Colab** - Ambiente de desenvolvimentoEste agente foi projetado para ser executado no **Google Colab**. Sua base de conhecimento é persistente graças ao **Google Drive**:

- **Arquivos Salvos**: Os documentos e a base de dados (`chunks.pkl`, `metadados.json`, `indice.faiss`) são salvos em `Meu Drive/alura_agente_base/`, garantindo que seu trabalho não seja perdido ao fechar o Colab.
- **Pasta Padrão**: A pasta `Agente_Alura_Documentos` no Drive serve como repositório para novos documentos que serão automaticamente importados.

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
📁 CHALLENGE-ONE-AI-TECH-BUILDER-AI-Knowledge-Assitante/
├── 📁 docs/
│   └── 📁 prints/
│       ├── interface_principal.png
│       ├── importacao_drive.png
│       └── exemplo_resposta.png
├── 📁 src/                          (opcional, se quiser modularizar)
│   └── agente.py                    (código principal, se extraído do notebook)
├── 📄 agente.ipynb                  # Notebook principal do Colab
├── 📄 requirements.txt              # Dependências (obrigatório)
├── 📄 .env.example                  # Exemplo de variáveis de ambiente
├── 📄 .gitignore                    # Ignorar arquivos temporários e .env
└── 📄 README.md                     # Documentação completa
```

### 📂 Estrutura Persistente no Google Drive (criada pelo agente)

```
Meu Drive/
├── 📁 Agente_Alura_Documentos/ # Pasta para novos documentos
│ ├── manual.pdf
│ └── relatorio.docx
└── 📁 alura_agente_base/ # Base de dados persistente
├── chunks.pkl # Chunks de texto
├── metadados.json # Metadados dos chunks
├── indice.faiss # Índice FAISS
└── 📁 arquivos/ # Cópia dos arquivos processados
```

## 📁 Estrutura do Projeto

### Repositório GitHub
- `agente.ipynb`: Notebook principal para execução no Google Colab.
- `requirements.txt`: Dependências do projeto.
- `.env.example`: Modelo para variáveis de ambiente (a chave é configurada via Secrets do Colab).
- `docs/prints/`: Prints de tela da interface.
- `README.md`: Documentação completa.

### Google Drive (Criado Automaticamente)
- `Agente_Alura_Documentos/`: Pasta onde você deve colocar seus documentos (PDF, DOCX, TXT, MD). O agente importa automaticamente os arquivos desta pasta.
- `alura_agente_base/`: Base de dados persistente com chunks, metadados e índice FAISS, garantindo que seu trabalho não seja perdido ao fechar o Colab.

## 📸 Prints de Tela

### 📄 Imagem do Agente
![📄 Agente Funcionando](docs/prints/Alura-Agente-Imagem-do-Agente.png)
*📄 Agente Funcionando*

### 💬 Interação com o Agente - Pergunta Respondida 
![💬 Exemplo de Pergunta](docs/prints/Alura-Agente-Imagem-Pergunta-Respondida.png)

*💬 Exemplo de pergunta e 🎯 resposta completa e estruturada ao agente* 

## 🖥️ Interface Gradio

A interface Gradio gera um link público temporário
 
## 🗺️ Roadmap e Melhorias Futuras

### Implementado (Versão Atual)

✅ Extração de texto de PDFs com PyPDF2

✅ Upload de documentos no Google Drive

✅ Persistência da base no Google Drive

✅ Leitura de múltiplos formatos (.pdf, .docx, .txt, .md)

✅ Integração com Google Gemini

✅ Respostas baseadas em documentos

### Melhorias Futuras (Planejado)

#### 🔍 Camada de Recuperação com LangChain

- **Implementar retriever** para buscar os trechos mais relevantes
- **Criar cadeias RAG** (Retrieval-Augmented Generation)
- **Citar fontes** das respostas (transparência)
- **Suporte a múltiplos documentos** em uma única base de conhecimento

#### ⚡ Melhorias de Performance

- **Cache de embeddings** para reutilização
- **Busca híbrida** (semântica + palavras-chave)

#### 🌐 Expansão

- **Interface web** com Streamlit ou Gradio
- **Deploy na OCI** (Oracle Cloud Infrastructure)
- **Suporte a CSV** para dados estruturados
- **Dashboard de análise** de riscos

## 🤝 Como Contribuir

1. Faça um Fork do projeto
2. Crie uma branch (`git checkout -b feature/nova-funcionalidade`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova funcionalidade'`)
4. Push para a branch (`git push origin feature/nova-funcionalidade`)
5. Abra um Pull Request

## 🙏 Agradecimentos

- Oracle Next Education (ONE) - Pela Oportunidade e Mentoria
 
- OCI - Pela Infraestrutura

- Mentores e Organizadores - Pelo Suporte e Orientação

## 👨‍💻 Autor

**Marcus Guedes**
- LinkedIn: https://www.linkedin.com/in/marcusguedes/
- GitHub: https://github.com/MCLG1661

## ⭐ Projeto desenvolvido como CHALLENGE do ONE AI TECH BUILDER
